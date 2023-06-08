---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Orthogonal Matrices
use-math: true
---

## Orthogonal Matrices

$$
\begin{pmatrix}
    \overrightarrow{w_1}^T \\
    \overrightarrow{w_2}^T \\
    \overrightarrow{w_3}^T \\
\end{pmatrix}
\begin{pmatrix}
    \overrightarrow{v_1} & \overrightarrow{v_2} & \overrightarrow{v_3}
\end{pmatrix} =
\begin{pmatrix}
    \overrightarrow{w_1}^T \overrightarrow{v_1} & \overrightarrow{w_1}^T \overrightarrow{v_2} & \overrightarrow{w_1}^T \overrightarrow{v_3} \\
    \overrightarrow{w_2}^T \overrightarrow{v_1} & \overrightarrow{w_2}^T \overrightarrow{v_2} & \overrightarrow{w_2}^T \overrightarrow{v_3} \\ 
    \overrightarrow{w_3}^T \overrightarrow{v_1} & \overrightarrow{w_3}^T \overrightarrow{v_2} & \overrightarrow{w_3}^T \overrightarrow{v_3} \\ 
\end{pmatrix} \\

\text{Suppose that } \{\hat{v}_1, \hat{v}_2, ..., \hat{v}_n\} \text{ is an orthonormal basis} \\
A = \begin{pmatrix}
    \hat{v}_1 & ... & \hat{v}_n
\end{pmatrix} \\
\text{Then, } A^T = A^{-1} \\
(A^T A)_{ij} = \hat{v}_i \cdot \hat{v}_j = \begin{cases}
    1, i = j \\
    0, i \neq j
\end{cases}
$$

## Lines of Best Fit (LSRL)

$$
A \overrightarrow{x} = \overrightarrow{b}
\begin{pmatrix}
    1 & 0 \\
    1 & 1 \\
    1 & 2 \\
    1 & 3
\end{pmatrix}
\begin{pmatrix}
    \beta_0 \\
    \beta_1
\end{pmatrix} = 
\begin{pmatrix}
    \beta_0 & \beta_1(0) \\
    \beta_0 & \beta_1(1) \\
    \beta_0 & \beta_1(2) \\
    \beta_0 & \beta_1(3)
\end{pmatrix} =
\begin{pmatrix}
    2 \\
    4 \\
    1 \\
    3
\end{pmatrix} \\
A^T A = 
\begin{pmatrix}
    1 & 1 & 1 & 1 \\
    0 & 1 & 2 & 3
\end{pmatrix}
\begin{pmatrix}
    1 & 0 \\
    1 & 1 \\
    1 & 2 \\
    1 & 3
\end{pmatrix} = 
\begin{pmatrix}
    4 & 6 \\
    6 & 14 \\
\end{pmatrix} \\
A^T \overrightarrow{b} = 
\begin{pmatrix}
    1 & 1 & 1 & 1 \\
    0 & 1 & 2 & 3
\end{pmatrix}
\begin{pmatrix}
    2 \\
    4 \\
    1 \\
    3
\end{pmatrix} =
\begin{pmatrix}
    10 \\
    15 \\
\end{pmatrix} \\
\left( 
    \begin{array}{cc|c}
        4 & 6 & 10 \\
        6 & 14 & 15\\
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{cc|c}
        1 & 0 & 2.5 \\
        0 & 1 & 0 \\
    \end{array}
\right)
\begin{pmatrix} \beta_0 \\ \beta_1 \end{pmatrix} = \begin{pmatrix} 2.5 \\ 0 \end{pmatrix} \text{ which corresponds to the line } y = 2.5
$$ 