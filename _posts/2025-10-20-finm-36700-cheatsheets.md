---
layout: post
description: FINM 36700
categories: [finm36700, cheatsheets, fall25, markdown]
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


![Image](https://github-production-user-asset-6210df.s3.amazonaws.com/54915685/523954513-7bbf769b-f225-40d7-b032-8b1c14e1714f.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20251208%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20251208T223938Z&X-Amz-Expires=300&X-Amz-Signature=d50a388b537e86de7c03d20a3d1a1fa1dc96b462e49fac10add8b28ef125fed1&X-Amz-SignedHeaders=host)


- **Hedging**: Minimize basis risk between two or more instruments
- **Tracking**: Include intercept, see how well the RHS can replicate the LHS
- **Replication**: Exclude intercept to replicate as best you can the LHS

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

## Midterm 2 Case Studies

### DFA
- Investment philosophy, challenges, market and HML value factor
- Philosophy: market is efficient, so don't stock pick
    - Other two beliefs are that academic research and skilled traders matter, even when strategy is passive
    - Diversification, low turnover, low transaction costs
- Invested in small stocks and had low fees, catered to wealthy indivviduals through registered investment advisors (RIAs) and institutions
    - Rational of buying small stocks (Micro Cap Portfolio) was because academics had found out that small stocks had consistently outperformed large stocks, also captured a part of market that was not traditionally traded (SMB, small minus big)
    - In 1992, Fama and French also found that stocks with high book value to market value outperformed those with a lower ratio (book-to-market effect, value vs. growth) (HML, high minus low)
        - Fama-French Three-Factor model used HML, SMB, and correlation to market risk to explain risk
        - Further research was done to verify these findings in the past as well as internationally; led to DFA offering international funds
- 1980s: recession hit, small stocks not as profitable, DFA in tough spot due to popularity of SnP 500
- 1990s: value stocks continued to do well, but growth stocks skyrocketed due to tech stocks
- Trading strategy to reduce costs and get discounts: buy directly from traders in blocks
- Faced *adverse selection problem* where people only sell things because there is something wrong with them, mitigated by avoiding stocks with expected news or surpirses
- Used various strategies to trade blocks safely and in a manner so as to not drop the stock price
    - Led to overall discounts for purchasing stocks
- Created new tax-managed product that reduced taxes for traders
    - To reduce taxes, they reduced dividend-paying stocks, reduced capital gains, avoided short-term gains, and harvested capital losses

### Smart Beta

- iShares Factor Strategies Group (part of BlackRock) launched new ETFs known as smart beta funds; weighted based on financial characteristics instead of market cap
    - Used four factors: stock market value, relative value, quality of financial position, and momentum
- Fama French showed that the beta factor was not useful for predicting stock returns, smaller firms were more profitable, value firms outperformed growth firms, proftiable firms had better returns (aka quality factor) (RMW, robust minus weak), and firms with more conservative investments did better (CMA, conservative minus aggressive); led to Fama-French 5-factor model
    - Smart beta ETFs use factors like these and are a combination of passive and active investing
- Smart beta ETFs relatively new and not yet widely adopted
- Constructed by using a weighted average of some metric, and each stock has a Z-score that represents its percentile of a certain financial variable
- Factor portfolios were constructed as long-short to avoid correlation with market

### AQR

- Defined momentum as the relative performance compared to other stocks
    - Various theories as to why momentum works: momentum stocks are riskier, investors behave irrationally, sign of underreaction
    - Has empirical evidence to back the factor up, rebalancing winner minus loser portfolios perform well (UMD, up minus down)
- AQR entering the mutual fund market was different than what they were used to; mutual funds are limited in using shorts/leverage, have to deal with traders wanting to liquidate
    - Did empirical research and backtested a momentum index to determine its viability, found that momentum had no correlation with SMB and market rate, making it an attractive product
    - Did not use UMD because mutual funds can't short, instead created three long-only momentum indices for small-cap, large-cap, and international
- Wanted to offer dedicated momentum exposure as a mutual fund which is more liquid than an index
    - Could only invest in stocks with reasonable market cap and liquidity because of mutual fund rules
- Had many sources of tracking error: quarterly rebalancing -> staleness, not trading on boundary means the cutoffs are inaccurate, tax-aware trading, couldn't short

## Midterm 2 Cheat Sheet

### CAPM 
- **CAPM (Capital Asset Pricing Model)**: $E[\tilde{r}^i]=\beta^{i,m}E[\tilde{r}^m]$, where $\beta^{i,m} = \frac{\text{Cov}(\tilde{r}^i, \tilde{r}^m)}{\text{Var}(\tilde{r}^m)}$
- Considers the market portfolio to be the tangency portfolio; in practice, a broad equity index is used to denote the market portfolio's returns
- Claims that the expected return of an asset is based on the risk-free rate and the market riisk premium, $\beta$ is estimated usiing a regression
- Justification: every investor holds a portfolio on the MV frontier, so everyone must hold a combo of the tangency portfolio and the risk-free rate; in aggregate, this means that the market portfolio is the tangency portfolio
    - Other way to think about it: all investors care about mean and variance, so everyone holds MV portfolio
- Applied mostly to equities because of assumed normally distributed and i.i.d. returns
- $\beta$ represents volatility compared to market; positive beta means the asset moves more than the market, negative means the asset moves less
- In CAPM, idiosyncratic risk does not affect return
- Implies that market beta is the only risk that leads to higher average returns, not volatility, skewness, or other covariances
- Using some manipulation, we can see that $\text{SR}_i = \rho_{i,m}\text{SR}_m$, where $\rho_{i,m}=\text{Corr}(\tilde{r}_m, \tilde{r}_i)$
    - Shows that risk premiia are determined only by systematic risk, as idiosyncratic risk will lead to a lower $\rho_{i,m}$
    - Implies that no asset can have a higher Sharpe ratio than the market portfolio

#### Testing CAPM

- $E[\tilde{r}^i]=\beta^{i,m}E[\tilde{r}^m]$ implies that $\tilde{r}^i_t=\beta^{i,m}\tilde{r}^m_t + \varepsilon_t$, where $E[\varepsilon_t]=0$
    - Test CAPM on an asset by running a time series regression: $\tilde{r}^i_t=\alpha^i_t+\beta^{i,m}\tilde{r}^m_t + \varepsilon_t^i$
        - CAPM implies $\alpha^i = 0$
        - Can regress on multiple assets in order to determine multiple alphas, and a joint test should not be able to reject the fact that all alphas are 0
- Historically, CAPM had good performance in tests but with some doubts
    - Roll critique: market return should be return on all assets, not just an equity index
    - Short time series leads to statistical uncertainty
    - One way to test is to use a collection of industry portfolios to capture as much of the market as possible
- Can redefine market risk premium as $\lambda_m = E[\tilde{r}^m]$
    - $\lambda_m$ is the slope of the Security Market Line and represents the amount of risk premium an asset gets per unit of beta
    - Test CAPM using a regression model that finds the value of $\lambda_m$: $E[\tilde{r}^i] = \eta + \beta^{i,m}; \lambda_m + v$
        - CAPM implies that R-squared is 100% and no intercept; in other words, $v=0$ and $\eta=0$
        - Running this test shows that $\lambda_m$ is too small and that the SML lines doesnt start at 0

### Linear Factor Pricing Models (LFPM)

- The **FF3 (Fama-French 3-factor)** model is defined as $E[\tilde{r}^i] = \beta^{i,m}E[\tilde{r}^m] + \beta^{i,s}E[\tilde{r}^s] + \beta^{i,v}E[\tilde{r}^v]$
    - $m$ is the excess market return (same as CAPM), $s$ is the SMB portfolio, and $v$ is the HML, or value minus growth, portfolio
    - Value is defined by the book-to-market ratio, or the market value of an equity divided by its book/balance sheet value
        - Other measures include earnings-price (E/P), EBITDA-price, dividend-price
- Can test LFMs using the same methods as CAPM; time-series test, cross-sectional test, chi-squared test of alphas
    - Can test a factor $z^j$ by calculating the factor MV portfolio and looking at the weight of $z^j$
- There is no evidence of momentum in statistical tests
    - There is small autocorrelation between stocks; can take advantage by buying extreme winners and selling losers or holding a portfolio of both to reduce idiosyncratic risk
    - This autocorrelation leads to a momentum-like effect; can use momentum straategies such as going long on recent winners and shorting recent losers, rebalancing the portfolio as new information comes out
    - Must minimize trading costs; transaction costs and tax burden (capital gains)
    - Possible explanations include underreaction (price needs to go higher) or overreaction (see price go high, pushes hiigher)
    - Momentum is very popular
- The **APT (Arbitrage Pricing Theory)** shows when a Linear Factor Decomposition of return variation implies a Linear Factor Pricing for risk premia
    - Using excess-return faactors $x$ that work well as a LFD, we can run $\tilde{r}^i_t = \alpha^i + (\beta^{i,x})'x_t + \epsilon_t^i$
    - Asssume that residuals are uncorrelated, meaning that factors completely describe comovement
    - Consider an equally weighted portfolio of $n$ returns: $\tilde{r}_t^p = \frac{1}{n}\sum \tilde{r}_t^i$
        - The idiosyncratic risk of $\tilde{r}_t^p$ only depends on residual variances (that are uncorrelated with each other), so $Var(\epsilon^p) = \frac{1}{n}\sigma_\epsilon^2$
        - As $n$ grows, the risk goes to 0, meaning that $\tilde{r}^p$ can be perfectly replicated with factors $x$, and $\alpha^p = 0$
    - This means that a Linear Factor Decomposition with no correlation in its residuals will result in a perfect LFP, as the set of factors explains returns across time and returns across assets
- The **CCAPM (Consumption CAPM)** is an economic model that says the only systematic risk is consumption growth: $E[\tilde{r}^i] = \beta^{i,c}\lambda_c$
    - Must find a good measure for $c$ which is typically a non-traded factor
    - Test by running a time-series regression for each test-security $i$ and then running a cross-sectional regressiion to estimate $\lambda_c$ and $\alpha^i$
    - Instead of consumption, can use other factors like GDP growth, market volatility, etc.
    - Not used so much in industry

### TA Session

- Can think of pricing models as expected returns = prices of aggregate risks ($\lambda$) times risk exposures ($\beta$)
    - A linear factor decomposition (LFD) explains the variance of returns compared to some factors; a factor pricing model is a linear factor model that tries to find a regression where all $\alpha$ are equal to 0 and the factors explain everything
    - Factor test workflow: estimate $\beta$ using time-series regressions, use a cross-sectional regression to estimate $\lambda$, use the $\beta-\lambda$ structure to compute and compare returns
- For Fama-French models: long-short allows you to isolate the characteristic as the sole factor in determining price, reduces multicollinearity, makes tests cleaner
- Momentum strategy construction: Use both winners and losers, use many assets, try to limit transaction costs (less rebalancing, more assets)
    - Skip the most recent month to avoid short-term reversal effects
    - Use broad, liquid universes (industry indices are good to use)


## Final Case Studies

### GMO

- Context: In 2012, GMO was going to update their 7-year forecast and required some analysis
    - Two main factors in analysis: estimate of *equity risk premium* and *expected return in the intermediate term*
    - Important to get forecast accurate
- From 2000-2011, stocks underperformed bonds (negative risk premium) which led to some worrying that the risk premium would cease to exist
    - GMO believed that the risk premium would continue to exist
- GMO's original approach was to invest in unpopular value stocks, began to offer advice on asset allocation and to estimate expected returns
    - Had good track record; predicted 1990s crash, 2008 crash, and 2008 resurgence
    - Clients were mostly large institutional investors
    - Mutual Fund Product: GWMAX
    - Estimated long-run required return on stocks to predict fundamental value and exploited differences between market price and fundamentals
        - Main idea: Forecast intermediate-term returns and see if there are discrepancies between that and the long-run levels, using fine decompositions for every asset class to be as accurate as possible
        - 7-year horizon was perfect for intermediate-term
- Features: Macro data (recession timing), GDP, inflation corporate profits
- GMO also believed that investors suffered from cognitive biases, leading to distortions in price
    - Traders overreact to recent trends
- Kept track of price bubbles and could predict them well
- Better at predicting long-run than short-run due to trader biases causing aberrations and unnecessary risk
- GMO encouraged managers to be conservative most of the time and take big risks when they were confident in a forecast
- Important to keep cash to capitalize on new opportunities
- Asset allocation led to career risk; long-run investment often did not align with client goals, so many managers focus on short-term gains and adding new managers
    - Often led to contrarian positions where GMO was bearish while everyone else was bullish or vice versa
    - Correct predictions often led to clientele leaving before they came true

### LTCM

- LTCM used long-term trading strategies (6 months to 2+ years) and long-term financing to hold against short-term fluctuations
    - Often sold liquidity, buying illiquid assets and selling liquid ones
    - Many employees worked on building software and technologies for financial modeling
    - Investors were mostly financial institutions (e.g. banks) with few wealthy individuals, most were not American
        - International investors could take advantage of less tax
    - Did not get exposed to the stock market, used strategies similar to a capital market intermediary
- Mainly used *convergence* and *relative value* strategies
    - Long and short instruments that are close substitutes with large price gaps
    - Convergence trades referred to trades where there was a guaranteed convergence between instruments (e.g. bonds); relative value trades had no guarantee of convergence
    - Preferred strategies that had little to no default risk
- Swap-spread trades were a key component
    - Couldn't take on arbitrages that had too narrow of a spread due to the financing haircut
    - Potential to profit because of volatility; widening spread = sell early, narrowing spread = stay with the position
    - Made massive profit in 1997 when the swap spread was at a historic low
- Also performed:
    - Fixed-rate residential mortgages (thought mortgage investors weren't sharp)
    - Japanese bond swap spreads
    - Yield-curve relative value trades (abusing the fact that interest rates for some years were higher than they should be)
    - Volatility sales (selling options and hedging the position to only be exposed to vega)
    - Risk arbitrage (sell shares of acquiring company, buy shares of acquired company in merger)
- All positions were self-financing, meaning that the firm had no equity and risk was measured by deviations between long and short
    - Used value-at-risk to determine potential rofits and losses
    - LTCM believed that downside risk lessened as the discrepancies grew larger
    - Analyzed risk over one-year and one-month horizons; long-run risk was determined by changes in fundamental value

## Final Cheat Sheet

### Forecasting Returns

- The **risk premium** of an asset is the expected excess return $\mathbb{E}(\tilde{r}^i)$
    - Linear factor models explain how risk premia vary across assets, like the CAPM
    - These models do not condition on time and are stationary averages
- Some forms believe risk premia to vary over time (hence forecasting returns)
    - This can be expressed as the expectation of the next period's premium given information in this period: $\mathbb{E}_t(\tilde{r}_{t+1}) = f(x_t)$
    - We will specify a linear function so the statistics and computation are easier
- A **forecasting** regression takes the form of $\tilde{r}_{t+1} = \alpha + \beta x_t + \epsilon_{t+1}$
- The classic view (held by the CAPM and other similar models) states that $\beta = 0$ for any forecasting regression and that price growth is a random walk
    - We can test this by autoregressing returns: $\tilde{r}_{t+1} = \alpha + \beta \tilde{r}_t + \epsilon_{t+1}$
    - Empirical evidence shows that the regression coefficient is near 0, so the classic view of premia is true; this month's returns do not predict next months and returns are random
- Instead of setting $x_t = \tilde{r}_t$, we can use other predictors in order to forecast returns as a time series
- The **dividend-yield** $\text{DP}_t$ is a famous signal that refers to the dividend-price ratio $\frac{D_t}{P_t}$
    - Used as a measure of cashflow-to-value
- Stock returns can be expressed in terms of the dividend yield

$$
\begin{align*}
    R_{t+1} &= \frac{P_{t+1} + D_{t+1}}{P_t}\\
    &= \left(\frac{D_t}{P_t}\right)\frac{D_{t+1}}{D_t} + \frac{P_{t+1}}{P_t}\\
    \mathbb{E}_t[R_{t,t+k}] &= \text{DP}_t \mathbb{E}_t \left[\frac{D_{t+k}}{D_t}\right] + \mathbb{E}_t \left[\frac{P_{t+k}}{P_t}\right]
\end{align*}
$$

- In the classic view, since expected returns are constant and price appreciation is a random walk, we can rewrite this as $\theta_r = \text{DP}_t\mathbb{E}_t\left[\frac{D_{t+k}}{D_t}\right] + \theta_p$
    - This means that an increase in the dividend yield is offset by a decrease in expected dividend growth
    - Testing this regression reveals that the classiv view is flawed; in a five-year horizon, the risk premium increases by 20 basis points for every one the dividend-yield increases by 
- This result is only seen in long run regressions because of the persistent nature of $\text{DP}_t$
- Other potential variables include cyclically-adjusted price-earnings ratios, macro-economic indicators (CPI), inflation and rates
- There are some statistical concerns; the DP has high autocorrelation, and highly autocorrelated independent variables can lead to biased regressions

### Mutual Funds

- Lots of research has been done showing that, on average, mutual funds have negative excess returns (and even worse when considering fees)
    - However, mutual funds have shown momentum and highlighted the fact that "loser" funds will do very poorly, and fees and expenses are strongly related to poor performance
    - It is difficult to infer the mean return of any hedge fund due to high volatility and short lifespans
    - 20% of hedge funds go bankrupt annually, and data from hedge funds therefore have survivor bias, backill bias, and incubator bias
- Reported returns from hedge funds might be stale due to the illiquid nature of many of their assets, so market movements might show up in reports months after they happen
    - Stale reports bias the market beta down and hide factor exposure
- Hedge funds often take tail risk (e.g. selling puts that are out of the money)
    - Estimations overestimate excess returns and underestimate risk, leading to this tail risk being especially scary
- Hedge fund facts
    - Legal entities; "investing partnerships"
    - Have relatively few regulations
    - Open only to institutions and large investors
    - Funds are illiquid meaning that investors cannot easily take out all of their money
    - Actively trade and charge fees
    - Four main types: relative value (arbitrage), event-driven, directional, global macro
- Faulty reasons to invest in hedge funds
    - Diversification: Managers extract a large fee, and you can't be more diversified than holding the market portfolio
    - Enhanced return irrespective of market movements: Stale reports, highly leveraged positions, high risk
- Fees are based on assets under managements and investors are actively recruited
    - Some evidence shows that performance will persist between years and there is a momentum effect, but this evidence is not strong and is biased towards surviving funds
    - Most funds will charge a hefty fee on both assets under management and profits
        - This system leads to managers being encouraged to take high risks to extract a maximum fee
        - Skilled allocation should be rewarded, but basic, known strategies can lead to high returns, meaning that investors are essentially paying for a mutual fund
- Human behavior makes funds fragile; low asset value makes investors want to pull out, leading to bank-runs
    - Funds use lockups that restrict withdrawal, must be invested for a certain amount of time before withdrawing money
- Mutual funds are better because they are supposed to track factors and charge low fees while hedge funds are supposed to be creative (but aren't) and charge high fees