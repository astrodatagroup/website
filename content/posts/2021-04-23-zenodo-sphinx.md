---
title: How to automatically retrieve a Bibtex entry for a Zenodo record (and add
it to a Sphinx documentation page)
date: 2021-04-23
authors:
- Adrian Price-Whelan
draft: false
---

**Niche software trick warning!**

Today I have been working on overhauling the documentation theme and content for
a Python package I maintain, [gala](https://github.com/adrn/gala), which uses
Sphinx to build the documentation. On the current main documentation page, [I
ask users](http://gala.adrian.pw/en/latest/#attribution) who write papers with
`gala` to cite the [JOSS
paper](https://joss.theoj.org/papers/10.21105/joss.00388) and the [Zenodo
record](https://zenodo.org/record/4159870) for the version that they use, in
keeping with [good software citation
practices](https://journals.aas.org/news/policy-statement-on-software/).

I want to make it as easy as possible for users to retrieve the relevent Bibtex
entries for `gala` to include in papers, so I include the Bibtex directly on the
main page of the `gala` documentation. However, in my current documentation
setup, I have had to remember to manually copy-paste the Bibtex entry into the
documentation page whenever I release a new version. I am bad at remembering
things like this, so I recently noticed that the Zenodo bibtex entry is way out
of date.

Today I figured out how to query the Zenodo web API to retrieve the Bibtex entry
for the latest release of a software package with a record on Zenodo, and to
include this into the Sphinx (documentation) build process. Here's what I do
now:

In my Sphinx documentation configuration file, typically in `docs/conf.py`, I
query the Zenodo API and store the resulting Bibtex to a local (git ignored)
.rst file, or default to linking to the Zenodo record if that fails for any
reason:

    import pathlib
    import warnings
    zenodo_path = pathlib.Path('ZENODO.rst')
    if not zenodo_path.exists():
        import textwrap
        try:
            import requests
            headers = {'accept': 'application/x-bibtex'}
            response = requests.get('https://zenodo.org/api/records/4159870',
                                    headers=headers)
            response.encoding = 'utf-8'
            zenodo_record = (".. code-block:: bibtex\n\n" +
                            textwrap.indent(response.text, " "*4))
        except Exception as e:
            warnings.warn("Failed to retrieve Zenodo record for Gala: "
                          f"{str(e)}")
            zenodo_record = ("`Retrieve the Zenodo record here "
                            "<https://zenodo.org/record/4159870>`_")

        with open(zenodo_path, 'w') as f:
            f.write(zenodo_record)

Then, on my main documentation page `docs/index.rst` (or wherever you would like
to include this file), I use the Sphinx `.. include::` directive to include the
contents of the cached file:

    .. include:: ZENODO.rst

Anything we can do to make it easier to cite software helps!
