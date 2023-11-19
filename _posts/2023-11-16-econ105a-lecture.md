---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: 
use-math: true
---

## Technology

### Marginal Product and Returns-To-Scale

- Q: Can a technology exhibit increasing RTS even if all of its MPs are diminishing?
- A: Yes!
    - A Cobb-Douglas production function where y = x<sub>1</sub><sup>2/3</sup>x<sub>2</sub><sup>2/3</sup> has two diminishing MPs with increasing RTS
- Recall that the MP tracks the rate-of-change in output by increasing <u>one</u> input, while RTS tracks the rate-of-change in output by increasing <u>all</u> inputs proportionally

### Technical Rate-of-Substitution, or Slope of Isoquants

- The slope of an isoquant at any given budnle represents the rate at which one input must be substituted for another in order to maintain the same level of output
    - This slope is known as the **technical rate-of-substitution**, or TRS

$$
y = f(x_1, x_2) \\
\text{The change in output is } dy = \frac{\partial y}{\partial x_1} dx_1 + \frac{\partial y}{\partial x_2} dx_2 \\
\text{Along the isoquant, } dy = 0 \text{, so an isoquant must satisfy } \frac{\partial y}{\partial x_1} dx_1 + \frac{\partial y}{\partial x_2} dx_2 = 0 \\
\frac{\partial y}{\partial x_2} dx_2 = - \frac{\partial y}{\partial x_1} dx_1 \\
\frac{dx_2}{dx_1} = - \frac{\partial y / \partial x_1}{\partial y / \partial x_2} = -\frac{MP_1}{MP_2} \\

\text{Thus, given some production function } y = f(x_1, x_2), TRS = -\frac{MP_1}{MP_2} = -\frac{\partial y / \partial x_2}{\partial y / \partial x_1} \\
$$

### Well-Behaved Technologies

- A well-behaved technology is both monotonic and convex
    - **Monotonicity**: More of any input generates more output
    - **Convex**: If the input bundles x' and x'' both provide y units of output, then the mixture tx't(1-t)x'' provides at best y units of output, for any 0 < t < 1
        - *Strict Convexity* is when the mixture is <u>greater</u> than y, implying that the TRS increases (less negative) as x<sub>1</sub> increases, AKA diminishing TRS
        - *Weak Convexity* is when the mixture is <u>greater than or equal to</u> y

![Weakly Convex Techonology](https://i.ytimg.com/vi/jjSZ53Ni_ag/maxresdefault.jpg)

### Long Run and Short Run

- **Long run** means that a firm is unrestricted in its choice of all input levels
- **Short run** means that a firm is restricted in its choice of at *least one* input levels
    - The long run can be thought of as a firm "choosing" its short run circumstances
    - The long run will always be more optimized than the short run, as there are no constraints

$$
\text{Consider the following long run production function: } y = x_1^{1/3}x_2^{1/3} \\
\text{In the short run, good 2 might be limited to 1, so the function is } y = x_1^{1/3} 1^{1/3} = x_1^{1/3} \\
\text{Good 2 might be limited to 8 instead: } y = x_1^{1/3} 8^{1/3} = 2x_1^{1/3} \\
\text{There can be multiple SR production functions depending on the constraint on good 2.}
$$

## Profit Maximization

### Economic Profits

- A firm uses inputs j = 1, ..., m to make products i = 1, ..., n
    - Output levels are y<sub>1</sub>, ..., y<sub>n</sub>
    - Input levels are x<sub>1</sub>, ..., x<sub>n</sub>
    - Product prices are p<sub>1</sub>, ..., p<sub>n</sub>
    - Input prices are w<sub>1</sub>, ..., w<sub>n</sub>
    - The firm can choose the output and input levels, but the product and input prices must be taken as given