---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Orthogonal Sets
use-math: true
---

## Orthogonal Sets

$$
\text{A set } \{\overrightarrow{v_1}, \overrightarrow{v_2}, ..., \overrightarrow{v_n} \} \text{ of nonzero vectors is orthogonal if for all } i \neq j, \overrightarrow{v_i}, \overrightarrow{v_j} \rightarrow \overrightarrow{v_i} \perp \overrightarrow{v_j} \\
\text{Example: } \{ \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} \} \text{ is orthogonal} \\
\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix} \cdot \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} = 0, \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix} \cdot \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} = 0, \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} \cdot \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} = 0
$$

<hr>

$$
\text{Theorem: An orthogonal set is linearly independent}
$$

<hr>

$$
\{\overrightarrow{v_1}, ..., \overrightarrow{v_n} \} \text{ is orthonormal if it is already orthogonal and } ||\overrightarrow{v_i}|| = 1 \text{ (AKA all vectors are unit vectors)} \\
\text{Can easily get an orthonormal set from an orthogonal one by dividing each vector in the set by its norm}
$$

Orthonormal sets are good for getting a standard basis for a subspace, such as R<sup>n</sup>. In other words, orthonormal bases are as good as standard bases.

## Method for Transforming a Basis into an Orthonormal Basis

**Gram-Schmidt Orthogonalization**

Turns linearly independent sets into orthonormal ones

$$
\{\overrightarrow{v_1}, ..., \overrightarrow{v_n} \} \text{ is linearly independent} \\
\text{Let } \overrightarrow{u_1} = \overrightarrow{v_1} \\
\overrightarrow{u_2} = \overrightarrow{v_2} - \frac{\overrightarrow{u_1} \cdot \overrightarrow{v_2}}{\overrightarrow{u_1} \cdot \overrightarrow{u_1}} \overrightarrow{u_1} \\
\overrightarrow{u_3} = \overrightarrow{v_3} - \frac{\overrightarrow{u_1} \cdot \overrightarrow{v_3}}{\overrightarrow{u_1} \cdot \overrightarrow{u_1}} \overrightarrow{u_1} - \frac{\overrightarrow{u_2} \cdot \overrightarrow{v_3}}{\overrightarrow{u_2} \cdot \overrightarrow{u_2}} \overrightarrow{u_2} \\
... \\
\overrightarrow{u_n} = \overrightarrow{v_n} - \sum_{i = 1}^{n - 1} \frac{\overrightarrow{u_i} \cdot \overrightarrow{v_n}}{\overrightarrow{u_i} \cdot \overrightarrow{u_i}} \overrightarrow{u_i} \\

\text{To get the orthonoaml set, normalize all of the u vectors: } \{\hat{u_1}, \hat{u_2}, ..., \hat{u_n} \}
$$

### Example

$$
\{ \begin{pmatrix} 1 \\ -1 \end{pmatrix}, \begin{pmatrix} 2 \\ 1 \end{pmatrix} \} \\
\overrightarrow{u_1} = \overrightarrow{v_1} = \begin{pmatrix} 1 \\ -1 \end{pmatrix} \rightarrow \hat{u_1} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix} \\
\overrightarrow{u_2} = \begin{pmatrix} 2 \\ 1 \end{pmatrix} - \frac{\begin{pmatrix} 1 \\ -1 \end{pmatrix} \cdot \begin{pmatrix} 2 \\ 1 \end{pmatrix}}{\begin{pmatrix} 1 \\ -1 \end{pmatrix} \cdot \begin{pmatrix} 1 \\ -1 \end{pmatrix}} \begin{pmatrix} 1 \\ -1 \end{pmatrix} \\
= \begin{pmatrix} 2 \\ 1 \end{pmatrix} - \frac{1}{2} \begin{pmatrix} 1 \\ -1 \end{pmatrix} = \begin{pmatrix} 1.5 \\ 1.5 \end{pmatrix} \\
\hat{u_2} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} \\
\text{Thus, } \{ \hat{u}_1, \hat{u}_2 \} \text{ is orthonormal}
$$

## Solving an SLE with No Real Solutions

Method: **Least Squares**

$$
\text{Definition: an m x n matrix A and } \overrightarrow{b} \in \mathbb{R}^m \\
\text{A least squares solution to } A\overrightarrow{x} = \overrightarrow{b} \text{ is a vector } \hat{x} = \overrightarrow{x_{LS}} \in \mathbb{R}^n \text{ such that for all } \overrightarrow{v} \in \mathbb{R}^n , ||A\hat{x} - \overrightarrow{b} || \leq ||A\overrightarrow{v} - \overrightarrow{b}||
$$

<hr>

$$
\text{Theorem: If A is a m x n matrix and } \overrightarrow{b} \in \mathbb{R}^m \text{, the least squares solution of } A\overrightarrow{x} = \overrightarrow{b} \text{ corresponds to solutions of } A^T A\overrightarrow{x} = A^T \overrightarrow{b} \text{, which is always consistent.}
$$

