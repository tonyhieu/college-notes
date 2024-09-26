---
layout: post
description: Econ 105B
categories: [econ105b, lecture, winter24, markdown]
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
\pi = MR - MC = 0 \\
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

## Price Discrimination

- **Price Discrimination**: The practice of selling identical units of output at different prices
- Multiple ways of performing price discrimination

### Market Segmentation

- Monopolists divide customers into two or more groups, charging each group a different price
- Requirements
    - Monopolists must be able to separate buyers and enforce pricing policies
    - Leakage must be prevented; people from a cheaper market cannot sell to a more expensive market
- Also known as *third-degree price discrimination*

$$
\text{Suppose the firm identifies n separate markets. The firm's profits are:} \\
\pi = \sum _{i = 1}^{n} P_i (Q_i) \cdot Q_i - C(\sum _{i}^{n} Q_i) \\
\text{The first order condition is:} \\
\frac{\partial \pi (Q_i)}{\partial Q_i} = P_i + Q_i \frac{\partial P_i}{\partial Q_i} - \frac{\partial C}{\partial Q_i} = 0 \\
\text{Note that } MR_i = P_i + Q_i {\partial P_i}{\partial Q_i} 
\text{ and } \frac{\partial C}{\partial Q_i} \text{ is equal for all i.} \\
\text{Thus, the following equation holds: } MR_i = MR_j \text{ for all i, j where } i \neq j \\
\text{For each market i,} \\
MR_i = P_i + Q_i {\partial P_i}{\partial Q_i} = P_i [1 + \frac{Q_i}{P_i} \frac{\partial P_i}{\partial Q_i}] = P_i [1 - \frac{1}{|e_i|}] \\
\text{Thus, } P_i [1 - \frac{1}{|e_i|}] = P_j [1 - \frac{1}{|e_j|}] \\
\text{Therfore, if } P_i > P_j \text{, then} \\
1 - \frac{1}{|e_i|} < 1 - \frac{1}{|e_j|} \rightarrow \frac{1}{|e_j|} < \frac{1}{|e_i|} \iff |e_i| < |e_j|
$$

This math shows that the market segment with the more elastic demand will be charged a lower price, and vice versa.

### Multi-Part Pricing

- Defined as charging a different price for different quantities of output purchased by a single consumer
- Also known as second-degree price discrimination
- Allows firms to gain more profit by increasing the number of consumers

<img width="343" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/b2085906-dfa0-42fc-959b-20a3cd00cd4e">

### Perfect Price Discrimination

- A different price can be charged to each customer for each unit of output purchased 
- Also known as first-degree price discrimination
- Impossible in practice due to lack of information, but makes it so that there is no deadweight loss

<img width="573" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/b9d4f3ff-66b0-4897-ae95-8ec332ba6e52">

## Regulation of Natural Monopolies

- Monopolies are regulated to get rid of deadweight loss; marginal costs equaling marginal revenue is the most efficient way to have a market
- In practice, regulation aims to limit monopolies to accruing 0 economic profit
- Regulations depend on the nature of the monopoly, or the source of its power
    - **Natural monopolies** are monopolies which can produce any output at a lower cost than its competitors
- **Average Cost regulation** forces monopolies to charge at their average cost which causes the firm to have zero economic profit
    - Note that this regulation does not deincentivize innovation; in practice, the government cannot keep the regulated price at the firm's average cost, so if the firm innovates and decreases their average cost, they enjoy higher profits for a time
    - To prevent other firm's from entering the market, the monopolizing firm must keep their prices at or below their average cost; that is, P <= AC

# Models of Oligopoly

## Basic Models

- Oligopolies are defined as markets with a few firms that are all not price takers
$$
\text{Assume that all firms in the oligopoly are identical.} \\
\text{The quantity produced by a firm i in the oligopoly is denoted by } q_i \text{ for } i \in [1, n] \\
Q = \sum _{i = 1}^{n} q_i \\
P = P(Q) = P(\sum _{i = 1}^{n} q_i) \\
\text{Each firm maximizes its own profits subject to the market and technological constraints: } \\
\pi _i = P(Q) q_i - C(q_i)
$$

### Quasi-Competitive Model

If all firms are price-taking:

$$
\pi _i = P q_i - C(q_i) \\
\text{FOC: } \frac{\partial \pi _i}{\partial q_i} = P - \frac{\partial C(q_i)}{\partial q_i} = 0 \\
$$

This is identical to the perfectly competitive model.

### Cartel Model

If all firms coordinate their decisions to behave as a single monopoly, they can choose their outputs as follows to maximize joint profits:

$$
\Pi \equiv \sum _{i = 1}^{n} \pi _i = P(Q) Q - \sum _{i = 1}{n} C(q_i) \\
\text{FOC: } \frac{\partial \Pi}{\partial q_i} = P(Q) \frac{\partial Q}{\partial q_i} + \frac{\partial P(Q)}{\partial Q} \frac{\partial Q}{\partial q_i} Q - \frac{\partial C(q_i)}{\partial q_i} = 0
$$

This is identical to the single monopoly model. However, this is not feasible.
- Firms cannot collude due to anti-trust acts
- Too much information required; market demand, individual firm marginal costs, etc.
- Unstable solution; each firm has an incentive to increase their quantity to increase their profits

### Cournot Solution

Assume that all firms realize that they influence the price and that there is no collusion.

$$
\pi _i = P(Q) q_i - C(q_i) \\
\text{FOC: } \frac{\partial \pi _i}{\partial q_i} = P(Q) + \frac{\partial P(Q)}{\partial Q} \frac{\partial Q}{\partial q_i} q_i - \frac{\partial C(q_i)}{\partial q_i} = 0 \\
\text{SOC: } \pi '' \leq 0
$$

This solution lies between the cartel and perfect competition solutions.

- The Cournot solution will output more than the cartel solution, as each firm in the oligopoly will perceive an increase in their quantity to affect the price less compared to a monopoly
    - i.e. if one firm increases output by 1, they have less influence than if the monopoly increases output by 1
- The Cournot solution will output less than the competitive solution, as each firm acknowledges that they influence the price by increasing output


<img width="487" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/f21b156a-fa41-46db-8a52-c481c651b8e0">

## Game Theory

The Oligopoly market structure can be thought of as a game. Games are characterized by the following:
- *Players:* Each decision maker is called a player, indexed by i = A, B, ..., N where N is the number of players.
- *Actions:* Each player can choose an action  s<sub>i</sub> from a set of moves S<sub>i</sub>
- *Strategies:* A strategy specifies an action which might be contingent on some condition X. The action based on a strategy can be thought of as a function s<sub>i</sub>(X)
- *Payoffs:* Each possible outcome of a game creates a reward for the players. Realized payoff will be determined by strategies adopted by the players and perhaps some factors outside of the control of the players ("nature"). This can be expressed as a monetary reward or in utility.

$$
\text{In a two player game where } i = A, B \\
U_A (s_A, s_B) \text{ is the payoff obtained by player A when player A and B choose strategies} s_A \text{ and } s_B \text{, respectively.} \\
U_B (s_A, s_B) \text{ is the payoff obtained by player B when player A and B choose strategies} s_A \text{ and } s_B \text{, respectively.} \\
$$

In **Normal form representation**, games are represented as a payoff matrix.

<img width="714" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/6537424b-3f1b-4e63-8d9b-c036891ca7a3">


Games can have various rules.
- Cooperative or non-cooperative; i.e., cartel vs. competition
- One-shot or repeated; i.e., how many times is the game played?
- Simultaneous of sequential moves; i.e., do players act at the same time?
- Complete or incomplete information; i.e., how much do players know about each other?


Games in this class will be non-cooperative, one-shot, simultaneous, and with complete information.

### Nash Equilibrium in static games

Consider a two player game where i = A, B. The *equilibrium* of the game is defined in terms of the players' best responses.

A pair of strategies (s<sup>*</sup><sub>A</sub>, s<sup>*</sup><sub>B</sub>) represents a **Nash equilibrium** if s<sup>\*</sup><sub>A</sub> is A's best strategy when B plays s<sup>\*</sup><sub>B</sub> and vice versa. These strategies are also known as *dominant strategies*.

The classic example of Nash Equilibrium is the Prisoners' Dilemma, where both players have a dominant strategy and as such there is one equilibrium. However, there are cases where there are more than one equilibria, and those cases occur when there are many, continuous strategies.

### Examples of Games and Equilibria

<img width="648" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/115d947f-8109-45f9-9f57-32d83d1cfcaf">

<img width="543" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/1b3b237c-a3c8-4d80-95c3-daddcb6a5131">

<img width="536" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/e8b33090-301c-4150-8862-7a13429e9b15">

### Equilibrium Refinements

There are some ways to rule out equilibria when multiple exist.
- A strategy is **strictly dominant** if the payoff received is greater than any other strategy regardless of what the other player does
- A strategy is **weakly dominant** if the payoff received is greater than or equal to any other strategy regardless of what the other player does AND it is greater than at least one other strategy
- A **dominant strategy equilibrium** is a choice of strategies where each player has a strategy that (weakly) dominates all other strategies

To figure out the Nash equilibria, we can remove any strategies that are *dominated*. For example, in the Prisoners' Dilemma, though both parties cooperating result in the best outcome, cooperation is dominated by betrayal.

### Dynamic Games

Dynamic games are games with a temporal element (such as being sequential, repeated, etc.)

<img width="473" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/49e7bf72-17d4-4add-b83a-9de152605e9e">


We can turn this game into a sequential game.

<img width="533" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/557bc3b3-f589-453e-803a-f010a33381e3">


In this sequential game, A realizes that choosing N will always result in them receiving 2. Thus, A will choose L in order to receive 3 payoff, while B chooses N. The equilibrium is therefore (L, N).

A **sub-game perfect equilibrium** is an equilibrium which is not only an overall equilibrium but an equilibrium in each sub-game. To find this equilibrium, induction must be performed on each sub-game. For instance, in a sequential game, the player with the second-to-last move can look at what the player with the last move will choose.

## Imperfect Competition in Static Games

*Static games* are games that are non-cooperative, one-shot games with complete information and simultaneous moves.

### Bertrand-Nash Equilibrium

Consider a duopoly with firms A and B. Each produces the same good at a constant marginal cost c. A chooses a price P<sub>A</sub> and B chooses P<sub>B</sub>. Both firms make their choice such that P<sub>i</sub> >= c, where P = P(Q) and Q = q<sub>A</sub> + q<sub>B</sub>.

Since the goods are identical, the firm that offers the good at a lower price will capture the entire market. Assume that if P<sub>A</sub> = P<sub>B</sub>, each firm takes half. Note that, because both firms don't want to lose the market, they will both charge a price where P<sub>i</sub> = c, leading to both firms making no profit.

In the competitive solution, A and B choose the same price, where P<sub>A</sub> = P<sub>B</sub> = c.
- Neither firm can choose a price higher than their marginal cost, as the other firm will choose a lower price and capture the entire market
- Both firms must choose a price equal to their marginal cost, resulting in the equilibrium
- The profit will be equal to 0 because price is equal to marginal cost


Note that in situations where one firm captures the whole market does NOT mean that the firm has a monopoly. This is because the optimal pricing for the monopoly would allow the opposing firm to reenter the market, thus reducing market power.

### Cournot-Nash Equilibrium

$$
\text{Suppose that there are capacity constraints } \bar{q_i} \text{ and let } \bar{P} \\
\text{ represent the price that would prevail when production by the firms is at capacity, } \\
\bar{P} = P (\sum _i \bar{q_i})  
$$

Let there be two firms A and B who both produce at the same marginal cost c.

There are two stages to this game: 
1. Firms choosing their capacity
2. Firms engaging in Bertrand-Nash price competition


To solve the model, we go backwards:

$$
\text{Stage 2} \\
P_A = P_B = \bar{P} = P(\bar{Q}) = P(\bar{q_A} + \bar{q_B}) \\
\text{Facts:} \\
P_A = P_B \\
P_A = P_B < \bar{P} \text{ is impossible because there is excess demand} \\
P_A = P_B > \bar{P} \text{ is impossible because there isn't enough demand} \\
\text{Thus, both firms must produce at capacity.}
$$

$$
\text{Stage 1} \\
P(Q) = \mu _0 - \mu _1 Q \text{, where } Q = q_A + q_B, \mu _0 > c, \mu _1 > 0 \\
\pi _A = P(Q) q_A - c q_A = [\mu _0 - \mu _1[q_A + q_B] - c] q_A \\
\pi _B = P(Q) q_B - c q_B = [\mu _0 - \mu _1[q_A + q_B] - c] q_B \\
\pi _A ' = \mu _0 - c - 2 \mu _1 q_A - \mu _1 q_B = 0 \\
\pi _B ' = \mu _0 - c - 2 \mu _1 q_B - \mu _1 q_A = 0 \\
q_A = \frac{\mu _0 - c - \mu _1 q_B}{2 \mu _1} \\
q_B = \frac{\mu _0 - c - \mu _1 q_A}{2 \mu _1} \\
$$


<img width="436" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/3238bc24-aca9-47c6-8990-d157dd408ece">


## Repeated Static Games and Tacit Collusion

*Repeated static games*, which are defined as dynamic, non-cooperative, simultaneous move games with complete information, have wide strategy sets due to the sheer amount of moves that either firm can choose. Firms can announce their future moves that are based on the present state which can lead to collusion.

The question is: Does collusion occur in repeated static games?

### One-Shot Game

In a duopoly, firms have four options, based on (C)olluding and (D)efecting.
- (C, C): Both firms choose the monopoly price and maximize profits
- (D, D): Both firms attempt to undercut each other by setting price equal to marginal cost, leading to the competitive solution
- (D, C) and (C, D): One firm undercuts the monopoly price while the other doesn't, so the defecting firm gets the entirety of the market share and the most profit possible

In this scenario, the Nash equilibrium is (D, D).

### Finite Repetition

Suppose the game is played T times. The choice of defecting or colluding can be thought of as a *trigger strategy*.
- A simple trigger strategy would be: defect if the other firm defected last round; otherwise, collude.

However, in finite repetition, the repeated game degenerates to a one-shot game. Think about the scenario in which both firms colluded for all T - 1 games. Both firms are thus incentivized to defect on the last game, as they can get a temporary gain of half of the monopoly's profit and because there is no future to worry about. However, because this last game is fixed, the decision to defect recurses for the remaining subgames, all the way from T - 1, T - 2, ..., 1.


### Infinite Repetition

Assume that both firms take the same trigger strategy detailed in the finite games. Note that, if both firms collude initially, then they will collude infinitely, but if they don't collude, then they will defect infinitely. Suppose further that both firms have a discount factor that determines how likely they are to repeat the results of a given sub-game. Thus, the expected profits can as the following:


<img width="413" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/f870b5f7-32d2-4499-a186-089bb4fd9084">

<img width="641" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/75ed2218-fc8d-4110-9374-0ef3a5fdb99a">

There exist a few theorems regarding this result:
- **Severity of the Punishment**: A shorter punihsment might support collusion. Different punishment lengths lead to many equilibria
- **Power of the Shadow of the Future**: If firms are sufficiently patient or believe that the game will last sufficiently long, then collusion will be further supported in the finite game

## Strategic Considerations with Entry and Exit

One-time expenditures necessary to enter a market are known as **sunk costs**. This can be expressed in a cost function:

$$
c_t = c(q_t) = S + F_t + a \cdot q_t \\
\text{Where S is a per-period amortization of sunk costs, } F_1 \text{ denotes the fixed cost in period t,}\\
\text{and } q_t \text{ is the quantity produced in period t.}
$$

Are sunk costs good or bad?

### First-move Advantage

Suppose that firm A leads, and B follows. Firm A has a variety of options, and it knows that whatever price/quantity it chooses could influence B's decision to enter the market.

<img width="818" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/d7a01f68-4f1c-4990-b93b-689e0a9d54cd">

<img width="825" alt="image" src="https://github.com/tonyhieu/college-notes/assets/54915685/ecdf5a63-0ff9-480b-80fb-2865b8963948">