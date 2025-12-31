---
layout: post
title:  "Detecting software regressions"
date:   2025-12-28 
categories: blog
post_icon : "/assets/images/gandalf-balrog.jpg"
---

<img src="/assets/images/gandalf-balrog.jpg" style="width: auto; height: 350px;">

# TL;DR
Cloud promises infinite compute and storage with 5 9's reliability. This abstraction is built by a network of interdependent components. Components are constantly upgraded to meet customers' expectations. We would like to allow each component to upgrade without interacting with other components so that upgrade velocity is not compromised. Going fast however has its cost. Sometimes this results in regression. In such an event, how do we know which component is the culprit? Let us explore.

# Health signals
A complex system like Azure reports its state continuously which is saved in easy to query logs. There are various indicators of health in these logs. For e.g. when a component is under stress, it will show a flurry of exceptions. These health indicators allow us to probe deeper into regressions.

# Health and Upgrade correlation
Our aim is to build correlation between a component upgrade event and worsening of component health. We call such correlation spatio-temporal correlation. Stronger the correlation, more the possibility that a specific component is causing a software regression and should lead the investigatin.

## Temporal correlation
Assume a burglary is reported on a Sunday morning. The police investigates by looking at closed circuit TV around that time. It finds few suspects which helps create a suspect list. Pressence of suspects at the time of burglary is an example of temporal correlation.

## Spatial correlation
Suppose the burglary is more widespread and is reported at different times around the city. The police finds that a common suspect shows up in the CC TV footage. Pressence of suspect at different location around the city at the time of burglary is an example of spatial correlation.

Armed with this intution, we built a software that allowed us to zero in on the component that is most likely behind a software regression. We named it [Gandalf](https://www.usenix.org/conference/nsdi20/presentation/li).


# Metrics

### Precision
This measures the percentage of regression detections across all detections. 
It is important to err on the side of precision specially in initial phases so that partners can start trusting the system. 

### Recall
This measures the percentage of regression detections across all regressions. High recall indicates that we are able to catch most of the regressions happening in the system. Recall is progressively improved by onboarding more components to the Gandalf framework.



