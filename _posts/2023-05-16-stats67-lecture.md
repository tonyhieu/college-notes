---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Maximum Likelihood Estimator
use-math: true
---

The **Maximum Likelihood Estimator** uses gathered sample data to predict the population parameter or the parameter of the true distribution.

$$
\text{The likelihood function, } L(\theta) \text{ is the product of the pdf evaluated at the data points. Multiply 1 by the pdf at each data point}
$$

## Steps to find the MLE

1. Find L(θ) (also known as the likelihood function)
2. Find ln L(θ)
3. Calculate the Score Function

$$
\frac{\partial ln L(\theta)}{\partial \theta}
$$

4. Find the Score equation by setting the Score Function = 0
5. Solve for the parameter
6. Check that the second derivative of ln L(θ) is negative, that is 

$$
\frac{\partial^2 ln L(\theta)}{\partial \theta^2}
$$

7. Check the support

### Example

$$
f(x_i \sigma) = \frac{1}{2\sigma}e^{-\frac{|x|}{\sigma}} \\
L(\theta) = \prod_{i = 1}^{n} f(x | \theta = \sigma) = \prod_{i = 1}^{n} \frac{1}{2\sigma}e^{-\frac{|x_i|}{\sigma}} \\
L(\theta) = [\frac{1}{2\sigma}e^{-\frac{|x_1|}{\sigma}}] [\frac{1}{2\sigma}e^{-\frac{|x_2|}{\sigma}}] \dots [\frac{1}{2\sigma}e^{-\frac{|x_i|}{\sigma}}] \\
L(\theta) = (\frac{1}{2\sigma})^n e^{-\frac{\sum_{i = 1}^{n} |x_i|}{\sigma}} \\
$$

<hr \>

$$
ln L(\theta) = ln[(\frac{1}{2\sigma})^n e^{-\frac{\sum_{i = 1}^{n} |x_i|}{\sigma}}] \\
ln L(\theta) = ln[(\frac{1}{2\sigma})^n ] + ln[e^{-\frac{\sum_{i = 1}^{n} |x_i|}{\sigma}}] \\
ln L(\theta) = n * ln(1) - n * ln(2) - n * ln(\sigma) + ln[e^{-\frac{\sum_{i = 1}^{n} |x_i|}{\sigma}}] \\
ln L(\theta) = 0 - n * ln(2) - n * ln(\sigma) + e^{-\frac{\sum_{i = 1}^{n} |x_i|}{\sigma}}
$$

<hr \>

The last term is technically sigma to the power of -1, so we can use the power rule on it

$$
Score = \frac{d}{d\theta} \ell(\theta) = \frac{d}{d\sigma} [- n * ln(2) - n * ln(\sigma) + e^{-\frac{\sum_{i = 1}^{n} |x_i|}{\sigma}}] \\
Score = -\frac{n}{\sigma} + \frac{\sum_{i = 1}^{n} |x_i|}{\sigma^2}
$$

Maximums and minimums occur when the score is equal to 0, so we must set the score equal to 0

$$
-\frac{n}{\sigma} + \frac{\sum_{i = 1}^{n} |x_i|}{\sigma^2} = 0 \\
\frac{\sum_{i = 1}^{n} |x_i|}{\sigma^2} = \frac{n}{\sigma} \\
n \sigma = \sum_{i = 1}^{n} |x_i| \\
\sigma = \frac{\sum_{i = 1}^{n} |x_i|}{n}
$$

This is our Maximum Likelihood Estimator; we can estimate sigma by adding all of our data points and dividing by n. However, before doing this, we need to check the concavity to ensure that it really is the <u>maximum</u> likelihood estimator (must be negative).

<hr \>

$$
\frac{d^2}{d^2 \theta} < 0 \rightarrow \frac{d}{d \theta} Score < 0 \\
\frac{d}{d\sigma} [-\frac{n}{\sigma} + \frac{\sum_{i = 1}^{n} |x_i|}{\sigma^2}] = \frac{n}{\sigma^2} - 2\frac{\sum_{i = 1}^{n} |x_i|}{\sigma^3} < 0 \\
\text{We must combine the two fractions together in order to determine whether the term is less than 0} \\
\frac{n}{\sigma^2} - 2\frac{\sum_{i = 1}^{n} |x_i|}{\sigma^3} = \frac{n \sigma}{\sigma^3} - 2\frac{\sum_{i = 1}^{n} |x_i|}{\sigma^3} = 
\frac{n \sigma - 2\sum_{i = 1}^{n} |x_i|}{\sigma^3} \\
\text{Substituting the first derivative into the second derivative:} \\
\frac{n \frac{\sum_{i = 1}^{n} |x_i|}{n} - 2\sum_{i = 1}^{n} |x_i|}{\sigma^3 } = \frac{\sum_{i = 1}^{n} |x_i| - 2\sum_{i = 1}^{n} |x_i|}{\sigma^3 } = -\frac{\sum_{i = 1}^{n} |x_i|}{\sigma^3 } < 0\\
\text{Because the numerator must always be positive (sum of absolute values), the second derivative is therefore always less than 0.}
$$

<hr \>

$$
\text{Final answer: } \hat{\sigma} = \frac{\sum_{i = 1}^{n} |x_i|}{n} \text{ is the MLE of } \sigma
$$