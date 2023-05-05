---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Normal, Uniform, and Exponential Distributions
use-math: true
---

## Normal
X ~ Normal/Approximately Normal(μ, σ)

$$
\text{f(x) } = \frac{1}{\sigma \sqrt{2 \pi}} e^{- \frac{(x - \mu)^2}{2\sigma ^2}}
$$

E(X) = μ

VAR(X) = σ<sup>2</sup>

z = (x - μ)/σ

## Uniform
f(x) = 1/(b - a)

F(X) = (x - a)/(b - a)

E(X) = (b + a) / 2

VAR(X) = (b - a)<sup>2</sup> / 12

NOTE: If asked about a value x outside the range of a and b, the probability is always 0. For instance, if a = 2 and b = 7, then P(X = 1) is 0 and P(X > 1) is 1

## Exponential
Distribution of time between events in a Poisson distribution

f(x) = λe<sup>-λx</sup>

E(X) = 1/λ

VAR(X) = 1/λ<sup>2</sup>

Memory-less; P(X > x + t | X > x) = P(X > t)
- For example, if alarms are exponentially distributed, then the chance that an alarm will go off in 35 minutes from some point given that its already been 30 minutes is the same as the chance that the alarm will go off in 5 minutes