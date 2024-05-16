---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Utility Functions and Indifference Curves
use-math: true
---

## Indifference Curves with Utility

- All of the bundles on one indifference curve should have the same output from the utility function
- Similarly, bundles on different indifference curves should have different values
    - These values/outputs are known as *utility levels*
- The collection of all indifference curves with their assigned utility levels for a given preference relation is known as an **indifference map**
    - In other words, this map maps each curve to a utility level which creates a one-to-one (injective) relationship which leads to a utility function
    - There are an infinitely many number of ways to create a utility function for a preference relation
        - For example, adding or subtracting any number from the function will still maintain the required ordering

$$
\text{Consider a consumer who values bundles in the following way: } (2, 3) > (4, 1) ~ (2, 2) \\
\text{Suppose that } u(x_1, x_2) = x_1 x_2 \text{ represents a preference relation.} \\
\text{Consider (4, 1), (2, 3), and (2, 2):} \\
u(2, 3) = 6 \\
u(4, 1) = u(2, 2) = 4 \\
u(2, 3) > u(4, 1) = u(2, 2) \\
\text{Thus, this utility function correctly represents the consumer's preferences.} \\
\text{Consider a new function } v = u^2 \text{. Then, } v(x_1, x_2) = x_1^2 x_2^2 \\
u(2, 3) = 36 \\
u(4, 1) = u(2, 2) = 16 \\
u(2, 3) > u(4, 1) = u(2, 2) \\
\text{Therefore, v is also a valid utility function.} \\
\text{Another valid utility function could be } w = u + 10 \\
\text{Thus, there an infinite amount of valid utility functions.} \\
$$

- If u is a utility function that represents a preference relation p, and f is a strictly increasing function, then v = f(u) is also a utility function representing p

## Goods, Bads, and Neutrals

- A *good* is a commodity unit which increases utility
- A *bad* is a commodity unit which decreases utility
- A *neutral* is a commodity unit which doesn't affect utility

![image](https://github.com/tonyhieu/college-notes/assets/54915685/61b49ceb-b310-4eea-afc5-56478e770a0b)

## Examples of Utility Functions

$$
\text{The general form for a utility function of perfect substitutes is } u(x_1, x_2) = x_1 + x_2 \\
\text{The general form for a utility function of perfect complements is } u(x_1, x_2) = min(x_1, x_2)
$$

## Cobb-Douglas Utility Functions

$$
\text{Cobb-Douglas utility functions take the form of } u(x_1, x_2) = x_1^a + x_2^b \\
\text{where a > 0 and b > 0}
$$

- Cobb-Douglas indifference curves are all hyperbolic and asymptote to but never touch the x or y axes

## Marginal Utility
- The **marginal utility** of any commodity i is the rate of change of total utility as the quantity of commodity i changes
    - To measure the rate of change, we find the partial derivative of the utility function with respect to i

$$
mu_i = \frac{\partial u}{\partial i} \\
u(x_1, x_2) = x_1^{0.5} + x_2^2 \text{, } mu_1 = \frac{1}{2} x_1^{-0.5} x_2^2 \text{, } mu_2 = 2 x_1^{0.5} x_2
$$

## Marginal Utility (MU) and Marginal Rate of Substitution (MRS)

- Recall that the MRS is the slope of the indifference curve

$$
u(x_1, x_2) \equiv k \text{, where k is some constant} \\
\text{Along an indifference curve, a change in } x_1 \text{ perfectly offsets changes in } x_2 \\
\text{such that the utility of the bundle remains the same. This means that the MU and MRS are related.} \\
\text{This gives us the following identity:} \\
\frac{\partial u}{\partial x_1} dx_1 + \frac{\partial u}{\partial x_2} dx_2 = 0 \\
\frac{\partial u}{\partial x_1} dx_1 = - \frac{\partial u}{\partial x_2} dx_2 \\
\frac{dx_2}{dx_1} = - \frac{\partial u / x_1}{\partial u / x_2} \\
MRS = - \frac{\partial u / x_1}{\partial u / x_2} \\
$$

- As long as there is a slope, then the identity holds

Example:
$$
u(x_1, x_2) = x_1 x_2 \\
\frac{\partial u}{\partial x_1} = x_2 \text{, } \frac{\partial u}{\partial x_2} = x_1 \\
MRS = - \frac{mu_1}{mu_2} = -\frac{x_2}{x_1}
$$