---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: More on Eigenvalues and Eigenvectors
use-math: true
---

## Similar Matrices

$$
\text{Two matrices A and B are similar if there exists invertible P such that } A = PBP^{-1}
$$

<ul>Theorem</ul>: If A and B are similar, then they have the same eigenvalues and determinants

### Proof

$$
\lambda I_n - A = \lambda I_n - PBP^{-1} = \lambda PI_nP^{-1} - PBP^{-1} = P(\lambda I_nP^{-1} - BP^{-1}) \\
= P(\lambda I_n - B)P^{-1}
$$

Upon taking determinants, we get that the characteristic polynomial of A is equal to the characteristic polynomial of B. Notated as P<sub>A</sub>(λ) = P<sub>B</sub>(λ).

$$
\overrightarrow{v} \text{ is an eigenvector for A } \implies P^{-1}\overrightarrow{v} \text{ is an eigenvector of B} \\
\overrightarrow{u} \text{ is an eigenvector for B } \implies P\overrightarrow{u} \text{ is an eigenvector of A} \\
$$

### Example

$$
A = \begin{pmatrix} 
    \frac{1}{2} & \frac{3}{2} \\
    \frac{3}{2} & \frac{1}{2} 
\end{pmatrix},
B = \begin{pmatrix} 
    2 & 0 \\
    0 & -1
\end{pmatrix},
P = \begin{pmatrix} 
    1 & 1 \\
    1 & -1
\end{pmatrix} \\

\begin{pmatrix} 
    1 & 1 \\
    1 & -1
\end{pmatrix}
\begin{pmatrix} 
    2 & 0 \\
    0 & -1
\end{pmatrix}
* \frac{1}{2}
\begin{pmatrix} 
    1 & 1 \\
    1 & -1
\end{pmatrix} \\
= \frac{1}{2}
\begin{pmatrix} 
    1 & 1 \\
    1 & -1
\end{pmatrix}
\begin{pmatrix} 
    2 & 2 \\
    -1 & 1
\end{pmatrix} =
\frac{1}{2}
\begin{pmatrix} 
    1 & 3 \\
    3 & 1
\end{pmatrix}

$$

In this example, the eigenvalues of A and B are 2 and -1 (based on B).

$$
\begin{pmatrix} 1 \\ 0 \end{pmatrix} \text{ is a 2-eigenvector of B (because you simply have to multiply by the top row)} \\
\begin{pmatrix} 0 \\ -1 \end{pmatrix} \text{ is a -1-eigenvector of B} \\
$$



$$
\begin{pmatrix}
    1 & 1 \\
    1 & -1
\end{pmatrix}
\begin{pmatrix} 1 \\ 0 \end{pmatrix} =
\begin{pmatrix} 1 \\ 1 \end{pmatrix} \text{ is a 2-eigenvector for A} \\
\begin{pmatrix}
    1 & 1 \\
    1 & -1
\end{pmatrix}
\begin{pmatrix} 0 \\ 1 \end{pmatrix} =
\begin{pmatrix} 1 \\ -1 \end{pmatrix} \text{ is a -1-eigenvector for A} 
$$

## Diagonalization

A **diagonal matrix** is a square matrix whose only potentially nonzero entries lie on the diagonal. Note that you CAN have zeroes on the diagonal (thus, the zero matrix is a diagonal matrix), but you can NOT have nonzeroes off of the diagonal.

### Example

$$
\text{We want to turn }
A = \begin{pmatrix}
    1 & 6 \\
    5 & 2
\end{pmatrix} \text{ into }
D = \begin{pmatrix}
    7 & 0 \\
    0 & -4
\end{pmatrix}
\text{ to more easily find its eigenvalues.} \\
\text{A matrix is diagonalizable if there is a diagonal matrix D such that } A = PDP^{-1} \text{ (i.e. A and D are similar).}
$$



$$
A = \begin{pmatrix}
    1 & 6 \\
    5 & 2
\end{pmatrix}, 
D = \begin{pmatrix}
    7 & 0 \\
    0 & -4
\end{pmatrix} \\
\text{Instead of using } A = PDP^{-1} \text{ we can use } AP = PD \\
\text{From last time: 7 is an eigenvalue with eigenvector } \begin{pmatrix} 1 \\ 1 \end{pmatrix} \text{ and -4 is an eigenvalue with eigenvector } \begin{pmatrix} -6 \\ 5 \end{pmatrix} \\
P = \begin{pmatrix}
    1 & -6 \\
    1 & 5
\end{pmatrix}, det(P) = 11 \\
AP = (A\begin{pmatrix} 1 \\ 1 \end{pmatrix} A \begin{pmatrix} -6 \\ 5 \end{pmatrix}) = 
\begin{pmatrix}
    7 & 24 \\
    7 & -20
\end{pmatrix} \\
PD = \begin{pmatrix}
    1 & -6 \\
    1 & 5
\end{pmatrix}
\begin{pmatrix}
    7 & 0 \\
    0 & -4
\end{pmatrix} = 
\begin{pmatrix}
    7 & 24 \\
    7 & -20
\end{pmatrix} \\
\text{Thus, we have verified that AP = PD.}
$$



$$
\text{If we know that eigenvalues of n x n matrix A are } \lambda _1, ..., \lambda _n \text{ with eigenvectors } \overrightarrow{v_1}, ..., \overrightarrow{v_n} \\
D = \begin{pmatrix}
    \lambda _1 & ... & 0 \\
    \vdots & \ddots & \vdots \\
    0 & ... & \lambda _n
\end{pmatrix},
P = \begin{pmatrix} \overrightarrow{v_1} & ... & \overrightarrow{v_n} \end{pmatrix} \\
\text{Only applies if A has n distinct, linearly independent eigenvectors.}
$$