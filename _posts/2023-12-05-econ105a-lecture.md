---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Supply Curves
use-math: true
---

## Cost Minimization Curves

### Output Expansion Path

- The **output expansion path** is the curve containing the cost-minizing input bundles at differing levels of output
    - Analagous to the price offer curve on the demand side
    - Can only exist in the long-run where all costs are variable

![Output Expansion Path](https://i.ytimg.com/vi/shzsFVoN5iY/maxresdefault.jpg)

### Conditional Input Demand Curves

- The **conditional input demand curve** plots the conditional input demand against output
    - Analagous to the Engel curve on the demand side
    - y-axis would have output y, x-axis would have input x<sub>i</sub>

### Fixed-Proportions Technology Curves

$$
y = min\{4x_1 , x_2\} \\
4x_1^* = x_2^* = y \\
x_1^* (w_1, w_2, y) = y/4 \\
x_2^* (w_1, w_2, y) = y \\
$$

In this situation, you would choose bundles at the vertices of the L-shaped isoquants.

![Fixed-Proportions Example](https://www.economicsdiscussion.net/wp-content/uploads/2016/09/clip_image002-61.jpg)

$$
\text{The firm's total cost function is therefore: } \\
c(w_1, w_2, y) = w_1 x_1^*(w_1, w_2, y) + w_2 x_2^*(w_1, w_2, y) = w_1 \frac{y}{4} + w_2 y \\
= (\frac{w_1}{4} + w_2)y
$$

### Perfect Substitutes Technology Curves

Depending on whether or not the slopes of the isocost and isoquant are the same, there could be infinitely many solutions (slopes equal) or one corner solution (slopes unequal).

$$
y = x_1 + 2x_2, \frac{MP_1}{MP_2} = 1/2 \\
\text{Three cases:}\\
\text{If } w_1 / w_2 > 1/2 \text{, then } x_1^* = 0, x_2^* = y/2, c(w_1, w_2, y) = \frac{y w_2}{2} \\
\text{If } w_1 / w_2 < 1/2 \text{, then } x_1^* = y, x_2^* = 0, c(w_1, w_2, y) = y w_1 \\
\text{If } w_1 / w_2 = 1/2 \text{, then any bundle on the isoquant can be chosen.} \\
\text{Thus, } c(w_1, w_2, y) = min\{yw_1, \frac{yw_2}{2}\} = y \cdot min\{w_1, \frac{w_2}{2}\}
$$

## Cost Curves

### Average Cost

- For a positive y, a firm's **average cost** of producing y output units is AC(w<sub>1</sub>, w<sub>2</sub>, y) = c(w<sub>1</sub>, w<sub>2</sub>, y) / y
    - This is also known as *cost per unit of output*
    - Given constant RTS, doubling the output level from y' to 2y' requires doubling all input levels. Thus, the AC does not change, as both c and y are multiplied by 2
    - Given decreasing RTS, doubling the output level from y' to 2y' requires more than doubling all input levels. Thus, the AC increases, as c increases at a higher rate than y
    - Given increasing RTS, doubling the output level from y' to 2y' requires less than doubling all input levels. Thus, the AC decreases, as y increases at a higher rate than c

### Short Run and Long Run Total Costs

$$
\text{The LR cost minization problem minimizes } w_1 x_1 + w_2 x_2, \text{ } x_1, x_2 \geq 0 \text{ such that } f(x_1, x_2) = y \\
\text{The SR cost minization problem minimizes } w_1 x_1 + w_2 x'_2, \text{ } x_1 \geq 0 \text{ such that } f(x_1, x'_2) = y \\
\text{The SR problem can be rewritten as } w_1 x_1 + w_2 x_2, \text{ } x_1, x_2 \geq 0 \text{ such that } f(x_1, x_2) = y, x_2 = x'_2
$$

- Note that this means that SR total cost will exceed LR total cost except for the output level where the SR input level restriction is the same as the LR input level choice