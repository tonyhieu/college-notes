---
layout: post
description: Econ 105A
categories: [econ105a, lecture, fall23, markdown]
title: Comparative Static Analysis of Budget Constraints 
use-math: true
---

## Opportunity Cost

$$
\text{Recall that the graph of the BC is given by } x_2 = -\frac{p_1}{p_2} x_1 + \frac{m}{p_2} \\
\text{The opportunity cost of an extra unit of good 1 is } \frac{p_1}{p_2} \text{ units of good 2.} \\
\text{The opportunity cost of an extra unit of good 2 is } \frac{p_2}{p_1} \text{ units of good 1.} \\
$$

## Comparative Static Analysis

- Comparative static analysis involves changing one parameter at a time to see how the BC and BS change

<img width="1400" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/b7952c97-02bc-4f68-9c19-a07764edf315">


### Income and Price Changes

- Recall that m represents the consumer's income
    - Increasing m increases the x and y intercepts; thus, the maximum amount of goods for both good 1 and good 2 increase, meaning that budget set grows (represented by change in area) and choice is improved; shifts parallel to the right/outward
    - <img width="767" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/c1dd6aa1-b3ac-4dea-95e5-dab7fd8e5451">
    - Decreasing m decreases the amount of goods available for purchase, thus shrinking the budget set and reducing choice; shifts graph parallel to the left/inwards
    - <img width="521" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/75d59f49-80bc-4f44-a186-2e35b8f9887e">
    - Note that the slope does not change in either case because the prices are unaffected
- Recall that p<sub>1</sub> and p<sub>2</sub> represent the prices of goods 1 and 2, respectively
    - We will only look at changing the price of one good to keep it simple
    - A decrease in p<sub>1</sub> increases the amount of good 1 that the consumer can buy, thus enlarging the budget set and improving choice; makes slope of BC more "shallow" (represented by the black graph)
    - An increase in p<sub>1</sub> decreases the amount of good 1 that the consumer can buy, thus shrinking the budget set and reducing choice; makes slope of BC more "steep" (represented by the green graph)
    - <img width="719" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/1f6ee15a-628f-4a65-b380-9fb477254af9">
    - These movements can be thought of as "pivots" around the y-intercept, as the amount of good 2 that can be purchased remains the same

### Uniform Ad Valorem Sales Tax

- Hypothetically, if all prices are changed in the same fashion (such as when the tax rate is increased on all goods), then the BC is moved in a parallel manner to the left
    - This tax policy is known as **uniform ad valorem sales tax** and is tied to the price of the good
        - "Ad valorem" means that the tax is levied in proportion to the value; i.e. tax is levied at 5% instead of $10

$$
\text{A uniform ad valorem sales tax ar rate t changes the BC from} \\
p_1 x_1 + p_2 x_2 = m \text{ to } (1+t)p_1 x_1 + (1+t)p_2 x_2 = m \\
\text{This is equivalent to an income decrease.} \\
(1+t)p_1 x_1 + (1+t)p_2 x_2 = m \rightarrow p_1 x_1 + p_2 x_2 = \frac{m}{1 + t}
$$

- A uniform ad valorem sales tax is therefore equivalent to an income tax
- <img width="404" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/7dc03b2f-397a-4c98-9cd0-2701c118d882">

## Real World Applications: Food Stamp Program

- Food stamps are coupons that only allow you to buy one good (food)
- The question: how does a commodity-specific gift (such as a food stamp) change a family's budget constraint and affect their decision making?
- Suppose that m = 100, p<sub>F</sub> = 1, and p<sub>G</sub> = 1 where p<sub>F</sub> represents the price of food and p<sub>G</sub> represents the price of all other goods
    - The budget constraint is defined as p<sub>F</sub>x<sub>F</sub> + p<sub>G</sub>x<sub>G</sub> = 100
- Suppose that 40 food stamps are issued to the family
    - The new budget constraint is p<sub>F</sub>(x<sub>F</sub> + 40) + p<sub>G</sub>x<sub>G</sub> = 100

$$
\text{The new budget constraint is } p_F (x_F - 40) + p_G x_G = 100 \\
p_F x_F - 40 p_F + p_G x_G = 100 \\
p_G x_G = 100 + 40 p_F - p_F x_F \\
x_G = - \frac{p_F}{p_G} x_F + \frac{100 + 40 p_F}{p_G}
$$

- The budget thus "increases", but you cannot utilize the entire budget increase
<img width="732" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/e4be3aac-fee7-4c91-a732-1fc925f35261">
