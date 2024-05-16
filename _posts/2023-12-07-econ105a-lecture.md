---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Cost Curves
use-math: true
---

# Cost Curves

- Three main cost curves
    - Total cost curve
    - Variable cost curve
    - Average total cost curve
- Related cost curves
    - Average variable cost curve
    - Average fixed cost curve
    - Marginal cost curve

- In all of these curves, the horizontal axis is the output level (y) and the vertical axis is the cost

## Cost Functions

- F is the cost of the short run fixed inputs (AKA fixed cost)
- C<sub>v</sub>(y) is the cost of the variable inputs (AKA variable cost)
- C(y) is the total cost of all inputs (AKA total cost)
    - C(y) = F + C<sub>v</sub>(y)

![Cost Curves](https://d1whtlypfis84e.cloudfront.net/guides/wp-content/uploads/2018/09/03090118/SRTC4.jpg)

- Notice how C(y) and C<sub>v</sub>(y) have the same slope, but C(y) is shifted up by F units

## Average Cost Functions

- Three functions: average fixed cost, average variable cost, and average total cost
- For y > 0, the firm's average total cost function is AC(y) = (F + C<sub>v</sub>(y)) / y = AFC(y) + AVC(y)
    - AC and ATC are synonymous
- As y increases, AC and AVC will get closer and closer to each other, as AFC will trend towards 0 as y increases
- Note that natural monopolies arise as a result of decreasing AFC; the more customers a monopoly can serve, the lower the AFC gets and the lower the cost for the consumer

## Marginal Cost Function

- The marginal cost function is the rate of change of the variable cost as the output level changes

$$
MC(y) = \frac{\partial C_v (y)}{\partial y} = \frac{\partial C (y)}{\partial y} \\
\text{This result occurs because the total cost and variable cost functions have the same slope.}
$$

## Marginal and Average Cost Functions

- Note that, if the marginal cost is lower than the average cost, then the average cost will go down, and vice versa
- This means that the MC curve will intersect the ATC and AVC at their lowest point, being lower than them before the intersection and higher than them afterwards

![Average and Marginal Curves](https://d1whtlypfis84e.cloudfront.net/guides/wp-content/uploads/2018/09/03151911/SRAC1.jpg)

$$
\text{Mathematical proof:} \\
AVC(y) = \frac{C_v (y)}{y}
\frac{\partial AVC(y)}{y} = \frac{y \cdot \partial C_v (y) / \partial y - C_v(y)}{y^2} \text{ by the Quotient Rule} \\
MC = \partial C_v (y) / \partial y \\
\frac{\partial AVC(y)}{y} >, <, = 0 \text{ when } y \cdot MC(y) >, <, = C_v(y) \\
\frac{\partial AVC(y)}{y} >, <, = 0 \text{ when } MC(y) >, <, = AVC(y) \\
\text{The same can be proven for ATC as well, where } ATC(y) = \frac{C (y)}{y} \\
\frac{\partial AVC(y)}{y} = \frac{y \cdot \partial C (y) / \partial y - C(y)}{y^2} \\
MC = \partial C(y) / \partial y \\
\frac{\partial ATC(y)}{y} >, <, = 0 \text{ when } y \cdot MC(y) >, <, = C(y) \\
\frac{\partial ATC(y)}{y} >, <, = 0 \text{ when } MC(y) >, <, = ATC(y) \\
$$

In other words, the MC curve will intersect the ATC curve from below at the ATC curve's minimum. The same applies to the AVC curve.