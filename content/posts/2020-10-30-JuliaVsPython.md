---
title: Coding in _Julia_ vs. _Python_ (when using existing _Python_ Packages)
date: 2020-10-31
authors:
- Daniel Yahalomi
images: ["/fig/2020-10-31.png"]
draft: false
---

![img](/fig/2020-10-31.png)

At this week's meeting, I asked the group for some advice about coding in Julia or Python. I am starting a project simulating the exoplanet astrometry yield from the [_Nancy Grace Roman Space Telescope_](https://www.nasa.gov/content/goddard/nancy-grace-roman-space-telescope) and I am trying to decide whether to write the code in _Julia_ or in _Python_. We are going to look at synergies between _Roman_ exoplanet astrometry and radial velocity (RV) observations from the [Terra Hunting Experiment](http://www.terrahunting.org/). In order to simulate the joint RV and astrometry signals, we are planning on using [exoplanet](https://docs.exoplanet.codes/en/stable/) or [The Joker](https://github.com/adrn/thejoker) as well as some other exclusively _Python_ packages. So, I asked for advice on whether it would still be "worth it" in terms of computational speed to write the code in _Julia_ if the code I am writing will be primarily a wrapper for other _Python_ packages. In addition, I was curious whether calling _Python_ packages in _Julia_ (using PyCall) would introduce a slowdown in the code.

Eric Ford said that there is no speed penalty in using PyCall in order to run _Python_ packages in _Julia_. He also mentioned that _Python_ actually works quite well as a scripting language, so if I will primarily be calling _Python_ packages for the meat of the code, then it would work well to do so in _Python_. The conversation then turned into a deeper discussion about the possible benefits/downsides of re-implementing the existing _Python_ packages in _Julia_. Dan Foreman-Mackey suggested that the codes themselves are quite replicable and it wouldn't be too difficult to re-implement them in _Julia_. David Hogg brought up the benefit in writing my own code from scratch in terms of developing a deeper understanding of how the code works. He also suggested for me to "think about your goals and do what makes sense within those goals." Megan Bedell and Adrian Price-Whelan then suggested an alternative approach could be to implement a few toy or simpler cases to get a feel for what's going on, but ultimately using existing packages in production work. Dan Foreman-Mackey also mentioned that the _Julia_ code wouldn't be quicker than the existing _Python_ packages, as these packages use C or C++ for the computationally expensive portions of the code.

The main takeaway I got from the conversation is that it would be possible to do the project in _Julia_, by re-writing the _Python_ packages that I would need, but that this is only really the right approach if it is something that I am specifically interested in doing as a project in itself. Otherwise, if the primary goal is to quickly produce a functioning simulation of _Roman_ astrometry + Terra Hunting RVs, then it is likely better to use the existing _Python_ code bases and to write the wrapping/scripting code in _Python_ as well.


