---
layout: post
title:  "Fraud detection in Cloud"
date:   2025-12-29 
categories: blog
post_icon : "/assets/images/fox-mouse-chase.jpg"
---

<img src="/assets/images/fox-mouse-chase.jpg" style="width: auto; height: 350px;">

# TL;DR
We live in a digital world where fraud has become a common experience. Perhaps you have been a victim of credit card fraud. If you bank with a sophisticated institution, you might have been notified before the fraud strikes. Hyperscalers face fraud on a persistent basis and they need to protect their legitimate customers against fraud. Here we discuss the nature of fraud in cloud business and ways to deal with the challenge.

# Fraud Types

## Payments Fraud
The threat actor has access to the victim's payment instrument. A compromised card can be used to purchase cloud resources. When the victim realizes the fraud, she will work with the cloud provider to revert the charges. She will also reach out to the card issuer to block the card. At this point, the bleeding will stop. 

## Accounts Fraud
Account fraud is more sinister kind of fraud where the threat actor has access to the account of a legitimate user. In essence, the fraudster is able to create resources on the same account as that of the valid user. When we look at the usage, only a part of the usage is fraudulent. Even when we are able to spot the fraud, it is hard to identify the right set of resources to block. Once a bad behavior is banned, the fraudster can restart the fraud in another way. Victim may be deeply involved in the mitigation process raising cost both to the user and the cloud provider.

# Catching Fraud
A common way to detect fraud is to do velocity analysis. A legitimate user has some patterns of transactions. For e.g. she will create certain number of resources, say virtual machines in a given duration. Let us call this operation velocity. We can extend this idea of counting regions where the the operations occurred. Let us call tis region velocity. In both cases, we have notion of a 'normal' behavior and if the user behavior deviates from this normal, we can suspect fraud.

# Metrics
Let us review some desirable attributes of our detection mechanism by defining metrics.

## Accuracy

Industry practices is to measure precision and recall. These metrics pull in opposite directions. If the business cares about one metric over other, we can tailor our detection system for that.

### Precision
This measures the percentage of fraudulent detections across all detections. High precision detection will catch the fraudster without impacting other legitimate usage. 

### Recall
This measures the percentage of fraudulent detections across all frauds. High recall indicates that we are able to catch most of the fraud happening in the system.

## Transparency
We are answerable to the customer as well as the business on fraud detection. So capturing the reason behind detection in simple format is crucial in building trust and incrementally improving the system.

## Impact
Business has to devote its energy on the most important tasks. It is important to measure the impact of each fraud so that we can prioritize our efforts. Converting impact into dollar amount lets us measure revenue leak to fraud and helps set a goal for coming business cycles. For e.g. we can set a goal of keeping fraud to less than 1% of revenue. This assumes that the fraud scales linearly to revenue growth.






