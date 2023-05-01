---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Matrix Multiplication and Operations
use-math: true
---

To recap: a linear transformation is also known as a function that maps vectors to other vectors, and matrices can be thought of as linear transformations and coordinates

Matrix operations should coordinate with operations on Linear Transformations

| Matrix operations | Operations on Linear Transformations |
| --- | --- |
| Scalar multiplication | Scalar multiplication |
| Addition/subtraction | Addition/substraction |
| Multiplication of Matricies | Function composition |
| Vector multiplication | Functions |

A linear transformation that maps a vector space onto itself must be represented by a square matrix

In matrix multiplication, and linear transformations in general, the order in which you do things matters because you can get different results

## Matrix operations
Matrix addition is well defined when A and B have the same dimensions. Addition can be defined as (A + B)<sub>ij</sub> = A<sub>ij</sub> + B<sub>ij</sub>

Matrix addition is well defined when the number of columns in B is equal to the number of rows in A

### Examples

$$
\text{Addition (and subtraction): }
\begin{pmatrix}
    1 & 2\\
    3 & 1
\end{pmatrix} + 
\begin{pmatrix}
    -1 & 4\\
    3 & 0
\end{pmatrix} = 
\begin{pmatrix}
    0 & 6\\
    6 & 1
\end{pmatrix} \\

\text{Multiplication: }

\begin{pmatrix}
    -1 & 2 & 1 & 0\\
    6 & -4 & 3 & 1
\end{pmatrix}
\begin{pmatrix}
    6 & 2 \\
    -7 & 5 \\
    -1 & -3 \\
    2 & -1
\end{pmatrix} =
\begin{pmatrix}
    6(-1) - 7(2) - 1(1) + 2(0) & 2(-1) + 5(2)  - 3(1) - 1(0) \\ 
    6(6) - 7(-4) - 1(3) + 2(1) & 2(6) + 5(-4)  - 3(3) - 1(1)
\end{pmatrix} = 
\begin{pmatrix}
    -21 & 5\\
    63 & -18
\end{pmatrix} 
$$

### Properties of Matrix Arithmetic
- A + B = B + A
- A + (B + C) = (A + B) + C
- 0 + A = A
- A - A = 0
$$
\lambda(A + B) = \lambda A + \lambda B \\
\begin{pmatrix}
    1 & ... & 0 \\
    \vdots & \ddots & \vdots \\
    0 & ... & 1
\end{pmatrix} * A = A
$$