---
layout: post
description: Stats 67
categories: [stats67, lecture, spring22-23, markdown]
title: Intro to Stats
---

- Population: A set of people that you want to study
    - Average represented by μ (quantitative variables)
    - Standard deviation represented by σ (quantitative variables)
    - Proportion represented by p (categorical variables)
- Sample: A group of people taken from the population from which you can make generalizations about the population
    - Average represented by x̄ (quantitative variables)
    - Standard deviation represented by s (quantitative variables)
    - Proportion represented by p̂ (categorical variables)
- R command for standard deviation: sd(c([SET OF DATA]))
- Discrete variables are ones that are **countable**, such as change, where continuous variables are ones with an **infinite range of values**, such as age (cannot count age because you can go infinitely small: 10 years, 2 months, 5 days, 40 seconds, 3 milliseconds, etc.)
- Nominal variables are used to sort things into groups while ordinal variables are used to rank options
- Histograms are used to represent data; variable on x-axis, frequency on the y-axis
    - Example: ![image](https://user-images.githubusercontent.com/54915685/230423372-746ff383-0cd2-437e-8def-e0a50894469b.png)
    - Histograms can take different shapes; symmetric, left/right skewed, peaks
- Bar and whisker plot graph shows IQR, maximum, minimums, and outliers
    - Example: ![image](https://user-images.githubusercontent.com/54915685/230424533-f4b5f4d2-21f1-40fa-b8ed-81b91cae079e.png)
- Points are considered outliers if they are less than Q<sub>1</sub> - 1.5 * IQR or greater than Q<sub>3</sub> + 1.5 * IQR
- Experiments consist of two groups: treatment and control groups
    - Compare data from both groups and see if there is a statistically significant result