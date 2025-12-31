---
layout: post
title:  "Touch Production with Care"
date:   2022-12-29 
categories: blog
post_icon : "/assets/images/hobbit-hot.jpg"
---

<img src="/assets/images/hobbit-hot.jpg" style="width: auto; height: 350px;">

# TL;DR
A complex system like a cloud needs continuous care. From time to time, we need to access production resources. These touches are necessary but risky. We would like to assess riskyness of our production touch points such that we can reduce risk overtime. Is there a way to get there given the deluge of touches staring at us? Let us explore.

# The Challenge
Typically we have governance around touches to production. You request for access to production providing justification and you are granted access for a short time window. Few of these justifications give us window to the risk score of the production access. For other touches, we may need to look elsewhere. So our problem is two fold. How to assess risk for majority of production touches? And how to group these touches in smaller set that is easy to review and take action on?

# The Solution

## Assessing Risk
We review historical production touches and build rules on features like justification to bootstrap risk score. We then try to exploit similarity between the requests of production touch points. This can be done by embedding the request trace(e.g. building search index) and then finding similar requests. These requests will inherit the rule based risk score if they are close enough.

## Grouping touches
Once indexed, we can find neighbors of each production touch request. These peer similarity score helps build similarity matrix. We feed similarity matrix into clustering algorithm , and out comes clusters of production touches.

## Serving
Finally, we publish clusters of production touches with counts and owners ordered by risk scores. This enables owners to start taking action on the riskiest of production touches. 