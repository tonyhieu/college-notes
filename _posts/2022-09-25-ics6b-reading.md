---
layout: post
description: ICS 6B Reading Notes
categories: [ics6b, reading, fall22-23, markdown]
title: ICS 6B Sections 1.1-1.5
---

## 1.1: Propositions and logical operations

- **Proposition**: A statement that is either true or false
    - Does not include commands (Shut the door!) or questions (What time is it?)
    - Propositions have a **truth value**, can be either: true, false, unknown, or a matter of opinion

- A **compound proposition** is the combination of propositions using a **logical operator**
    - **∧** represents "and"; p ∧ q is true if both p and q are true
        - AKA <u>conjunction operator</u>
        - Truth table: ![Screen Shot 2022-09-25 at 1 38 32 PM](https://user-images.githubusercontent.com/54915685/192164581-8aba8598-5a40-40e3-b29a-991c2360ddc9.png)

    - **∨** represents "or"; p ∨ q is true if either p or q are true
        - AKA <u>disjunction operator</u>
        - Truth Table: ![Screen Shot 2022-09-25 at 1 41 58 PM](https://user-images.githubusercontent.com/54915685/192164678-3dd82aed-cba3-423f-b7af-d6fa8ba5ecb5.png)
    
    - In English, "or" is typically used to represent "either/or", or <u>exclusive or</u> (represented by ⊕), where both conditions cannot be true at the same time (She is eating or running)
        - ∨ represents <u>inclusive or</u> where both conditions CAN be true at the same time

    - **¬** represents <u>negation</u>, or NOT; ¬True == False and ¬False == True

## 1.2 Evaluating compound propositions

- Compound propositions can have more than one operation
    - Order of operations w/o parantheses: ¬ (not), ∧ (and), ∨ (or)
    - Good practice to use parantheses

- ![Screen Shot 2022-09-25 at 1 58 38 PM](https://user-images.githubusercontent.com/54915685/192165376-5f776dde-786b-42c5-95ec-0d0331e5bd87.png)
    - Truth tables will contain 2<sup>n</sup> rows for n variables(2 options for each variable)
    - Rightmost variable is filled in with TFTF..., leftmost is filled in with TTFF...; T and F alternates based on 2<sup>column number</sup> where rightmost column = 1

- Example of a truth table with intermediate steps: ![Screen Shot 2022-09-25 at 2 01 01 PM](https://user-images.githubusercontent.com/54915685/192165478-8ccceeaf-9062-4ea6-bee1-c0e8754272ce.png)

## 1.3 Conditional statements

- **Conditional operations** are represented with the symbol →
    - p → q is read as "if p then q"
    - Truth table: ![Screen Shot 2022-09-25 at 9 54 46 PM](https://user-images.githubusercontent.com/54915685/192196624-382641a9-8e18-4d3f-a201-a828ea5475ad.png)
    - Think of it as a contract; if condition one is fulfilled, then the second condition <u>HAS</u> to be fulfilled, but if condition one is not fulfilled, then the second condition can either be fulfilled or not.
    - Different ways to express conditional operations: ![Screen Shot 2022-09-25 at 10 01 31 PM](https://user-images.githubusercontent.com/54915685/192197279-6f537ba4-337b-4137-bfdb-b18617de2cda.png)
    - p only if q is also p → q; most confusing one

- Related conditional statements include the contrapositive, converse, and inverse
    - The **converse** of  p → q is q → p
    - The **contrapositive** of p → q is ¬q → ¬p
    - The **inverse** of p → q is ¬p → ¬q
![Screen Shot 2022-09-25 at 10 07 44 PM](https://user-images.githubusercontent.com/54915685/192197923-e9d272ae-0ed0-4c83-b7b6-2e8307b18485.png)

- **Biconditional operations** are represented with ↔
    - p ↔ q stands for "p if and only if q" - AKA true if p == q and false if not
    - If and only if can be represented with <u>iff</u> 

- Conditional and biconditional operations can be used in conjunction with other operations
    - ∧, ∨, and ¬ takes precedence before → or ↔

## 1.4 Logical equivalence

- A **tautology** is a compound proposition that is always true, while a **contradiction** is a compound proposition that is always false
    - p ∨ ¬p is a tautology, while p ∧ ¬p is a contradiction

- **Logical equivalence** means that two compound propositions always return the same value
    - ≡ is used to denote logical equivalence
    - If s ≡ r, then s ↔ r is a tautology, and s ≡ r if and only if r ≡ s
![Screen Shot 2022-09-25 at 11 56 32 PM](https://user-images.githubusercontent.com/54915685/192212413-dc1f1874-9a32-4a19-b59d-1620cd1211f0.png)

- **De Morgan's Laws** are laws that use logical equivalences to show how to distribute negation, or NOT, operations
    - First version of the law: ¬(p ∨ q) ≡ (¬p ∧ ¬q) or !(p or q) == !p and !q
    - Second version of the law: ¬(p ∧ q) ≡ (¬p ∨ ¬q) or !(p and q) == !p or !q

**NOTE TO SELF:** Challenge activity 1.4.1 is a great capstone activity for practice

## 1.5 Laws of propositional logic

- You can substitute a proposition in for another one if both propositions are logically equivalent
    - ex: Because p → q ≡ ¬p ∨ q, (p ∨ r) ∧ **(¬p ∨ q)** ≡ (p ∨ r) ∧ **(p → q)**
    - Useful laws for logical equivalence: ![Screen Shot 2022-09-26 at 12 23 56 AM](https://user-images.githubusercontent.com/54915685/192217023-af49871d-8b47-40c3-8c56-5292817297a2.png)

**NOTE TO SELF:** Challenge activities 1.5.1-1.5.3 are great practice activities