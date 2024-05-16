---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Cost Minimization
use-math: true
---

# Cost Minimization

- A firm is a <u>cost minimizer</u> if it produces any given output level (y > 0) with the smallest possible total cost
- Note that factor and input are synonyms in this chapter; they are interchangable

$$
\text{When the firm faces given input prices } w = (w_1, w_2, ..., w_n) \\
\text{the total cost function will be written as } c(w_1, ..., w_n, y)
$$

- Note that the total cost function does not include the amounts of inputs; this is because the total cost function is implied to use the optimal amount of inputs to minimize costs
    - In other words, the total cost function gives the firm's **smallest** possible total cost for producing y units of output given input prices w = (w<sub>1</sub>, ..., w<sub>n</sub>)

## Cost Minimization Problem

- Given two inputs and one output, we get the production function y = f(x<sub>1</sub>, x<sub>2</sub>)
- Given the input prices w<sub>1</sub>, w<sub>2</sub>, the cost of an input bundle (x<sub>1</sub>, x<sub>2</sub>) is w<sub>1</sub>x<sub>1</sub> +  w<sub>2</sub>x<sub>2</sub>

$$
\text{Given } w_1, w_2, y \text{, the firm's cost minimization problem is } min\{w_1 x_1 + w_2 x_2\} \text{ such that } f(x_1, x_2) = y
$$

The levels x<sub>1</sub><sup>\*</sup>(w<sub>1</sub>, w<sub>2</sub>, y) and x<sub>2</sub><sup>\*</sup>(w<sub>1</sub>, w<sub>2</sub>, y) in the least costly input bundle are the firm's <u>conditional demands</u> for inputs 1 and 2.

The <u>smallest possible</u> total cost for producing y output units is therefore c(w<sub>1</sub>, w<sub>2</sub>, y) = w<sub>1</sub>x<sub>1</sub><sup>\*</sup>(w<sub>1</sub>, w<sub>2</sub>, y) + w<sub>2</sub>x<sub>2</sub><sup>\*</sup>(w<sub>1</sub>, w<sub>2</sub>, y) 

## Isocost Lines

- An **isocost curve** contains all the input bundles that cost the same amount
- The isocost curve is extremely similar to the budget constraint, even sharing similar equations

$$
\text{Given } w_1 \text{ and } w_2 \text{, the equation of an isocost line with a cost of c is } w_1 x_1 + w_2 x_2 = c
\text{This can also be written as } x_2 = -\frac{w_1}{w_2} x_1 + \frac{c}{w_2}
$$

- The graph of isocost lines is therefore a series of parallel lines, with lower costs being closer to the origin

![Isocost lines](https://images.saymedia-content.com/.image/ar_1:1%2Cc_fill%2Ccs_srgb%2Cq_auto:eco%2Cw_1200/MTc2NDU3OTU4NTMwNjIyNjc3/profit-maximization-through-the-technique-of-isoquant-and-isocost-line.png)

- To minimize costs, we must find the lowest possible isocost line that is tangent with the isoquant curve corresponding to a given output level

![Isocost Isoquant Graph](https://upload.wikimedia.org/wikipedia/commons/1/1f/Isoquant_isocost_graph.png)

- To find the cost minizing bundle, set the slope (TRS) of the isoquant curve equal to the slope of the isocost curve

$$
\text{At an interior cost-minimizing input bundle:} \\
f(x_1^*, x_2^*) = y'
\text{Slope of isocost = slope of isoquant, or } -\frac{w_1}{w_2} = TRS = -\frac{MP_1}{MP_2} \text{ at } (x_1^*, x_2^*)
$$

## Cobb-Douglas Example

$$
y = f(x_1, x_2) = x_1^{1/3} x_2^{2/3} \text{ with input prices } w_1, w_2 \\
\text{Must satisfy two conditions: } \\
y = x_1^{1/3} x_2^{2/3} \\
-\frac{w_1}{w_2} = -\frac{MP_1}{MP_2} = \frac{x_2^*}{2x_1^*} \\
\text{From the second condition: } x_2^* = \frac{2w_1}{w_2} x_1^* \\
y = (x_1^*)^{1/3} (\frac{2w_1}{w_2} x_1^*)^{2/3} = x_1^* (\frac{2w_1}{w_2})^{2/3} \\
x_1^* = y (\frac{w_2}{2w_1})^{2/3}
x_2^* = \frac{2w_1}{w_2} y (\frac{w_2}{2w_1})^{2/3} = (\frac{2w_1}{w_2})^{1/3} y
$$