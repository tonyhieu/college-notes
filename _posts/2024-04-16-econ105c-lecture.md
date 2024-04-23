---
layout: post
description: Econ 105C
categories: [econ105c, lecture, winter23, markdown]
title: The Monetary System and Money Multiplier
use-math: true
toc: true
---

## A Theory of the Money Supply

- Currency in circulation (D) and deposits (D) make up money (M = C + D)
- Assume there are $1000 in currency

### Case 1: No Banks

- With no banks, D = 0 and M = C = 1000

### Case 2: Banks Don't Make Loans

- In this scenario, banks don't make loans; they hold 100% of all deposits as cash reserves
- If people deposit half of their currency into banks:
    - C = 500
    - D = 500
    - M = 1000
    - R (reserves, not counted in money supply) = 500
- Monetary base (B) is C + R = 1000, shows how much money the economy started with

### Case 3: Banks Take Deposits and Make Loans

- Banks make money based on the fact that most depositors don't need all of their money all the time; they can make loans and investments w/ depositor's cash to make more money

- Suppose that people deposit half of their currency into the bank, and banks keep 20% of those deposits as reserves and lend out 80% as loans
    - C = 500 + 400 = 900
    - D = 500, 100 of which is kept and 400 of which is given out as loans
    - M = 1400
    - R = 100
    - B = C + R = 1000

This effect is known as the **money multiplier**. The scenario where banks hold a fraction of their deposits as reserves is known as **Fractional Reserve Banking**, and this automatically expands the amount of money M in the economy.

The borrower can further deposit their lone into another bank, thus redepositing the loan into another bank, and this process can continue until there are no more banks left, vastly increasing the money supply.

- Scenario with two banks:
    - C = 500 + 200 + 160 = 860
    - D<sub>Bank 1</sub> = 500 -> 100 + 400
    - D<sub>Bank 2</sub> = 200 -> 40 + 160
    - M = 860 + 500 + 200 = 1560
    - R = 100 + 40 = 140
    - B = C + R = 1000

This effect is known as **multiple deposit creation**, and it makes the money multiplier bigger.

<table>

<thead>
    <td>C</td>
    <td>D</td>
    <td>Bank</td>
    <td>R</td>
    <td>L</td>
</thead>

<tr>
    <td>500</td>
    <td>500</td>
    <td>Firstbank</td>
    <td>100</td>
    <td>400</td>
</tr>

<tr>
    <td>200</td>
    <td>200</td>
    <td>Secondbank</td>
    <td>40</td>
    <td>160</td>
</tr>

<tr>
    <td>80</td>
    <td>80</td>
    <td>Thirdbank</td>
    <td>16</td>
    <td>64</td>
</tr>

<tr>
    <td>32</td>
    <td>32</td>
    <td>Fourthbank</td>
    <td>6.40</td>
    <td>25.60</td>
</tr>

</table>

This goes on until C = 500 / (1 - 0.4) = 833.3

**Note**: This is representative of a geometric series, and the sum of a geometric series will converge to a * (1 - x), which will be the final amount of money available in the economy.

## Theory of the Money Multiplier

- Monetary Base: B = C + R
- Currency-Deposit Ratio: cr = C/D (determined by household preferences)
- Reserve-Deposit Ratio: rr = R/D (determined by regulations)

$$
M = C + D \\
B = C + R \\
\frac{M}{B} = \frac{C + D}{C + R} = \frac{C/D + 1}{C/D + R/D} = \frac{cr + 1}{cr + rr} \\
rr \leq 1 \rightarrow \frac{M}{B} \geq 1, \frac{M}{B} > 1 \iff rr < 1 \\
\text{If rr or cr goes up, then M/B will go down}
$$

- M/B is given a special letter: m, such that M = m * B
    - m is called the **money multiplier**
- A **central bank** is an institution that regulates and controls the monetary base B
    - Does not have perfect control over the total quantity of money M in the economy (cr and rr)
    - In depressive periods, cr and rr increase drastically because of reduced confidence in the economy
        - To keep M stable, the government can increase B in order to offset the increases in cr and rr, thus maintaining the value of m