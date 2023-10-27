---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Further Comparative Static Analysis of Demand
use-math: true
---

### Inverse Demand Function

- Typically, demand curves have the quantity on the x-axis and price on the y-axis; these are the graphs of **inverse demand functions** 
    - Especially useful if trying to find the price of a good given a quantity
    - Parameter of inverse demand function is quantity

$$
\text{Using the Cobb-Douglas utility function: } u(x_1, x_2) = x_1^a x_2^b \\
\text{A Cobb-Douglas demand function looks like } (x_1^* , x_2^* ) = (\frac{am}{(a + b)p_1}, \frac{bm}{(a + b) p_2}) \\
\text{The inverse demand function would be } (p_1 , p_2 ) = (\frac{am}{(a + b)x_1^*}, \frac{bm}{(a + b) x_2^*})
$$


$$
\text{With perfect complements: } u(x_1, x_2) = min\{x_1, x_2\} \\
\text{The demand function looks like } (x_1^* , x_2^* ) = (\frac{m}{p_1 + p_2}, \frac{m}{p_1 + p_2}) \\
\text{The inverse demand function would be } (p_1 , p_2 ) = (\frac{m}{x_1^*} - p_2, \frac{m}{x_2^*} - p_1)
$$

### Income Changes

$$
\text{How does } x_1^*(p_1, p_2, m) \text{ change as y changes, holding other variables constant?}
$$

- Note that changes in income do not change indifference curves; it only changes the budget constraint, changing the highest curve obtainable
    - The curve containing the bundles that are demanded at different levels of income is known as the **income offer curve** (also known as the *income expansion path*)
- Two graphs can then be drawn to find the optimal amounts of both good 1 and good 2
    - The graphs mapping income (on y-axis) to quantity (on x-axis) is known as the **Engel curve**

![Engel and Income Offer Curves](https://www.economicsdiscussion.net/wp-content/uploads/2017/05/clip_image054_thumb2_thumb.jpg)

$$
\text{With Cobb-Douglas utility: } u(x_1, x_2) = x_1^a x_2^b \\
\text{The demand equations are } (x_1^* , x_2^* ) = (\frac{am}{(a + b)p_1}, \frac{bm}{(a + b) p_2}) \\
\text{Isolating for m: } m = (\frac{(a + b)p_1}{a}x_1^*, \frac{(a + b)p_2}{b}x_2^*) \\
\text{Note that m and the optimal amounts of either good are directly proportional to each other, } \\
\text{so in a Cobb-Douglas scenario, the Engel curves are straight lines.}
$$

![Cobb-Douglas Engel Curve](https://o.quizlet.com/PgV7CVurQTWz79-WjKIUAw.png)


$$
\text{With perfect complements: } u(x_1, x_2) = min\{x_1, x_2\} \\
\text{The demand function looks like } (x_1^* , x_2^* ) = (\frac{m}{p_1 + p_2}, \frac{m}{p_1 + p_2}) \\
\text{Isolating for m: } m = ((p_1 + p_2)x_1^*, (p_1 + p_2)x_2^*) \\
\text{Note that m and the optimal amounts of either good are directly proportional to each other, } \\
\text{so in a Cobb-Douglas scenario, the Engel curves are straight lines.}
$$

![Perfect Complements Engel Curve](https://images.slideplayer.com/26/8849357/slides/slide_7.jpg)

$$
\text{With perfect substitutes: } u(x_1, x_2) = x_1 + x_2 \\
\text{The demand function looks like: } \\
x_1^* (p_1, p_2, y) =
\left\{
    \begin{array}{lr}
        0, & \text{if } p_1 > p_2\\
        y / p_1, & \text{if } p_1 < p_2
    \end{array}
\right\} \\
x_2^* (p_1, p_2, y) =
\left\{
    \begin{array}{lr}
        0, & \text{if } p_1 < p_2\\
        y / p_2, & \text{if } p_1 > p_2
    \end{array}
\right\} \\ \\
\text{Suppose } p_1 < p_2 \text{. Then, } x_1^* = \frac{m}{p_1}, x_2^* = 0 \rightarrow m = p_1 x_1^*, x_2^* = 0 \\
\text{The opposite happens if } p_2 > p_1
$$

![Perfect Substitutes Engel Curve](https://o.quizlet.com/jbBVEbbW66d.WYSmUZaThQ.png)

- In all of the examples so far, the Engel curves have been straight lines, but this isn't always the case
    - Engel curves are only straight lines if the consumer's preferences are homothetic
    - **Homothetic preferences** are preferences in which the demand for any good goes up by the same proportion as income
    - **Luxury goods**: demand for the good goes up by a greater proportion than income
    - **Necessary good**: demand for the good goes up by a smaller proportion than income