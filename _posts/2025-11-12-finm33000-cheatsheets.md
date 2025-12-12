---
layout: post
description: FINM 33000
categories: [finm33000, cheatsheets, fall25, markdown]
title: Options
use-math: true
toc: true
---

## Midterm

### Lecture 1

- Assume frictionless market; no default/counterparty risk, no transaction costs, no slippage, shorting, etc.
- A market is filled with some amount of assets with nonrandom time-0 times and random time-$T$ prices (aka payoffs)
    - *Zero-coupon or discount bond*: Each unit pays at time $T$ a fixed payoff, usually 1
    - *Stock*: Doesn't pay dividends, each unit has a time-$t$ price $S_t\geq 0$
    - *Bank account or money market account*: Each unit has a time-$t$ price $\exp\left(\int_0^t r_udu\right)$; if $r$ is constant, then $B_t = e^{rt}$
- A portfolio $\Theta$ is a vector of nonrandom quantities that denotes the number of units of asset owned, where negative numbers are shorts and positive numbers are longs
- An **arbitrage** is a way to profit from price inconsistencies
    - **Type 1**: $V_0 = 0$ and both $P(V_T \geq 0) = 1$ and $P(V_T>0) > 0$ (free and no risk of loss)
    - **Type 2**: $V_0 < 0$ and $P(V_T\geq 0 ) = 1$ (get credit and guaranteed not to pay it back)
- **Superreplication**: A portfolio $\Theta^a$ superreplicates $\Theta^b$ if $P(V_T^a\geq V_T^b) = 1$. Then, $V_0^a\geq V_0^b$, otherwise arbitrage exists
    - **Subreplication** is same except with $P(V_T^a\leq V_T^b) = 1$; **replication** mean that if $P(V_T^a= V_T^b) = 1$, then $V_0^a = V_0^b$
    - Also known as *law of one price*
- For a discount bond, the time-0 price should be $Z_0 = \frac{1}{B_T}$, or $Z_0=e^{-rT}$ if $r$ is constant
- A **forward contract** is a contract with maturity date $T$ and a fixed delivery price $K$ where the holder MUST pay $K$ and receive $S_T$ at time $T$; payoff is $S_T-K$
    - The time-0 value of a forward contract is equal to $S_0-KZ_0$
- A linear/affine contract on a stock $S$ that pays $a+bS_T$ has a time-0 value $aZ_0 + bS_0$
- A **call option** with strike $K$ and expiry $T$ on an underlying process $S$ has a payoff of $(S_T-K)^+$, as the holder is not obligated to exercise the option
    - The time-0 value $C_0$ satisfies $(S_0-KZ_0)^+\leq C_0\leq S_0$, as a call option dominates the forward contract and a zero payoff while being dominated by the stock
    - With two time-0 call options where $K_1 < K_2$, the payoff spread is defined as $0\leq C_0(K_1)-C_0(K_2)\leq (K_2-K_1)Z_0$
- A **put option** with strike $K$ and expiry $T$ on asset $S$ gives the holder the right to pay $S_T$ to receive $K$; its payoff is $(K-S_T)^+$
    - The time-0 price of a put satisfies $(KZ_0-S_0)^+ \leq P_0 \leq KZ_0$
    - With two puts: $0 \leq P_0(K_2) - P_0(K_1)\leq (K_2-K_1)Z_0$
- **Put-call parity**: A call option has the time-0 value $C_0(K,T) = P_0(K,T) + S_0 - KZ_0(T)$

### Lecture 2

- **Binomial model**
    - There are two times: $0$ and $T$
    - There are two states $\{\omega_u, \omega_d\}$ at time $T$ with probability greater than 0
    - Each unit has time-$t$ value $B_t = e^{rt}$
    - The stock $S$ takes values $S_T(\omega_u)=s_u$ and $S_T(\omega_d)=s_d$
        - Also exists an option contract $C$ that has $C_T(\omega_u)=c_u$ and $C_T(\omega_d)=c_d$
    - Nonrandom: $S_0$, $s_u$, $s_d$, $c_u$, $c_d$
