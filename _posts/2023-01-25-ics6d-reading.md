---
toc: true
layout: post
description: ICS 6D Chapter 8.8-8.11
categories: [ics6d, reading, winter22-23, markdown]
title: Recursion and Structural Induction
use-math: true
---

## 8.8: Recursive definitions

- A **recursive definition** of a function where the output value of a function is based on the outputs of smaller inputs
- **Recrusion** is the process of computing the value of a function using the result of the function on smaller input values
- **Recursively defined sets** are sets which are specified using the following components:
    - **Basis**: Explicitly states that one or more elements are in a set
    - **Recursive rule**: Shows how to build more elements in the set using the existing ones
    - **Exclusion statement**: States that an element is in the set only if it is in the basis or can be created using recursive rules
        - Typically follows the format of "an element is in the set only if it is given in the basis or can be constructed by applying the recursive rules to elements in the basis"
        - Usually left out of recursive definitions
- Examples
    - Binary string: ![image](https://user-images.githubusercontent.com/54915685/214706381-8ad8e7c3-6e07-4ff4-a588-a5277dc634ef.png)
    - Binary trees: ![image](https://user-images.githubusercontent.com/54915685/214706464-e3ee29e4-a1fe-45a5-94b3-a853d5c0b978.png)

## 8.9: Structural induction

- **Structural induction**: a type of induction used to prove thorems about recursively defined sets
- Graphic showing the outline and a proof using structural induction: ![image](https://user-images.githubusercontent.com/54915685/214706621-a8be2bae-3d35-4d5d-b122-42b1f634969a.png)
- Formal examples
    - Balanced parantheses set: ![image](https://user-images.githubusercontent.com/54915685/214706774-e086e8c9-b118-4fcc-a8a4-8cb9ccca45ec.png)
    - Number of vertices in a perfect binary tree: ![image](https://user-images.githubusercontent.com/54915685/214706868-83b53413-3731-4ab3-9466-20d3ba9fefcb.png)


## 8.10: Recursive algorithms
- **Recursive algorithms** are algorithms that call themselves
    - A call that an algorithm makes to itself is called a **recursive call**
- Examples
    - Fibonacci: ![image](https://user-images.githubusercontent.com/54915685/214707090-4d8ad501-9d5f-492a-ad65-a3750c7ac8b2.png)
    - String reversal: ![image](https://user-images.githubusercontent.com/54915685/214707152-d517213a-844f-4a8e-8050-276ea7cbe153.png)

## 8.11: Induction and recursive algorithms
- Induction can also be used to prove theorems about recursive algorithms, such as their accuracy
    - Proof for string reversal: ![image](https://user-images.githubusercontent.com/54915685/214707332-8e0a0d85-e61a-4be1-962f-a9f05496f369.png)
    - Proof for PowerSet function
        - Function: ![image](https://user-images.githubusercontent.com/54915685/214707576-b4528323-a21b-4239-b2d7-6ed319aaae4a.png)
        - Proof: ![image](https://user-images.githubusercontent.com/54915685/214707619-f6128f0a-ce67-4abb-9e91-03e33d1fdf10.png)
