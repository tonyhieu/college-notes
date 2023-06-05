---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Hypothesis Testing
use-math: true
---

## Hypothesis Testing

Must compare **test statistic** to **critical value** and see if the test statistic is more extreme; if it is, then you REJECT the null hypothesis, and if it isn't, then you FAIL TO REJECT the null hypothesis.

Critical values are calculated using qt and qnorm based on the significance levels (denoted by alpha).

### Test statistic formulas

<img width="647" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/bbd51ebb-c845-4c15-93a2-8ee31349efa9">

<img width="557" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/1ac840c8-0e02-4edf-a8b6-0fea1944129b">

### Decisions and Errors

Can make different errors and mistaken conclusions based on the data, which is where Type 1 and Type 2 errors come in.

![image](https://github.com/tonyhieu/college-notes/assets/54915685/51c287a7-cc4e-4a55-8ad4-2c48e5d8f54c)

- Chance of a true positive is also known as the test's **power**, or **sensitivity**
- Chance of a true negative is also known as the test's **specificity**

Visualized as a graph: ![image](https://github.com/tonyhieu/college-notes/assets/54915685/92dfb905-c9a5-4eb4-8139-78c6c5da53cf)

To decrease alpha and beta, the only thing you can do is decrease sample size.