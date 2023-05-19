---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Big 5
use-math: true
---

## Table for the Big Five
<img width="728" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/6b8c49c7-a220-406f-b058-582cbe0175ef">

Standard Error: if the population standard deviation is not known, we can use the standard deviation from the sample instead

## Proportion Distributions

<img width="695" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/7d20061e-c874-40b5-9b2e-34632ad076eb">

1. 1 Population Proportion where population standard deviation is known
2. 1 Population Proportion where population standard deviation is not known; standard error is used instead
3. Difference in 2 Population Proportions where both population standard deviations are known
4. Difference in 2 Population Proportions where both population standard deviations are not known; standard error is used instead

## Mean Distributions

<img width="661" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/d7971bf0-8529-4716-acb5-eedd3147503f">
<img width="782" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/0744cb7a-067c-4c33-9571-4fe2e1d5c6e2">

1. 1 Population Mean where population standard deviation is known
2. 1 Population Mean where population standard deviation is not known; standard error and t distribution are used instead
3. Matched pairs where population standard deviation is known and each data point is the difference between two, related subjects (twins, change in health, etc.)
4. Matched pairs where population standard deviation is not known; standard error + t distribution are used instead
5. Difference in 2 Population Means where both population standard deviations are known
6. Difference in 2 Population Means where both population standard deviations are not known; standard errors + t distribution are used instead
7. Difference in 2 Population Means where standard deviations are equal; **NOT USED COMMONLY**

## Z and T values

z = (Observed - Expected) / Standard Deviation
- Calculated in R using pnorm(z)

t = (Observed - Expected) / Standard Error
- Calculated in R using pt(t, df)
- Can also use qt(% to the left, df) to find a t value based on a desired percentile