---
toc: true
layout: post
description: ICS 6D Chapter 8.5-8.6
categories: [ics6d, reading, winter22-23, markdown]
title: Sequences and Induction Proofs
use-math: true
---

## 8.5: More Inductive Proofs

### Divisibility Proof by Induction

- Proof that attempts to prove the theorem that a number evenly divides some statement
- Example: ![image](https://user-images.githubusercontent.com/54915685/213084466-4a54fb76-dea1-42ab-90f5-bf55d2070ca9.png)

### Using induction to prove an assertion about a recurrence relation

- Induction is useful to prove facts about sequence defined by recurrence relations, as you can define each term as an expression of the previous one
- Can be used to prove explicit formulas as shown below: ![image](https://user-images.githubusercontent.com/54915685/213084690-f0ea55a6-2072-4513-a2f9-1df16e8ca7f9.png)

### More examples

- Proof of closed form for an arithmetic sequence: ![image](https://user-images.githubusercontent.com/54915685/213084800-0b8d7846-8346-4e04-867a-4a61841bc3fe.png)
- Proof of closed form for a geometric sequence: ![image](https://user-images.githubusercontent.com/54915685/213084922-ef9cc517-a2cf-4dc3-bab2-99f967a28ca4.png)
- Proof of the DeMorgan's Law applying to multiple sets: ![image](https://user-images.githubusercontent.com/54915685/213085008-f6a50a78-e5c9-4043-bb6f-0a81a835ec71.png)

## 8.6: Strong induction and well-ordering

- The **principle of strong induction** stipulates that a theorem holds for every value less than or equal to k and attempts to prove that it holds for k+1
    - Weak induction instead states that a theorem holds for k and attempts to prove it holds for k+1
    - Strong induction is better for use in recurrence relations or any proof where multiple previous terms are necessary to prove the theorem
- Example of a proof by strong induction: ![image](https://user-images.githubusercontent.com/54915685/213325497-253ee231-1d96-4572-bdd1-e4c66bf826b5.png)
- Often times, a strong induction will require multiple base cases in order to prove that a theorem holds
    - Figure of the inductive step with multiple base cases: ![image](https://user-images.githubusercontent.com/54915685/213325669-8330f3ba-f618-43ae-8406-8b7986a1d9a8.png)

**More examples of proof by induction**

![image](https://user-images.githubusercontent.com/54915685/213325778-4e57d2b3-9f1f-43ec-a880-c800c00d56a7.png)
![image](https://user-images.githubusercontent.com/54915685/213325804-5c601ac1-46a3-4239-a5cd-b80b2a7c2e6d.png)

**Well-ordering principle**

- The **well-ordering principle** states that a non-empty subset of non-negative integers will always have a smallest element
- Example of a proof using the principle: ![image](https://user-images.githubusercontent.com/54915685/213325944-b801b431-9c55-4ce6-9956-2da295a2c8f9.png)
