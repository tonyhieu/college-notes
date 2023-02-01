---
toc: true
layout: post
description: ICS 6D Chapter 10.1-10.4
categories: [ics6d, reading, winter22-23, markdown]
title: Counting and Permutations
use-math: true
---

## 10.1: Sum and Product Rules

- **Counting**: The process of finding the total amount of combinations that something can be

- **The product rule** is one way to count sequences (or combinations)
    - $$ { \text{Let } A_{1}, A_{2}, ..., A_{n} \text{be finite sets. Then, } |A_{1} * A_{2} * ... * A_{n}| = |A_{1}| * |A_{2}| * ... * |A_{n}| } $$
    - Example: ![image](https://user-images.githubusercontent.com/54915685/216173912-72f8c861-4e74-4d5c-afc8-3fe80ed73458.png)
- A set of characters can be called an **alphabet**, and in an alphabet Σ, Σ<sup>n</sup> is the set of all strings of length n that contain characters only from Σ
    - Cardinality of Σ<sup>n</sup>:
    - $$ {|Σ^n| = |Σ * Σ * ... * Σ| = |Σ| * |Σ| * ... * |Σ| = |Σ|^n} $$
- The **sum rule** is used when you can make multiple choices but only one seelection is made
    - $$ { \text{Consider n sets,} A_{1}, A_{2}, ..., A_{n} \text{. If the sets are pairwise disjoint, then} |A_{1}\cup A_{2}\cup ...\cup A_{n}| = |A_{1}| + |A_{2}| + ... + |A_{n}|} $$

## 10.2: The bijection rule

- The **bijection rule** states that if there is a bijection from one set to another, then they have the same cardinality
    - A function that maps one set A to another set B is called a **bijection** if and only if it has a well defined inverse, where the **inverse** is a function that maps set B to set A
    - This rule can be applied to map a power set to different strings: ![image](https://user-images.githubusercontent.com/54915685/216175970-035eace8-47c9-4270-abb3-99cf24d93d6f.png)
- The **k-to-1** rule applies for functions that map a set A to another set B such that, for every element in A, there are exactly k different elements in B that it maps to
    - Thus, |A| = |B|/k

## 10.3: The generalized product rule

- **The generalized product rule** states that, when selecting an item from a set, if the number of choices at each step does not depend on the previous choices, then the number of combinations is the product of the number of choices in each step
    - Definition: ![image](https://user-images.githubusercontent.com/54915685/216176485-80af8cb0-35b1-4b9f-a028-0bcdec8f04ef.png)

## 10.4: Counting permutations

- An **r-permutation** is a sequence of r items with no repetitions, all taken from the same set
    - Order matters in sequences, so {A, B, C} is different than {B, C, A}; both are 3-permutations
    - Formula for number of r-permutations: ![image](https://user-images.githubusercontent.com/54915685/216176803-57003960-874d-470b-b232-68d855548d12.png)
- A **permutation** is a sequence that contains every element of a set exactly once
    - Formula for number of permutations of a set with n elements:
    - $$ {P(n, n) = n * (n-1) * ... * 2 * 1 = n!} $$