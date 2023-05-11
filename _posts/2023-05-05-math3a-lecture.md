---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Invertible Matrix Theorem
use-math: true
---

## Theorem

$$
\text{Given an n x n matrix } A = \begin{pmatrix}\overrightarrow{a_1} & ... & \overrightarrow{a_n} \end{pmatrix} \text{, the following are equivalent:} \\
\text{1. A is invertible: } A * A^{-1} = A^{-1} * A = I_n \\
\text{2. A has n pivots} \\
\text{3. } T(\overrightarrow{x}) = A * \overrightarrow{x} \text{ is onto} \\
\text{4. } Span\{\overrightarrow{a_1}, ..., \overrightarrow{a_n} \} = \mathbb{R}^n\\
\text{5. } A\overrightarrow{x} = \overrightarrow{b} \text{ is consistent for every }\overrightarrow{b} \\
\text{6. } A\overrightarrow{x} = \overrightarrow{b} \implies \overrightarrow{x} = \overrightarrow{0} \\
\text{7. } \{\overrightarrow{a_1}, ..., \overrightarrow{a_n} \} \text{ is linearly independent} \\
\text{8. } T(\overrightarrow{x}) = A * \overrightarrow{x} \text{ is one-to-one} \\
\text{9. } BA = I_n \text{ for some B} \\
\text{10. } AB = I_n \text{ for some B} \\
\text{11. } A\overrightarrow{x} = \overrightarrow{b} \text{ has exactly one solution for every } \overrightarrow{b}
$$

Note that 3-5 is the same as the Row Theorem and 4-6 is the same as the Column Theorem.

### Examples

$$
\text{Prove that 1 implies 11} \\
A\overrightarrow{x} = \overrightarrow{b} \\
A^{-1}\overrightarrow{b} = A^{-1}A\overrightarrow{x} = I_n * \overrightarrow{x} = \overrightarrow{x} 
$$



$$
\text{Q. If A is 3 x 3 and its columns span } \mathbb{R}^3 \text{, are the columns linearly independent?} \\
\text{A. Yes because of the Invertible Matrix Theorem (4 and 7)} \\
\text{Q. If A is 4 x 4 and } A\overrightarrow{x} = \overrightarrow{0} \text{ has a nontrivial solution, does } A\overrightarrow{x} = \overrightarrow{0} \text{ have a unique solution for every } \overrightarrow{b} \text{?}\\
\text{A. No, as it fails condition 6 so it fails all conditions (specifically 11)}
$$

### Additional properties of inverses

1. If A is invertible, so is A<sup>-1</sup>, and (A<sup>-1</sup>)<sup>-1</sup> = A

2. If A and B are invertible, so is AB and (AB)<sup>-1</sup> = B<sup>-1</sup>A<sup>-1</sup>
- This is because the identity matrix is only gotten through ABB<sup>-1</sup>A<sup>-1</sup> or B<sup>-1</sup>A<sup>-1</sup>AB

3. If A ias invertible, so is A<sup>T</sup> and (A<sup>T</sup>)<sup>-1</sup> = (A<sup>-1</sup>)<sup>T</sup>

### 2 x 2 Example

$$
A = \begin{pmatrix}
    a & b \\
    c & d \\
\end{pmatrix}
\text{, and if A is invertible, then }
A^{-1} = \frac{1}{ad - bc} * \begin{pmatrix}
    d & -b \\
    -c & a \\
\end{pmatrix} \\
\text{A is invertible } \iff ad - bc = det(A) \neq 0
$$

The determinant of a 2 x 2 matrix is simple, but larger matrices are extremely difficult to calculate the determinant for.

$$
\text{Consider } A = \begin{pmatrix}
    1 & 1 \\
    3 & 4 \\
\end{pmatrix} \\
A^{-1} = \frac{1}{4 - 3} * \begin{pmatrix}
    4 & -1 \\
    -3 & 1 \\
\end{pmatrix} = \begin{pmatrix}
    4 & -1 \\
    -3 & 1 \\
\end{pmatrix}
$$

### Reliance on Square Matrices

$$
\text{Consider } A = \begin{pmatrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
\end{pmatrix} \text{, } B = \begin{pmatrix}
    1 & 0 \\
    0 & 1 \\
    0 & 0
\end{pmatrix} \\
AB = \begin{pmatrix}
    1 & 0 \\
    0 & 1 \\
\end{pmatrix} \text{, but } 
BA = \begin{pmatrix}
    1 & 0 & 0\\
    0 & 1 & 0\\
    0 & 0 & 0
\end{pmatrix}
$$

## Subspaces

$$
\text{A subspace of } \mathbb{R}^n \text{ is a subset } H \subset \mathbb{R}^n \text{ such that} \\
\overrightarrow{0} \in H \\
\overrightarrow{u}, \overrightarrow{v} \in H \implies \overrightarrow{u} + \overrightarrow{v} \in H \\
\overrightarrow{u} \in H, r \in \mathbb{R} \implies r * \overrightarrow{u} \in H
$$

Spans are an example of a subspaces

$$
A = \begin{pmatrix} \overrightarrow{a_1} & ... & \overrightarrow{a_n}\end{pmatrix} \text{, } Col(A) = Span\{\overrightarrow{a_1}, ..., \overrightarrow{a_n}\} \text{ is a subspace} 
$$

### Null Subspace

$$
\text{m x n matrix A, } Null(A) = \{\overrightarrow{x} \in \mathbb{R}^n | A\overrightarrow{x} = \overrightarrow{0}\} \\
A\overrightarrow{0} = \overrightarrow{0} \\
A\overrightarrow{u} = \overrightarrow{0} \text{ and } A\overrightarrow{v} = \overrightarrow{0} \text{, } A(\overrightarrow{u} + \overrightarrow{v}) = A\overrightarrow{u} + A\overrightarrow{v} = \overrightarrow{0} + \overrightarrow{0} = \overrightarrow{0} \\
A\overrightarrow{u} = \overrightarrow{0}, r \in \mathbb{R}, A(r\overrightarrow{u}) = r A(\overrightarrow{u}) = r\overrightarrow{0} = \overrightarrow{0}
$$

### Examples

$$
A = \begin{pmatrix}
    1 & 0 & 2 \\
    3 & 5 & -1
\end{pmatrix}\\
\text{What is Nul(A) and Col(A) as spans?} \\
\text{By the row theorem, Col(A) is } \mathbb{R}^2 \\
\overrightarrow{x}_0 = \begin{pmatrix} -2 \\ \frac{7}{5} \\ 1 \end{pmatrix}, Nul(A) = Span\{\begin{pmatrix} -2 \\ \frac{7}{5} \\ 1 \end{pmatrix}\}
$$

