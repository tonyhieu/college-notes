---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Confidence Intervals
use-math: true
---

Always do Point Estimate +/- Margin of Error. z star and t star refer to the *critical values* from the confidence level; i.e. 95% corresponds to qnorm(0.975) and qt(0.975, df).
- Margin of error will always equal the critical value times the standard error, i.e. ME = t star * SE / z star * SE

Must satisfy three conditions to have a valid confidence interval: Random Sample, Independent Sample, Large Enough Sample (n ≥ 30 for mean confidence intervals, np ≥ 10 AND n(1-p) ≥ 10 for proportion confidence intervals)
- The large enough condition can also be satisfied if the population has a bell shaped curve

## One Sample

$$
\hat{p} \pm z^* \sqrt{\frac{\hat{p}\hat{q}}{n}} \\
\bar{x} \pm t^* \frac{S_{\bar{x}}}{\sqrt{n}}
$$

## Two Sample

$$
\hat{p_1} - \hat{p_2} \pm z^* \sqrt{\frac{\hat{p_1}\hat{q_1}}{n_1} + \frac{\hat{p_2}\hat{q_2}}{n_2} } \\
\bar{x_1} - \bar{x_2} \pm t^* \sqrt{ \frac{S_{\bar{x_1}}^2}{n_1} + \frac{S_{\bar{x_2}}^2}{n_2} } \\
\bar{x_d} \pm t^* \frac{S_{\bar{x_d}}}{\sqrt{n}}
$$