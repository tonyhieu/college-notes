---
layout: post
description: Introduction Lecture (kinda bedge)
categories: [ics32a, lecture, fall22-23, markdown]
title: Sept 22 ICS 32A Lecture
---

## Intro to Python
- First 20 minutes - going over data types, errors, zzz
- "Floats represent really big or really small numbers", 64 bit in Python

```
type(type(4)) ==> <class 'type>
```

- // represents integer, or floor, division

```
16 // 5 == 3; 16.0 // 5.0 == 3.0
```

- Precedence and Associativity: Order of operations, PEMDAS
    - Ex. Subtraction is "left associative" meaning that it goes left to right; exponentiation is "right associative"

```
16 - 5 * 3 == 1  # Precedence
16 - 5 - 3 == 8  # Left Associative
2 ** 3 ** 2 == 2^9 == 512  # Right Associative
```

- Statement: Doesn't return anything, changes a variable or any piece of data (such as x = 3)
