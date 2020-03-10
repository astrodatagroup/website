---
title: Eclipsing binaries with archival radial velocities
date: 2020-03-10
authors:
- Dan F-M
draft: false
---

![img](/fig/2020-03-10.png)

At [the TESS Ninja 3 workshop](https://tess.science/three/), Jessica Birky (UW) cross matched [Adrian's catalog of binary star systems found using APOGEE](https://adrian.pw/apogee-dr16.html) with the TESS 2-minute cadence light curves and found a handful of light curves with eclipses.
With APOGEE cadence, it can be hard to tie down the period of the orbit, but a TESS light curve can approximately perfectly measure the period, epoch, and inclination of the orbit.
This breaks degeneracies in the orbital solution and can lead to precise contraints on the stellar parameters.
At the workshop, I worked with Birky and others to start fitting these orbits and since then I added [support for eclipsing binary light curves directly into *exoplanet* (the code)](https://github.com/exoplanet-dev/exoplanet/commit/5d0f32afa2fc00474ffed30c79f22baae9e0add2).
The figure this week shows an initial fit for one of these targets.
This one is interesting because the deeper eclipse seems to actually be the *secondary*; the star being eclipsed during the shallower event is actually brighter, but the orbital configuration (specifically the inclination and eccentricity) is such that this produces a shallower signal.
This falls out of light curve only fit (the flux ratio is required to be >1) and is consistent with the radial velocity measurements (APOGEE only measures one set of velocities—presumably for the brighter star).
The top panels show the TESS light curve and APOGEE radial velocities and the bottom panels show the best fit orbital configuration (the observer is at z = infinity) with the configuration during the deepest event shown with the radii drawn to scale.
I haven't been able to get the MCMC to run efficiently for this yet (probably because of parameterization issues), but hopefully we'll have a fully working system soon!
