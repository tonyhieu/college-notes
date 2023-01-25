---
toc: true
layout: post
description: ICS 6D Chapter 8.1-8.4
categories: [ics6d, reading, winter22-23, markdown]
title: Sequences and Induction Proofs
---

## 8.1: Sequences

- **Sequences** are a type of function where the domain is a set of consecutive integers (such as 1, 2, 3, 4)
    - A value in a sequence is called a **term**, and its corresponding integer is its **index**
- Sequences with a finite domain are called **finite sequences**, and they have an **initial index** and a **final index** whos corresponding terms are the **initial term** and the **final term**
- **Infinite sequences** have an infinite domain
- Sequences can be specified via an **explicit formula** which shows the value of the term a<sub>k</sub> depending on the value of k
- **Increasing** sequences are ones where consecutive terms increase in value
- **Non-decreasing** sequences are ones where consecutive terms either increase in value or remain the same
- **Decreasing** sequences are ones where consecutive terms decrease in value
- **Non-increasing** sequences are ones where consecutive terms either decrease in value or remain the same
- **Geometric sequences** are sequences where each term after the initial one is found by multiplying the previous term by a fixed, **common ratio**
- **Arithmetic sequences** are sequences where each term after the initial one is found by adding to the previous term by a fixed, **common difference**

## 8.2: Recurrence relations
- A sequence whos rule defines its terms as a function of previous terms is called a **recurrence relation**
    - Recurrence relations can be used to define both arithmetic or geometric sequences (a<sub>n</sub> = a<sub>n-1</sub> + d or * r)
    - The **Fibonacci sequence** is a famous sequence that attempts to predict the number of rabbits after a number of months
- **Dynamical systems** are systems that change over time, and they can often be represented by recurrence relations due to the current state of the system being determined by previous states
    - **Discrete time dynamical systems** are ones where time is divided into time intervals and the state of the system remains the same inside of each interval

## 8.3: Summations

- **Summation notation** is used to represent the sum of terms in a sequence
    - Example: ![image](https://user-images.githubusercontent.com/54915685/212458612-2f501a14-bf53-4614-b1dd-c0455e66fb64.png)
- i represents the **index**, s is the **lower limit**, t is the **upper limit**
- The left side of the equation is the **summation form** and the right side of the equation is the **expanded form**
- Can pull out the last term of a summation by subtracting one from the upper limit and adding it on to the end
    - Example: ![image](https://user-images.githubusercontent.com/54915685/212458714-422011eb-1a40-4a52-9068-288f41d7e885.png)
- Guide on how to change variables in summations: ![image](https://user-images.githubusercontent.com/54915685/212458812-ca4a940b-973c-4c05-bfd7-d91ad7616150.png)
- A **closed form** for a sum is a mathematical expression/formula that represents the sum of a summation notation
    - Arithmetic: ![image](https://user-images.githubusercontent.com/54915685/212458839-6b3530b7-ef49-4aba-b5b9-ef42b60abe32.png)
    - Geometric: ![image](https://user-images.githubusercontent.com/54915685/212458850-83f82d2e-4375-48ce-92c7-ee44406b6354.png)

## 8.4: Mathematical Induction

- Steps to an inductive proof:
    - **Base case**: Prove that the smallest integer/initial term is valid
    - **Inductive step**: prove that if the theorem is true for an element in the domian k, then the theorem holds for k + 1
- The **principle of mathematical induction** states that if the base case (for n = 1) is true and inductive step is true, then the theorem holds for all positive integers. 
- In the inductive step, in the statement that "if S(k) then S(k+1)", the assumption that S(k) is true is the **inductive hypothesis**
- Examples:
![image](https://user-images.githubusercontent.com/54915685/212458975-4818d57a-c503-4e40-a9f2-3f54d56d2577.png)
![image](https://user-images.githubusercontent.com/54915685/212458983-8f865911-e9f4-422a-86f0-d4e2b845a7c2.png)