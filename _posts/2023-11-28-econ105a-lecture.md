---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Profit Maximization
use-math: true
---

## Competitive Firms

- Competitive firms are defined as suppliers that can only choose the amount of goods to output/the amount of inputs used
- Such firms cannot change the prices of its inputs nor its outputs; thus, these values are fixed

## Profit Maximizing in the Short-Run

- In the short-run, firms have one or more fixed costs; in the long-run, all costs are variable
- Assuming that a firm uses two inputs (with the amount of one of the inputs being fixed), we can write the profit function as follows:
$$
\pi = pf(x_1, \bar{x_2}) - w_1 x_1 - w_2 \bar{x_2} \\
\text{where p is output price, w is input price, and f is the production function}
$$
- Maximizing this function means that we must find the local maximum of π with respect to x<sub>1</sub>

$$
\text{The first derivative of the profit is given as:} \\
\pi' = \frac{p \partial f(x_1^*, \bar{x_2})}{\partial x_1} - w_1 \\

\text{The maximizing quantity of } x_1 \text{ is found when the first derivative is 0 and the second derivative is negative:} \\
\frac{p \partial f(x_1^*, \bar{x_2})}{\partial x_1} - w_1 = 0 \\

\text{This can be simplified to } p MP_1 = w_1 \text{ which will give the maximizing quantity of } x_1
$$

## Isoprofit Line

$$
\text{Using the equation for profit: } \\
\pi = pf(x_1, \bar{x_2}) - w_1 x_1 - w_2 \bar{x_2} = py - w_1 x_1 - w_2 \bar{x_2}\\
\text{The equation of a short-run isoprofit line is: } \\
y = \frac{w_1}{p} x_1 + \frac{\pi + w_2 \bar{x_2}}{p}
$$

- The isoprofit line is useful in order to find the profit-maximizing plan, as the best plan will lie on the highest isoprofit line
<img width="563" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/cb606602-1a9a-467e-86b7-3fe5feb29b5a">

## Comparative Static Analysis of Profit Maximization

- Keeping x<sub>2</sub> fixed:
    - If the price of the output (y) goes up, then the optimal amounts of y and x<sub>1</sub> go up as well
    - If the price of input 1 goes up, then the slope of the isoprofit line goes up, meaning that the optimal amounts of y and x<sub>1</sub> go down
    - <img width="370" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/201ae6f1-1471-4de7-8d4a-b4b3003d1776">
    - If the price of input 2 goes up, then the optimal amounts of either inputs are unchanged; the only thing that changes is the y-intercept of the isoprofit line, meaning that the firm simply makes less profit

## Long-Run Profit Maximization

- Using the same logic as the short-run, we can find the optimal amount of inputs for any amount of variable inputs

$$
\text{Recall that the optimal amount of input 1 in the short-run is given by } p MP_1 = w_1 \text{.} \\
\text{When there are multiple variable costs, this equation MUST hold.}
$$

### Cobb-Douglas Example

$$
y = x_1^{1/3} x_2^{1/3} \\
p \cdot MP_1 = w_1 \rightarrow p \cdot \frac{1}{3} x_1^{-2/3} x_2^{1/3} = w_1 \\
p \cdot MP_2 = w_2 \rightarrow p \cdot \frac{1}{3} x_1^{1/3} x_2^{-2/3} = w_2 \\
\text{Dividing the two above equations gives} \frac{x_1}{x_2} = \frac{w_2}{w_1} \rightarrow x_1 = \frac{w_2}{w_1} x_2\\
\frac{p}{3} ({\frac{w_2}{w_1} x_2})^{-2/3} x_2^{1/3} = w_1 \\
\frac{p}{3} ({\frac{w_2}{w_1}})^{-2/3} x_2^{-1/3} = w_1 \\
\frac{p^3}{27} ({\frac{w_2}{w_1}})^{-2} x_2^{-1} = w_1^3 \\
\frac{p^3}{27} ({\frac{w_2}{w_1}})^{-2} w_1^{-3} = x_2 \\

x_2^{**} = \frac{p^3}{27w_1 w_2^2} \\

x_1^{**} = \frac{p^3}{27w_1^2 w_2} \\

\text{Plugging the optimal amounts of input 1 and 2 into the production function:} \\
y^{**} = \frac{p^2}{9w_1w_2}
$$

## Returns-to-Scale
- If a competitive firm's techonology exhibits decreasing RTS, then there is only one "highest" isoprofit line, meaning that there is one, unique production plan
- If a competitive firm's technology exhibits increasing RTS, then there are infinitely many highest isoprofit lines, meaning that the firm does NOT have a profit-maximizing plan
    - A technology can have increasing RTS in the short-run, but if it is infinitely increasing RTS, then firms would keep getting infinitely bigger, breaking the assumption that the firm is competitive
- If a competitive firm's technology exhibits constant RTS, then the production function is linear, meaning that the isoprofit line MUST coincide with the production function
    - The profit of this isoprofit line has to be 0, as doubling the inputs should lead to a double in your outputs (2 x 0 = 0)
    - If the profit of the isoprofit lines was not 0, then you could continue to make more and more profit infinitely, leading to the same conclusion as increasing RTS
    - If the slope of the isoprofit line does NOT coincide with the production function, then you can keep taking higher and higher isoprofit lines; thus, they must coincide

## Revealed Profitability

Suppose that production bundle (x', y') is chosen at (w', p'). (x', y') must therefore be profit-maximizing at (w', p').
- Assuming that nothing is known about the production function, all we can do is draw one isoprofit line intersecting (x', y')
- The more known points, the more isoprofit lines drawn, and the more is revealed about the technology set
<img width="562" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/76f788c5-422b-4172-87e2-0a233c41c593">

## Weak Axiom of Profit Maximization (AKA WAPM)

- Suppose that a production bundle (x', y') is chosen at prices (w', p') and bundle (x'', y'') is chosen at prices (w'', p'')
    - This means that p'y' - w'x' MUST be greater than p'y'' - w'x'', as (x', y') is the profit maximizing bundle at (w', p')
- This observation gives the Weak Axiom of Profit Maximization

$$
\text{The Weak Axiom of Profit Maximization gives the following equation:} \\
\Delta p \Delta y - \Delta w_1 \Delta x_1 - ... - \Delta w_n \Delta x_n \geq 0
$$

Proof:

<img width="455" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/e1fd4317-b6ba-4786-962e-34507ee97732">

- The WAPM also gives observations regarding other fundamentals of economics
    - **Law of Supply**: If the change in w is 0, then ΔpΔy >= 0, meaning that a competitive firm's output supply curve cannot slope downward
        - Both Δp and Δy have to be negative or positive; one can't be negative while the other is positive
    - **Law of Demand**: If Δp = 0, then ΔwΔx <= 0, implying that a competitive firm's input demand curve cannot slope upwards
        - Δw and Δx have to have opposite signs to be less than zero