- In this model, we can derive the option price $C_0$ using algebra: $C_0 = e^{-rT}(p_uc_u + p_dc_d)$
    - $p_u = \frac{S_0e^{rT}-s_d}{s_u-s_d}$, $p_d = 1-p_u$
    - Special cases: *up-contract* $U$ where $(c_u, c_d) = (1,0)$ (only pays when stock goes up) and *down-contract* $D$ where $(c_u, c_d) = (0,1)$
    - We can decompose the contract into $C_T=c_uU_T + c_dD_T$
    - Can think of the time-0 price as $C_0 = e^{-rT}\mathbb{E}(C_T)$, or $C_0/B_0 = \mathbb{E}(C_T/B_T)$
- **First Fundamental Theorem of Asset Pricing**: No arbitrage exists if and only if that there exists a probability measure $\mathbb{P}$, equivalent to $P$, such that the discounted prices are martingales with respect to $\mathbb{P}$
    - Equivalency: for any event $A$, $\mathbb{P}(A)=0 \iff P(A)=0$
    - Discounted price: price $X$ is divided by bank account price to give $X/B$
    - This means that you can determine the price of an asset by using the discounted expectation of time-$T$ payoffs, solving for an expression for the probability of each state occuring
- A market is **complete** if you can replicate any possible payoff
    - Mathematically, it is complete if a matrix of the vector payoffs spans the entire space
    - Solve by creating an augmented matrix to find the value of the probabilities using the equations $\mathbb{E}(X_T/B_T) = X_0/B_0$ for each asset and $\sum_i p_i = 1$

### Lecture 3

- When you allow intermediate trading, you can replicate more payoffs, and intermediate (multi-period) trading can be defined using stochastic processes
    - Random walk is most popular: $S_n = S_0 + X_1 + \ldots + X_n$
    - *Filtration*: $\mathcal{F}_t$ represents all the information revealed at or before time $t$
    - A stochastic process $Y$ is *adapted* to $\mathcal{F_t}$ if $Y_t$ is $\mathcal{F}_t$-measurable for each $t$
    - $M_t$ is a *martingale* with respect to the filtration if, for all $t$ and all $T$, $\mathbb{E}_tM_T = M_t$
    - A *stopping time* $\tau$ is a random time such that $\{\tau \leq t\} \in \mathcal{F}_t$ for all $t$
        - If $M$ is a martingale and $S\leq T$ are bounded stopping times then $\mathbb{E}_SM_T=M_S$
        - If $S,T$ are unbounded and finite, the optional stopping time theorem applies if $M$ is uniformly integrable
- A trading strategy is a sequence $\Theta_t$ adapted to $\mathcal{F}_t$
    - A strategy is *self-financing* if $\Theta_{t-1}X_t = \Theta_tX_t$, where $X_t$ represents the prices in the market
- Arbitrage in a multi-period model uses the same conditions as the previous definition of arbitrage with the caveat that the strategy must be self-financing

### Lecture 4
- A *Brownian motion* is a stochastic process $W$ where $W_0 = 0$, $W$ has independent, normal increments ($W_t-W_s \sim N(0,t-s)$), and $W$ is continuous in $t$
- An Ito process $X$ is defined as $dX_t = \mu_tdt + \sigma_tdW_t$
    - For each path of $\mu$, we define the Riemann integral $\int_0^T \mu_tdt$ and the Ito integral $\int_0^T \sigma_t dW_t$
    - This means that we can express $X$ as the sum of a constant, a Riemann integral, and an Ito integral: $X_t = X_0 + \int_0^T \mu_tdt + \int_0^T \sigma_t dW_t$
- The Ito integral is a martingale and its expectation is equal to 0
- **Geometric Brownian Motion**: $dX_t = aX_tdt + bX_tdW_t$
    - Used to model stock prices since it tracks percentage returns
    - *Realized variance*: $\frac{1}{T}\sigma^{N-1}_{n=0}\left(\frac{\log\Delta S}{S_{t_n}}\right)^2$
