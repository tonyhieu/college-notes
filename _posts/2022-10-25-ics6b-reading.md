---
toc: true
layout: post
description: ICS 6B Reading Notes
categories: [ics6b, reading, fall22-23, markdown]
title: ICS 6B Chapter 4
---

## 4.1: Definition of functions

- **Function**: Maps elements from one set to another using some sort of operation
    - Can be represented as a set and as a subset of X × Y such that for every x ∈ X, there is exactly one y ∈ Y for which (x, y) ∈ f
    - f: X -> Y is used to show that f is the function that maps set X to Y
    - Set X is the **domain** of the function while set Y is the **target** or **co-domain** of the function
    - "f maps x to y" can be written as (x, y) ∈ f and can also be denoted as f(x) = y
    - If a function maps an element of the domain to either 0 elements or >1 element, then it is not **well-defined**
    - An element is in the **range** of f if there is an x ∈ X such that (x, y) ∈ f
        - Alternate definition: Range of f = { y: (x, y) ∈ f, for some x ∈ X }
- A function that has a finite domain can be shown graphically as an **arrow diagram**
    - Example: ![Screen Shot 2022-10-25 at 4 00 56 PM](https://user-images.githubusercontent.com/54915685/197897879-b2182fed-b7b2-42f6-863c-d80bf727897c.png)
    - Non well-defined function example: ![Screen Shot 2022-10-25 at 4 02 34 PM](https://user-images.githubusercontent.com/54915685/197898062-06a073e5-2aff-4926-b3b4-cfdb1bfd6c3d.png)
- A function definition is incomplete without specifying the domain and target
    - *Correct*: g: R → R, where g(x) = \|x\|
    - *Incorrect*: g(x) = \|x\|

## 4.2: Floor and ceiling functions

- **Floor function**: Function that maps a real number to its closest integer, rounded down
    - Definition: floor: R → Z, where floor(x) = the largest integer y such that y ≤ x.
    - Notated as such: ![Screen Shot 2022-10-25 at 4 10 47 PM](https://user-images.githubusercontent.com/54915685/197898927-7aee5430-d4e5-4e26-9059-d1844d45c189.png)
- **Ceiling function**: Function that maps a real number to its closest integer, rounded down
    - Definition: ceiling: R → Z, where ceiling(x) = the smallest integer y such that x ≤ y.
    - Notated as such: ![Screen Shot 2022-10-25 at 4 11 44 PM](https://user-images.githubusercontent.com/54915685/197899023-e8533cdb-3d46-4db3-91e5-692461d46b17.png)

## 4.3: Properties of functions
- A function is **one-to-one** or **injective** if each value of x maps to a unique value of y
    - x<sub>1</sub> ≠ x<sub>2</sub> implies that f(x<sub>1</sub>) ≠ f(x<sub>2</sub>)
- A function is **onto** or **surjective** if the range of f is equal to its target
    - For every y ∈ Y, there is an x ∈ X such that f(x) = y
- A function is **bijective** if it is both onto and one-to-one
    - Such functions are called **bijections** or **one-to-one correspondences**
- Can infer the sizes, or cardinality, of the domain and target sets depending on the function's properties
    - If f: D → T is onto, then for every element in the target, there is at least one element in the domain: \|D\| ≥ \|T\|.
    - If f: D → T is one-to-one, then every element in the domain maps to a unique element in the target: \|D\| ≤ \|T\|.
    - If f: D → T is a bijection, then f is one-to-one and onto: \|D\| ≤ \|T\| and \|D\| ≥ \|T\|, which implies that \|D\| = \|T\|.
    - Visual: ![Screen Shot 2022-10-25 at 4 20 03 PM](https://user-images.githubusercontent.com/54915685/197899886-226a035c-9126-4be7-a483-715f7eb76e61.png)

<mark>Challenge Activity is good to practice onto vs. one-to-one</mark>

## 4.4: The inverse of a function

- The **inverse** of a function is found by reversing the order of its tuples; that is, f-1 = { (y, x) : (x, y) ∈ f }.
    - Inverses may not be well-defined, so some functions don't have inverses
    - Example: ![Screen Shot 2022-10-25 at 4 26 16 PM](https://user-images.githubusercontent.com/54915685/197900491-362b3bbe-0a31-49b6-9832-2ba400ea9285.png)
    - <u>A function has an inverse if and only if it is a bijection</u>
    - Analytically solving for the inverse of a function with an infinite domain: ![Screen Shot 2022-10-25 at 4 29 49 PM](https://user-images.githubusercontent.com/54915685/197900836-a9e1e365-78c7-4211-bdf7-ca722dd33be7.png)

## 4.5: Composition of functions
- A **composition** of functions is when a function is applied to another function
    - Example: f(g(x)), or (f ο g)(x)
    - Visual example: ![Screen Shot 2022-10-25 at 4 33 41 PM](https://user-images.githubusercontent.com/54915685/197901233-91861044-5f53-4953-aca3-3b5bca309b86.png)
- The **identity function** (denoted by I) takes a set and maps each of its elements onto itself
    - If a function f has an inverse, then f composed with its inverse is an identity function
    - Mathematical definitions:
        - (f o f<sup>-1</sup>)(x) = I<sub>f</sub>
        - Let f: A → B be a bijection. Then f<sup>-1</sup> ο f = I<sub>A</sub> and f ο f<sup>-1</sup> = I<sub>B</sub>.

## 4.6: Logarithms and exponents
- **Exponential** function and **logarithmic** function are featured
    - Properties of exponents: ![Screen Shot 2022-10-25 at 4 41 48 PM](https://user-images.githubusercontent.com/54915685/197902019-7e50bfa6-b032-4156-9b1c-d820a62eae26.png)
    - Properties of logarithms: ![Screen Shot 2022-10-25 at 4 43 16 PM](https://user-images.githubusercontent.com/54915685/197902168-3a731f71-fa21-41f9-8a88-9fbd2f5c77c0.png)
- A function is **strictly increasing** if, for each increasing value of x, f(x) is bigger than the last
    - if whenever x<sub>1</sub> < x<sub>2</sub>, then f(x<sub>1</sub>) < f(x<sub>2</sub>)
- A function is **strictly decreasing** if, for each increasing value of x, f(x) is smaller than the last
    - if whenever x<sub>1</sub> < x<sub>2</sub>, then f(x<sub>1</sub>) > f(x<sub>2</sub>)
- Logarithmic function is strictly increasing