---
layout: post
title: "Notes on shrinkage & prediction in hierarchical models"
date: 2014-12-13 12:36
comments: true
categories:
---

Ecologists increasingly use mixed effects models, where some intercepts or slopes are fixed, and others are random (or varying).
Often, confusion exists around whether and when to use fixed vs. random intercepts/slopes, which is understandable given their [multiple definitions](http://andrewgelman.com/2005/01/25/why_i_dont_use/).

In an attempt to help clarify the utility of varying intercept models (and more generally, hierarchical modeling), specifically in terms of shrinkage and prediction, here is a [GitHub repo](https://github.com/mbjoseph/hierarchical_models) with materials and a slideshow from our department's graduate QDT (quantitative (th)ink tank) group.

For fun, I've included a simple [example](https://github.com/mbjoseph/hierarchical_models/blob/master/R_examples/nba_freethrows.R) demonstrating the value of shrinkage when trying to rank NBA players by their free throw shooting ability, a situation with wildly varying amounts of information (free throw attempts) on each player.
The example admittedly is not ecological, and sensitive readers may replace free throw attempts with prey capture attempts for topical consistency.
Many if not most ecological datasets suffer from similar issues, with varying amounts of information from different sites, species, individuals, etc., so even without considering predation dynamics of NBA players, the example's relevance should be immediate.

Spoiler alert: Mark Price absolutely dominated at the free throw line in the early nineties.

![](/images/freethrows.jpeg)

![](/images/markprice.jpg)

<div class="rpres" style="padding-bottom: 70%;"><iframe src="https://dl.dropboxusercontent.com/u/18637425/hm_slides/HM2.html"
frameborder="0" marginwidth="0" marginheight="0"></iframe></div>
