---
layout: post
description: MIT OpenCourseWare; Topics in Mathematics with Applications in Finance
categories: [mit, lecture, fall24, markdown]
title: Stochastic Calculus
use-math: true
toc: true
---

## Stochastic Processes I (Discrete Processes)

### Simple Random Walk

$$
\text{Let } Y_1, Y_2, ... \text{ be i.i.d. random variables such that } Y_i = \pm 1 \text{ with equal probability. Let } X_0 = 0 \text{ and } \\
X_k = Y_1 + ... + Y_k \\
\text{for all } k \geq 1 
$$

- X<sub>k</sub> is known as a **simple random walk**
- By CLT, the distribution of $\frac{1}{\sqrt{n}} X_n$ converges to the standard normal distribution N(0, 1)
- Properties:
    - $E[X_k] = 0$ for all k
    - *Independent Increment*: For all $0 = k_0 \leq k_1 \leq ... \leq k_r$, the random variables $X_{k_{i+1}} - X_{k_i}$ for all $0 \leq i \leq r - 1$ are mutually independent
    - *Stationary*: For all h ≥ 1 and k ≥ 1, the distribution of $X_{k+h} - X_k$ is the same as the distribution of $X_h$

- For two positive integers A and B, the probability that the random walk reaches A before it reaches -B is given by $\frac{B}{A+B}$

### Martingale

- A discrete-time stochastic process is a **martingale** if $X_t = E[X_{t+1} \vert X_0, ..., X_t]$ for all t ≥ 0
    - In other words, a process is a martingale if the expected gain in the process is zero at all times
    - Can be thought of as a "fair game"
- The simple random walk is a martingale, but the expected balance of a roulette player is not

### Optional Stopping Theorem

- Given a stochastic process, a non-negative integer-valued random variable $\tau$ is called a **stopping time** if, for every integer k ≥ 0, the event $\tau \leq k$ depends only on the events $X_0, X_1, ..., X_k$
    - In the simple random walk, the first time you reach x = 100 is a stopping time
    - The time you reach a local maximum in the random walk is not a stopping time; depends on future events
- **Stopping Time Theorem**: Suppose that $X_0, X_1, X_2, ...$ is a martingale sequence and $\tau$ is a stopping time such that $\tau \leq T$ for some constant T. Then, $E[X_\tau] = E[X_0]$.

$$
\text{Let } \tau \text{ be the first time at which the balance of a coin toss gambler reaches either A or -B.} \\
E[X_\tau] = 0 \\
E[X_\tau] = pA - (1-p)B \\
pA - (1-p)B = pA + pB - B = 0 \\
p = \frac{B}{A+B}
$$

## Stochastic Processes II (Continuous Processes)

- Continuous time processes can be thought of as a probability distribution of the paths a process can take

- Consider a probability space ($\Omega, P$). A stochastic process X can also be thought of as a map from the universe $\Omega$ to the space of real functions defined over $[0, \infty]$
    - The probability of taking a path in some set A can be computed as $P(X^{-1}(A))$
    - P is the probability distribution of the stochastic process

### Standard Brownian Motion

- Also known as a *Weiner process*
- **Standard Brownian motion**: There exists a probability distribution over the set of continuous functions $B: \R \rightarrow \R$ satisfying the following conditions:
    - B(0) = 0
    - *Stationary*: For all 0 ≤ s < t, the distribution of B(t) - B(s) follows Normal(0, t - s)
    - *Independent Increment*: The random variables $B(t_i) - B(s_i)$ are mutually independent if the intervals $[s_i, t_i]$ are nonoverlapping
- Can be thought of as the limit of simple random walks where the distance between intervals gets infinitely smaller
- Facts:
    - Crosses the x-axis infinitely often
    - Does not deviate from $x = y^2$ too much
    - Is nowhere differentiable (with probability 1)
        - Proved using Borel-Cantelli lemma

#### Quadratic Variation
- For a partition $\Pi = \{t_0, t_1, ..., t_j\}$ of an interval $[0, T]$, let $\vert \Pi \vert = \text{max}_i (t_{i+1} - t_i)$. A Brownian motion $B_t$ satisfies the following equation with probability 1:

