---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Bernoulli/Binomial Distribution
---

Bernoulli distribution refers to an event that has two outcomes: failure or success
- Sample set is {0, 1} and the probability of 1 occuring is p while the probability of 0 occuring is 1 - p (also written as q)
- f(x) = (1 - p)<sup>1 - x</sup>p<sup>x</sup>
- E(x) = p
- VAR(x) = p(1 - p) = pq
Binomial distributions refer to multiple Bernoulli distributions
- Takes two parameters: n (number of trials) and p (chance of success)
    - p must be constant, n must be set, and each event must be independent from each other
- f(x) = nCx (1 - p)<sup>n - x</sup>p<sup>x</sup>
    - Accessed in R with dbinom(x, n, p) where x is the desired number of successful trials
- F(X) = pbinom(x, n, p) 
- E(X) = np
- VAR(X) = np(1 - p) = npq

A variable can be expressed using tilde notation
- For example, X ~ Binomial(n = 22, p = 1/4) indicates that X follows a binomial distribution where the number of trials is 22 and the chance of success is 0.25