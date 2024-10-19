---
layout: post
description: STATS 295
categories: [stats295, lecture, fall24, markdown]
title: Causal Machine Learning
use-math: true
toc: true
---

## Motivating Questions

- Causal machine learning asks, "What would happen if we took another action in the past?"
- Different past actions can lead to causal inference - if I changed this action and the outcome is different, then that action is a cause

## Key Terminology
- **Confounder**: A variable that affects multiple parts of a model
    - $C \rightarrow (A, Y), C \rightarrow A \text{, so C is a confounder}$
- **Mediator**: A variable that is downstream of A but upstream of Y
    - $A \rightarrow M \rightarrow Y$
- 

## Treatment Effects

- Measures how much changing a past action affects the result
- **Indirect Effect**: How much one variable affects another through mediators
    - $IE = E(Y | do(A = a, M = m_{a+1})) - E(Y | do(A = a))$
- **Direct Effect**: How much one variable affects another, directly
    - $DE = E(Y | do(A = a+1, M = m_{a})) - E(Y | do(A = a))$
- **Total Effect**: How much one variable effects another, totally
    - $TE = IE + DE = E(Y|do(A=a+1)) - E(Y|do(A=a))$
- **Heterogenous Treatment Effect**
    - $HTE = E(Y^*(1) - Y^*(0) | X) = E(Y|A=1, X) - E(Y|A=0, X)$
- **Average Treatment Effect**
    - $ATE = E(Y(1) - Y(0)) = E(Y|do(A=1)) - E(Y|do(A=0))$
- **Individualized Treatment Effect**
    - $ITE = Y_i - Y_i^* (0) \text{, given that subject i was assigned treatment 1}$

## Do-operator
- **Do-operator**: denotes the intervention of treatment; that is, changing A = a<sub>i</sub> to A = a<sub>j</sub> while holding everything else constant
- Can be used to learn a policy π and see the effects: $Y^*(A = \pi (x))$
- Do-operator notations
    - $Y(a) \triangleq Y^*(a) \triangleq Y | do(A = a) \triangleq Y_{do(A=a)}$

## Assumptions of Causal Learning
- **Stable Unit Treatment Value Assumption (SUTVA)**: $Y = Y^* (a)$
- **No Unmeasured Cofounders**: ${Y^* (a) : a \in A} \perp A|X$
    - Allows us to find the true causal graph