$$
\lim_{\vert \Pi \vert \to 0} \sum_{i} (B_{t_{i+1}} - B_{t_i})^2 = T
$$

- Functions that are continuously differentiable follow $\lim_{\vert \Pi \vert \to 0} \sum_{i} (f(t_{i+1}) - f(t_i))^2 \leq 0$, so Brownian motion varies a lot
    - Can be written as $(dB)^2 = dt$

#### Brownian Motion with Drift

- Let B(t) be a Brownian motion, and let $\mu$ be a fixed real. The process $X(t) = B(t) + \mu t$ is called a *Brownian motion with drift $\mu$*.
    - $\mu t$ dominates B(t) over time; X(t) will vary around the line $\mu t$

## Ito Calculus

- There are various applications where we want to create a function that depends on Brownian motion; in other words, some function f such that f = f(t, B<sub>t</sub>) = f(B<sub>t</sub>)
    - Assume that f is a smooth function (differentiable everywhere)
- Can't use Chain Rule to find derivative of f, as $\frac{dB_t}{dt}$ does not exist
- Must use Taylor expansion to find the derivative

### Derivatives

$$
f(x + \Delta x) - f(x) = (\Delta x) \cdot f'(x) + \frac{(\Delta x)^2}{2} f''(x) + \frac{(\Delta x)^3}{6} f'''(x) + ... \\
\text{Using a function that uses Brownian motion:} \\
\Delta f = (\Delta B_t) \cdot f'(B_t) + \frac{(\Delta B_t)^2}{2} f''(B_t) + \frac{(\Delta B_t)^3}{6} f'''(B_t) + ... \\
\text{Since } E[(\Delta B_t)^2] = \Delta t \text{, we cannot neglect it. Thus, we rewrite the equation to the following:} \\
\Delta f = (\Delta B_t) \cdot f'(B_t) + \frac{(\Delta t)^2}{2} f''(B_t) + ... \\
df(B_t) = f'(B_t) dB_t + \frac{1}{2} f''(B_t)dt \\
\text{This equation is known as Ito's lemma.}
$$

More generally, consider a smooth function f(t, x) which depends on two variables.

$$
\text{Classical result: } df = \frac{\partial f}{\partial t} dt + \frac{\partial f}{\partial x} dx \\
\text{Ito result: } df(t, B_t) = \frac{\partial f}{\partial t} dt + \frac{\partial f}{\partial x} dB_t + \frac{1}{2} \frac{\partial^2 f}{\partial x^2} (dB_t)^2 = (\frac{\partial f}{\partial t} + \frac{1}{2} \frac{\partial^2 f}{\partial x^2}) dt + \frac{\partial f}{\partial x} dB_t \\
$$

$$
\text{Let } f(t, x) \text{ be smooth and } X_t \text{ be a stochastic process satisfying } dX_t = \mu_{t}dt + \sigma_{t}dB_t \\
df(t, X_t) = (\frac{\partial f}{\partial t} + \mu_{t} \frac{\partial f}{\partial x} + \frac{1}{2} \sigma_{t}^2 \frac{\partial^2 f}{\partial x^2}) dt + \frac{\partial f}{\partial x} dB_t \\
\text{This is because } dt dB_t \text{ and } (dt)^2 \text{ go to 0.}
$$

### Integration

$$
\text{Integration is defined as the inverse of differentiation:} \\
F(t, B_t) = \int f(t, B_t) dB_t + \int g(t, B_t) dt \iff dF = f(t, B_t) dB_t + g(t, B_t) dt \\
$$

$$
\text{Consider the function } f(x) = \frac{1}{2} x^2 \\
df(B_t) = B_t dB_t + \frac{1}{2}dt \text{ by Ito's lemma.} \\
\frac{1}{2} B_T^2 = \int_0^T B_t dB_t + \int_0^T \frac{1}{2}dt = \int_0^T B_t dB_t + \frac{T}{2} \text{ using our definition of integration.} \\
\text{This implies that } \int_0^T B_t dB_t = \frac{1}{2} B_T^2 - \frac{T}{2} \text{ which contradicts classical calculus.}
$$