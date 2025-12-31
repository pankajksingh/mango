---
layout: post
title:  "Support , fast and relevant"
date:   2020-12-29 
categories: blog
post_icon : "/assets/images/tiger-fastlane.jpg"
---

<img src="/assets/images/tiger-fastlane.jpg" style="width: auto; height: 350px;">

# TL;DR
All institutions are drowning in a deluge of support cases. As the cloud scales, so does the support requests. How can we keep the support cost under control? Is there a way to automate a slice of such cases? Let us explore.

# Problem 
We observe that there are a slice of support requests where a support engineer looks at the complaint and other attributes of the impacted resource and uses her expertise to build a search query. Then she searches for the query on a search engine , processes the web links and produces a resolution. It seems that the customer can take all these steps herself. However, she lacks the knowledge that the support engineer has accumulated. We can benefit from a faster resolution in case we have a model that translates the customer request directly into resolution steps.

# Solution
We aim to build a model that reads the customer complaint and produces resolution steps. We can simplify the problem into learning a function that translates customer complaint into a search query. How can we get such a mapping? Observability comes to rescue! Support request logs map complaint into weblinks that resulted in resolution. Search logs map search query into weblinks. Using weblink as the pivot, we can generate training data that maps customer complaint into search query. Then we can train a model that can infer resolution search query given a new complaint. 

# Metrics
How effective is this approach? We can measure the number of cases that got resolved using such an approach. In case of partial resolution, we need to use feedback loop to improve the system. 
