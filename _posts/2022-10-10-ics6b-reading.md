---
toc: true
layout: post
description: ICS 6B Reading Notes
categories: [ics6b, reading, fall22-23, markdown]
title: ICS 6B Sections 1.12, 1.13, and all of 2
---

## 1.12: Rules of inference with propositions

- There are rules of inference that can be generally applied to arguments to know if they are valid
    - List of rules: ![Screen Shot 2022-10-10 at 5 32 22 PM](https://user-images.githubusercontent.com/54915685/194972318-9a0f142d-502b-4239-a018-0cf43c82e862.png)

- Proving the validity of an argument using the rules of inference and laws of propositions is called a **logical proof**
    - Each step has different justifications; providing a hypothesis is calleda "hypothesis", and you must state the law/rule if not
    - Example of a logical proof: ![Screen Shot 2022-10-10 at 5 37 07 PM](https://user-images.githubusercontent.com/54915685/194972710-2c6d8378-bae6-4d92-8143-6f39dcf754ab.png)

<mark>STUDY THIS SECTION, Challenge Activity 1.12.1 part 4 is good</mark>

## 1.13: Rules of inference with quantifiers

- To apply a rule of inference to a quantified statement, you must use an **element** in the domain of the statement
    - Elements can be defined in the hypotheses, example below: ![Screen Shot 2022-10-10 at 5 46 50 PM](https://user-images.githubusercontent.com/54915685/194973459-0ecf42a3-8b2c-44f6-8249-88fbe4bf3f84.png)
    - Can use one of two elements in a logical proof
        - **Arbitrary** elements have no special properties other than the fact that they are in the domain
        - **Particular** elements can have properties that aren't shared by others in the domain
    - An element defined in a hypothesis is particular by default and must be labeled as "Hypothesis", while an element defined in the proof is labeled "Element definition"

- Table of rules of inference for quantified statements: ![Screen Shot 2022-10-10 at 5 50 34 PM](https://user-images.githubusercontent.com/54915685/194973808-9eb8bcf3-559c-4bd2-bd4d-04fbe6b01a1d.png)

- A common error is defining the same variable for two different instances of existential instantiation; make sure to mark one variable as C and one as D

<mark>STUDY THIS SECTION, Challenge Activity is good</mark>

## 2.1: Mathematical definitions

- Even integers can be written as 2k; odd ones are written as 2k + 1 (also known as **parity**)
- **Same parity** is if two numbers are both odd or even; if not, they are of **opposite parity**
- Rational numbers are ones where there exists integers x, where y!= 0 and r = x/y
- A number (x) that **divides** another number (y) is one where y % x == 0
    - Denoted as x\|y (x divides y); x is a multiple of y if it divides it
    - Numbers that don't divide are denoted as so: ![Screen Shot 2022-10-10 at 9 20 20 PM](https://user-images.githubusercontent.com/54915685/194996330-5c29427c-87fa-4503-babf-24e2d790f8e3.png)
    - A number that divides another is called a multiple
- Prime numbers and composite numbers (if you don't know this shit ur dumb)
- Inequalities: <, >, =, etc.

## 2.2: Introduction to proofs
- **Theorem**: A statement that can be proven to be true via a **proof**
    - Proofs might use **axioms** which are statements assumed to be true
- Theorems are often rewritten as universally or existentially quantified statements
- **Proof of exhaustion**: A proof that is done by examining every element in a domain
- Proofs involving **universal generalizations** uses a statement to define an arbitrary element
- **Counterexample**: definition of one element in a domain that makes the statement false
- **Existence proofs** show that existential statements are true
    - **Constructive proofs of existence** are the most common, and they provide a specific example in the domain that satisfies the statement
    - **Nonconstructive proofs of existence** provide an example with certain properties that satisfies the statement
    - Disproving existential statements requies DeMorgan's Law and a proof that a negated statement is true
        - Example: ![Screen Shot 2022-10-10 at 9 42 13 PM](https://user-images.githubusercontent.com/54915685/194998828-ad544fce-3aef-4ecf-858b-41b81d2dce92.png)

## 2.3: Best practices and common errors in proofs

Section includes various important factoids to know

![Screen Shot 2022-10-10 at 9 46 21 PM](https://user-images.githubusercontent.com/54915685/194999403-8d11fd69-b124-4609-84d5-985d6f183a20.png)

![Screen Shot 2022-10-10 at 9 46 49 PM](https://user-images.githubusercontent.com/54915685/194999453-19e5de57-f118-43e0-a333-f0024ec9fe66.png)

![Screen Shot 2022-10-10 at 9 47 13 PM](https://user-images.githubusercontent.com/54915685/194999502-26651742-00fe-4c88-8844-4e5800668873.png)

## 2.4: Writing direct proofs

- **Direct proofs**: A hypothesis, p, is assumed to be true and the conclusion, c, is proven due to that assumption (p -> c)

## 2.5: Proof by contrapositive
- **Proof by contrapositive**: A proof of a conditional theorem of the form (p -> c) by proving (!c -> !p)
    - Example of what to do with multiple hypotheses: ![Screen Shot 2022-10-10 at 10 13 06 PM](https://user-images.githubusercontent.com/54915685/195002409-f4216656-60b3-43e4-9952-a845c779254b.png)

## 2.6: Proof by contradiction
- **Proof by contradiction** assumes that the theorem is false and shows a logical inconsistency with such assumption; also called an **indirect proof**
    - Example: ![Screen Shot 2022-10-10 at 10 19 55 PM](https://user-images.githubusercontent.com/54915685/195003266-474bf9e1-9a14-4e0b-8eae-1a6a2375ab0d.png)

## 2.7: Proof by cases
- **Proof by cases**: Separates the domain into separate classes (**cases**) and proves that each class is true
    - Example: ![Screen Shot 2022-10-10 at 10 27 40 PM](https://user-images.githubusercontent.com/54915685/195004117-21074b57-85b0-4f3f-8ede-9663dd5bce0c.png)
- **Without loss of generality** is written to show that one case can apply to all cases
    - Example: ![Screen Shot 2022-10-10 at 10 31 44 PM](https://user-images.githubusercontent.com/54915685/195004644-754087d7-0272-46a7-87ba-f128c0ea7288.png)