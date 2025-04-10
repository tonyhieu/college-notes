---
layout: post
description: STATS 295
categories: [stats295, lecture, spring25, markdown]
title: Reinforcement Learning
use-math: true
toc: true
---

# Introduction

- **Reinforcement learning (RL)** is a *sequential decision making process*
- Two actors: an environment and an agent
    - The environment provides the agent with a state $s$ and a reward $r$
    - The agent performs an action $a$ on the environment
    - Goal: find a policy $\pi$ to maximize the agent's reward
- Modern RL theory foregoes simplifying the environment; instead, we study the complex function directly and attempt to build policies using it
- Most RL uses simulators
    - Unlimited data, decisions with real consequences, and ease of evaluation are all benefits of using a simulator
    - Without a simulator, these benefits disappear

## Markov Decision Process
- Consider the policy as a function that determines the action: ${a \sim \pi (s)}$
- Send the reward and new state: $r(s, a), s' \sim P(\cdot\vert s,a)$
- This continues on infinitely 

$$
s_0 \sim \mu_0, a_0 \sim \pi(s_0), (r_0, s_1) \sim P(s_0, a_0), a_1 \sim \pi(s_1), \ldots
$$

- Infinite Horizon Discounted Markov Decision Process
    - An MDP is defined as $M = (S, A, P, R, \gamma)$
    - State space $S$
    - Action space $A$
    - Transition kernel $P : S\times A \rightarrow \Delta(S)$, where $\Delta(S)$ is the probability simplex over $S$
    - Reward function $R : S\times A \rightarrow [0,1]$ (deterministic reward function)
    - Discount factor $\gamma \in [0, 1)$; important for convergence
- We want to take actions that maximize the cumulative reward

$$
E\left[\sum_{h=0}^\infty \gamma^h r(s_h, a_h)\right]
$$

- A policy $\pi : A \rightarrow \Delta(S)$ describes how the agent acts
- Value function:

$$
V^\pi(s) = E\left[\sum_{h=0}^\infty \gamma^h r(s_h, a_h) \vert s_0 = s, a_h \sim \pi(s_h), s_{h+1} \sim P(\cdot \vert s_h, a_h)\right]
$$

- The value function provides the value of a policy given differing starting states $s$
- Bellman equation for value function:

$$
V^\pi(s) = E_{a\sim\pi(s)}\left[r(s,a) + \gamma E_{s'\sim P(\cdot \vert s,a) V^\pi(s')} \right]
$$

- Q-function (Action-value function)

$$
Q^\pi (s,a) = E\left[\sum_{h=0}^\infty \gamma^h r(s_h, a_h) \vert (s_0, a_0) = (s, a), a_h \sim \pi(s_h), s_{h+1} \sim P(\cdot \vert s_h, a_h)\right]
$$

- Bellman equation for Q-function:

$$
Q^\pi(s,a) = r(s, a) + \gamma E_{s'\sim P(\cdot \vert s,a)} V^\pi (s')
$$

- Research revolves around estimating the value function and/or Q-function in order to find an optimal policy
- **Bellman Optimality** states that, for an infinite horizon discounted MDP, there exists a deterministic stationary policy $\pi ^*$ which is optimal

$$
\pi^* : S \rightarrow A, \text{ s.t.,} V^{\pi^*}(s) \geq V^\pi(s), \forall s,\pi
$$

## Bellman Optimality Equation Derivation

- Denote $V^* := V^{\pi*}$, $Q^* := Q^{\pi*}$
- Define $\hat{\pi}(s) := \text{arg max}_a Q^*(s,a)$; greedy policy
- **Bellman Optimality Equation**: ${V^*(s) = \max_a [r(s,a) + \gamma E_{s'\sim P(\cdot \vert s,a)} V^*(s')]}$
- We can prove that $V^{\hat{\pi}} = V^*(s), \forall s$
- This implies that $\hat{\pi}(s) := \argmax_a Q^*(s,a)$ is an optimal policy

*Theorem*: For any $V : S \rightarrow \mathbb{R}$, if ${V(s) = \max_a [r(s,a)+ \gamma E_{s'\sim P(\cdot\vert s,a)} V(s')], \forall s}$, then ${V(s) = V^*(s), \forall s}$

- $V^*$ satisfies Bellman Optimality
- Any V that satisfies Bellman Optimality must be that $V(s) = V^*(s), \forall s$
- Similarly, for any $Q$ that satisfies Bellamn Optimality, $Q(s,a) = Q^*(s,a), \forall s,a$

*Theorem*: For any $Q : S\times A \rightarrow \mathbb{R}$, if ${Q(s,a) = r(s,a)+ \gamma E_{s'\sim P(\cdot\vert s,a)} \max_{a'}Q(s', a'), \forall s}$, then ${Q(s,a) = Q^*(s,a), \forall s}$

## Value Iteration Algorithm

- **Bellman operator** $\mathcal{T}$ has the property that $Q^* = \mathcal{T}Q^*$
    - Formal definition: Given a function ${f : S\times A \rightarrow \mathbb{R}}$, $\mathcal{T}f$ satisfies ${(\mathcal{T}f)(s,a) := r(s,a) + \gamma E_{s'\sim P(\cdot \vert s,a)} \max_{a'\in A} f(s',a'), \forall s,a \in S\times A }$
- The **value iteration algorithm** is a dynamic programming method to find the optimal $Q$-function $Q^*$ by solving the Bellman equations iteraively
    - Converges exponentially fast
- Initialization: $Q^0 : \lVert Q^0 \rVert _\infty \in (0, \frac{1}{1-\gamma})$
- Iterate until convergence: $Q^{t+1} = \mathcal{T}Q^t$
- **Bellman Contraction Property**: ${\lVert \mathcal{T}Q - \mathcal{T}Q' \rVert _\infty \leq \gamma \lVert Q - Q' \rVert _\infty}$
- **Value Iteration Theory**: Given $Q^0$, the following inequality holds for any iteration: ${\lVert Q^{t+1} - Q^* \rVert _\infty \leq \gamma^{t+1} \lVert Q^0 - Q^* \rVert _\infty}$
- The difference between a learned policy at some iteration and the optimal policy has a performance bound dependent on $\gamma$
    - ${V^*(s) - V^{\pi^{t+1}}(s) \leq \frac{2\gamma^{t+1}}{1-\gamma} \lVert Q^0 - Q^* \rVert _\infty \forall s\in S}$
    - If the performance bound is small, then performance is guaranteed to be good; requires Q-functions to be similar