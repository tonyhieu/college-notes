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
- K increases; K = kEL, so K increases at (n + g)
- Y increases; Y = yEL, so Y increases at (n + g)

Thus, standard of living (K/L) growth improves due to improvements in technology.



### Implications of the Solow Growth Model

- A higher savings rate s implies a higher standard of living
- A higher population growth rate n implies a lower standard of living
- Assumed that g is the same across countries in steady state
- Standard of living grows at rate g in steady state
- GDP (Y) grows at g + n in steady state
- Countries below k* grow more quickly than those at the steady state
- Many of the models grow at the same rate (Y/L and K/L grow at g, for example)
- The real wage grows at the same rate as Y/L over time while real return to capital remains constant


### Human Capital

- The skills of the labor force also matter for production
    - New production function: Y = F(K, H, L), where H represents human capital
    - Now two types of capital: physical capital (k = K/EL) and human capital (h = H/EL)
    - k now depends on two types of saving/investment: investment in physical capital (s<sub>k</sub>) and investment in human capital (s<sub>h</sub>)

### Convergence

- The Solow model predicts that "poor" countries with lower Y/L and K/L should grow more quickly than "rich" ones due to the catch-up effect
    - If this was true, then living standards would converge over time, but there is still a disparity
    - Studies have disproved *unconditional convergence*
- New addendum: The Solow Model predicts *conditional convergence* which is determined by a country's own savings and population growth rates
    - Countries therefore have different steady states

### Government Policies

- According to the Solow Growth Model, the long-run *growth rate* of output per worker is determined by technology growth rate (g)
- The long-run *level* of output per effective worker is determined by savings rate (s), population growth rate (n), and depreciation rate (delta)
    - Encouraging savings (s)
        - Subsidize savings, reduce budget deficits
    - Encourage investment (s<sub>k</sub>)
        - Subsidize (or give tax breaks to) investment
    - Encourage education (s<sub>h</sub>)
        - Subsidize education, give student loans
    - Lower population growth (n)
        - "one child" policy
        - Education leads to lower population growth, especially for girls
    - Promote technology growth
        - Patent protections, subsidize R&D
- Institutions are also important for economic growth and output/worker
    - Property rights, laws, contract enforcement, risk of government confiscation, competitive markets, (reducing) corruption

### Production Function, f

- Technology in advanced countries is assumed to be the same, but there can be differences in the production function f
    - Differences in natural resources, climate, geography, urbanization, regulations, financial markets, competitiveness, efficiency, etc.

### The Golden Rule

- More savings isnt better
    - Higher savings rate s implies higher k and y
    - If savings rate is too high, then people save all of their income; k and y are maximized but consumption is 0
- c = (1-s)f(k) where k is determined by the intersection point of (delta + n + g)k and sf(k)
    - k<sup>*</sup> is determined by s and vice versa
- The k* that maximizes consumption is the one where (delta + n + g)k and f(k) have the same slope; in other words, f'(k) = (delta + n + g)k
    - Can calculate s from there

### Endogenous Technology Growth

- Because so much of growth depends on the growth rate of technology g, there are models that assume g as endogenous
- Romer Model models technology as new varieties of capital goods; the more resources devoted to R&D, the higher g gets
- No endogenous growth model can be proved empirically

### Growth and the IS-MP-AD-IA Model

- Over time, the AD curve shifts to the right because there is more demand (Y, K, C, and I all increase due to population and capital growth)
- The IS curve also shifts to the right over time due to passive growth
    - MP curve shifts down to keep interest rates the same over time

