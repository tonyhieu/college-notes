---
layout: post
description: Econ 105C
categories: [econ105c, lecture, winter23, markdown]
title: Economic Growth
use-math: true
toc: true
---

In general, the US economy has been growing for (at least) the last 160 years (previously 3.85%/year, slowed down recently). Additionally, GDP per person also grows over time (previously 2.1%/year, slowed down recently). GDP growth typically leads to a massively higher standard of living over time. There are models to project future growth.

## Solow Growth Model

- Used as a basis for all other growth models

### Production Function

- In the Classical Model, K and L are treated as fixed, but in the long run, this is not the case
- In the Solow Growth Model:
    - K is not fixed; investment causes it to grow, depreciation cuases it to shrink
    - L is not fixed; population growth causes it to grow
    - No G or T; excluded for simplicity, but can be included
    - Variables are in per worker terms; uppercase is total, lowercase is per worker (i.e. K is total capital, k is capital per worker)
- **Production function**: Y = F(K, L)
    - Assumed that the function has constant returns to scale

$$
Y = F(K, L) \\
F(zK, zL) = zY \\
y = Y/L, k = K/L \\
F(K / L, 1) = 1 / L \cdot Y \\
y = F(k, 1) \iff y = f(k) \\
Y = C + I \iff y = c + i
$$

### Savings and Investment

- Let s equal the saving rate, or the fraction of income that people save

$$
\frac{S}{L} = \frac{sY}{L} = sy \\
S = sY \\
c = \frac{C}{L} = \frac{Y - S}{L} = y - sy = (1 - s)y \\
\text{From before: } y = c + i \rightarrow i = y - c = y - (1-s)y = sy = s \cdot f(k) \\
i = s \cdot f(k) \text{, implying that savings equals investment}
$$


- Capital wears out over time and depreciates, decreasing capital

$$
\text{Fraction of capital that depreciates: } \delta \\
\text{Total depreciation = } \delta K \\
\text{Depreciation per worker = } \frac{\delta K}{L} = \delta k
$$

- Investment (I, i) makes the capital stock increase

$$
\text{Net change } = \dot{k} = s f(k) - \delta k \\
\dot{k} = \frac{dk}{dt}
$$

### Steady State

The **steady state** is where the economy will tend to stay over time.

$$
\text{Defined as:} \\
\dot{k} = 0 \iff sf(k) = \delta k
$$

Increasing things about savings rate or depreciation rate will change the steady state

### Capital Accumulation

- Savings = Investment; S = sY, I = S
    - This means that I/L = S/L, so i = sy
- Depreciation = deltaK, deltaK/L = deltak
- Stock accumulation (K dot) = sY - deltaK, k dot = sy - delta k

$$

\text{How much investment is required to keep K/L constant?} \\
\frac{d}{dt} (\frac{K}{L}) = 0 \\
\frac{1}{L} (\frac{dk}{dt}) = 0 \\
\frac{1}{L} (sY - \delta K) = 0 \\
sy - \delta k = 0 \rightarrow sy = \delta k \\ 
\delta k \text{ is known as the break-even investment per worker.}

$$

### Population Growth

$$
\text{Assume that the labor force grows at an exogenous rate n.} \\
\dot{L} = nL \\
\frac{\dot{L}}{L} = n \\
$$

With the labor force increasing, break-even investment has to increase.

$$

(\delta + n)k = \text{break-even investment} \\
\delta k \text{ is used to replace capital as it wears out}\\
n k \text{ is used to provie new workers with capital}\\
\text{Derivation:} \\

\frac{d}{dt} (\frac{K}{L}) = 0 \\
\frac{L\frac{dK}{dt} - K \frac{dL}{dt}}{L^2} = 0 \\
L\frac{dK}{dt} - K \frac{dL}{dt} = 0 \\
L(sY - \delta K) - K (nL) = 0 \\

s \frac{Y}{L} - \delta \frac{K}{L} - n \frac{Y}{L} = 0 \\
sy - \delta k - nk = 0 \\
s \cdot f(k) - (\delta + n) k = 0 \\
(\delta + n) k \text{ is the break-even investment per worker when accounting for labor force growth.}

$$

### Production Function

- The Cobb-Douglas production function fits data reasonably well
    - Y = F(K, L) = AK<sup>a</sup>L<sup>b</sup>, where a ~ 1/3 and b ~ 2/3

$$
y = Y / L = \frac{AK^\alpha L^\beta}{L} = A (\frac{K}{L})^\alpha = Ak^\alpha \\
f(k) = A \cdot k^\alpha \\
\text{At steady state:} \\
s \cdot f(k) = (\delta + n)k \\
s \cdot Ak^\alpha = (\delta + n)k \\
k^{1-\alpha} = \frac{A \cdot s}{\delta + n} \\
\text{Thus, increases in } \frac{A \cdot s}{\delta + n} \text{ imply an increase in k.}
$$

Note that the Solow Growth Model has implied that capital per worker does not grow at the steady state and thus output per worker also does not grow at the steady state.
- K increases because L increases; grows at nK
- Y increases because L increases; Y = F(K, L) goes to F((1 + n)K, (1 + n)L) goes to (1 + n)Y

### Technology Growth

- Technology improvements over time means that the production function should also get better over time
- Define a new variable E for labor efficiency
    - Y = F(K, E * L)
    - E * L represents the number of effective efficiency; this means that increases in labor efficiency is analogous with adding workers to the economy
    - E grows at rate G; E dot = gE
- Modify Solow Growth Model notation
    - y = Y / (LE), output per *effective* worker
    - k = K / (LE), capital per *effective* worker

$$
Y = F(K, EL) \\
\frac{1}{EL} = F(\frac{K}{EL}, \frac{EL}{EL}) \\
y = F(k, 1) = f(k) \\
\frac{S}{EL} = \frac{sY}{EL} = sy = s \cdot f(k) \\
I = S \rightarrow i = s \cdot f(k)
$$



$$
\text{How much investment is required to keep K/(EL) constant?} \\
\frac{d}{dt} (\frac{K}{EL}) = 0 \\
\frac{EL \frac{dK}{dt} - KL \frac{dE}{dt} - KE \frac{dL}{dt}}{E^2 L^2} = 0 \\
\frac{1}{EL} \frac{dK}{dt} - \frac{KL}{E^2 L^2} \frac{dE}{dt} - \frac{KE}{E^2 L^2} \frac{dL}{dt} = 0 \\
\frac{1}{EL} (sY - \delta K) - \frac{K}{E^2 L} (gE) - \frac{K}{E L^2} (nL) = 0 \\
sy - \delta k - kg - kn = 0 \\
sy - (\delta + g + n) k = 0 \\
\text{Therefore, the break-even investment per worker is } (\delta + g + n) k \\
$$

According to this new model, capital per effective worker doesn't grow at the steady state, so capital per effective worker also doesn't grow
- K/L increases; K / L = kE, so K/L increases at a rate of g
- Y/L increases; Y / L = yE, so Y/L increases at a rate of g