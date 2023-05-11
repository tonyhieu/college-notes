---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Bases
use-math: true
---

## Basis

A basis is a linearly independent AND spanning set. They can be thought of as coordinates and a way to frame linear algebra into a coordinate system.

The best way to find a basis is to get a set of vectors and cut it down until the vectors are linearly independent.

### Theorem

Any subspace of R<sup>n</sup> has a basis and any bases have the same number of elements. The dimension of a subspace (notated as dim(H)) is equal to the number of elements of a basis.

### Examples
$$
\text{Q: What is } dim(\mathbb{R}^n) \text{?} \\
\text{A: } dim(\mathbb{R}^n) = n \text{ because } \{\hat{e}_1, ..., \hat{e}_n,\} \text{ is a basis.}
$$



$$
\text{Q: Is it true that } dim(Span\{\overrightarrow{v}_1, ..., \overrightarrow{v}_n\}) = k \text{ is always true?} \\
\text{A: No. It is only true if } Span\{\overrightarrow{v}_1, ..., \overrightarrow{v}_n\} \text{ is linearly independent.}
$$



$$
dim(Span\{
    \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix},
    \begin{pmatrix} 2 \\ 0 \\ 2 \end{pmatrix},
    \begin{pmatrix} 3 \\ 1 \\ 4 \end{pmatrix}
    \}) = ? \\

\begin{pmatrix}
    1 & 2 & 3 \\
    1 & 0 & 1 \\
    1 & 2 & 4
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 2 & 3 \\
    0 & -2 & -2 \\
    0 & 0 & 1
\end{pmatrix}\\
\text{Because the matrix has a pivot in every row, the dimension of the span is 3.}
$$

## Rank Nullity Theorem

$$
\text{Suppose we have an m x n matrix A where rank(A) = dim(Col(A)).} \\
\text{THEOREM: } dim(Nul(A)) + rank(A) = n \\
\text{THEOREM: The pivot columns form a basis for Col(A). Therefore, rank(A) is equal to the number of pivot columns.} \\
\text{Also, dim(Nul(A)) is equal to the number of non-pivot columns or number of free variables.} \\
$$

**To find the basis for the nullspace, you have to find the homogenous solution and get the free variables**

### Example

$$
A = \begin{pmatrix}
    1 & 3 & 6 & -8 \\
    4 & 3 & 2 & -3 \\
    2 & 4 & -1 & -1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 0 & 0 & \frac{19}{73} \\
    0 & 1 & 0 & -\frac{47}{73} \\
    0 & 0 & 1 & -\frac{27}{73}
\end{pmatrix}\\
rank(A) = 3, dim(Nul(A)) = 1
$$



$$
A = \begin{pmatrix}
    1 & 0 & 1 & -3 \\
    0 & 1 & 0 & 2 \\
    1 & 2 & 0 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 0 & 1 & -3 \\
    0 & 1 & 0 & 2 \\
    0 & 2 & -1 & 4
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 0 & 1 & -3 \\
    0 & 1 & 0 & 2 \\
    0 & 0 & -1 & 0
\end{pmatrix} \\
rank(A) = 3, dim(Null(A)) = 1
$$



$$
A = \begin{pmatrix}
    2 & 5 & -3 & -4 & 8 \\
    4 & 7 & -4 & -3 & 9 \\
    6 & 9 & -5 & 2 & 4 \\
    0 & -9 & 6 & 5 & -6
\end{pmatrix} \rightarrow
\begin{pmatrix}
    2 & 5 & -3 & -4 & 8 \\
    0 & -3 & 2 & 5 & -7 \\
    0 & 0 & 0 & 4 & -6 \\
    0 & 0 & 0 & 0 & 0
\end{pmatrix} \\
rank(A) = 3 \text{, where columns 1, 2, and 4 form the basis for our column space.} \\
dim(Nul(A)) = 2 \\
\begin{cases}
    2x_1 + 5x_2 -3x_3 -4x_4 + 8x_5 = 0 \\
    -3x_2 + 2x_3 + 5x_4 - 7x_5 = 0 \\
    4x_4 - 6x_5 = 0 \\
    x_3, x_5 \text{ free}
\end{cases} \rightarrow
\begin{cases}
    x_1 = -\frac{1}{6}x_3 - \frac{17}{12}x_5 \\
    x_2 = \frac{2}{3}x_3 + \frac{1}{6}x_5 \\
    x_4 = \frac{3}{2}x_5 \\
\end{cases} \\
\overrightarrow{x_0} = \begin{pmatrix}
    -\frac{1}{6}s - \frac{17}{12}t \\
    \frac{2}{3}s + \frac{1}{6}t \\
    s \\
    \frac{3}{2}t \\
    t
\end{pmatrix} =
s \begin{pmatrix}
    -\frac{1}{6} \\
    \frac{2}{3} \\
    1 \\
    0 \\
    0
\end{pmatrix} +
t \begin{pmatrix}
    -\frac{17}{12} \\
    \frac{1}{6} \\
    0 \\
    \frac{3}{2} \\
    1
\end{pmatrix}
$$ 

## Additions to the Invertible Matrix Theorem

Suppose A is an n x n matrix.

12. Col(A) = R<sup>n</sup>
13. rank(A) = n
14. Nul(A) = {0}
15. dim(Nul(A)) = 0


