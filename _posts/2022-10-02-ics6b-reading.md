---
toc: true
layout: post
description: ICS 6B Reading Notes
categories: [ics6b, reading, fall22-23, markdown]
title: ICS 6B Sections 1.6-1.11
---

## 1.6: Predicates and quantifiers

- **Predicate**: A statement whose truth value depends on one or more variables, even if the outcome is predetermined
    - Represented as a function; "P of x"
    - Ex: "x is an even number" would be true if x = 4, but not if x = 5
    - **Domain**: All of the possible values of x for a predicate
        - "x is an even number" would have a domain of all natural numbers
        - If not apparent from context, should be defined in the predicate
    - Predicates do not have to be strictly mathematical; general statements can be turned into predicates as well
- **Universal quantifier**: A way to turn a predicate into a proposition; denoted by ∀ which reads as "for all"
    - ∀x P(x) reads as "for every x, P(x)" and is a proposition that only returns true if every x in the domain is true
        - ∀x P(x) is a **universally quantified statement**
    ![image](https://user-images.githubusercontent.com/54915685/193474892-483d8db0-1ceb-4329-86f7-3b6758bb99cc.png)
    - Proof showing that a universally quantified statement is true: ![image](https://user-images.githubusercontent.com/54915685/193476215-4460f7a4-b1c3-455e-8a81-ec744c477d1e.png)

    - **Counterexample**: An element in the domain of a universally quantified statement that is false; used to prove that a statement is false

- **Existensial equantifier**: A way to turn a predicate into a proposition; denoted by ∃ which reads as "there exists"
    - ∃x P(x) reads as "there exists an x, such that P(x)" and is a proposition that returns true if *any* x in the domain is true
        - ∃x P(x) is an **existentially quantified statement**
    - **Example**: An element in the domain of a existentially quantified statement that is true; used to prove that a statement is true
    - Proof showing that an existentially quantified statement is false: ![image](https://user-images.githubusercontent.com/54915685/193476249-850607f3-5d88-4c34-9739-25d085cece65.png)

<hr />

## 1.7: Quantified statements

- Can combine **quantifiers** and logical expressions to create **quantified statements**
    - Example: Let P(x) = x is prime and O(x) = x is odd; ∃x (P(x) ∧ ¬O(x)) states that there exists a positive number that is prime and not odd
- A **free variable** is defined as a variable that can be any value in the domain, while a **bound variable** is defined as a variable that is bound to a quantifier
    - x in P(x) is a free variable, while x in ∃x P(x) is a bound variable
    - A statement is a proposition if it contains no free variables
- Can express quantified statements in English
    - Let P(x) = x came to the party and S(x) = x was sick
    - ∃x (S(x) ∨ P(x)) is true because Joe satisfies the proposition: S(Joe) ∨ P(Joe) == True

| Name | S(x) | P(x) |
| --- | --- | --- |
| Joe | F | T |
| Theodore | T | F |
| Gertrude | F | T |
| Samuel | F | F |

<hr />

## 1.8: De Morgan's law for quantified statements

- ¬∀x F(x) can be rewritten as ∃x ¬F(x); AKA <u>¬∀x F(x) ≡ ∃x ¬F(x)</u>
    - Ex: "Not every bird can fly" == "There exists a bird that cannot fly"
- Likewise, ¬∃x F(x) can be rewritten as ∀x ¬F(x); AKA <u>¬∃x F(x) ≡ ∀x ¬F(x)</u>
    - Ex: "There does not exist a bird that can fly" == "Every bird cannot fly"
- When simplifying a quantifier, make sure to use a double negation on it
    - Example: ![image](https://user-images.githubusercontent.com/54915685/193478430-82c5024c-1a34-45ca-beee-bac230a574ed.png)

<hr />

## 1.9: Nested quantifiers

- When there are multiple variables in a predicate, you must use multiple, **nested quantifiers**
    - Examples of nested quantifiers: ![image](https://user-images.githubusercontent.com/54915685/193478540-d8315487-41c7-40ac-a48d-4f29a2695ed5.png)

- Propositions with multiple variables can be thought of as pairs
    - Take ∀x ∀y M(x, y); this proposition is false if there is ANY pair of x, y that does not satisfy M(x, y) (including if x and y are the same)
    - For ∃x ∃y M(x, y), the proposition is false if ALL pairs of x, y are not true for M(x, y) (also including if x and y are the same)

- If a quantified statement has two quantifiers (one existential (∃) and one universal (∀)), it's effective to think of the statement as a **two player game**
    - The existential player (variable) tries to make the expression true, while the universal player (variable) tries to make the expression false
    - The player (variable) on the left goes first, and the next player (variable) tries their best to succeed in their goal
    - Ex: In ∀x ∃y (x + y = 0), x goes first and chooses a random value; y tries its best to set x + y = 0 and is successful because it can always become -x

- DeMorgan's can be applied to nested quantifiers as well; it switches the signs of the quantifier to its opposite

![image](https://user-images.githubusercontent.com/54915685/193479323-38ec0980-5fc9-4e2b-af05-2d0ef69ac869.png)

<hr />

## 1.10: More nested quantified statements

- If you want to express ∀x ∀y without including situations where x == y, then you can write the proposition as ∀x ∀y ((x ≠ y) → M(x, y))
    - If x == y, then x, y cannot be used as a counter example because it's not false
- To express uniqueness, you can use a combination of nested quantifiers and conditionals

![image](https://user-images.githubusercontent.com/54915685/193479698-b47e7ba3-a4eb-46ad-af84-6fe90f4ee520.png)

- You can also move the quantifiers depending on where it is located in the statement

![image](https://user-images.githubusercontent.com/54915685/193480097-a6623048-3678-48d3-b42b-b76b49cf396e.png)

**NOTE TO SELF:** Challenge activity 1.10.1 is good practice

<hr />

## 1.11: Logical reasoning

- **Argument**: A sequence of propsitions (AKA **hypotheses**) that is followed by a final proposition (AKA **conclusion**)
    - **Valid** arguments have true conclusions when all hypotheses are true; **invalid** otherwise
    - ∴ symbol denotes "therefore"
    - Commutative law allows hypotheses to be in any order

    - Ex: These two arguments are the same ![image](https://user-images.githubusercontent.com/54915685/193480793-1d2467fd-8552-431d-a961-5be478c2bd5e.png)
    - Proving an arguments validity via truth table: ![image](https://user-images.githubusercontent.com/54915685/193480861-ab48d867-f833-47ab-b4ca-e016baf8b797.png)

    - You can prove that an argument is invalid by showing an example where the hypotheses are true but the conclusion is not

- An argument's **form** is found by replacing propositions with variables
    - Ex: "It is raining today. + If it is raining today, I will not ride my bike to school. ∴ I will not ride my bike to school." can be replaced with "p + (p --> q) ∴ q"
    - Forms can be useful because it can invalidate an argument with known truth values
        - Ex: ![image](https://user-images.githubusercontent.com/54915685/193481034-8ad0d20f-2c38-493b-9d3a-aef98d0a3082.png)

- If an argument does not have an assignment where the hypotheses are true, then the argument is valid

**NOTE TO SELF:** Challenge activity 1.11.1 is good practice


Questions:

What is the difference between (x != y) -> and (x != y) ^? Is it because ^ is for existentials and -> is for universals?