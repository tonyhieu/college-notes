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
DX = CX - (X'X)^{-1}X' = I - I = 0 \text{ (Optimal when DX = 0)} \\
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

- Instead of $Var(\epsilon \vert X) = \sigma^2 I_n$, we know have $Var(\epsilon \vert X) = \Omega^2_{\text{n x n}}$, where $\Omega$ is symmetric positive definite
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
- Model is equivalent to $y = X \beta + C' \eta$ where $E(\eta \vert X) = u, Var(\eta \vert X) = I_n$
    - $C'C = \Omega$ where C is the Cholesky factor; C' is lower triangular