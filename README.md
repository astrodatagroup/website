# Astrodata.nyc

This is the blog for the [Astronomical Data Group](https://www.simonsfoundation.org/flatiron/center-for-computational-astrophysics/astronomical-data/) at the [CCA](https://www.simonsfoundation.org/flatiron/center-for-computational-astrophysics/).
Our plan is to update this blog once a week to highlight the work in progress in our group.

[![Build Status](https://github.com/astrodatagroup/website/workflows/Build/badge.svg)](https://github.com/astrodatagroup/website/actions)

## How to submit a new post

*This information will generally be for group members.*

1. Create a fork of this GitHub repo.
2. On that fork, add the figure that you want to the `static/fig` directory. It's best to name it something like `2019-09-25.jpg` if you're post is to be published on Sept. 25, 2019.
3. Then, copy the file `content/posts/2000-01-01-template.md` and rename it using the current date and the short title that you want.
4. Edit that file to include your post. Don't forget to put in the right image filename and your name as the author.
5. Set `draft: false` in the header of your post or just delete the `draft` line.
6. Open a pull request.

Some day we might make it easier using issues and a bot, but no promises.
