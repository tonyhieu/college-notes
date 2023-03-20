---
layout: post
toc: true
description: Principles of Economics Ch. 24
categories: [econ20b, reading, winter22-23, markdown]
title: Measuring the Cost of Living
use-math: true
---

## Chapter 24: Measuring the Cost of Living

### 24-1: The Consumer Price Index

- **Consumer price index (CPI)**: The measure of the overall cost of goods and services bought by a typical consumer

**How The CPI Is Calculated**

- The Bureau of Labor Statistics (BLS) uses a few steps to calculate the CPI

1. *Fix the basket*
    - The prices most important to the typical consumer are taken into account
    - Goods and services that are purchased more are given a greater weight when calculating the CPI
    - Important goods and services found through surveys
2. *Find the prices*
    - Find the prices of the baskets' goods and services at each point in time that you want to caluclate
3. *Compute the basket's cost*
    - Use the data on the prices and multiply each price by the good/service's weight
4. *Choose a base year and compute the index*
    - After choosing a base year, you can calculate the CPI by comparing the price of a basket from the current year to the base year
    - $$ | { \text{CPI} = {\text{Price of basket of goods and services in current year} \over \text{Price of basket in base year}} * 100 } | $$
5. *Compute the inflation rate*
    - Can use the CPI to calculate the **inflation rate** from year to year
    - $$ | { \text{Inflation rate in year 2} = {\text{CPI in year 2 - CPI in year 1} \over \text{CPI in year 1}} * 100 } | $$
- Example of following the steps: ![image](https://user-images.githubusercontent.com/54915685/213329728-bc6f12b1-6042-4648-b0dd-1a3c1710890b.png)
- The CPI is useful to find the cost of living for the average consumer
- The **core CPI** is similar to the CPI except it excludes food and energy, as they have higher volatility
- The **producer price index (PPI)** measures the cost of a basket of goods and services bought by producers rather than consumers
    - Changes in PPI are often thought to be useful to predict changes in CPI

**Problems in Measureing the Cost of Living**

- There are many issues with the CPI that are difficult to solve
- *Substitution Bias*
    - Some prices might rise higher than others, and if said prices become too high, then consumers will substitute those expensive goods and services with cheaper ones
    - Because the goods and services are substituted, the goods and services in the basket change weight drastically, but the base year always uses a fixed basket, so the CPI might not reflect these new changes
- *Introduction of New Goods*
    - If a new good is introduced, then the buying power of a dollar increases
    - Since the basket is fixed to a base year, the new product that is introduced is not included in the basket, and the CPI does not accurately reflect the new change
- *Unmeasured Quality Change*
    - A good or service can increase or decrease in quality without the price of it changing
    - Quality is hard to measure and thus cannot be accurately reflected in the CPI
- The accuracy is extremely important for the government; services such as Social Security give out money based on the CPI
    - Economists argue on how to balance it to make it more accurate

**The GDP Deflator versus the Consumer Price Index**

- The GDP deflator and the CPI both reflect changes in prices, but there are two key differences between them
    - The GDP deflator reflects the prices of all goods and services *produced* domestically while the CPI reflects the prices of all goods and services *purchased by consumers*
        - For instance, if the price of oil increases, then the CPI will rise much more than the GDP deflator
    - The weighting of the GDP deflator and the CPI differs
        - The CPI does not change the goods and services in its fixed basket, but the GDP deflator measures all *currently produced* goods and services so it changes more often

## 24-2: Correcting Economic Variables for the Effects of Inflation

**Dollar Figures from Different Times**
- You can calculate the value of a dollar using the following formula
    - $$ { \text{Amount in today's dollars} = \text{Amount in year T dollars} * {\text{Price level today} \over \text{Price level in year T}} } $$

**Indexation**
- A price that is corrected to reflect inflation is said to be **indexed**, and indexation is typically done through a law or a contract
- Many laws use indexation, such as Social Security

**Real and Nominal Interest Rates**
- An interest rate means that your money increases over time, but the purchasing power of said new dollar is effected by inflation
- If your money increases through an interest rate, it may have less or more purchasing power if the inflation rate is higher than the interest rate
- Two types of interest rates: **nominal interest rate**, which does not correct for the effects of inflation, and **real interest rate**, which does
    - Real interest rate = Nominal interest rate - Inflation rate