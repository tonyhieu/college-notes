---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Finishing Utility and Starting Choice
use-math: true
---

## Utility

### Monotonic Transformation and MRS

- Monotonic transformation refers to the transformation of a (utility) function, u, by a strictly increasing (AKA monotonic) function, f
    - Mathematically, this is written as f(u(x))
    - This transformation does not change the indifference curves or preference ordering; the only thing that is changed is the magnitude of the outputs
        - This means that the MRS of a preference relation will not change

$$
\text{Showing how the MRS does not change using partial derivatives} \\
u(x_1, x_2) \text{, } MRS_u = - \frac{\partial u / \partial x_1}{\partial u / \partial x_2} \\
\text{Let v be a monotonic function and represent a monotonic transformation: } v = f(u) \\
MRS_v = - \frac{f'(u) \cdot \partial u / \partial x_1}{f'(u) \cdot \partial u / \partial x_2} = - \frac{\partial u / \partial x_1}{\partial u / \partial x_2}
$$

This proof also shows that any function transformation will not affect the MRS. However, non-monotonic transformations will destroy the order of the preference relation.

## Choice

- <u>Rational Constrained Choice</u> refers to how consumers choose a bundle based on their constraints, such as budget
- Consider the following graph:

![Rational Constrained Choice graph](https://slideplayer.com/slide/14615612/90/images/4/RATIONAL+CONSTRAINED+CHOICE.jpg)

- The point on the indifference curve that both intersects the budget constraint (represented by the straight line) and is tangent to it is the most preferred affordable bundle, as there are no strictly preferred bundles to it
    - Other affordable bundles have strictly preferred bundles to them, and the strictly preferred bundles are not affordable

$$
\text{The most preferred affordable bundle at given prices and income will be denoted } x_1^* (p_1, p_2, m) \text{ and } x_2^* (p_1, p_2, m) \\
\text{These are functions that will change based on the prices and income.} \\
\text{When } x_1^* > 0 \text{ and } x_2^* > 0, \text{ the demanded bundle is known as an interior solution.} \\
\text{When } x_1^* = 0 \text{ or } x_2^* = 0, \text{ the demanded bundle is known as a corner solution.} \\
\text{If buying } (x_1^* , x_2^* ) \text{ costs m, then the budget is exhausted.}
$$

Requirements for the most preferred affordable bundle:

$$
\text{Assuming that } (x_1^* , x_2^* ) \text{ is interior, we make the following assumptions:} \\
(x_1^* , x_2^* ) \text{ exhausts the budget. That is, } p_1 x_1^* + p_2 x_2^* = m \\
\text{The MRS of the IC at } (x_1^* , x_2^* ) \text{ is equal to the slop of the budge constraint.} \\
\text{The second condition is violated when considering corner bundles.}
$$

Solving for the most preferred affordable bundle at the interior:

$$
u(x_1 , x_2) = x_1^a x_2^b \\
MRS = - \frac{ax_1^{a-1} x_2^b}{bx_1^a x_2^{b-1}} = - \frac{a x_2}{b x_1} \\
\text{At } (x_1^* , x_2^* ), MRS = - \frac{p_1}{p_2} \\
\text{Equation A: } - \frac{a x_2^*}{b x_1^*} = - \frac{p_1}{p_2} \rightarrow a p_2 x_2^* = b p_1 x_1^* \\
\text{Equation B: } p_1 x_1^* + p_2 x_2^* = m \\
\text{Plugging A into B: } \\
x_2^* = \frac{b p_1 x_1^*}{a p_2} \\
p_1 x_1^* + p_2 \frac{b p_1 x_1^*}{a p_2} = m \\
p_1 x_1^* (1 + \frac{b}{a}) = p_1 x_1^* (\frac{a + b}{a}) = m \\
x_1 = \frac{am}{(a + b)p_1}\\

\text{Plugging } x_1 \text{ back into Equation A: } \\
a p_2 x_2^* = b p_1 \frac{am}{(a + b)p_1} \\
p_2 x_2^* = \frac{bm}{(a + b)} \rightarrow x_2^* = \frac{bm}{(a + b) p_2} \\

(x_1^* , x_2^* ) = (\frac{am}{(a + b)p_1}, \frac{bm}{(a + b) p_2}) \\
\text{This final solution shows that the a and b in the Cobb-Douglas equation represent } \\
\text{the proportions at which good 1 and good 2 are bought/preferred}
$$

One use case for corner bundles is when goods are perfect substitutes, as a consumer would spend their entire budget on the cheaper good and buy none of the more expensive one. Recall that the graph of the ICs for perfect substitutes looks like this (slopes of -1):

![Substitute Graph](https://www.dyingeconomy.com/images/perfect_substitutes_graph.jpg)

If the price of one good is cheaper than another, then the BC would intersect both the highest IC (when purchasing all of cheaper good) and lowest IC (when purchasing all of expensive good). This is because the slope of the BC (-p<sub>1</sub>/p<sub>2</sub>) is not -1 if the prices differ. When the prices are the same, any bundle on the budget constraint will do, as all the bundles on the BC belong to the same IC.

![Corner Solution](https://i.ytimg.com/vi/-bB5kHOK1iE/sddefault.jpg)

### Perfect Complements

$$
\text{Recall that if two goods are perfect complements, then the utility function takes the form } u(x_1, x_2) = min(ax_1, x_2) \\
$$

In this case, there are no corner solutions, and you can draw a line through the kinks. The intersection of the line through the kinks with the budget constraint thus gives the most preferred affordable bundle.

![PC Graph](https://slideplayer.com/slide/17743712/105/images/44/Kinky+Solutions%3A+Perfect+Complements.jpg)

$$
ax_1 = x_2 \text{ represents the line of "perfect consumption"; that is, no units of good 1 or 2 are wasted.} \\
\text{To find the most preferred affordable bundle, the bundle should lie on } ax_1 = x_2 \text{ and on the BC.} \\
\text{Equation A: } ax_1 = x_2 \\
\text{Equation B: } p_1 x_1 + p_2 x_2 = m \\
\text{Plug Equation A in to B:} \\
p_1 x_1 + p_2 (ax_1) = m \\
x_1 (p_1 + ap_2) = m \\
x_1 = \frac{m}{p_1 + ap_2} \\
x_2 = \frac{am}{p_1 + ap_2}
$$