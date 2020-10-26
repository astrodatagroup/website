---
title: Evolution of the exoplanet radius gap 
date: 2020-10-24
authors:
- Trevor David
images: ["/fig/2020-10-24.png"]
draft: false
---

![img](/fig/2020-10-24.png)

At this week's meeting I updated the group on an ongoing project examining the influence of age on the [exoplanet radius gap](https://arxiv.org/abs/1703.10375), a relative scarcity of close-in exoplanets sized between 1.5-2 Earth radii. The feature is widely believed to be a signature of atmospheric loss, with planets below the gap having rocky compositions and planets above the gap requiring a few percent-by-mass atmospheres to explain their low bulk densities. In the atmospheric loss paradigm, some fraction of the rocky planets are the remnant cores of planets that lost the entirety of their atmospheres. 

At the core of this project is the observation of a more sparsely populated radius gap at younger system ages. My question to the group was in regards to estimating the statistical significance of the feature in 1D (i.e. just the radius distribution) and 2D (i.e. the orbital period-radius plane). While the gap appears to be remarkably empty in 2D, the feature is somewhat washed out (or, less statistically significant) in 1D partially due to the fact that the precise location of the gap decreases with increasing orbital period. In the 1D case, David W. Hogg proposed that the data could be projected orthogonally to an assumed functional form of the gap. A grid search of the gap function parameters could be performed to test different projections and find the "best" or emptiest gap, which would also allow us to estimate the feature's significance through simulations.

Christina Hedges brought up [Hough transforms](https://en.wikipedia.org/wiki/Hough_transform) for the 2D case. Since there also appears to be a stellar mass dependence to the location of the radius gap (and conceivably a metallicity dependence), we would be interested in exploring the location of the gap in higher dimensions. Generalizing the Hough transform to higher dimensions was discussed, and Christina threw together a lovely [notebook](https://github.com/christinahedges/hufflescuff) for the 2D case.   

