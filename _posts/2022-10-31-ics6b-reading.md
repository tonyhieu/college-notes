---
toc: true
layout: post
description: ICS 6B Reading Notes
categories: [ics6b, reading, fall22-23, markdown]
title: ICS 6B Chapter 5
---

## 5.1: An introduction to Boolean algebra
- **Boolean algebra**: a set of rules and operations for working with variables with values of 0 or 1; similar to propositional logic
    - **Boolean multiplication**: Denoted by • and works the same as regular multiplication, logically the same as ∧
        - Table: <img width="187" alt="Screen Shot 2022-10-31 at 8 13 12 AM" src="https://user-images.githubusercontent.com/54915685/199042277-268c2dfb-8382-42e8-94a8-4c3cd3e862ef.png">
    - **Boolean addition**: Denoted by + and works the same as regular addition except 1 + 1 = 1, logically the same as ∨
        - Table: <img width="187" alt="Screen Shot 2022-10-31 at 8 14 51 AM" src="https://user-images.githubusercontent.com/54915685/199042640-f04d0afa-fb2e-46f4-9e00-bd00687c2e60.png">
    - **Complement**: Denoted by an over bar, works the same as the ¬ operator: 0 becomes 1 and 1 becomes 0
- Relates to **digital logic** which is used to create computers
- Variables that have a value of 1 or 0 are called **Boolean variables**, and **Boolean expressions** can be created by using Boolean operations on Boolean variables
- Rules of precedence for boolean operations:
    - Boolean multiplication takes precedence over Boolean addition.
    - The complement operation is applied as soon as the entire expression under the bar is evaluated.
    - Parentheses can be used to override the precedence rules.
- Two Boolean expressions are **equivalent** if, for any combination of values of its variables, they have the same value
    - Laws of Boolean algebra: <img width="445" alt="Screen Shot 2022-10-31 at 8 23 59 AM" src="https://user-images.githubusercontent.com/54915685/199044823-91b1360f-d81d-4f7a-853d-09f878427447.png">

## 5.2: Boolean functions
- Boolean functions map multiple Boolean input values to the set {0, 1}
    - Can be represented by an **input/output table** (similar to a truth table) but is not feasible for larger numbers of inputs, as the outputs are equal to 2<sup>k</sup> where k = the number of inputs
    - Can express functions using Boolean expressions
- Steps to derive a Boolean function via table: <img width="691" alt="Screen Shot 2022-10-31 at 8 32 16 AM" src="https://user-images.githubusercontent.com/54915685/199046727-ba31c7c0-4136-4ac2-84e3-9f0d183fee46.png">
    - **Literal**: One expression that either equals a variable or a variable's complement
    - Must take the **minterm** (a group of literals that make each variable equal 1) of each row that equals 1

## 5.3: Disjunctive and conjunctive normal form
- The **disjunctive normal form (DNF)** is a Boolean expression that is the sum of products of literals
    - Example: <img width="465" alt="Screen Shot 2022-10-31 at 8 41 07 AM" src="https://user-images.githubusercontent.com/54915685/199048748-cf88568c-0ab6-4ec0-8612-5271cf89ec12.png">
- The **conjunctive normal form (DNF)** is a Boolean expression that is the sum of sums of literals
    - Example: <img width="484" alt="Screen Shot 2022-10-31 at 8 42 23 AM" src="https://user-images.githubusercontent.com/54915685/199049022-6153c76c-7c84-4e77-a804-2e553cbd5900.png">

## 5.4: Functional completeness
- A set of operations is **functionally complete** if any Boolean expression can be rewritten using the set
    - {addition, multiplication, complement} is functionally complete
    - {multiplication, complement} is also functionally complete because addition can be rewritten with multiplication: ![Screen Shot 2022-10-31 at 1 37 27 PM](https://user-images.githubusercontent.com/54915685/199105617-5eb13a1e-4958-4e14-9a38-b272c073b9c8.png)
    - {addition, complement} is also functionally complete because multiplication can be rewritten as addition: ![Screen Shot 2022-10-31 at 1 38 23 PM](https://user-images.githubusercontent.com/54915685/199105808-475dc6ed-d99e-4f40-a4dd-7e9a059c510a.png)
- **NAND** operation is denoted by ↑ and returns the complement of Boolean multiplication
- **NOR** operation is denoted by ↓ and returns the complement of Boolean addition
    - Tables for NAND and NOR: ![Screen Shot 2022-10-31 at 1 44 26 PM](https://user-images.githubusercontent.com/54915685/199106889-21388c0a-fda6-44c8-aeaf-ce0af267ee15.png)
- One way to test functional completeness is to start with a known set and try replacing one of the operations with another

## 5.5: Boolean satisfiability
- The **Boolean satisfiability (SAT)** problem asks if a Boolean expression can possibly evaluate to 1
    - If you can set it equal to 1, then it is **satisfiable**; if not, it is **unsatisfiable**
    - A particular set of values **satisfies** a Boolean expression if it makes it equal to 1
    - There is no sufficient, fast method to solve SAT, as you have to check each input
- If an expression is in DNF form, then it is easy to check if the expression is satisfiable
    - Check if one of the literals does NOT contain a variable and its complement
- In the CNF form, it is harder to check if the expression is satisfiable; you must check if each of the constraints equals 1 given a set of input values

## 5.6: Gates and circuits
- Boolean algebra is used to create circuits an electronic devices
    - A circuit built from electrical devices is called a **gate**, and a gate receives an input of Boolean values and returns an output
    - **AND** gates represent Boolean multiplication, **OR** gates represent Boolean addition, and the **inverter** represents the complement ![Screen Shot 2022-10-31 at 2 15 26 PM](https://user-images.githubusercontent.com/54915685/199112051-00eda08d-0db3-46d3-a3d5-5be1b8b6e545.png)
    - Can combine gates together to create complex functions
- This class will focus only on **combinatorial circuits** which do not store variables or loop
    - Combinatorial circuits compute a Boolean function
    - Finding a Boolean function from a circuit: ![Screen Shot 2022-10-31 at 2 18 48 PM](https://user-images.githubusercontent.com/54915685/199112560-5ac7e369-3bba-4d4c-acab-96c1c5d5d7dc.png)