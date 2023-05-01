---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Geometric/Poisson Distribution
---

Geometric Distribution (Geometric(x) where x = the chance of success)
- Measures the chance of success after a number of events
- f(x) = (1 - p)<sup>x - 1</sup> p (dgeom)
- F(X) = pgeom
- E(x) = 1/p
- VAR(x) = (1 - p) / p<sup>2</sup>
- Remember in R that you need to subtract the x value by 1, as x represents the number of failures until a success instead of the number of tries to get a success

Poission Distribution (Poission(λ) where λ = the expected successes in a time frame)
- Measures the expected number of successes in a time frame
- f(x) = e<sup>-λ</sup>λ<sup>x</sup> / x! (dpois)
- F(x) = ppois
- E(x) = λ
- VAR(x) = λ