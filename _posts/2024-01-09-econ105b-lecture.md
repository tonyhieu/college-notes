---
layout: post
description: Econ 105B
categories: [econ105b, lecture, winter23, markdown]
title: Market Structures
use-math: true
toc: true
---

# Competitive Equilibrium

## Cost Minimization

- Recall that the average cost of goods is minimized when MC = AC
- Must minimize cost before trying to maximize profit
- Note that in the long run, there are no fixed costs, so AC = AVC

## Demand Curves and Market Structures

- Maximizing profit comes with constraints
    - *Technological constraints* refer to the ability to produce some maximum amount of output
    - *Market constraints* refer to the demand curve a firm faces
        - Monopolies (1 firm markets) face a downward sloping demand curve
        - Perfect competition (many firms in a market) face a static, horizontal demand curve
        - Oligopoplies (few firm markets) are in the middle

## Competitive Equilibrium

$$
\text{Competitive firms attempt to maximize } \pi (q) = pq - c(q) \\
\text{First order condition: } \pi '(q^*) = p - c'(q^*) = 0 \\
\text{Second order condition: } \pi ''(q^*) = -c''(q^*) \leq 0 \rightarrow c''(q^*) \geq 0 \\
\text{Thus, the profit maximizing quantity occurs when } p - c'(q^*) = 0
$$

<img width="527" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/7193ad74-e02b-4c27-880b-e0790b5abdc3">

### Competitive Firm Short-Run

