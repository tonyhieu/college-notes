---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Properties of Functions
use-math: true
---

## Properties

$$
\text{Consider a linear function T: } \mathbb{R}^n \rightarrow \mathbb{R}^m \\
\text{T is \underline{onto} if every } \overrightarrow{w} \in \mathbb{R}^m \text{ can be written as } T(\overrightarrow{v}) = \overrightarrow{w} \\
\text{T is \underline{one-to-one} if } T(\overrightarrow{v}) = T(\overrightarrow{v}) \implies \overrightarrow{v} = \overrightarrow{w} \\
\text{T is a \underline{bijection} if it is both onto and one-to-one}
$$

### Other ways to define properties

$$
\text{T is onto if and only if } A_T \overrightarrow{x} = \overrightarrow{b} \text{ is consistent for every } \overrightarrow{b} \in \mathbb{R}^m \\
\text{T is one-to-one if and only if the columns of } A_T \text{ are linearly independent}
$$

### Examples

$$
\text{The function defined by this matrix multiplication is onto:}\\
\begin{pmatrix}
    1 & 0 & 1 \\
    0 & 1 & 0
\end{pmatrix}
\begin{pmatrix} a \\ b \\ 0 \end{pmatrix} =
\begin{pmatrix} a \\ b \end{pmatrix} \\

\text{The function defined by this matrix multiplication is one-to-one:} \\
\begin{pmatrix}
    1 & 0 \\
    0 & 1 \\
    0 & 0
\end{pmatrix}
\begin{pmatrix} a \\ b \end{pmatrix} =
\begin{pmatrix} a \\ b \\ 0\end{pmatrix} \\

\text{The function defined by this matrix multiplication is a bijection:} \\
\begin{pmatrix}
    cos\theta & -sin\theta \\
    sin\theta & cos\theta
\end{pmatrix}
$$

## Invertible Matrices

$$
\text{Consider a n x n matrix A. A is invertible if there exists } A^{-1} \text{ such that } A^{-1} * A = A * A^{-1} = I_n \\
\text{The matrix A also has to represent a bijective linear transformation.}
$$



$$
\text{Theorem: An n x n matrix A is invertible if and only if the RREF of A is } I_n \text{.}\\
\text{In this case, row operations that take A to } I_n \text{ transform } I_n \text{ into } A^{-1} \\
(A | I_n) \rightarrow (I_n | A^{-1})
$$

$$
\text{Theorem: For an n x n matrix A, the following are equivalent:} \\
\text{A is invertible} \\
\text{A has a pivot in every row} \\
\text{A has a pivot in every column}
$$

### Examples
$$
\begin{pmatrix}
    0 & 0 \\
    0 & 1
\end{pmatrix}
\text{ is not invertible because you cannot get a 1 in the top left cell. Proof: }\\
\begin{pmatrix}
    0 & 0 \\
    0 & 1
\end{pmatrix} 
\begin{pmatrix}
    a & b \\
    c & d
\end{pmatrix} = 
\begin{pmatrix}
    0 & 0 \\
    c & d
\end{pmatrix}
$$



$$
\text{Invert }
\begin{pmatrix}
    1 & 2 & 3 \\
    0 & 1 & 4 \\
    5 & 6 & 0
\end{pmatrix} \\

\left( 
    \begin{array}{ccc|ccc}
        1 & 2 & 3 & 1 & 0 & 0 \\
        0 & 1 & 4 & 0 & 1 & 0\\
        5 & 6 & 0 & 0 & 0 & 1
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|ccc}
        1 & 2 & 3 & 1 & 0 & 0 \\
        0 & 1 & 4 & 0 & 1 & 0\\
        0 & -4 & -15 & -5 & 0 & 1
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|ccc}
        1 & 2 & 3 & 1 & 0 & 0 \\
        0 & 1 & 4 & 0 & 1 & 0\\
        0 & 0 & 1 & -5 & 4 & 1
    \end{array}
\right) \\
\left( 
    \begin{array}{ccc|ccc}
        1 & 2 & 0 & 16 & -12 & -3 \\
        0 & 1 & 0 & 20 & -15 & -4\\
        0 & 0 & 1 & -5 & 4 & 1
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|ccc}
        1 & 0 & 0 & -24 & 18 & 5 \\
        0 & 1 & 0 & 20 & -15 & -4 \\
        0 & 0 & 1 & -5 & 4 & 1
    \end{array}
\right) \\
\text{Therefore, the inverse of }
\begin{pmatrix}
    1 & 2 & 3 \\
    0 & 1 & 4 \\
    5 & 6 & 0
\end{pmatrix}
\text{ is }
\begin{pmatrix}
    -24 & 18 & 5 \\
    20 & -15 & -4 \\
    -5 & 4 & 1
\end{pmatrix}
$$



$$
\text{Invert }
\begin{pmatrix}
    1 & 2 & 0 \\
    3 & -1 & 2 \\
    -2 & 3 & -2
\end{pmatrix} \\

\left( 
    \begin{array}{ccc|ccc}
        1 & 2 & 0 & 1 & 0 & 0 \\
        3 & -1 & 2 & 0 & 1 & 0\\
        -2 & 3 & -2 & 0 & 0 & 1
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|ccc}
        1 & 2 & 0 & 1 & 0 & 0 \\
        0 & -7 & 2 & -3 & 1 & 0\\
        0 & 7 & -2 & 2 & 0 & 1
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|ccc}
        1 & 2 & 0 & 1 & 0 & 0 \\
        0 & -7 & 2 & -3 & 1 & 0\\
        0 & 0 & 0 & -1 & 1 & 1
    \end{array}
\right) \\
\text{Since the RREF of the matrix does not have a pivot in every row and column, it is not invertible.}
$$

