---
layout: post
title:  "Caching containers"
date:   2025-12-30 
categories: blog
post_icon : "/assets/images/cheese-inventory.jpg"
---

<img src="/assets/images/cheese-inventory.jpg" style="width: auto; height: 350px;">

# TL;DR
Traditional 3 tiered architecture is built around a data store, a middle tier and a UI layer. One key focus of middle tier is to cache entities for rapid serving. Caching is typically done in memory or using caching platforms like redis.  Here we cover how to cache resources like containers. Can we leverage ready made solutions for caching? For this, we need to analyze how close our scenario is with the typical scenarios. At the outset it appears that containers are just like any key-value pairs. But are there any key attributes that force us to use custom solution? Let's think.

# Cache Hit
We design caching solutions to increase cache hits. This means that a user request is served at the middle cache layer without refreshing the data from the backend store. The cache is still valid and can serve future requests. The cache only gets invalidated if there is an update to it. For containers, user requests for a container backed by specific image. We can serve the container from cache pool but once the container is served to a user, it is no longer available for future. This smells more like inventory management where we fill the inventory with specific objects and serve users till the inventory lasts. Let us follow our nose.

# Container Inventory Management
Inventory management requires us to make decision on what objects to insert in the pool, when to evict an unused object and when to order for new inventory. We can define policies for each of these actions keeping in mind the velocity of consumption, the variability of demand and the duration for the reorder to be fulfilled. Insertion policy relies on accurate demand forecast. We have notion of safety stock for each cached container. Safety stock can be increased to raise the service level but it raises the operational cost. Similarly, we can reduce the safety stock to save cost but that will increase the latency of serving. These considerations help us define reorder policy.If we find stale container not being requested, we need an eviction policy to manage them.

# Metrics

## Customer Metrics
Customer cares about the time it takes to fulfill her request. Bigger caching layer can meet this expecation but it raises operational costs. This means that we should focus on methods beyond caching to make the system fast. 

## Platfrom metrics
Platform maintains a series of metrics to manage inventory efficiently. This includes hit-rate and eviction-rate. To manage cost of inventory, we need to measure the age of objects in the pool. We aim to have short-lived containers that are served to the end users. Platform benefits from flexibility to make trade-offs between service level and operational cost.