$$
\text{In the short run, there are fixed costs, so } \pi = pq - c(q, k') \text{ where k represents the fixed value.} \\
\text{The firm will thus choose q such that } \pi = p - c_s ' = 0 \text{ and } -c_s '' \leq 0 
$$

- Note that a firm can still make a loss despite profit maximizing

$$
\text{A firm will NOT shut down if it can cover its variable costs; that is:} \\
pq^* \geq c_v (q^*) \rightarrow p \geq AVC
$$

### Short-Run Supply Function of Competitive Market

$$
\text{The quantity supplied by a competitive market is given as the horizontal summation of firms' supply functions:} \\
Q_S = \sum q_i
$$

Q<sub>S</sub> is inaccurate because of the *input-price effect*; the result of all firms expanding output would cause all of their input prices to rise higher. Thus, the industry's short-run supply curve is *less* elastic than the individual firms' supply curves

<img width="439" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/0e8251a8-242c-4408-a762-94d56501a72f">

### Competitive Firm Long-Run

$$
\text{In the long run, there are no fixed costs, so the profit maximizing quantity satisfies the following:} \\
\pi '(q^*) = p - c_l' = 0 \\
\pi ''(q^*) = -c_l'' \leq 0 \\
\text{Additionally, the long-run no-shutdown condition must be satisfied:} \\
p \geq min\{\text{Long-Run Average Cost}\}
$$

### Industry Supply in the Long Run

- You can use horizontal summation on individual firms' supply curve to find the industry supply curve
- *Exit-entry effect*: In the long-run equilibrium, every firm belonging to the industry must make nonnegative economic profits
    - Positive economic profits cause firms to enter the industry
- Assumption: The elasticity of supply is greater in the long run than in the short run, as firms can more easily enter/exit from the market
- Assumption: In the long run, economic profit for any firm in a competitive equilibrium must equal 0

### Competitive Long vs. Short Run

If a firm perceives a change to be permanent, then it will make gradual changes; otherwise, it will make more drastic ones to capitalize

<img width="628" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/28ded7a5-3c5c-4c94-8319-da0f2fbffb71">

### Benefits of Exchange Under Perfect Competition

Because trade is mutually beneficial, the sum of producer and consumer surplus is maximized under a competitive market.

<img width="339" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/edbb5d01-c715-4e2d-bba0-76804bac4384">

The overall surplus can be hindered by government policies, such as taxes or supply quotas.

<img width="436" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/b44ef200-a096-4b77-b0c9-6db487e0317d">

<img width="433" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/4edbb3b3-04d3-4580-9f51-b85c40df6cf7">


# Models of Monopoly

- Monopolies are markets with a single supplier
- Occurs due to two reasons
    - *Technological constraints*: The marginal or average costs to produce a good is decreasing over a wide range of output levels relative to the market; in other words, monopolists have extremely low costs of production
    - *Legal constraints*: The government might grant certain suppliers the sole right to produce their good

## Profit Maximization

Monopolies can choose both the price and the quantity of the good supplied. Their profit maximization problem can be written in one of two ways:

In terms of price:
$$
\pi (P) = P \cdot Q(P) - C(Q(P)) \\
Q(P) = f(P) \text{, or the demand function} \\
P \cdot Q(P) = P \cdot f(P) \text{, or the total revenus} \\
C(Q(P)) = \text{ total costs} \\
R = P \cdot Q(P) \\
MR_P = Q + P \cdot \frac{\partial Q}{\partial P} \\
MC_P = \frac{\partial C}{\partial Q} \cdot \frac{\partial Q}{\partial P}
$$


Or in terms of demand:
$$
\pi (Q) = P(Q) \cdot Q - C(Q) \\
P(Q) = g(Q) = f^{-1} (Q) \text{, inverse demand} \\
P(Q) \cdot Q = g(Q) \cdot (Q) \text{, total revenues} \\
C(Q) = \text{ total costs}
R = P(Q) \cdot Q \\
MR_Q = P + Q \cdot \frac{\partial P}{\partial Q} \\
MC_Q = \frac{\partial C}{\partial Q}
$$

To find the profit maximizing quantity/price, we must set the marginal revenue and cost equal to each other; that is, the first-order condition:

$$
\pi = MR - MC = 0
\text{Price:} \\
\pi ' = Q + P \cdot \frac{\partial Q}{\partial P} - \frac{\partial C}{\partial Q} \cdot \frac{\partial Q}{\partial P} \\
\text{Quantity:} \\
\pi ' = P + Q \cdot \frac{\partial P}{\partial Q} - \frac{\partial C}{\partial Q}
$$


Another condition that must be satistfied is the second-order condition:

$$
\pi = \frac{\partial MR}{\partial Q} - \frac{\partial MC}{\partial Q} \leq 0 \\
\text{Quantity:} \\
\pi '' (Q^*) = 2 \frac{\partial P}{\partial Q} + \frac{\partial ^2 P}{\partial Q^2} - \frac{\partial ^2 C}{\partial Q^2}
$$


However, monopolies can markup their price higher over their cost. Thus, we can use elasticity to find the optimal price/quantity:


$$
e_{QP} = \frac{\partial QP}{\partial PQ} < 0 \\
MR = P + Q \cdot \frac{\partial P}{\partial Q} = P [1 + \frac{Q}{P} \frac{\partial P}{\partial Q}] = P [1 - \frac{1}{|e_{QP}|}]
$$


There are three cases of elasticity:
- Demand is infinitely elastic (like it is in perfect competition). Then, MR = P > 0
- Demand is relatveily inelastic (i.e. it is between negative infinity and -1). Then, MR > 0, but MR < P
- Demand is relatively elastic (i.e. it is between -1 and 0). Then, MR <= 0

We can apply elasticity to marginal cost as well.

$$
MC = P[1 - \frac{1}{|e_{QP}|}] \\
\frac{P - MC}{P} = \frac{1}{|e_{QP}|} \\
P = MC \div [1 - \frac{1}{|e_{QP}|}]
$$

## Comparison with Perfect Competition

### Comparing First-Order Conditions

One big difference between competitive and monopolistic firms are their marginal revenue functions.

$$
\text{Competitive: } MR = P \\
\text{Monopoly: } MR = P + Q \cdot \frac{\partial P}{\partial Q}
$$

This is because competitive firms are price takers and do not influence the price of their good.

### Comparing Outcomes

The overall surplus in a monopolistic industry is lower than in competitive industries, as firms will abuse their leverage and take away from consumers.

<img width="706" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/6bbc88ce-60b8-4683-96c4-9873c5868ce8">