- **Ito's rule**: Given an Ito process $X$ and a sufficiently smooth function $f$, then $f(X_t)$ is an Ito process and $df(X_t) = \frac{\partial f}{\partial x}dX_t + \frac{1}{2}\frac{\partial^2 f}{\partial x^2}(dX_t)^2$
    - For a function with two parameters where $X_t$ and $Y_t$ are Ito processes: $df(X_t, Y_t) = \frac{\partial f}{\partial x}dX_t + \frac{\partial f}{\partial y}dY_t + \frac{1}{2}\frac{\partial^2 f}{\partial x^2}(dX_t)^2 + \frac{1}{2}\frac{\partial^2 f}{\partial y^2}(dY_t)^2 + \frac{\partial^2 f}{\partial x\partial y}(dX_t)(dY_t)$
        - Special case: $df(X_t, t) = \frac{\partial f}{\partial t}dt + \frac{\partial f}{\partial x}dX_t + \frac{1}{2}\frac{\partial^2 f}{\partial x^2}(dX_t)^2$$
- Result: $\log S_t \sim N(log S_0 + (\mu-\sigma^2/2)t, \sigma^2t)$
    - Explicit expression for $S_t$: $S_t = S_0e^{\mu-\sigma^2/2}t + \sigma W_t$

### Lecture 5
- A continuous time strategy is self-financing if $dV_t = \Theta_t \cdot dX_t \iff V_t = V_0 + \int_0^t \Theta_u \cdot dX_u$ 
- Black-Scholes formula: $C(S,t) = S_tN(d_1) - Ke^{-r(T-t)}N(d_2)$, where $d_1=\frac{\ln(S/K)+(r+\sigma^2/2)(T-t)}{\sigma\sqrt{T-t}}, d_2 = d_1 - \sigma\sqrt{T-t}$
- Greeks
    - Delta: $\frac{\partial C}{\partial S} = N(d_1)$
    - Gamma: $\frac{\partial^2 C}{\partial S^2} = \frac{N'(d_1)}{S_t\sigma\sqrt{T-t}}$
    - Theta: $$\frac{\partial C}{\partial t}$
- Call price is lower bounded by $S_t-Ke^{-r(T-t)}$
- Call delta is between 0 and 1, larger around the strike value, gets steeper the lower $T-t$ is
- Call gamma is higher around strike value, resembles dirac delta function as $T-t$ goes to 0; always positive
- Call theta lowest around strike price; lower $T-t$ means smaller tails (OTM and ITM), always negative
- $\Theta + rS\Delta + \frac{1}{2}\Gamma \sigma^2S^2 = rC$
    - If $r=0$, then $\Theta = -\frac{1}{2}\Gamma\sigma^2S^2$

### Lecture 6

- *Girasnov's Theorem*: If $W$ is a Brownian motion under $P$, and if $\mathbb{P}$ is a probability measure on $\mathcal{F}^W_T$ that is equivalent to $P$, then there exists an adapted process $\lambda$ such that for all $t\in[0,T]$, $\tilde{W}_t = W_t + \int_0^t \lambda_s ds$ is a Brownian motion under $\mathbb{P}$
- We can derive the Black-Scholes formula using risk-neutral probabilities via Girasnov's Theorem
    - No arbitrage means that each tradeable asset $X$ has $X/B$ as a martingale, so $dX_t = rX_tdt$ for all $X$
- Black-Scholes formula can be broken down into two parts
    - Probability that the call option finishes in the money: $N(d_2)$, so $e^{-r(T-t)}N(d_2)$ is the time-$t$ price of a $K$-strike $T$-expiry binary call (cash-or-nothing)
    - Share measure that the call expires in the money: $N(d_1)$, so $e^{-r(T-t)}F_tN(d_1)$ is the time-$t$ price of an asset-or-nothing call
- Vega of a call is positive and is larger the further away from maturity the call option is
- Interpretations about formula
    - $N(d_2)$ is the risk neutral probability of $S_T>K$
    - $e^{-r(T-t)}N(d_2)$ is the value of a $K$-strike binary call and is also $-\frac{\partial C}{\partial K}$
    - $-Ke^{-r(T-t)}N(d_2)$ is the value of a vanilla-call replicator's $B$ holdings
    - $N(d_1)$ is the share-measure probability of $S_T > K$; it is the time-$t$ price, in shares, of an asset that pays 1 share if $S_T>K$
        - It is also the delta of a vanilla call
    - $S_tN(d_1)$ is the value of an asset-or-nothing call that pays $S_T\mathbb{I}_{S_T>K}$ as well as the value of the vanilla-call replicator's share holdings
    