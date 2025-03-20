---
layout: post
description: ECON 123B
categories: [econ123b, lecture, winter25, markdown]
title: Econometrics II
use-math: true
toc: true
---

$$
\text{Linear algebra rules:} \\
(AB)' = B'A' \\
\frac{\partial Az}{\partial z} = A' \\
\frac{\partial z'A}{\partial z} = A \\
$$


## Multivariate Least Squares Derivation 
- $\text{Linear model: } y = X \beta + \epsilon$
- y is n x 1, x is n x k, beta is k x 1, epsilon is n x 1

$$
\min_{\beta} \sum_{i=1}^n (y_i - x_i' \beta)^2 = \min_{\beta} (y-X \beta)'(y-X \beta) \\
\frac{\partial}{\partial \beta} = 0 - X'y - X'y + X'X \beta + X'X \beta \triangleq 0 \\
2X'y = 2X'X \beta \rightarrow X'y = X'X \beta \\
\hat{\beta}_{OLS} = (X'X)^{-1} X'y
$$

- In order to calculate the OLS estimator, X'X must be invertible (full rank)
    - In other words, the rank of X has to be less than the minimum of n and k

### Gauss-Markov Theorem

**Gauss-Markov Theorem**: Under the assumptions of the classical regression model, the OLS estimator is the best (minimum variance) linear unbiased estimator (AKA BLUE)

$$
\text{Proof:}\\
\text{Suppose } \hat{\beta} = Cy \\
\text{If this estimator is unbiased, then } E(\hat{\beta} \vert X) = \beta \\
E(Cy \vert X) = E(CX\beta + C\epsilon \vert X) = CX\beta + CE(\epsilon \vert X) = CX\beta = \beta \\
\text{Thus, } CX = I \\
\text{Let } D = C - (X'X)^{-1}X' \\
DX = CX - (X'X)^{-1}X'X = I - I = 0 \text{ (Optimal when DX = 0)} \\
$$

$$
Var(\hat{\beta} \vert X) = Var(Cy \vert X) \\
= Var[(D + (X'X)^{-1}X')(X\beta + \epsilon) \vert X] \\
= Var[D\epsilon + (X'X)^{-1}X'\epsilon \vert X] \text{ (Since beta is a constant and DX = 0)} \\
= \sigma^2 DD' + \sigma^2 (X'X)^{-1} \\
= \sigma^2 DD' + Var(\hat{\beta}_{OLS} \vert X) \\
\text{Becase } \sigma^2 DD' \text{ is symmetric positive semi-definite, this variance is minimized when } D = 0 \\
\text{Thus, } C = (X'X)^{-1}X' \text{, so } \hat{\beta} = (X'X)^{-1}X'y
$$

### Omitted Variables Bias

$$
\text{True model: }y = X_1 \beta _1 + X_2 \beta _2 + \epsilon\\
\text{Estimated model: }y = X_1 \beta _1 + \epsilon\\ 

\hat{\beta} = (X_1'X_1)^{-1}X_1'y \\
= (X_1'X_1)^{-1}X_1'(X_1 \beta _1 + X_2 \beta _2 + \epsilon) \\
= \beta _1 + (X_1'X_1)^{-1}X_1' X_2 \beta _2 + (X_1'X_1)^{-1}X_1' \epsilon \\
E(\hat{\beta} \vert X) = \beta_1 + (X_1'X_1)^{-1}X_1' X_2 \beta \text{, has bias term} \\
$$

- Bias is 0 if $\beta _2 = 0$ or if $X_1$ and $X_2$ are orthogonal (independent)
- The bias depends on the correlation between the two features; negative bias leads to negative correlation, and vice versa

### Including Irrelevant Covariates

$$
\text{True model: }y = X_1 \beta _1 + \epsilon\\ 
\text{Estimated model: }y = X_1 \beta _1 + X_2 \beta _2 + \epsilon\\
Var(\hat{\beta} \vert X) = \sigma^2 (X'X)^{-1}
$$

- Running a model with more variables then needed will not affect the unbiasedness of the estimator, as the true value of the extra coefficients will go to 0
    - This also increases the variance

### Assumptions for Estimation
1. No micronumerosity (n must be greater than or equal to k)
    - Can solve this by adding more observations or removing parameters
2. No perfect multicollinearity (Columns must be linearly independent and span k dimensions)
    - Fixes: Drop collinear columns, get more data, use ridge regression

### Statistical Properties/Assumptions
1. $ y = X \beta + \epsilon $ is the true model (data generating process)
    - There exist many possible models given a dataset; hard to know if one is actually true
2. $ E(\epsilon \vert X) = 0 $
    - If X is fixed, then this is a harmless assumption as long as X has a constant term
    - If X is random, then we are ruling out endogeneity
3. $Var(\epsilon \vert X) = \sigma ^2 I_n$
    - Homoskedasticity; constant errors
    - No correlation between $\epsilon _i$ and $\epsilon _j$
4. $E(\hat{\beta}_{OLS} \vert X) = \beta$
    
$$
E(\hat{\beta}_{OLS} \vert X) = E((X'X)^{-1}X'y \vert X) \\
= E((X'X)^{-1}X'(X \beta + \epsilon) \vert X) \\
= E((X'X)^{-1}X'X \beta + (X'X)^{-1}X' \epsilon \vert X) \\
= E(\beta \vert X) + E((X'X)^{-1}X' \epsilon \vert X) \\
= \beta
$$

5. $Var(\hat{\beta}_{OLS} \vert X) = \sigma^2 (X'X)^{-1}$
    - $\sigma^2$ can affect the variance; depends on data/observations
    - $(X'X)^{-1}$ affects the variance depending on range; larger range of X means less variance, smaller range means more variance

$$
Var(\hat{\beta}_{OLS} \vert X) = Var((X'X)^{-1}X'y \vert X) \\
= Var((X'X)^{-1}X'(X\beta + \epsilon) \vert X) \\
= Var((X'X)^{-1}X'X\beta + (X'X)^{-1}X'\epsilon \vert X) \\
= Var(\beta + (X'X)^{-1}X'\epsilon \vert X)\\
= Var((X'X)^{-1}X'\epsilon \vert X) \text{ (Variance of a constant, beta, is 0)}\\
= (X'X)^{-1}X' Var(\epsilon \vert X) X(X'X)^{-1} \\
= (X'X)^{-1}X' \sigma^2 X(X'X)^{-1} \\
= \sigma^2 (X'X)^{-1}X'X(X'X)^{-1} \\
= \sigma^2 (X'X)^{-1}
$$

**DERIVATIONS WILL BE ON THE EXAM !**

6. $E(e'e \vert X) = \sigma ^2 [n-k]$

- This means that $s^2 = \frac{e'e}{n-k}$ is an unbiased estimator of $\sigma ^2$

$$
e = y - X \hat{\beta}_{OLS} \\
E(e'e \vert X) = E((y - X \hat{\beta}_{OLS})'(y - X \hat{\beta}_{OLS}) \vert X) \\
= E((y - X (X'X)^{-1} X'y)'(y - X (X'X)^{-1} X'y) \vert X) \\
= E(y'(I - X(X'X)^{-1}X')'(I - X(X'X)^{-1}X')y \vert X) \\
$$

$$
\text{An aside; Is } (I - X(X'X)^{-1}X') \text{ symmetrical?} \\
(I - X(X'X)^{-1}X')' = I - X'(X'X^{-1})X \text{; yes} \\
\text{Is } (I - X(X'X)^{-1}X') \text{ idempotent?} \\
I - X(X'X)^{-1}X' - X(X'X)^{-1}X' + X(X'X)^{-1}X'X(X'X)^{-1}X' \\
= I - X(X'X)^{-1}X' - X(X'X)^{-1}X' + X(X'X)^{-1}X' = I - X(X'X)^{-1}X' \text{; yes}\\
$$

$$
\text{Let } M = (I - X(X'X)^{-1}X') \\
E(y'M'My \vert X) \\
\text{Note: } MX = 0 \text{, so } My = MX \beta + M \epsilon = M \epsilon \\
E(y'M'My \vert X) = E(\epsilon 'M'M \epsilon \vert X) = E(\epsilon 'M\epsilon \vert X) \\
$$

$$
\text{Aside:} \\
Var(\epsilon \vert X) = E[(\epsilon - E(\epsilon))(\epsilon - E(\epsilon))' \vert X] = E(\epsilon \epsilon ' \vert X) \\
\text{Trace operation:} \\
tr(A) = \sum_{i=1}^n a_{ii} \\
tr(ABC) = tr(CAB) = tr(BCA) \text{ (Can put tail matrix at head)}
$$

$$

\epsilon 'M\epsilon \text{ is a scaler, so:} \\
E(\epsilon 'M\epsilon \vert X) = E(tr(\epsilon 'M\epsilon) \vert X) \\
= E(tr(\epsilon\epsilon 'M) \vert X) = tr(E(\epsilon\epsilon 'M) \vert X) \\
= tr(\sigma ^2 M) = \sigma ^2 tr(I - X(X'X)^{-1}X') \\
= \sigma ^2 [tr(I_n) - tr(X(X'X)^{-1}X')] = \sigma^2 [n - tr(X'X(X'X)^{-1})] \\
= \sigma^2 [n - tr(I_k)] = \sigma ^2 [n-k]
$$

## Hypothesis Testing

### Single Parameter Testing
- t distribution is calculated as follows: $t_{df}(0,1) \sim \frac{N(0, 1)}{\sqrt{\chi ^2_{df} / df}}$
$$
\frac{(\hat{\beta}_j - \beta _j) / \sqrt{\sigma ^2 \cdot v_{jj}}}{\sqrt{\frac{s^2(n-k)}{\sigma ^2} / n-k }} \sim t_{df}(0,1) \\
\frac{\hat{\beta}_j - \beta _j}{\sqrt{s^2 \cdot v_{jj}}} \sim t_{df}(0,1) \\
\text{Where } v = (X'X)^{-1} \text{ and } s^2 \text{ is the sample variance}
$$

### Multi Parameter Testing

$$
\frac{\chi ^2_p / p}{\chi ^2_r / r} \sim F_{p,r} \\
\frac{(e_R'e_R - e'e) / q}{e'e / (n-k)} \sim \frac{\chi ^2_q}{\chi ^2_{n-k}} \sim F_{q, n-k} \\
\text{where } e_R \text{ is the residuals from the restricted model and q is the number of restrictions}
$$

## Breaking Assumptions

### Heteroskedasticity

- Instead of $Var(\epsilon \vert X) = \sigma^2 I_n$, we know have $Var(\epsilon \vert X) = \Omega _{\text{n x n}}$, where $\Omega$ is symmetric positive definite
- $E(\hat{\beta}_{OLS}) = \beta$ since the expected value of the errors don't change
- $Var(\hat{\beta}_{OLS}) = (X'X)^{-1}X' \Omega X(X'X)^{-1}$

$$
Var(\hat{\beta}_{OLS} \vert X) = Var((X'X)^{-1}X'y \vert X) \\
= Var((X'X)^{-1}X'(X\beta + \epsilon) \vert X) \\
= Var((X'X)^{-1}X'X\beta + (X'X)^{-1}X'\epsilon \vert X) \\
= Var(\beta + (X'X)^{-1}X'\epsilon \vert X)\\
= Var((X'X)^{-1}X'\epsilon \vert X) \text{ (Variance of a constant, beta, is 0)}\\
= (X'X)^{-1}X' Var(\epsilon \vert X) X(X'X)^{-1} \\
= (X'X)^{-1}X' \Omega X(X'X)^{-1} \\
$$

- $\hat{\beta}_{OLS}$ is inefficient under this assumption, but it is unbiased
- OLS model is equivalent to $y = X \beta + C' \eta$ where $E(\eta \vert X) = 0, Var(\eta \vert X) = I_n$
    - $C'C = \Omega$ where C is the Cholesky factor; C' is lower triangular and C is upper triangular

$$
E[y \vert X, \beta] = E[X \beta + C' \eta \vert X, \beta] \\
= X \beta + E[C' \eta \vert X, \beta] \\
= X \beta + C' E[\eta \vert X, \beta] \\
= X \beta \\
\text{This is the same expectation as the OLS model}
$$

$$
Var[y \vert X, \beta] = Var[X \beta + C' \eta \vert X, \beta] \\
= Var[C' \eta \vert X, \beta] \\
= C' Var[\eta \vert X, \beta] C \\
= C' I_n C \\
= \Omega \\
\text{This is the same variance as the OLS model}
$$

- Multiplying both sides of the new model by $(C')^{-1}$ gives $(C')^{-1}y = (C')^{-1}X \beta + \eta$ which can be written as $y^* = X^* \beta + \eta$
    - Involves data transformation but can now have BLUE estimators with OLS process
- New estimator: $\hat{\beta}_{GLS} = (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}y$
    - Derivation involves the fact that $C'C = \Omega \iff \Omega ^{-1} = C^{-1}(C')^{-1}$

$$
\hat{\beta}_{GLS} = (X^{*T} X^*)^{-1} X^{*T} y^{*} \\
= (((C')^{-1}X)' (C')^{-1}X)^{-1} ((C')^{-1}X)' (C')^{-1}y \\
= (X'(C')^{-1 T} (C')^{-1}X)^{-1} X'C'^{-1 T} (C')^{-1}y \\
= (X'C^{-1} (C')^{-1}X)^{-1} X'C^{-1} (C')^{-1}y \\
= (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}y \\
$$

- Note that the GLS and OLS estimators are equal iff $\Omega = \sigma^2 I_n$

$$
\hat{\beta}_{GLS} = (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}y \\
= (X'(\sigma^2 I_n)^{-1}X)^{-1} X'(\sigma^2 I_n)^{-1}y \\
= (X'\sigma^2 I_n X)^{-1} X'\sigma^2 I_n y \\
= \frac{1}{\sigma ^2} (X'X)^{-1} \sigma ^2 X'y = (X'X)^{-1} X'y = \hat{\beta}_{OLS}
$$

- The GLS estimator is BLUE under heteroskedasticity
    - OLS is not efficient compared to GLS

$$
E[\hat{\beta}_{GLS} \vert X] = E[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}y \vert X] \\
= E[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}(X \beta + \epsilon) \vert X] \\
= E[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}X \beta \vert X] + E[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1} \epsilon \vert X] \\ 
= E[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}X \beta \vert X] \\
= E[\beta \vert X] = \beta
$$

$$
Var[\hat{\beta}_{GLS} \vert X] = Var[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}y \vert X] \\
= Var[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}(X \beta + \epsilon) \vert X] \\
= Var[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}X \beta + (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1} \epsilon \vert X] \\ 
= Var[\beta + (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1} \epsilon \vert X] \\ 
= Var[(X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1} \epsilon \vert X] \\ 
= ((X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}) Var[\epsilon \vert X] ((X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1})' \\
= (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1} \Omega ((X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1})' \\ 
= (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1} \Omega \Omega ^{-1} X (X'\Omega ^{-1}X)^{-1}\\
= (X'\Omega ^{-1}X)^{-1} X'\Omega ^{-1}  X (X'\Omega ^{-1}X)^{-1}\\
= (X'\Omega ^{-1}X)^{-1} \\
$$

- Since $\Omega$ cannot be found in practice, we estimate it and use the (F)easible GLS estimator $\hat{\beta}_{FGLS} = (X'\hat{\Omega} ^{-1}X)^{-1} X'\hat{\Omega} ^{-1}y$
    - Note that $E[\hat{\Omega}] = \Omega$ does not imply that $E[\hat{\Omega} ^{-1}] = \Omega ^{-1}$; 
    - However, $\hat{\Omega}$ IS consistent by Slutsky's Theorem
    - FGLS is biased in small samples, but as the sample size gets larger, it becomes efficient; thus, it is asymptotically efficient

#### Jensen's Inequality

- **Jensen's inequality**: $f(E[X]) \geq E[f(x)] \text{ if f is concave, and } f(E[X]) \leq E[f(x)] \text{ if f is convex}$ 
    - Uses the fact that $E[X] = \overline{X}$ and $E[f(X)] = \overline{f(X)}$; compares $f(\overline{X})$ and $\overline{f(X)}$
- We can use this inequality to show that $\hat{\Omega} \rightarrow \Omega$ and $\hat{\Omega}^{-1} \rightarrow \Omega^{-1}$

#### Estimating Variance

- Model: $y_i = X_i' \beta + \epsilon _i \rightarrow y = X \beta + \epsilon$
- Since the variance is a nonnegative random variable, and we assume that the variance goes up with the values of i, then we can model variance as $ln(\sigma ^2_i) = w_i' \gamma$

Steps to estimate variance (or to test for heteroskedasticity)

1. Regress y on X using OLS
2. Construct the residuals $e = y - X \hat{\beta}_{OLS}$
3. Do one of two regressions to get $\gamma$
    - Regress $e_i^2$ on $w_i$
    - Regress $ln(e_i^2)$ on $w_i$
    - This can be done using $\hat{\gamma} = (\omega ' \omega)^{-1} \omega ' e^2$
    - Final result: $\omega _i' \hat{\gamma} + u_i$
4. Obtain $\hat{\sigma}_i^2 = \omega _i' \hat{\gamma} + u_i$ or $\hat{\sigma}_i^2 = e^{\omega _i' \hat{\gamma}}$
5. Construct $\hat{\Omega}$ using $\hat{\sigma}_i^2$ and apply FGLS

#### Tests for Heteroskedasticity

- [Breusch-Pagan](https://en.wikipedia.org/wiki/Breusch%E2%80%93Pagan_test): Run an OLS, get the residuals, and run OLS on the residuals
    - $\omega _i' \hat{\gamma} + u_i$ can be rewritten as $\gamma_1 + \underline{\omega_{i2}\gamma_2 + ... + \gamma_{iq}\omega_{q}} + u_i$; if the underlined part is nonzero, then we have heteroskedasticity
    - Can test this via an Chi-square with degrees of freedom (q-1)
    - To choose what variables to include in $\omega_i$, take the [Kronecker product](https://en.wikipedia.org/wiki/Kronecker_product) of $x_i$ and remove any duplicate elements
- [Goldfeld-Quandt](https://en.wikipedia.org/wiki/Goldfeld%E2%80%93Quandt_test): Split the data into two regions and check if the variances are different in these two regions
    - Uses an F-test with df $(n_1 - k, n_2 - k)$
    - Reject if F is not inside of the reasible region $(c_L, c_R)$
- White's robust standard errors: Uses the fact that we can consistently estimate $Var(\hat{\beta}_{OLS}) = (X'X)^{-1}X'\Omega X (X'X)^{-1}$ (specifically the $X'\Omega X$ term) by substiuting squared residuals into $\Omega$

### Instrumental Variables and Two-Stage Least Squares (TSLS) Estimation

- Assumption broken: $E(\epsilon \vert X) \neq 0$
- OLS estimator is biased and inconsistent as the number of observations goes to infinity

$$
\begin{align*}
    E[\hat{\beta}_{OLS} \vert X] &= E[(X'X)^{-1}X'y \vert X]\\
    &= E[(X'X)^{-1}X'(X\beta + \varepsilon) \vert X]\\
    &= E[(X'X)^{-1}X'X\beta + (X'X)^{-1}X'\varepsilon \vert X]\\
    &= \beta + (X'X)^{-1}X'E[\varepsilon \vert X]
\end{align*}
$$

- An **instrumental variable** is a variable that directly affects X but does not effect the error terms nor the Y terms
    - In other words, the IV, Z, should be related to the explanatory variables X (informative) and uncorrelated with $\varepsilon$ (valid)
- Can create two equations out of this: $y = X\beta + \varepsilon$ and $X = Z\Pi + v$
    - Estimate $\hat{\Pi} = (Z'Z)^{-1}Z'X$ and let $\hat{X} = Z\hat{\Pi}$
    - Regress $y$ on $\hat{X}$
    - $\hat{\beta}_{2SLS/TSLS/IV} = (\hat{X}'\hat{X})^{-1}\hat{X}'y$

#### Properties of TSLS Estimator

$$
\begin{align*}
    \hat{\beta}_{IV} &= (\hat{X}'\hat{X})^{-1}\hat{X}'y\\
    &= ((Z\hat{\Pi})'(Z\hat{\Pi}))^{-1}\hat{X}'y\\
    &= [(Z(Z'Z)^{-1}Z'X)'(Z(Z'Z)^{-1}Z'X)]^{-1}\hat{X}'y\\
\end{align*}
$$

$$
P_Z = Z(Z'Z)^{-1}Z'\\
P_Z = P_Z'\\
P_Z=P_ZP_Z
P_ZX = \hat{X}
$$

$$
\begin{align*}
    \hat{\beta}_{IV} &= [(Z(Z'Z)^{-1}Z'X)'(Z(Z'Z)^{-1}Z'X)]^{-1}\hat{X}'y\\
    &= [(P_ZX)'(P_ZX)]^{-1}\hat{X}'y\\
    &= [X'P_Z'P_ZX]^{-1}\hat{X}'y\\
    &= [\hat{X}'\hat{X}]^{-1}\hat{X}'y\\
    &= [\hat{X}'X]^{-1}\hat{X}'y\\
    &= [X'\hat{X}]^{-1}\hat{X}'y\\
\end{align*}
$$

$$
\begin{align*}
    \hat{\beta}_{IV} &= [\hat{X}'X]^{-1}\hat{X}'y\\
    &= [\hat{X}'X]^{-1}\hat{X}'(X\beta + \varepsilon) \\
    &= [\hat{X}'X]^{-1}\hat{X}'X\beta + [\hat{X}'X]^{-1}\hat{X}'\varepsilon \\
    &= \beta + [\hat{X}'X]^{-1}\hat{X}'\varepsilon\\
    \plim_{n\rightarrow \infty} \hat{\beta}_{IV} &= \plim_{n\rightarrow \infty}(\beta + [\hat{X}'X]^{-1}\hat{X}'\varepsilon)\\
    &= \beta + \plim_{n\rightarrow \infty}(\left[\frac{\hat{X}'X}{n}\right]^{-1}) \cdot \plim_{n\rightarrow \infty} (\frac{\hat{X}'\varepsilon}{n})
\end{align*}
$$

$$
AsyVar(\hat{\beta}_{IV}\vert X) = \hat{\sigma}^2(\hat{X}'\hat{X})'\\
\hat{\sigma}^2 = \frac{e'e}{n-k}\text{, where } e = y - X\hat{\beta}_{IV} \\
\text{Do NOT use }\hat{X} \text{, as it is not used in the DGP}
$$

$$
\plim_{n\rightarrow \infty}(\left[\frac{\hat{X}'X}{n}\right]^{-1}) \text{ will exist and is non-singular as long as } \hat{X} \text{ and } X \text{ are correlated,}\\
\text{such that } \Pi \neq 0 \text{ i.e. the IV is informative or relevant.}\\
\plim_{n\rightarrow \infty} \frac{\hat{X}'\varepsilon}{n} \text{ will equal 0 as long as } \hat{X} \text{ and } \varepsilon \text{ are uncorrelated, which is implied when}\\
\text{Z is a valid instrument.}\\
\text{Therefore, } \hat{\beta}_{IV} \text{ is a consistent estimator given an appropriate instrument.}
$$

#### Additional Notes

**Restrictions:**
1. Since Z is n by l and X is n by k, l must be greater than or equal to k
    - In other words, there should be at least as many instruments as endogenous covariates
2. $rank(\Pi_{l \times k}) = k$; rank condition
    - Rules out irrelevant covariates, can't be verified until regression is run
3. l must be much lower than n, as $\hat{X}$ should not be close to $X$
    - If $\hat{X}$ is too similar to $X$, then we find that $\hat{X}$ becomes correlated with $\varepsilon$
4. No weak instruments; causes biases to explode
    - One way to test this is to check that the F-statistic ≥ 10
    - $\frac{(e_R'e_R - e'e) / q}{e'e/(n-k)} \sim F_{q, (n-k)}$, where we set the number of restrictions to the number of features, as $e_R'e_R = e'e$ if and only if there is no endogeneity ($E(\varepsilon \vert X) = 0$)

- OLS will be better than IV if there is perfect exogeneity, as IV is more volatile, but if the RHS variables are correlated, then IV will be better

#### Hausman Test for Endogeneity

- Test whether a model as endogeneity or not
- Null: Gauss-Markov assumptions

$$
(\hat{\beta}_{IV} - \hat{\beta}_{OLS})'(AsyVar(\hat{\beta}_{IV}) - AsyVar(\hat{\beta}_{OLS}))^{-1}(\hat{\beta}_{IV} - \hat{\beta}_{OLS}) \sim \chi^2_k
$$

## Maximum Likelihood Estimator

- Given a data generating process (DGP) $y = f(y \vert \Theta)$, we want to find the $\Theta$ that has the maximum likelihood of generating our data $y$
    - $f(y \vert \Theta)$ is known as the *likelihood function*
    - MLE estimator: $\hat{\Theta}_{MLE} = \text{argmax } ln f(y \vert \Theta)$
- We can use the likelihood function to find our coefficients in a linear model
    - Assumes that Y is generated independently using $y_i = x_i'\beta + \epsilon_i$ and $\epsilon \sim N(0, \sigma^2)$; $y_i \sim N(x_i'\beta, \sigma^2)$

$$
\theta = \begin{bmatrix}\beta\\\sigma^2\end{bmatrix}\\
f(y \vert \Theta) = \prod_{i=1}^n f(y_i \vert \Theta)\\
= \prod_{i=1}^n f_N(y_i \vert x_i'\Beta, \sigma^2)\\
= \prod_{i=1}^n (2\pi\sigma^2)^{-1/2}\cdot e^{-\frac{1}{2\sigma^2}(y_i-x_i'\beta)^2}\\
= (2\pi\sigma^2)^{-n/2}\cdot e^{-\frac{1}{2\sigma^2}\sum(y_i-x_i'\beta)^2}\\
= (2\pi\sigma^2)^{-n/2}\cdot e^{-\frac{1}{2\sigma^2}(y-X\beta)'(y-X\beta)}\\
$$

- This technique is more general and works for different DGP setups; e.g. ordinal data

$$
\text{Example Derivation:}\\
ln f(y \vert \Theta) = -\frac{n}{2}ln(2\pi) - \frac{n}{2}ln(\sigma^2) -\frac{1}{2\sigma^2}(y-X\beta)'(y-X\beta) \\
\frac{\partial ln f(y \vert \Theta)}{\beta} = -\frac{1}{2\sigma^2} (-X'y - X'y + (X'X + X'X)\beta) = 0\\
\rightarrow 2X'y = 2X'X\beta \rightarrow \hat{\beta}_{OLS} = (X'X)^{-1}X'y\\
\frac{\partial ln f(y \vert \Theta)}{\sigma^2} = - \frac{n}{2\sigma^2} + \frac{1}{2\sigma^4}(y-X\beta)'(y-X\beta) = 0\\
\rightarrow -n\sigma^2 + (y-X\beta)'(y-X\beta) = 0\\
\rightarrow \hat{\sigma}^2_{MLE} = \frac{(y-X\beta)'(y-X\beta)}{n}
$$

These results suggest that $\hat{\beta}_{OLS} = (X'X)^{-1}X'y$ and $s^2 = \frac{e'e}{n}$
are unbiased.


Another way to express this is that $\hat{\Theta}_{MLE} \sim N(\Theta_0, I(\Theta_0)^{-1})$, where $\Theta_0$ is the true $\Theta$ and $I(\Theta_0)$ is the [Fisher information](https://en.wikipedia.org/wiki/Fisher_information) matrix
- $I(\Theta_0) = - E\left(\frac{\partial^2 ln f(y\vert\Theta)}{\partial \Theta \partial \Theta '}\right) = E\left(\frac{\partial ln f(y\vert\Theta)}{\partial\Theta}\cdot\frac{\partial ln f(y\vert\Theta)}{\partial\Theta}'\right)$
- $asy Var(\hat{\beta}_{MLE}) = - E\left(\frac{\partial^2 ln f(y\vert\beta, \sigma^2)}{\partial \beta \partial \beta '}\right) = \frac{1}{\sigma^2}X'X$
- $asy Var(\hat{\sigma^2}_{MLE}) = - E\left(\frac{\partial^2 ln f(y\vert\beta, \sigma^2)}{\partial \sigma^2 \partial \sigma^{2T}}\right) = \frac{n}{2\sigma^4}$

## Panel Data 

### Fixed Effects
- Model: $y_{it} = x_{it}'\beta + \alpha_i + \varepsilon_{it}$ where i ranges from 1 to n and t ranges from 1 to T<sub>i</sub>
    - If $T_i$ is constant, then we have a *balanced panel*; otherwise, it is an *unbalanced panel*
    - *n should be large, T should be small*
- **Mean differencing**: $$(y_{it} = x_{it}'\beta + \alpha_i + \varepsilon_{it}) - (\bar{y_i} = \bar{x_i}'\beta + \alpha_i + \bar{\varepsilon}_i) \rightarrow {(y_{it} - \bar{y_i}) = (x_{it} - \bar{x_i})'\beta + v_{it}}$$
    - Can be rewritten as an OLS model where $y_{it}^* = x_{it}^{*T}\beta + v_{it}$
- **First differencing**: $$(y_{it} = x_{it}'\beta + \alpha_i + \varepsilon_{it}) - (y_{i,t-1} = x_{i,t-1}'\beta + \alpha_i + \varepsilon_{i,t-1}) \rightarrow {(y_{it} - y_{i,t-1}) = (x_{it} - x_{i,t-1})'\beta + (\varepsilon_{it} - \varepsilon_{i,t-1})}$$
    - Rewritten as $\tilde{y_{it}} = \tilde{x_{it}'} \beta + \eta_{it}$

#### Drawbacks
1. Differencing in general loses data; first-differencing drops n observations, mean-differencing removes degrees of freedom
    - This makes them inefficient
2. Eliminates time-invariant covariates (bad)
3. Only accounts for heterogeneity in intercepts; does not account for heterogeneity in slopes
4. Not applicable in non-linear models

#### Benefits
1. You don't need to make assumptions about $\alpha_i$

### Random Effects

- Model: $y_{it} = x_{it}' \beta + w_{it}'b_i + \epsilon_{it}$
    - $w_{it}\subseteq x_{it}$
    - $b_i \sim N(0, D)$
    - $\varepsilon_i \sim N(0, \sigma^2I_T)$
    - Therefore, $y_i \sim N(X_i\beta, \sigma^2 I_t)$
    - For an individual: $y_i = X_i\beta + W_ib_i + \varepsilon_i$
        - $y_i$ is T by 1, where T is the number of observations available for an individual

Likelihood function: 

$$
\begin{align*}
    f(y \vert \beta, \sigma^2, D) &= \prod_{i=1}^n f(y_i \vert \beta, \sigma^2, D)\\
    &= \prod_{i=1}^n \int f(y_i, b_i \vert \beta, \sigma^2, D) db_i\\
    &= \prod_{i=1}^n \int f_N(y_i \vert X_i\beta + W_ib_i, \sigma^2I_T)f_N(b_i \vert 0, D) db_i\\
    &= \prod_{i=1}^n f_N(y_i \vert X_i\beta, \sigma^2I_t + W_iDW_i')\\
    &= \prod_{i=1}^n (2\pi)^{-T/2} \vert W_iDW_i' + \sigma^2I_T\vert^{-1/2} \exp(-\frac{1}{2}(y_i - X\beta)'(W_iDW_i + \sigma^2 I_T)^{-1}(y_i - X\beta))
\end{align*}
$$

- Can use gradient descent to find the optimal MLE estimator

#### Benefits
1. Asymptotically efficient (because no data is lost)
2. Can draw inferences about the effects of time-invariant covariates
3. Can be employed in non-linear models
4. Can address heterogeneity in both intercepts and slopes

#### Drawbacks
1. Must assume that $b_i \sim N(0,D)$

### Seemingly Unrelated Regression (SUR) Model

- Model: $y_{it} = x_{it}'\beta_i + \varepsilon_{it}$
    - In this case, *n is small while T is large*
- Instead of having models for individuals, we have models for time periods through stacking on time periods
    - $y_t = X_t\beta + \varepsilon_t$
    - $E(\varepsilon_t \vert X_t) = 0$
    - $Var(\varepsilon_t \vert X_t) = \Omega_{n\times n}$ (doesn't vary over time)
- Rewrite the model as $y = X\beta + \varepsilon$, where y is nT by 1 and X is nT by k
$$
E(\varepsilon\vert X) = 0_{nT\times 1}\\
Var(\varepsilon\vert X) = \begin{bmatrix}\Omega_{n\times n} & 0 & 0\\ 0 & \ddots & 0\\ 0 & 0 & \Omega_{n\times n}\end{bmatrix}_{nT\times nT} = \Psi
$$
- We can use GLS now
$$
\hat{\beta}_{GLS} = (X'\Psi^{-1}X)^{-1}X'\Psi^{-1}y = (\sum_{t=1}^T X_t'\Omega^{-1}X_t)^{-1}(\sum_{t=1}^T X_t'\Omega^{-1}y_t)
$$

#### FGLS Estimation

1. Regress the observations for each equation separately by OLS ($i=1,\ldots,n$)
    - Obtain $\hat{\beta}_{OLS}$ for $i=1,\ldots,n$
2. Form residuals $e_t = \begin{pmatrix}e_{1t} & e_{2t} & \ldots & e_{nt}\end{pmatrix}$' for $t=1,\ldots,T$ 

$$
{e_t = y_t -X_t\hat{\beta}_{OLS}} \text{, or} \\
{e_{it} = y_{it}- x_{it}'\hat{\beta}_{i, OLS}}
$$

3. Produce $\hat{\Omega} = \frac{\Sigma e_ie_i'}{T}$

$$
\hat{\beta}_{FGLS} = (X'\hat{\Psi}^{-1}X)^{-1}X'\hat{\Psi}^{-1}y = (\sum_{t=1}^T X_t'\hat{\Omega}^{-1}X_t)^{-1}(\sum_{t=1}^T X_t'\hat{\Omega}^{-1}y_t)
$$

$$
asyVar(\hat{\beta}_{FGLS}\vert X) = (X'\hat{\Psi}^{-1}X)^{-1} = (\sum_{t=1}^T X'_t\hat{\Omega}^{-1}X_t)^{-1}
$$

## Discrete Data Models

- Various different types
    - Binary data: $y_i\in\{0,1\}$
        - Use probit, logit, robit; don't use linear probability model, which is just OLS
    - Ordinal data: $y_i\in\{1,2,\ldots, J\}$, where $1 \leq 2 \leq \ldots \leq J$
        - Use ordinal probit, ordinal logit
    - Count data: $y_i\in \mathbb{Z}^+$
    - Censored data: $y_i\in\{0\}\cup\mathbb{R}^+$, or the data is continuous but there is a point mass at 0
        - Use tobit model
    - Sequential data: ordinal data but with discontinuities (i.e. 11 vs 12 years of education)
- **Heckit Model**: $y_i = x_i'\beta + \varepsilon_i$
    - $y_i$ is only observed when $d_i = 1$, where $d_i\in\{0,1\}$
    - If $d_i = 0$, then $y_i$ is missing
    - AKA Heckman sample selection model


### Binary Data

#### Linear Probability Model
- **Linear probability model**: $Pr(y_i=1\vert x_i) = x_i'\beta$
    - Basic model has issues; heteroskedastic, $Pr(y_i=1\vert x_i)$ might not be between 0 and 1
    - **Three modeling strategy**: Force it so that $0\leq Pr(y_i=1\vert x_i) \leq 1$ by updating our model to $Pr(y_i=1\vert x_i) = F(x_i'\beta)$
        - *Probit*: $Pr(y_i=1\vert x_i) = \Phi(x_i'\beta)$, where $\Phi$ is the Normal CDF
        - *Logit/Logistic Regression*: $Pr(y_i=1\vert x_i) = \frac{\exp(x_i'\beta)}{1+\exp(x_i'\beta)} = \frac{1}{1+\exp(-x_i'\beta)}$
        - *Robit/Robust Regression*: $Pr(y_i=1\vert x_i) = F_{T_\nu}(x_i'\beta)$, where $F_{T_\nu}$ is the CDF of the t distribution with $\nu$ degrees of freedom

#### Latent Utility Framework

- Let $y_i^*\in(-\infty, \infty)$ represent the latent (unobserved) utility
- $y_i^* = x_i'\beta + \varepsilon_i, \varepsilon_i \sim N(0,1)$
- Model two utilities: $u_{i0}$ is the utility from choosing $0$, and $u_{i1}$ is the utility from choosing $1$
    - $u_{i0} = f(x_i'\beta_0) + \eta_{i0}$
    - $u_{i1} = f(x_i'\beta_1) + \eta_{i1}$
    - $y_i^* = u_{i0} - u_{i1} = F(x_i'\beta) + \eta_{i0}-\eta_{i1}$
- If $y_i^* > 0$, then $y_i = 0$; otherwise, $y_i=1$
- Now, we have $Pr(y_i=1\vert x_i) = Pr(y_i^* > 0 \vert x_i) = Pr(\varepsilon_i > -x_i' \beta \vert x_i) = 1-Pr(\varepsilon_i\leq -x_i'\beta\vert x_i) = 1-\Phi(-x_i'\beta) = \Phi(x_i'\beta)$ (Probit model)
    - For different error distributions, we find the different regressions
    - If $\varepsilon_i\sim \mathcal{L}(0,1)$, where $\mathcal{L}$ is a Logit random variable, then we derive the Logit model
    - If $\varepsilon_i\sim t_{\nu}(0,1)$, where $t_{\nu}$ is the t-distribution with $df=\nu$, then we derive the Robit model


#### Estimating Coefficients

Probit:

$$
Pr(y_i=1 \vert x_i) = \Phi(x_i'\beta)\\
f(y_i\vert\beta) = \begin{cases}
    \Phi(x_i'\beta) & y_i=1\\
    1- \Phi(x_i'\beta) & y_i=0
\end{cases} \rightarrow \Phi(x_i'\beta)^{y_i} (1 - \Phi(x_i'\beta))^{1-y_i}\\
\begin{align*}
    f(y\vert\beta) &= \prod^n_{i=1} f(y_i\vert\beta) \\
    &= \prod^n_{i=1} \Phi(x_i'\beta)^{y_i} (1 - \Phi(x_i'\beta))^{1-y_i}\\
    &= \left\{\prod_{i:\text{ } y_i=1} \Phi(x_i'\beta)\right\} \left\{\prod_{i:\text{ } y_i=0}(1 - \Phi(x_i'\beta))\right\}\\
    \mathcal{L}(\beta) &= \sum^n_{i=1}\left[y_i\ln(\Phi(x_i'\beta) + (1-y_i)\ln(1-\Phi(x_i'\beta)))\right]
\end{align*}
$$

- Explaining the MLE derivation will be on the final

### Ordinal Data

- $y_i^* = x_i'\beta + \varepsilon_i, \varepsilon_i\sim N(0,\sigma^2)$
- Since there is an order to the variables, we will divide the CDF into $J$ subsections 
    - Option 1: Set $\sigma^2 = 1$ and set $J-1$ cutpoints (denoted by $\gamma$)
    - Option 2: Let $\sigma^2$ be free and set $J-2$ cutpoints
    - Regardless, we will have a *location restriction* ($E[\varepsilon_i\vert X] = 0$) and a *scale restriction*

$$
\begin{align*}
    Pr(y_i=1) &= Pr(\gamma_0 \leq y_i^* \leq \gamma_1) \\ 
    Pr(y_i=2) &= Pr(\gamma_1 \leq y_i^* \leq \gamma_2) \\
    Pr(y_i=3) &= Pr(\gamma_2 \leq y_i^* \leq \gamma_3) \\
    Pr(y_i=4) &= Pr(\gamma_3 \leq y_i^* \leq \gamma_4) = Pr( y_i^* \leq \gamma_4) - Pr(y_i^*\leq \gamma_3)\\ 
    &\vdots\\
    f(y_i=j\vert x_i) = Pr(y_i=j\vert x_i) &= \Phi(\gamma_{j} - x_i'\beta) - \Phi(\gamma_{j-1} - x_i'\beta)
\end{align*}
$$

- Estimate using MLE
- Define $\gamma_0 = -\infty$ and $\gamma_J = \infty$

$$
\begin{align*}
    f(y_\vert\theta) &= \prod_{i=1}^n f(y_i\vert \beta, \sigma^2, \gamma_1, \ldots, \gamma_{J-1})\\
    &= \prod_{i=1}^n [\Phi(\gamma_{y_i}-x_i'\beta) - \Phi(\gamma_{y_i - 1}-x_i'\beta)]\\
    \mathcal{L}(f(y\vert\theta))&= \sum_{i=1}^n \ln[\Phi(\gamma_{y_i}-x_i'\beta) - \Phi(\gamma_{y_i - 1}-x_i'\beta)]
\end{align*}
$$

### Censored Data Model

- Main model: **Tobit model**

$$
y_i^* = x_i'\beta + \varepsilon_i \text{, where } \varepsilon_i \sim N(0, \sigma^2)\\
y_i^* \sim N(x_i'\beta, \sigma^2)\\
\text{One-sided DGP: } y_i = \begin{cases}
    0, & y_i^* \leq 0\\
    y_i^*, & y_i^* > 0
\end{cases}\\
\text{Two-sided DGP: } 
y_i = \begin{cases}
    l, & y_i^* \leq l\\
    y_i^*, & l < y_i^* < u \\
    u, & y_i^* > u
\end{cases} \\
$$

For the Tobit model, we can use an MLE model:

$$
\begin{align*}
    f(y_i \vert y_i=0) &= Pr(y_i = 0) \\
    &= Pr(y_i^* \leq 0)\\
    &= Pr(x_i'\beta + \varepsilon_i \leq 0)\\
    &= Pr(\frac{\varepsilon_i}{\sigma} \leq -\frac{x_i'\beta}{\sigma})\\
    &= \Phi(-\frac{x_i'\beta}{\sigma})
\end{align*}\\
\begin{align*}
    f(y_i \vert \beta, \sigma^2) &= f_N(y_i^* \vert \beta, \sigma^2)\\
    &= \frac{1}{\sqrt{2\pi\sigma}}\exp(-\frac{(y-x_i'\beta)^2}{2\sigma^2})
\end{align*}\\
\begin{align*}
    f(y\vert\beta, \sigma^2) &= \prod^n_{i=1} f(y_i\vert\beta,\sigma^2)\\
    &= \left\{\prod^n_{i:y_i=0} 1 - \Phi(\frac{x_i'\beta}{\sigma}) \right\} \times \left\{\prod^n_{i:y_i>0} \frac{1}{\sqrt{2\pi\sigma}}\exp(-\frac{(y-x_i'\beta)^2}{2\sigma^2}) \right\}
\end{align*}
$$

### Count Data Model

- Technique: **Poisson regression**

$$
\text{DGP: } y_i \sim Poisson(\lambda_i)\\
Pr(y_i=k) = \frac{e^{-\lambda_i}\lambda_i^{y_i}}{y_i!} = \frac{e^{-\lambda_i}\lambda_i^{k}}{k!}\\
\lambda_i = e^{x_i'\beta}\iff \ln \lambda_i = x_i'\beta\\
\begin{align*}
    \mathcal{L} &= \prod_{i=1}^n f(y_i\vert \lambda_i)\\
    &= \prod_{i=1}^n \frac{e^{-\lambda_i}\lambda_i^{y_i}}{y_i!}\\
    \ln\mathcal{L} &= \sum_{i=1}^n \ln(\frac{e^{-\lambda_i}\lambda_i^{y_i}}{y_i!}) \\
    &= \sum_{i=1}^n \left[-\lambda_i + y_i\ln(\lambda_i) - \ln(y_i!)\right]\\
    &= \sum_{i=1}^n \left[-\exp(x_i'\beta) + y_i(x_i'\beta) - \ln(y_i!)\right]
\end{align*}
$$