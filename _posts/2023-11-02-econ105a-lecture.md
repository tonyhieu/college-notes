---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Taxation
use-math: true
---

### Taxes Related to Equilibrium

- Types of taxes
    - **Quantity Taxes**: a set tax levied on each unit of a good traded
    - **Excise Tax**: a tax levied on sellers
    - **Sales Tax**: a tax levied on buyers
- The definition of equilibrium means that the market <u>clears</u>; that is, Q<sub>S</sub> = Q<sub>D</sub>, or D(p) = S(p)
- A tax rate t makes the price paid by buyers P<sub>b</sub> higher than the price received by sellers P<sub>s</sub>:  P<sub>b</sub> -  P<sub>s</sub> = t
- To solve for the market equilibrium after a tax is levied, we need two equations
    - Note that regardless of levying an excise or sales tax, the outcome is the same
    1. D(p<sub>b</sub>) = S(p<sub>s</sub>)
    2. p<sub>b</sub> -  p<sub>s</sub> = t

- The division of the tax burden between buys and sellers is known as the **incidence** of the tax
    - Note that the incidence of the tax is evenly split between buyers and sellers
    - [Tax Graph](https://enotesworld.com/wp-content/uploads/2020/08/Screenshot-770-1024x647.png)

$$
\text{Solving for equilibrium price + quantity} \\
D(p_b) = a - bp_b, S(p_s) = c + dp_s \\
\text{Two necessary equations: } p_b - p_s = t, D(p_b) = S(p_s) \\
p_b = p_s + t \rightarrow a - b(p_s + t) = c + dp_s \rightarrow p_s = \frac{a - c - bt}{b + d} \\
p_b = p_s + t = \rightarrow p_s = \frac{a - c + dt}{b + d} \\
q^t = D(p_b) = S(p_s) = a - bp_b = \frac{ad + bc - bdt}{b + d} \\
\text{Note that the equilibrium price and quantity are nearly the same as it is without taxes.} \\
\text{As the tax, t, goes to 0, the tax equilibrium goes closer to the original equilibrium. } \\
\text{The tax paid per unit by the buyers: }\\
p_b - p^* = \frac{a - c + dt}{b + d} - \frac{a - c}{b + d} = \frac{dt}{b+d} \\
\text{The tax paid per unit by the sellers: }\\
p^* - p_s = \frac{a - c}{b + d} - \frac{a - c - bt}{b + d} = \frac{bt}{b+d} \\
\text{Note that the tax paid per unit by sellers and buyers is equal to t:} \\
\frac{bt}{b+d} + \frac{dt}{b+d} = \frac{(b+d)t}{b+d} = t
$$

- The total tax paid by buyers and sellers can be found by graphing the relationship between tax revenue and tax levied (AKA Laffer curve)
- ![Laffer Curve](https://www.investopedia.com/thmb/2mB9A8wzVXE506uOi-R6vwOuXrk=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/LafferCurve2-3509f81755554440855b5e48c182593e.png)
$$
\text{Equation: } T = tq^t = t \frac{ad + bc - bdt}{b + d}
$$

### Tax Incidence and Elasticities of Supply and Demand

$$
\text{Around } p = p^* \text{ the own-price elasticity of demand is approximately: } \\
\varepsilon _D \approx \frac{\frac{\triangle q}{q^*}}{\frac{p_b - p^*}{p^*}} \rightarrow p_b - p^* \approx \frac{\triangle q \cdot p^*}{\varepsilon _D \cdot q^*} \\
\text{Around } p = p^* \text{ the own-price elasticity of supply is approximately: } \\
\varepsilon _S \approx \frac{\frac{\triangle q}{q^*}}{\frac{p_s - p^*}{p^*}} \rightarrow p_s - p^* \approx \frac{\triangle q \cdot p^*}{\varepsilon _S \cdot q^*} \\
$$