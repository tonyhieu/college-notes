---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Determinants/Inverting Matrices
use-math: true
---

## Determinants

$$
A = \begin{pmatrix} a & b \\ c & d\end{pmatrix}, det(A) = ad - bc \text{ (can be generalized to any SQUARE matrix and is also notated as |A|)}\\
\text{Theorem: A is invertible if and only if } det(A) \neq 0 \\
$$

### Examples

$$
\text{If A is a 1 x 1 matrix, then } det(A) = A \text{, such as} det([-7]) = -7 \\
det\begin{pmatrix} 1 & 1 \\ -1 & 1 \end{pmatrix} = 1 * 1 - 1 * (-1) = 2 \\
$$

### Finding the Determinant of a 3 x 3 matrix

$$
det\begin{pmatrix}
    2 & 3 & 0 \\
    2 & 0 & 3 \\
    -1 & 1 & 1
\end{pmatrix}
$$

Step 1: Choose a row OR column (with many zeroes)
- In this example, choose row 1 because it has a 0

Step 2: Construct a sign table, where each sign alternates from the last

$$
\begin{bmatrix}
    + & - & + \\
    - & + & - \\
    + & - & +
\end{bmatrix}
$$

This signifies what we should be doing with our chosen row; we should do +2 * something - 3 * something + 0 * something
- This is why we choose a row with zeroes; makes it easier because we don't need to compute as many terms

Step 3: Cancelling time
- Find the determinants of the elements of the rows/columns that the numbers aren't in

$$ 
2 * det\begin{pmatrix}0 & 3 \\ 1 & 1\end{pmatrix} - 3 * det\begin{pmatrix}2 & 3 \\ -1 & 1\end{pmatrix} + 0 * det\begin{pmatrix}2 & 0 \\ -1 & 1\end{pmatrix} \\
= 2(-3) - 3(5) = -21
$$

### More Examples

$$
det\begin{pmatrix}
    1 & 0 & -1 \\
    3 & 0 & 5 \\
    6 & 9 & 7
\end{pmatrix} =
0 * det\begin{pmatrix} 3 & 6 \\ 6 & 7 \end{pmatrix} - 0 * det\begin{pmatrix} 1 & -1 \\ 6 & 7 \end{pmatrix} + 9 * det\begin{pmatrix} 1 & -1 \\ 3 & 5 \end{pmatrix} \\
= -9(5 + 3) = -72
$$



$$
det\begin{pmatrix}
    1 & 0 & 0 & 0 & 0 \\
    \sqrt{5} & 4 & 0 & 10^{10} & \gamma \\
    \pi & e & 3 & 42 & \pi + e \\
    \lambda & 0 & 0 & 2 & 3 \\
    \pi^e & 0 & 0 & 5 & 7
\end{pmatrix} = 
1 * det\begin{pmatrix}
    4 & 0 & 10^{10} & \gamma \\
    e & 3 & 42 & \pi + e \\
    0 & 0 & 2 & 3 \\
    0 & 0 & 5 & 7
\end{pmatrix} \\ =
1 * 3 * det\begin{pmatrix}
    4 & 10^{10} & \gamma \\
    0 & 2 & 3 \\
    0 & 5 & 7
\end{pmatrix} = 
3 * 4 * det\begin{pmatrix}
    2 & 3 \\
    5 & 7
\end{pmatrix} \\ =
12 * (14 - 15) = -12
$$