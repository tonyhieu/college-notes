---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: PMF/CDF
---

S<sub>x</sub> is the support of an event, AKA the set of outcomes that can occur
- For example, when flipping a coin, the support can be thought of as 0 and 1, where 0 is heads and 1 is tails

f(x) = P(X = x) corresponds to a pmf (probability mass function)
- Accessed in R using d

F(x) = P(X ≤ x) corresponds to a cdf (continuous discrete function)
- Accessed in R using p

E(X) corresponds to the Expectation of X (or expected value)

VAR(X) corresponds to the variance of X, where the standard deviation of a set is equal to the square root of the variance.
- VAR(X) = E(X<sup>2</sup>) - E(X)<sup>2</sup>
- SD = sqrt(VAR(X))