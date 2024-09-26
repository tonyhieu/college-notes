---
layout: post
description: Econ 105C
categories: [econ105c, lecture, spring24, markdown]
title: Keynesian Economics
use-math: true
toc: true
---

## Distinction Between Classical and Keynesian Economics
- Classical economics focuses on the long run, doesn't acknowledge "bumps" that the economy might go through
- Keynesian economics focuses on these "bumps" and aruges that they are persistent and important to the economy

## Fundamentals of Keynesian Economics
- Keynes argues that there is a general economic theory, and classical economics represents one aspect of his theory
- Output and employment depends not only on fixed labor supply and capital, but also demand for goods and services
    - Demand is affected by fiscal/monetary policy, demand from foreigners, and other exogenous changes (I, C, etc.)
    - Output is therefore demand-determined

## Keynesian Cross

- The cross expresses the (classic) goods market equilibrium in terms of planned expenditure
    - C = *planned* consumption
    - I = *planned* investment
    - G = *planned* gov't purchases
    - PE = C + I + G = *planned* expenditure
    - Y = real GDP = production
    - Difference between PE and Y is unplanned inventory investment
- Other elements of the Cross
    - Consumption function: C(Y - T) = MPC * (Y - T) (where MPC is marginal propensity to consume)
    - Government purchases, taxes: G and T
    - Investment: I(r), but can be also written as I
    - Planned expenditure: PE = C + I + G = MPC * (Y - T) + I + G
    - Equilibrium condition: PE = Y, or Y = MPC * (Y - T) + I + G, where T, I, and G are constants

![Cross](https://cdn.kastatic.org/ka-perseus-images/0416b52f0139d8121326a9ec6ba996a6e874cac0.jpg)

## Keynesian Multiplier

### Government Purchases Multiplier
$$
Y = C + I + G \\
\Delta Y = \Delta C + \Delta I + \Delta G \\
I = \bar{I}, \Delta I = 0 \\
C = MPC \cdot (Y - \bar{T}), \Delta C = MPC \cdot \Delta Y \\
\Delta Y =  MPC \cdot \Delta Y + \Delta G \\
\Delta Y = \frac{1}{1 - MPC} \Delta G \\
\text{Since MPC >= 1,} \Delta Y \geq \Delta G
$$

The **government purchases multiplier** is the increase in output that results from a $1 increase in G (or delta Y / delta G). An increase in G implies an increase in Y.

### Keynesian Tax Multiplier
$$
\Delta Y = \Delta C + \Delta I + \Delta G \\
\Delta Y = \Delta C + 0 + 0 \\
\Delta Y = MPC \cdot (\Delta Y - \Delta T)\\
(1 - MPC) \Delta Y = - MPC \cdot \Delta T\\
\Delta Y = \frac{-MPC}{1 - MPC} \cdot \Delta T
$$

The **Keynesian tax multiplier** is the increase in output that results from a $1 increase in T (or delta Y / delta T). An increase in T implies a decrease in Y.


## IS Curve

Earlier, investment was assumed to be exogenous; now, let's go back to the assumption that it depends on the interest rate.

PE = MPC * C(Y - T) + I(r) + G

The cominbations of all r and Y that result in a goods market equilibrium is known as the **IS curve**.

![IS Curve](https://i.ytimg.com/vi/g6aba0V6ifo/maxresdefault.jpg)

Note that the IS curve is negatively sloped. Intuitively, this makes sense, as a lower interest rate will increase investment, thus increasing the amount firms plan to spend. To match the increase in expenditure, Y must also increase.

Shifts in the PE curve also shift the IS curve.

## MP Curve

The IS curve describes the set of points for which *planned expenditure* by households and firms equal *actual expenditure*. In other words, it is a function that describes Y in terms of r, or Y(r).

The MP curve describes how the *central bank* sets interest rates in response to the economy. In other words, it is a function that describes r in terms of r, or r(Y).

In the IS Curve, we assume that the MP curve is horizontal, but in reality, the central bank sets interest rates in response to the economy as opposed to having it be horizontal. They will lower interest rates if the output is low and increase them if the output is high.

## Things that Shift the IS and MP Curves

- IS Curve
    - Changes in gov't spending
    - Changes in taxes
    - Changes in consumer confidence (preferences)
    - Changes in business confidence (preferences)
    - Changes in an investment subsidy
- MP Curve
    - Generally, changes to Fed policy will change MP
    - Changes in inflation
    - Changes in concerns about future inflation
    - Changes in the Fed chair