---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Finding Eigenvectors and Eigenvalues
use-math: true
---

## Finding Eigenvalues

$$
\lambda \text{ is an eigenvalue of A } \iff \lambda \text{ is a root of } det(t I_n - A) = P_A (t)
$$

P<sub>A</sub>(t) is known as the **characteristic polynomial. Also, lambda and t can be used interchangeably.

### Example

$$
det(\lambda \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} - \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}) \\
= det(\begin{pmatrix} \lambda - 1 & -1 \\ -1 & \lambda - 1 \end{pmatrix}) = \lambda ^2 - 2\lambda = \lambda (\lambda - 2) \\
\text{There are two eigenvalues: 0 and 2.}
$$



$$
A = \begin{pmatrix} 0 & 6 \\ -1 & 5 \end{pmatrix} \\
det(\lambda \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} - \begin{pmatrix} 0 & 6 \\ -1 & 5 \end{pmatrix}) \\
= det(\lambda \begin{pmatrix} \lambda & -6 \\ 1 & \lambda - 5 \end{pmatrix}) = \lambda^2 - 5\lambda + 6 = (\lambda - 3)(\lambda - 2) \\
\text{There are two eigenvalues: 2 and 3.}
$$



$$
A = \begin{pmatrix} 1 & 6 \\ 5 & 2 \end{pmatrix} \\
det(\lambda \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} - \begin{pmatrix} 1 & 6 \\ 5 & 2 \end{pmatrix}) \\
= det(\lambda \begin{pmatrix} \lambda - 1 & -6 \\ -5 & \lambda - 2 \end{pmatrix}) = \lambda^2 - 3\lambda - 28 = (\lambda - 7)(\lambda + 4) \\
\text{There are two eigenvalues: -4 and 7.} \\
Nul(7 I_2 - A) \text{ contains our eigenvectors, as } (7 I_2 - A) \overrightarrow{v} = \overrightarrow{0} \rightarrow 7\overrightarrow{v} - A\overrightarrow{v} = \overrightarrow{0} \\

Nul(7 I_2 - A) = Nul(\begin{pmatrix} 6 & -6 \\ -5 & 5 \end{pmatrix}) = Nul(\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}) = Nul(\begin{pmatrix} 1 & -1 \\ 0 & 0 \end{pmatrix}) \\
\begin{pmatrix} 1 & -1 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} a - b \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \text{ when a = b}\\
\text{Thus, any vectors where a = b are 7-eigenvectors for A, such as } \begin{pmatrix} 1 \\ 1 \end{pmatrix} \\

Nul(-4 I_2 - A) = Nul(4 I_2 + A) = Nul(\begin{pmatrix} 5 & 6 \\ 5 & 6 \end{pmatrix}) = Nul(\begin{pmatrix} 5 & 6 \\ 0 & 0 \end{pmatrix}) = Nul(\begin{pmatrix} 1 & \frac{6}{5} \\ 0 & 0 \end{pmatrix})\\
\begin{pmatrix} 1 & \frac{6}{5} \\ 0 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} a + \frac{6}{5}b \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \text{ when } a = -\frac{6}{5}b\\
\text{Thus, any vectors where } a = -\frac{6}{5}b \text{ are -4-eigenvectors for A, such as } \begin{pmatrix} -6 \\ 5 \end{pmatrix} \text{ or } Span\{\begin{pmatrix} -6 \\ 5 \end{pmatrix}\} \\
$$

**Note**: The nullspace associated with an eigenvalue has a special name: E<sub>x</sub> = the x-eigenspace of A, where x is replaced by the eigenvalue that represents the eigenspace.



$$
A = \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix}, \text{eigenvalues are } \frac{1}{2} (3 \pm \sqrt{5}) \\
\begin{pmatrix} a \\ b \end{pmatrix} \in E_{\frac{1}{2} (3 \pm \sqrt{5})} \\
A \begin{pmatrix} a \\ b \end{pmatrix} = \lambda \begin{pmatrix} a \\ b \end{pmatrix} \rightarrow \frac{1}{2} (3 \pm \sqrt{5}) \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} a + b \\ a + 2b \end{pmatrix} \\
\frac{1}{2} (3 \pm \sqrt{5}) a = a + b \text{, so } b = \frac{1}{2} (1 \pm \sqrt{5}) \\
E_{\frac{1}{2} (3 \pm \sqrt{5})} \text{ is spanned by } \{\begin{pmatrix} 1 \\ \frac{1}{2} (1 \pm \sqrt{5}) \end{pmatrix} \}
$$