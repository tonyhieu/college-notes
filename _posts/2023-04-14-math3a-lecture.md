---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Span Properties, Matrix-Vector Multiplication, and Matrix Equations
use-math: true
---

## Span Properties
$$
\text{If }
\overrightarrow{b}, \overrightarrow{c} \in Span\{\overrightarrow{v_1}, ..., \overrightarrow{v_n}\} \\
\text{Then: } \\
\overrightarrow{b} + \overrightarrow{c} \in Span \\
-\overrightarrow{b} \in Span \\
\overrightarrow{0} \in Span \text{ (always true)} \\
\lambda \in \mathbb{R}, \overrightarrow{b} \in Span \rightarrow \lambda * \overrightarrow{b} \in Span
$$

Spans can either have no points (only the zero vector) or an infinite amount of points, but the magnitude of that infinity can vary.

$$
Span\{\overrightarrow{v_1}, ..., \overrightarrow{v_n}\} = \mathbb{R}^m
$$

## Matrix-Vector Multiplication

$$
A = 
\begin{pmatrix}
a_{11} & ... & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{m1} & ... & a_{mn}
\end{pmatrix} \\

\overrightarrow{V} = \begin{pmatrix}v_1 \\ \vdots \\ v_n\end{pmatrix}\\

A * \overrightarrow{V} = 

\begin{pmatrix}
a_{11} & ... & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{m1} & ... & a_{mn}
\end{pmatrix} 

\begin{pmatrix}v_1 \\ \vdots \\ v_n\end{pmatrix} =

\begin{pmatrix}
a_{11}v_1 + a_{12}v_2 + ... + a_{1n}v_n \\
a_{21}v_1 + a_{22}v_2 + ... + a_{2n}v_n \\
\vdots \\
a_{m1}v_1 + a_{m2}v_2 + ... + a_{mn}v_n
\end{pmatrix} \\

A * \overrightarrow{V} = (\overrightarrow{a_1} \ldots \overrightarrow{a_n})\begin{pmatrix}v_1 \\ \vdots \\ v_n\end{pmatrix} = 
v_1\overrightarrow{a_1} + v_2\overrightarrow{a_2} + ... + v_n\overrightarrow{a_n}
$$

### Examples of Matrix-Vector Multiplication

$$
A = \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{pmatrix} \\

\overrightarrow{V} = \begin{pmatrix}1 \\ 0 \\ -1\end{pmatrix} \\

A * \overrightarrow{V} = \begin{pmatrix}-2 \\ -2\end{pmatrix} = -2\begin{pmatrix}1 \\ 1\end{pmatrix}
$$

<hr />

$$
A = \begin{pmatrix}
a & b \\
c & d
\end{pmatrix} \\

\overrightarrow{V} = \begin{pmatrix}x \\ y\end{pmatrix} \\

A * \overrightarrow{V} = \begin{pmatrix}ax + by \\ cx + dy\end{pmatrix}
$$

<hr />

$$
5\overrightarrow{u} - 7\overrightarrow{v} + 3\overrightarrow{w} = \begin{pmatrix}\overrightarrow{u} & \overrightarrow{v} & \overrightarrow{w}\end{pmatrix} \begin{pmatrix}5 \\ -7 \\ 3\end{pmatrix}
$$

## SLEs as Matrix Equations

$$
A * \overrightarrow{x} = \overrightarrow{b} \text{ where } \overrightarrow{x}, \overrightarrow{b} \in \mathbb{R}^m \\

A = 

\begin{pmatrix}
a_{11} & ... & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{m1} & ... & a_{mn}
\end{pmatrix} \\

\overrightarrow{x} = \begin{pmatrix}x_1 \\ \vdots \\ x_n\end{pmatrix} \\

\overrightarrow{b} = \begin{pmatrix}b_1 \\ \vdots \\ b_m\end{pmatrix} \text{ (where b are all constants)} \\

A * \overrightarrow{x} = x_1\overrightarrow{a_1} + \ldots + x_n\overrightarrow{a_n} \\

\text{To find a solution to this, we can create an augmented matrix.} \\
\left( 
    \begin{array}{c|c}
        A & \overrightarrow{b}
    \end{array}
\right) = 
\left( 
    \begin{array}{ccc|c}
        \overrightarrow{a_1} & \ldots & \overrightarrow{a_n} & \overrightarrow{b}
    \end{array}
\right)
$$

### Example

$$
A = \begin{pmatrix}
3 & 0 & 1 \\
1 & -1 & 0 \\
1 & 3 & 4
\end{pmatrix}, \overrightarrow{b} = \begin{pmatrix}1 \\ 1 \\ 2\end{pmatrix} \\

\left( 
    \begin{array}{c|c}
        A & \overrightarrow{b}
    \end{array}
\right) = 
\left( 
    \begin{array}{ccc|c}
        3 & 0 & 1 & 1 \\
        1 & -1 & 0 & 1 \\
        1 & 3 & 4 & 2 \\
    \end{array}
\right) = 
\left( 
    \begin{array}{ccc|c}
        1 & 0 & 0 & -\frac{1}{8} \\
        0 & 1 & 0 & -\frac{9}{8}  \\
        0 & 0 & 1 & \frac{11}{8}  \\
    \end{array}
\right) \\
\text{Thus, } A \begin{pmatrix} -\frac{1}{8} \\ -\frac{9}{8} \\ \frac{11}{8} \end{pmatrix} = \overrightarrow{b}
$$

## Properties of Matrix-Vector Multiplication

$$
A * (\overrightarrow{v} + \overrightarrow{w}) = A * \overrightarrow{v} + A * \overrightarrow{w} \\
A * (c * \overrightarrow{v}) = c * (A * \overrightarrow{v})
$$

## Row Theorem

$$
\text{Suppose we have }\overrightarrow{a_1}, \ldots, \overrightarrow{a_n} \in \mathbb{R}^m \\
\text{Letting } A = (\overrightarrow{a_1}, \ldots, \overrightarrow{a_n}) \text{, the following statements are equivalent. (They're all true or all false)}\\
\text{1. } Span\{\overrightarrow{a_1}, \ldots, \overrightarrow{a_n}\} = \mathbb{R}^m \\
\text{2. } A\overrightarrow{x} = \overrightarrow{b} \text{ is consistent for every } \overrightarrow{b} \\
\text{3. The RREF of A has a pivot in every row}
$$

### Example

$$
\overrightarrow{u}, \overrightarrow{v}, \overrightarrow{w} \in \mathbb{R}^4 \\
\text{Can } Span\{\overrightarrow{u}, \overrightarrow{v}, \overrightarrow{w}\} = \mathbb{R}^4\text{?}\\

A = \begin{pmatrix}
u_1 & v_1 & w_1 \\
\vdots & \vdots & \vdots \\
u_4 & v_4 & w_4
\end{pmatrix} \\
\text{Because there is at least one row that does not have a pivot, all of the parts of the theorem are not true. Therefore, it does not span R4.}
$$