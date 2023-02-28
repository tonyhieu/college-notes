---
toc: true
layout: post
description: ICS 6D Chapter 9.1-9.5
categories: [ics6d, reading, winter22-23, markdown]
title: Integer Division and Finding Factors/Multiplies
use-math: true
---

## 9.1: The Division Algorithm

- **Integer division** is division where the input and output must always be integers
    - 9 / 4 returns 2 remainder 1 instead of 2.25
    - Definition of division: ![image](https://user-images.githubusercontent.com/54915685/220762070-53fd66ec-5da6-4be9-ab14-8f8bc6e89df1.png)
- **Linear combination**: The sum of the multiples of two numbers
    - If a number x can divide two numbers y and z, then x can divide any linear combination of y and z
- **The Division Algorithm** defines division and remainders
    - Theorem: ![image](https://user-images.githubusercontent.com/54915685/220762493-9967b5fd-7c8a-473b-b6db-0aef2f777af9.png)
    - Definitions derived: ![image](https://user-images.githubusercontent.com/54915685/220762552-5d2812a8-5bfc-4fa8-ad7f-c2b5bfe27787.png)
    - Note that the Division Algorithm states that applying the modulo operator on negative numbers will never return a negative number; -7 % 4 = 1, not -3

## 9.2: Modular arithmetic

- Mod m can be seen as a function that maps an integer to the target {0, 1, 2, ..., m-1}
    - If we want addition and multiplication functions to return integers in a certain set, then we can use **addition mod m** and **multiplication mod m** (adding and multiplying then applying mod m, respectively) in order to do so
    - The set {0, 1, 2, ..., m-1} along with addition mod m and multiplication mod m creates a closed mathematical system called a **ring**, denoted by Z<sub>m</sub>
    - Z<sub>5</sub> multiplication and addition tables: ![image](https://user-images.githubusercontent.com/54915685/220764218-c6cc46c1-3c93-4ff0-8746-dd56b9ab16e8.png)
- For a fixed m, two integers x and y are **congruent** if x mod m = y mod m
    - This is denoted as $$ {x \equiv y \text{ (mod m)}} $$
    - Can also be defined as m|(x - y), or m evenly divides x - y
- The mod operation has the same precedence as multiplication or division, so 6 * 2 mod 7 = 12 mod 7 = 5
- To compute other arithmetic operations mod m, we can use the following definitions: ![image](https://user-images.githubusercontent.com/54915685/220765979-04af28bf-f400-4a42-ab6a-ad275d4ec868.png)

## 9.3: Prime factorizations

- **The Fundamental Theorem of Arithmetic** states that every positive integer (besides 1) can be uniquely expressed as a product of prime numbers
    - The multiplicity of a prime number in a prime factorization is the number of times p appears in the factorization
        - For example, in 12, 2 has a multiplicity of 2 and 3 has a multiplicity of 1
- The **greatest common divisor (gcd)** of two integers is the greatest integer that divides both of them
- The **least common multiple (lcm)** of two inegers is the smallest positive integer that is a multiple of them
- Two numbers are **relatively prime** if their gcd is 1
- Formulas for finding the GCD and LCM of two integers with known prime factorizations: ![image](https://user-images.githubusercontent.com/54915685/220769856-46bc2d4f-b6f8-4b39-a6c1-5b4d666db756.png)

## 9.4: Factoring and primality testing

- Many ways to find if a number is prime
    - A **brute force algorithm** solves a problem by trying all possible inputs and outputs
- There are an infinite amount of primes, with proof: ![image](https://user-images.githubusercontent.com/54915685/220770379-eae880a1-3178-47cb-b616-59b5df80a0ae.png)
    - **The Prime Number Theorem** stipulates how dense prime numbers are packed among integers: ![image](https://user-images.githubusercontent.com/54915685/220770544-5e6f9f43-801e-41e9-9a39-bc318ad64d5c.png)
    - This theorem can be interpreted as follows: If a random number is randomly selected from 2 to x, then the chance that the number is prime is approximately 1/ln(x)

## 9.5: Greatest common divisor and Euclid's algorithm

- Euclid's algorithm gives a way to recursively calculate the GCD of any two integers
    - Algorithm: gcd(x, y) = gcd(y mod x, x)
    - Written out in code: ![image](https://user-images.githubusercontent.com/54915685/220770981-bdd05d6f-143b-4dae-b773-3036b7c6960a.png)
- The **Extended Euclidean Algorithm** states that gcd(x, y) = sx + ty
- The **multiplicative inverse mod n (AKA inverse mod n)** of an integer x is an integer s such that sx mod n = 1
    - For example, 3 is the inverse of 7 mod 10 because 3 * 7 mod 10 = 21 mod 10 = 1
- This section is something you need to practice; can't really understand off of notes