---
layout: post
description: FINM 36700
categories: [finm34000, cheatsheets, fall25, markdown]
title: FINM Portfolios
use-math: true
toc: true
---

Course website can be found [here](https://markhendricks.github.io/finm-portfolio/index.html).

## Midterm 1 Cheat Sheet

### Risk and Return Metrics
- **Moments**
    - $\mu = E[r]$
        - $\hat{\mu} = \frac{1}{N}\sum^N_{t=1}r_t$
    - Variance (centered): $\sigma^2 = E[(r-\mu)^2]$
        - $\hat{\sigma} = \frac{1}{N-1}\sum^N_{t=1}(r_t-\hat{\mu})^2$
        - Uncentered: $E(r^2)$, estimate using $\hat{\sigma} = \frac{1}{N-1}\sum^N_{t=1}r_t^2$
    - Skewness (centered and scaled): $\gamma = \frac{1}{\sigma^3}E[(r-\mu)^3]$
        - $\hat{\gamma} = \frac{1}{\hat{\sigma}^3}\frac{1}{N-1}\sum^N_{t=1}(r_t-\mu)^3$
        - Represents tails/asymmetry
    - Kurtosis (centered and scaled): $\kappa = \frac{1}{\sigma^4}E[(r-\mu)^4]$
        - $\hat{\kappa} = \frac{1}{\hat{\sigma}^4}\frac{1}{N-1}\sum^N_{t=1}(r_t-\mu)^4$
        - Represents thickness of tails; normal distribution has kurtosis of 3
    - To annualize moments using some frequency $\tau$, multiply the mean by $\tau$ and the volatility (standard deviation) by $\sqrt{\tau}$
- **Maxmium drawdown**: maximum cumulative loss suffered in a time period; biggest peak-to-trough
- **Covariance**: $\sigma_{i,j}= E[(r_{i,t}-\mu_i)(r_{j,t}-\mu_j)]$
    - Estimator: $\hat{\sigma}_{i,j}= \frac{1}{N}\sum^N_{t=1}(r_{i,t}-\hat{\mu}_i)(r_{j,t}-\hat{\mu}_j)$
    - $K\times K$ covariance matrix: $\Sigma=E[(r-\mu)(r-\mu)']$
        - Estimator: $\hat{\Sigma}=(R-\hat{\mu})(R-\hat{\mu})'\frac{1}{N-K}$
- **Correlation**: $\rho_{i,j} = \frac{\sigma_{i,j}}{\sigma_i\sigma_j}$; represented as a percentage
- **Beta**: For a linear decomposition of $r_i$ on $r_j$ ($r_{i,t}=\alpha + \beta r_{j,t} + \epsilon_t$), the OLS estimator is $\begin{bmatrix}\hat{\alpha}\\ \hat{\beta}\end{bmatrix}= (R_j'R_j)^{-1}R_j'r_i$, where $R_j$ is a $N\times 2$ matrix with a column of ones
    - Beta is also a scaled correlation for single-variable regression: $\beta = \frac{\sigma_i}{\sigma_j}\rho_{i,j}$
    - For multivariate regression, $\begin{bmatrix}\hat{\alpha}\\ \hat{\beta}\end{bmatrix}= (R'R)^{-1}R'r_i$, where $R$ is a matrix where the first column is ones and then each following column is a variable

### Optimizing Risk and Return
- Let $r_f$ be the risk free rate; then the excess return is $\tilde{r}_{i,t}\equiv r_{i,t}-r_f$ or $\tilde{\mu}\equiv \mu-r_f$
- **Alpha**: The excess return against a benchmark; $\tilde{r}_{i,t}=\alpha + \beta \tilde{r}_{\text{SPY},t}+\epsilon_t$
    - Can extend to multiple factors; leads to models like CAPM or Fama-French
- **Sharpe ratio**: Measures tradeoff between excess return against volatility; $\frac{\tilde{\mu}}{\tilde{\sigma}}$
- **Treynor ratio**: Measures tradeoff between excess return and beta; $\frac{\tilde{\mu}}{\beta}$
- **Information ratio**: Measures tradeoff between excess return against unexplained volatility (volatility of error term $\epsilon$); $\frac{\alpha}{\sigma_\epsilon}$
- Portfolio variance is subadditive; the sum of the variance of individual stocks is less than or equal to the variance of the portfolio
- Portfolio mean is additive
- Optimization problem for portfolios: minimize variance and achieve a mean return target
    - Objective function: $\min_w w'\Sigma w$, where $w$ is a vector of weights for assets
    - Constraint function: $w'\tilde{\mu}=m$
    - Solution is $w^* = \delta_m\Sigma^{-1}\tilde{\mu}$
        - All solutions will be a rescaling of $\Sigma^{-1}\tilde{\mu}$, so we define it as the **tangency portfolio** $w^\text{tan} = \delta_\text{tan}\Sigma^{-1}\tilde{\mu}$ whose weights sum to 1
    - Other constraints
        - No cash, weights add to one: $w'\mathbb{1}=1$
        - No short positions: $w_i\geq 0$
        - Hold at least or at most some value: $a\leq w_i\leq b$

### Hedging and Tracking

- Long one unit of asset $i$ and short $h$ units of asset $j$ yields net exposure $\epsilon_t=r_{i,t}-hr_{j,t}$
    - **Basis risk** is the volatility of $\epsilon_t$
    - The **optimal hedge ratio** is given by $h^*=\frac{\sigma_i}{\sigma_j}\rho_{i,j}$
        - Higher correlation means larger hedge
        - Can also be thought of as the beta from $r_{i,t}=\beta_{i,j}r_{j,t} + \varepsilon_t$, so $\beta_{i,j}=h^*$
- With multiple hedges, we can use the regression beta tactic: $r_{i,t} = \beta_{i,1}r_{1,t}+\cdots+\beta_{i,k}r_{k,t}+\varepsilon_t$
    - Adding an intercept isolates the portion of the mean that the hedge cannot replicate
- To get exposure to asset $i$ without market risk $m$, estimate $\tilde{r}_{i,t}=\alpha + \beta_{i,m}\tilde{r}_{m,t}+\varepsilon_t$ and take the positionn $\tilde{r}_{i,t}-\beta_{i,m}\tilde{r}_{m,t}$
- A **tracking** portfolio tries to follow a target factor: $\tilde{r}_{i,t}=\alpha + \beta\tilde{r}_{j,t}+\varepsilon_t$, where $\varepsilon$ is the tracking error and $R^2$ gauges tracking quality
    - $\text{IR}=\alpha/\sigma_\varepsilon$ trades excess mean vs. extra trackinng error

### Value at Risk (VaR)

- **VaR** is a quantile of a distribution; formally defined as the $\tau$-day, $q$ quantile such that $\mathbb{P}\left(\Gamma_{t,t+\tau}\leq\Gamma_t^{\text{VaR}_{q,\tau}}\right)=q$
    - VaR can be interpreted as the expected loss in extreme scenarios; value iis typically negative
- If the returns has a cdf that is continuous and strictly increasing then we can write the VaR as $\Gamma_t^{\text{VaR}_{q,\tau}}=\Phi_\Gamma^{-1}(q)$
- Model VaR using a normal distribution: $r_{t,t+\tau}\sim \mathcal{N}(\mu_\tau, \sigma_\tau^2)$
    - We have $r^{\text{VaR}_{q,\tau}} = \mu_\tau + z_q\sigma_\tau$
    - If prices are lognormal so log returns are normal, then we get the result that the VaR return scales with the square root of the horizon
    - Typically, *VaR compounds with the square root of the horizon*
- **Conditional VaR (CVaR)**: AKA the expected shortfall (ES), the expected value conditional on being less than the VaR threshold
    - For normals: $r^{\text{CVaR}_{q,\tau}} = \mu_{\tau,t} - \frac{\phi_z(z_q)}{q}\sigma_{\tau,t}$
- VaR is not coherent
- To estimate the volatility for the VaR normal distribution, we use the second moment instead of the centered second moment (mean is 0)
- **Volatility estimates**
    - Expanding: $\sigma_t^2 = \frac{1}{t-1}\sum^{t-1}_{i=1}r_i^2$
    - Rolling: $\sigma_t^2 = \frac{1}{m}\sum^{m}_{i=1}r_{t-i}^2$
    - Exponential weighted moving average (EWMA): $\sigma_t^2 = \sum^{N-1}_{i=1}\lambda^{(i-1)}r_{t-i}^2$
    - GARCH: $\sigma_t^2 = \alpha_0 + \gamma_1\sigma^2_{t-1}+\alpha_1r_{t-1}^2$
- Hit test: check q-VaR to see if there really are only q% of days where the return is lower
- Historic Simulation: Use historical data and empirical CDF to calculate VaR and CVaR
    - Has issues with statistical power and dynamics, but CDF can take any shape