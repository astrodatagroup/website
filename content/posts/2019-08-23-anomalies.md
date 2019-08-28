---
title: Finding Anomalies in Galaxy Surveys
date: 2019-08-23
authors:
- Kate Storey-Fisher
draft: false
---

![img](/fig/2019-08-23.png)

I have been working on a new method for detecting anomalies in astronomical images with deep learning, with Marc Huertas-Company (Observatoire de Paris) and Alexie Leauthaud (UCSC). The idea is to use unsupervised learning to pick out potentially interesting (or "anomalous") objects in galaxy surveys, as there is way too much data to look through by hand; the lack of supervision also means we can find interesting things we may not know to look for. I first trained a Generative Adversarial Network (GAN) to generate fake images that are similar to the real images in the survey. This "generator" will learn what the objects look like and their distribution. It will do a good job reconstructing images like those that are more common in the survey, and it will be worse at generating the more "anomalous" images.

The top set of images shows a random sample of objects. The first row is the real image, the second is the generator's attempt at reconstructing it, and the third is the residual. The generator does a pretty solid job on the common blob-like galaxies. It has a harder time with the rarer, more extended objects (and the background noise). I let the generator try to reconstruct a million objects from the Hyper Suprime-Cam survey. Based on these residuals (and other features), I assigned each object an "anomaly score." The plot shows the distribution of scores for all million objects; you can see a longer tail of high-anomaly-score objects, as there are more ways to be anomalous than to be normal.

I then make a cut to get the top-scoring objects, and performed some clustering on these. The bottom sets of images show a random selection of objects for four of these clusters, each labeled with its anomaly score. You can see that not only have we found more anomalous objects (these look qualitatively different than the random set), but we have also organized them a bit to help us identify truly interesting anomalies. The GAN identifies anomalies in both morphology and color. Some of the anomalies are bad detections (e.g. red cluster, 2nd and 4th columns) or empty images (greenish cluster, 3rd and 4th columns). But the last group definitely contains some interesting objects! The far right image is a galaxy with a strong tidal feature, which is interesting for galaxy formation studies. So far we have identified multiple galaxies with tidal features as well as some potential AGN; we hope to find other interesting objects, such as green-pea galaxies or even strongly lensed systems.

Up next is improving my GAN and clustering methods to better sort out the anomalies, and continuing to validate our method by cross-correlating our anomaly catalog with known interesting objects and pipeline errors.