### Steps

$$
\text{1. Compute } A^T A \text{ and } A^T \overrightarrow{b} \\
\text{2. Form the augmented matrix}  ( A^T A | A^T \overrightarrow{b} ) \text{ and row reduce} \\
\text{3. This is always consistent, and any solution is a least squares solution of } A\overrightarrow{x} = \overrightarrow{b}
$$

### Examples

$$
A = \begin{pmatrix}
    0 & 1
    1 & 1 \\
    2 & 1
\end{pmatrix},
\overrightarrow{b} = \begin{pmatrix}6\\0\\0\end{pmatrix} \\
A^T A = 
\begin{pmatrix}
    0 & 1 & 2 \\
    1 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
    0 & 1 \\
    1 & 1 \\
    2 & 1 
\end{pmatrix} = 
\begin{pmatrix}
    5 & 3 \\
    3 & 3 \\ 
\end{pmatrix} \\
A^T \overrightarrow{b} = 
\begin{pmatrix}
    0 & 1 & 2 \\
    1 & 1 & 1
\end{pmatrix} 
\begin{pmatrix}6\\0\\0\end{pmatrix} = 
\begin{pmatrix}0\\6\end{pmatrix} \\
\left( 
    \begin{array}{cc|c}
        5 & 3 & 0 \\
        3 & 3 & 6
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{cc|c}
        1 & 0 & -3 \\
        0 & 1 & 5
    \end{array}
\right) \\
\hat{x} = \begin{pmatrix}-3\\5\end{pmatrix}
$$

<hr>

$$
A = \begin{pmatrix}
    1 & 3 \\
    1 & -1 \\
    1 & 1
\end{pmatrix},
\overrightarrow{b} = \begin{pmatrix}5\\1\\0\end{pmatrix} \\
A^T A = 
\begin{pmatrix}
    1 & 1 & 1 \\
    3 & -1 & 1
\end{pmatrix}
\begin{pmatrix}
    1 & 3 \\
    1 & -1 \\
    1 & 1
\end{pmatrix} = 
\begin{pmatrix}
    3 & 3 \\
    3 & 11 \\ 
\end{pmatrix} \\
A^T \overrightarrow{b} = 
\begin{pmatrix}
    1 & 1 & 1 \\
    3 & -1 & 1
\end{pmatrix}
\begin{pmatrix}5\\1\\0\end{pmatrix} =
\begin{pmatrix}6\\14\end{pmatrix} \\
\left( 
    \begin{array}{cc|c}
        3 & 3 & 6 \\
        3 & 11 & 14
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{cc|c}
        1 & 0 & 1 \\
        0 & 1 & 1
    \end{array}
\right) \\
\hat{x} = \begin{pmatrix}1\\1\end{pmatrix} 
$$

Can find the distance from the least squares solution to the desired point as well:

$$
|| A\overrightarrow{x_{LS}} - \overrightarrow{b}|| = ||
\begin{pmatrix}
    1 & 3 \\
    1 & -1 \\
    1 & 1
\end{pmatrix}
\begin{pmatrix}1\\1\end{pmatrix} - 
\begin{pmatrix}5\\1\\0\end{pmatrix}
||
= ||
\begin{pmatrix}4\\0\\2\end{pmatrix} - 
\begin{pmatrix}5\\1\\0\end{pmatrix}
|| =
\sqrt{6}
$$

<hr>

Orthogonal Example

$$
A = \begin{pmatrix}
    1 & 1 \\
    1 & -1 \\
    -1 & 1 \\
    1 & 1
\end{pmatrix},
\overrightarrow{b} = \begin{pmatrix}2\\4\\6\\8\end{pmatrix} \\
\text{Project b onto } Col(A) = Span\{\overrightarrow{v}, \overrightarrow{w}\} \\
\overrightarrow{v} \perp \overrightarrow{w} \text{, so } proj_{Col(A)} (\overrightarrow{b}) = \frac{\overrightarrow{b} \cdot \overrightarrow{v}}{\overrightarrow{v} \cdot \overrightarrow{v}} \overrightarrow{v} +  \frac{\overrightarrow{b} \cdot \overrightarrow{w}}{\overrightarrow{w} \cdot \overrightarrow{w}} \overrightarrow{w} = \begin{pmatrix}5\\-1\\1\\5\end{pmatrix} \\

\left( 
    \begin{array}{cc|c}
        1 & 1 & 5 \\
        1 & -1 & -1\\
        -1 & 1 & 1\\
        1 & 1 & 5
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{cc|c}
        1 & 0 & 2 \\
        0 & -1 & 3\\
        0 & 0 & 0\\
        0 & 0 & 0
    \end{array}
\right)
\hat{x} = \begin{pmatrix} 2 \\ 3 \end{pmatrix}
$$