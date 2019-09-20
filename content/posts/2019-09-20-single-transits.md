---
title: Fitting single transits
date: 2019-09-20
authors:
- Dan F-M
draft: false
---

![img](/fig/2019-09-20.png)

Shortly before group meeting, I asked Twitter what I should work on today (see above).
But, working on writing the paper is much less fun than thinking about new features so I went through a derivation of the right "priors" to use when characterizing a single transit.
I have [previously published on this topic](https://arxiv.org/abs/1607.08237) (as have many others!) and the basic idea is that even if you only detect a single transit you can place some constraint on the orbital period because the duration of the transit is informative.
This constraint on the period tends to be weak because the transit duration is covariant with all of the properties of the system (especially eccentricity, impact parameter, and stellar density).
Recently, [David Kipping pointed out](https://iopscience.iop.org/article/10.3847/2515-5172/aaf50c) that *the fact that the planet transits* is a useful datum when fitting a system like this.
However, the full story of how this information can be included in the fit of a single transit is slightly more complicated than presented in that note.
So at group meeting I shared my derivation and got some feedback about how to present it clearly.
The main argument is that you want to make inferences about `p(parameters | light curve, the planet transits)` instead of just `p(parameters | light curve)`.
Then since the light curve and the fact that the planet transits are conditionally independent (given the parameters of the system), the joint probability factors as `p(parameters) p(light curve, the planet transits | parameters) = p(parameters) p(the planet transits | parameters) p(light curve | parameters)` and `p(parameters) p(the planet transits | parameters)` looks like a "prior", but it isn't separable (it correlates the orbital period with all the other parameters).
This argument could also be applied to systems with more than one observed transit, but it looks like the effect would be negligible in most cases.
Stay tuned for a tutorial with more details!
