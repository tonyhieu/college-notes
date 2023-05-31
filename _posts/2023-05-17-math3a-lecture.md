---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Eigenvalues and Eigenvectors
use-math: true
---

## Inverting a Matrix

Given that A is invertible, we can calculate A<sup>-1</sup> as follows:

$$
(A^{-1})_{ij} = (-1)^{i+j} \frac{|A_{ji|}}{|A|}
$$

A<sub>ji</sub> is the matrix we get by deleting the jth row and the ith column. 

This is more of a conceptual method to invert a matrix, but less efficient than inverting matrices through row reduction

### Example

$$
A = \begin{pmatrix}
    3 & 6 & 7 \\
    0 & 2 & 1 \\
    2 & 3 & 4
\end{pmatrix} \\

A^{-1} = \frac{1}{|A|} *
(
\begin{pmatrix}
    + \begin{pmatrix} 2 & 1 \\ 3 & 4 \end{pmatrix} & - \begin{pmatrix} 0 & 1 \\ 2 & 4 \end{pmatrix} & + \begin{pmatrix} 0 & 2 \\ 2 & 3 \end{pmatrix} \\
    - \begin{pmatrix} 6 & 7 \\ 3 & 4 \end{pmatrix} & + \begin{pmatrix} 3 & 7 \\ 2 & 4 \end{pmatrix} & - \begin{pmatrix} 3 & 6 \\ 2 & 3 \end{pmatrix} \\
    + \begin{pmatrix} 6 & 7 \\ 2 & 1 \end{pmatrix} & - \begin{pmatrix} 3 & 7 \\ 0 & 1 \end{pmatrix} & + \begin{pmatrix} 3 & 6 \\ 0 & 2 \end{pmatrix} \\
\end{pmatrix}
)
$$

## Eigenvalues and Eigenvectors

$$
\text{Consider the matrix } A = \begin{pmatrix}
    1 & 6 \\
    5 & 2 
\end{pmatrix}, \overrightarrow{v} = \begin{pmatrix} 1 \\ 1 \end{pmatrix} \\
\begin{pmatrix}
    1 & 6 \\
    5 & 2 
\end{pmatrix}
\begin{pmatrix} 1 \\ 1 \end{pmatrix}
= \begin{pmatrix} 7 \\ 7 \end{pmatrix} = 7 * \begin{pmatrix} 1 \\ 1 \end{pmatrix}
$$

In the above example, the eigenvalue is 7 and the eigenvector is v.

$$
\text{If } A\overrightarrow{v} = \lambda \overrightarrow{v} \text{ for } \lambda \in \mathbb{R} \text{ and } \overrightarrow{v} \neq \overrightarrow{0} \\
\text{1. } \lambda \text{ is an eigenvalue of A} \\
\text{2. } \overrightarrow{v} \text{ is an eigenvector of A}
$$

### Examples

$$
A = \begin{pmatrix} 7 & -3 \\ 10 & -4 \end{pmatrix}, \overrightarrow{v} = \begin{pmatrix} 3 \\ 5 \end{pmatrix} \\
A \overrightarrow{v} = \begin{pmatrix} 6 \\ 10 \end{pmatrix} = 2 * \begin{pmatrix} 3 \\ 5 \end{pmatrix}
$$

<hr />

$$
A = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}, \overrightarrow{v_2} = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \overrightarrow{v_0} = \begin{pmatrix} 1 \\ -1 \end{pmatrix} \\
A \overrightarrow{v_2} = \begin{pmatrix} 2 \\ 2 \end{pmatrix} = 2 * \overrightarrow{v_2} \\
A \overrightarrow{v_0} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} = 0 * \overrightarrow{v_0}
$$

Note that each eigenvectors has ONE eigenvalue, but eigenvalues can have MULTIPLE eigenvectors. Each eigenvalue has a "family" of eigenvectors that can be scaled up or down to get the same eigenvalue.

## Finding eigenvalues

$$
\text{Suppose that } A\overrightarrow{v} = \lambda \overrightarrow{v} \text{ for } \lambda \in \mathbb{R} \text{ and } \overrightarrow{v} \neq \overrightarrow{0} \text{. Then, the following chain of implications holds: } \\
A\overrightarrow{v} = \lambda \overrightarrow{v} \iff \lambda \overrightarrow{v} - A\overrightarrow{v} = \overrightarrow{0} = \lambda I_n \overrightarrow{v} - A\overrightarrow{v} = \overrightarrow{0} \\
\iff (\lambda I_n - A) \overrightarrow{v} = \overrightarrow{0} \iff \overrightarrow{v} \in Nul(\lambda I_n - A) = \{\overrightarrow{0}\} \\
\iff (\lambda I_n - A) \text{ is non invertible } \iff det(\lambda I_n - A) = 0 \iff \lambda \text{ is a root of } det(\lambda I_n - A) \\
\text{Note: } det(\lambda I_n - A) \text{ can be represented as a nth degree polynomial } P_A (t)
$$