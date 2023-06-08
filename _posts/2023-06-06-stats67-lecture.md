---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Linear Regression
use-math: true
---

## Least Squares Regression Line

$$
\text{The predicted LSRL for one variable is defined as } \hat{y} = \hat{\beta}_0 + \hat{\beta}_1 x \\
\text{The actual correlation line for the population is defined as } y = \beta_0 + \beta_1 x + \epsilon_i \\
\text{where epsilon represents the natural variations in the population}
$$

r<sup>2</sup> is the coefficient of determination which describes the strength of the line (or how accurate it is)
- Can be used to interpret the data: "_% of the variance in y can be explained by x"

r represents the direction and the strength of the relationship (weak/moderate/strong, negative/posutive)
- "There is a (strength) (nega/posi) relationship betweenn IV and DV. As IV increases, DV (increases/decreases) on average."

r<sup>2</sup> is resistant to outliers while r is not

Formulas for the LSRL:

<img width="818" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/384f83e2-b93b-4cde-9bbb-6e93c8791270">

Must make three assumptions to make a model:
1. The experimental units are independent from each other
2. The error follows a Normal distribution
3. The residual plot should look random

Distributions: 
<img width="535" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/c0324153-e1f9-46f9-a48a-91dec14cabf3">
<img width="514" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/350ae3e2-d017-4a02-bfa6-b8b3502ebb17">
