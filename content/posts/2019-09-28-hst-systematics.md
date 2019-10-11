---
title: Removing HST Systematics based on Our Knowledge of K2 Systematics
date: 2019-09-28
authors:
- Christina Hedges
draft: false
---

<video src="/fig/2019-09-28.mp4" controls preload></video>

This week, Rodrigo and I have been working on using our knowledge on removing instrument systematics from Kepler to better understand how to remove instrument systematics from HST. In my research I use HST’s Wide Field Camera 3 to observe transiting exoplanets in the infrared, and use the spectrum to try to identify water in the upper atmospheres of planets. This is a tall order, seeing as the signals we are looking for are <200ppm, and the instrument systematics can easily introduce correlated noise at the 0.1% level. Because of these large instrument systematics, it can be hard to trust small water detections. To address this, we’re interested in removing instrument systematics from HST data in a more bayesian and principled way. Rodrigo and Dan have both been teaching me a lot about how to do this!

The “figure” I’m including is a movie of the frames from HST observations of HD209458b. The spectrum of the object has been scanned up the detector over the course of ~20 seconds, and then a new image is taken during the course of the transit. There are several systematic effects making this data imperfect. The scan rate is not exactly even, causing there to be a “wave” pattern during the scan going up the detector. There is a geometric distortion which causes the dispersion to be slightly tilted in the x and y axis. The flat field for these pixels hasn’t been removed, and there is clear structure that is unrelated to the observation. Finally, over the course of the transit many of these images are taken, and they are not perfectly registered, causing a drift over time. All of these effects add up to a large systematic component.

This week Rodrigo and I have used similar techniques to his PLD pipeline to iteratively fit for the stellar spectrum and the instrument effects. We are able to fit out the distortions, pixel flat field and image registration errors, and find a transmission spectrum that is consistent with the literature spectrum. Our next steps are to ensure that we are not over fitting, and add in sampling so that we can find robust errors on the spectrum, marginalizing over the instrument systematics. Watch this space!
