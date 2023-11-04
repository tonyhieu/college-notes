---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Finishing Demand and Starting Equilibrium
use-math: true
---

### Basic Types of Goods

- From last lecture, there exist luxury and necessary goods
- **Inferior goods** are goods that have demands which fall with income
- **Normal goods** are goods that have demands which rise with income
- In other words, normal goods have <u>positively sloped</u> Engel curves while inferior goods have <u>negatively sloped</u> Engel curves

## Equilibrium Chapter

- A market is in equilibrium when the total quantity demanded by buyers is equal to the total quantity supplied by sellers
    - Equilibrium must be maintained in order to avoid *shortages* or *surpluses* such that there is no waste
- Mathematically, given a price p, the quantity demanded is D(p) and the quantity supplied is S(p)
    - Equilibrium is defined as the point (p<sup>\*</sup>, q<sup>\*</sup>)

### Equilibrium with Linear Supply + Demand Curves

- In this situation, D(p) = a - bp and S(p) = c + dp
    - To find p<sup>*</sup>, set the equations equal to each other

$$
\text{At the equilibrium, } D(p^*) = S(p^*) \\
a - bp = c + dp \rightarrow p^* = \frac{a - c}{b + d} \\
q^* = a - \frac{b(a - c)}{b + d} = \frac{a(b + d)}{b + d} - \frac{b(a - c)}{b + d} \\
= \frac{ab + ad}{b + d} - \frac{ab - bc}{b + d} = \frac{ad + bc}{b + d}
$$

We can do the same thing with the inverse demand and supply functions.

$$
q = D(p) = a - bp \iff p = \frac{a - q}{b} = D^{-1} (q) \\
q = S(p) = c + dp \iff p = \frac{-c + q}{d} = S^{-1} (q) \\
\text{At the equilibrium quantity, } D^{-1} (q^*) = S^{-1} (q^*) \\
\frac{a - q^*}{b} = \frac{-c + q^*}{d} \rightarrow d(a - q^*) = b(-c + q^*) \\
da - dq^* = -bc + bq^* \rightarrow q^* = \frac{ad + bc}{b + d} \\
p^* =  \frac{a - \frac{ad + bc}{b + d}}{b} \rightarrow p^* = \frac{a - c}{b + d}
$$

### Special Cases

- Quantity supplied is fixed, independent of the market price; that is, the supply curve is now a vertical line, and q<sup>*</sup> = c for some fixed quantity c
    - In our original equations, S(p) = c + dp, so in this case, d = 0
    - p^* = D<sup>-1</sup>(q<sup>*</sup>) = (a - c)/b
- Quantity supplied is extremely sensitive to the market price; that is, the supply curve is now a horizontal line, and S<sup>-1</sup>(q) = p<sup>*</sup>
    - Because p<sup>\*</sup> is fixed, we need to find q<sup>\*</sup>
    - q<sup>\*</sup> = a - bp<sup>\*</sup>
    - There is no "easy" way to find the optimal price because d would be infinity in this case