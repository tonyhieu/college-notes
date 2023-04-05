---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Systems of Linear Equations
use-math: true
---

## Definition of a linear equation

$$ \text{An equation in unknowns } x_{1}, x_{2}, \dots, x_(n) \text{ is linear if it only involves constant multiples of the } x_{i} \text{ and perhaps a constant term} $$

$$ \text{Example: } 5x + 3y + 7z = 0, x + y = 1 $$
$$ \text{Nonlinear equation: } x^{2} + y^{2} = 1 $$

- Typically want to put all variables on one side
- Equations with functions (such as sin and cosine) are not considered linear
- Equations with the form 1 = 1 are also linear

## System of linear equations (SLE)

$$ 
\text{Example system} = 
    \begin{cases}
        x + 2y + z = 0 \\
        x - y + 3z = -2 \\
        x + 0y - z = 4 \\
    \end{cases}
$$

- Note the 0y; must have all variables present in the system for each equation
- Acts as a constraint on a set of points
- Even one equation can count as a system of linear equations; the constraints are just limited to that one equation
- In two dimensions, linear equations can be thought of as lines (such as x - 3y = -3 or 2x + y = 8)
    - Usually has one solution: the intersecting point
- Systems of linear equations can also have no solutions (such as when two lines are parallel to each other) or infinite solutions (such as when the lines are the same)
    - Systems with no solutions are **unsolvable**
    - With these observations, systems of linear equations can either have zero, one, or infinite solutions; no in-betweens

$$
\text{Suppose that } (r_{1}, r_{2}) \text{ and } (s_{1}, s_{2}) \text{ both solve } \\
    \begin{cases}
        ax + by = \alpha \\
        cx + dy = \beta \\
    \end{cases} \\
\text{and } t\in\mathbb{R} \text{. Therefore, the point } (tr_{1} + (1 - t)s_{1}, tr_{2} + (1 - t)s_{2}) \text{ also solves the system of equations. Plugging in this point into the original system gives us:} \\
a(tr_{1} + (1 - t)s_{1}) + b(tr_{2} + (1 - t)s_{2}) \\
= atr_{1} + a(1 - t)s_{1} + btr_{2} + b(1 - t)s_{2} \\
= t(ar_{1} + br_{2}) + (1-t)(as_{1} + bs_{2}) \\
= t\alpha + (1 - t)\alpha = \alpha\\
\text{Therefore, any value of t can transform the two points, meaning that there are infinite solutions.}
$$

- Essentially, if there are 2, 3, 4, etc. points, then there are infinite points that satisfy the system