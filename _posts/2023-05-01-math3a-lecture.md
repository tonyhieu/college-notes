---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Properties of Matrix Operations
use-math: true
---

## Addition
- A + B = B + A (commutative)
- (A + B) + C = A + (B + C) (associative)
- 0 + A = A
- (-A) + A = 0

## Multiplication 
- In matrix multiplication, the number of columns in the first matrix need to be equal to the number of rows in the second
    - These properties work under the assumption that the dimensions match up
- A * (B * C) = (A * B) * C
- A * (B + C) = A * B + A * C
- (B + C) * A = B * A + C * A
- I<sub>m</sub> * A = A * I<sub>m</sub> = A
- The identity matrix is defined as follows:
$$
\begin{pmatrix}
    1 & ... & 0 \\
    \vdots & \ddots & \vdots \\
    0 & ... & 1 \\
\end{pmatrix}
$$
- Important properties multiplication DOES NOT have
    - Not commutative; A * B != B * A
    - AB = AC does NOT imply B = C (cannot cancel out)
    - AB = 0 does NOT imply A = 0 or B = 0

### Example Showing Matrix Multiplication

$$
\text{Consider the matrices }
\begin{pmatrix}
    0 & 0 \\
    0 & 1
\end{pmatrix}
\text{ and }
\begin{pmatrix}
    0 & 0 \\
    1 & 0
\end{pmatrix} \\
\begin{pmatrix}
    0 & 0 \\
    1 & 0
\end{pmatrix}
\begin{pmatrix}
    0 & 0 \\
    0 & 1
\end{pmatrix} =
\begin{pmatrix}
    0 & 0 \\
    0 & 0
\end{pmatrix} = 
\begin{pmatrix}
    0 & 0 \\
    0 & 0
\end{pmatrix}
\begin{pmatrix}
    0 & 0 \\
    1 & 0
\end{pmatrix} \\


\begin{pmatrix}
    0 & 0 \\
    0 & 1
\end{pmatrix}
\begin{pmatrix}
    0 & 0 \\
    1 & 0
\end{pmatrix} =
\begin{pmatrix}
    0 & 0 \\
    1 & 0
\end{pmatrix}
$$

## Scalar Multiplication
$$
A = \begin{pmatrix}
    a_{11} & ... & a_{1n} \\
    \vdots & \ddots & \vdots \\
    a_{m1} & ... & a_{mn} 
\end{pmatrix} \\
r * A = \begin{pmatrix}
    ra_{11} & ... & ra_{1n} \\
    \vdots & \ddots & \vdots \\
    ra_{m1} & ... & ra_{mn} 
\end{pmatrix} = 
\begin{pmatrix}
    r & ... & 0\\
    \vdots & \ddots & \vdots \\
    0 & ... & r
\end{pmatrix} * A = 
A * \begin{pmatrix}
    r & ... & 0\\
    \vdots & \ddots & \vdots \\
    0 & ... & r
\end{pmatrix}
$$

## Matrix Transpose

A matrix with m rows by n columns can be transposed into a matrix with n rows by m columns

### Examples 
$$
\begin{pmatrix}
    1 & 0 & 1 \\
    2 & 3 & 4
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 2 \\
    0 & 3 \\
    1 & 4
\end{pmatrix} \\
\begin{pmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9 \\
    10 & 11 & 12
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 4 & 7 & 10 \\
    2 & 5 & 8 & 11 \\
    3 & 6 & 9 & 12
\end{pmatrix} \\
\begin{pmatrix}
    0 & 1 \\
    1 & 0
\end{pmatrix}^T =
\begin{pmatrix}
    0 & 1 \\
    1 & 0
\end{pmatrix}
$$

### Properties of Transpose
- (A<sup>T</sup>)<sup>T</sup> = A
- (A + B)<sup>T</sup> = B<sup>T</sup> + A<sup>T</sup>
- r * A<sup>T</sup> = (rA)<sup>T</sup>
- (A * B)<sup>T</sup> = B<sup>T</sup> * A<sup>T</sup>

## Square Matrices

Square Matrices have an equal number of rows and columns

- If A and B are both square, then AB and BA both exist
- Square matrices can be raised to an exponent
    - A<sup>k</sup> = A * A * ... * A (k times)


### Examples
$$
\begin{pmatrix}
    0 & 1 \\
    1 & 0
\end{pmatrix}^2 = 
\begin{pmatrix}
    0 & 1 \\
    1 & 0
\end{pmatrix}
\begin{pmatrix}
    0 & 1 \\
    1 & 0
\end{pmatrix} =
\begin{pmatrix}
    1 & 0 \\
    0 & 1
\end{pmatrix} \\

\begin{pmatrix}
    1 & 1 & 0 \\
    1 & 0 & 0 \\
    0 & 0 & 1
\end{pmatrix}^3 = 
\begin{pmatrix}
    1 & 1 & 0 \\
    1 & 0 & 0 \\
    0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
    1 & 1 & 0 \\
    1 & 0 & 0 \\
    0 & 0 & 1
\end{pmatrix}^2 \\
= 
\begin{pmatrix}
    1 & 1 & 0 \\
    1 & 0 & 0 \\
    0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
    2 & 1 & 0 \\
    1 & 1 & 0 \\
    0 & 0 & 1
\end{pmatrix} = 
\begin{pmatrix}
    3 & 2 & 0 \\
    2 & 1 & 0 \\
    0 & 0 & 1
\end{pmatrix}
$$

## Identity Matrix

Denoted as A<sup>0</sup> and I<sub>n</sub>

$$
\begin{pmatrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
\end{pmatrix}
\begin{pmatrix} a \\ b \\ c \end{pmatrix} = 
\begin{pmatrix} a \\ b \\ c \end{pmatrix}
$$

## Inverse Matrices

Denoted as A<sup>-1</sup> 
- A<sup>-1</sup> only exists for a square matrix
- A<sup>-1</sup> * A = A * A<sup>-1</sup> = I<sub>n</sub>
- Only exists whenever there is a pivot in every row and column

### Examples
$$
\begin{pmatrix}
    1 & 1 \\
    0 & 1
\end{pmatrix} \\
\begin{pmatrix}
    1 & 1 \\
    0 & 1
\end{pmatrix}^2 =
\begin{pmatrix}
    1 & 2 \\
    0 & 1
\end{pmatrix} \\
\begin{pmatrix}
    1 & 1 \\
    0 & 1
\end{pmatrix}^3 = 
\begin{pmatrix}
    1 & 0 \\
    0 & 1
\end{pmatrix}
\begin{pmatrix}
    1 & 2 \\
    0 & 1
\end{pmatrix} =
\begin{pmatrix}
    1 & 3 \\
    0 & 1
\end{pmatrix} \\

\text{Guess: the inverse is } \begin{pmatrix}
    1 & -1 \\
    0 & 1
\end{pmatrix} \\
\begin{pmatrix}
    1 & -1 \\
    0 & 1
\end{pmatrix}
\begin{pmatrix}
    1 & 1 \\
    0 & 1
\end{pmatrix} = 
\begin{pmatrix}
    1 & 0 \\
    0 & 1
\end{pmatrix} \\
\begin{pmatrix}
    1 & 1 \\
    0 & 1
\end{pmatrix}
\begin{pmatrix}
    1 & -1 \\
    0 & 1
\end{pmatrix} = 
\begin{pmatrix}
    1 & 0 \\
    0 & 1
\end{pmatrix}

$$