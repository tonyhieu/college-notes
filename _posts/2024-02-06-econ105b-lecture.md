---
layout: post
description: Econ 105B
categories: [econ105b, lecture, winter23, markdown]
title: General Equilibrium and Welfare
use-math: true
toc: true
---

# General Equilibrium

*The Fundamental Theorem of Exchange*: Voluntary trade between two individuals is beneficial to both parties.
- Exceptions include scams, whimsical purchases, or vices
- Benefits are derived from the rearrangement of consumption goods and production
    - In other words, each person can obstain a consumption basket more preferred to what is given, and people can specialize in production which increases the goods available for consumption

## Pure Exchange Economy

Characteristics:
- Several consumers, each described by their preferences and their endowments (what goods they possess)
- Consumers trade among themselves, acting in their self-interests
- No production means that there is a fixed supply of goods
- Income becomes endogenous with prices, even when endowments are exogenous and fixed

### Preliminaries and Assumptions

Consider an economy with two individuals, i = A, B, and two goods, X (apples) and Y (bananas)

$$
\text{Endowments: } E_A = (\bar{x_A}, \bar{y_A}), E_B = (\bar{x_B}, \bar{y_B}) \\
\bar{x} = \bar{x_A} + \bar{x_B}, \bar{y} = \bar{y_A} + \bar{y_B} \\
\text{Assume that } \bar{x_A} < \bar{x_B} \text{ and } \bar{y_A} > \bar{y_B} \\
\text{Preferences: Defined by a utility function and its corresponding indifference curve.}
$$

<img width="392" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/f3646fb0-ccd9-4ac5-88c8-fca3539f883f">


Note that at point E, where both parties consume their initial endowments, there are multiple indifference curves for both parties that are better than their current ones. Thus, the middle of the two indifference curves that pass through E gives the **region of mutually advantageous trade**. At points of *mutual tangency* of the two curves, the parties cannot trade any further or else at least one of them will be at a loss.

### Prices, Income, and Competitive Equilibria

The *budget constraints* of both parties give an equilibrium for trade.

$$
\text{Expenditures must equal income for an individual.} \\
E_i = p_x x_i + p_y y_i = I_i = p_x \bar{x_i} + p_y \bar{y_i} \\
dE_i = p_x dx_i + p_y dy_i = 0 \rightarrow \frac{dy_i}{dx_i} = - \frac{p_x}{p_y} 
$$

The *budget line* with slope of -p<sub>x</sub>/p<sub>y</sub> indicates for a given endowment/income how much of one good would have to be sacrificed to increase consumption of the other good.


To find the competitive equilibrium, we must find the point at which:
1. Tangent to both indifference curves
2. On the budget line

$$
\text{At the equilibrium, the following holds:} \\
p_x x_A + p_y y_A = p_x \bar{x_A} + p_y \bar{y_A} \\
p_x x_B + p_y y_B = p_x \bar{x_B} + p_y \bar{y_B} \\
| MRS^A_{xy} | = p_x / p_y =| MRS^B_{xy} \\

\text{Solution: } \\
\text{Let } p_y = 1 \text{. x is now measured in units of y.} \\
\text{max } U_i (x_i, y_i) \text{ such that } p_x x_i + y_i = I_i \\
\text{Assuming that x > 0 and y > 0: } y_i = I_i - p_x x_i \\
dy_i / dx_i = -p_x
$$

<img width="459" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/f911c356-9f6d-46e1-ae06-c94f4b4fa334">

<img width="272" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/81fca1d6-0843-4c9b-bb4f-0201f64b8ad5">


Simple steps:
1. Find MRS
2. Plug into Expenditures = Income equation
3. Plug into Endowments equation: x<sub>A</sub> + x<sub>B</sub> = x

## Production Economies

Characteristics:
- Assume individuals are endowed with a set of resources that can be combined to produce goods for consumption
- Production precedes trade
- Individuals participate in both production and trade

### Autarky

Under autarky, an individual can create a set of bundles underneath their **production-possibilities frontier**, whose boundary can be written as Q(x, y).

The cost of specializing in the production of x in terms of y can be seen in the slope of the PPF. This is also known as the **marginal rate of transformation**, and it can be calculated by dividing the marginal cost of x by the marginal cost of y.


Similarly to the problem shown to consumers with budget constraints, the optimal set to produce will be the point of tangency between the PPF and the highest indifference curve.

<img width="332" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/ec053dfa-9b86-453f-967e-4c72490342cd">

<img width="449" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/54f87249-3e73-4baf-abdc-e6afd147e810">

### Trade

With trade, the individual will choose the production bundle that maximizes income given prices p<sub>x</sub> and p<sub>y</sub>.

<img width="492" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/791a2b09-f95a-46a5-a70a-98de46f72570">

Additionally, the consumer purchases the bundle that maximizes their utility, which often lies on a higher indifference curve than the autarkic optimum.

<img width="490" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/6040874d-f182-42e4-9565-1c73f169ec01">

Notice how that the introduction of trade incentives the individual to specialize in the production of a good.

Thus, under trade, there are two separate problems to solve: maximizing income, and maximizing utility. First, find the production bundle that gives the highest budget line and budget constraint. Then, find the highest indifference curve according to that budget constraint.

For consumers, trade allows for a more balanced, preferred bundle, but for the economy, trade allows for specialization which means that there are more goods in the economy.

<img width="674" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/4e774192-ac1f-4ea0-97a2-eb1e25cf315b">