---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Linear Transformations and Functions
use-math: true
---

## Linear Transformations

$$
\text{The matrix }
\begin{pmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6
\end{pmatrix}
\text{ takes elements of } \mathbb{R}^3 \text{ and outputs elements of } \mathbb{R}^2 \\
\begin{pmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6
\end{pmatrix}
\begin{pmatrix}a \\ b \\ c\end{pmatrix} = 
\begin{pmatrix}
    a + 2b + 3c \\
    4a + 5b + 6c
\end{pmatrix} \\
\text{In other words, it defines a \underline{function} from } \mathbb{R}^3 \text{ to } \mathbb{R}^2 \\
$$

## Linear functions

A function takes elements from one set (known as the domain) and outputs elements of another set (known as the range or codomain).

Multiplying by a m * n matrix (where m is the number of columns and n is the number of rows) defines a function that maps elements from R<sup>n</sup> to R<sup>m</sup>.

$$
T: \mathbb{R}^n \rightarrow \mathbb{R}^m
\text{ is linear if} \\
T(\overrightarrow{v} + \overrightarrow{w}) = T(\overrightarrow{v}) + T(\overrightarrow{w}) \text{ and } T(\lambda \overrightarrow{v}) = \lambda T(\overrightarrow{v})
$$

### Classic examples of linear functions
$$
T\begin{pmatrix}x \\ y \end{pmatrix} = x + y \\
T(\overrightarrow{v}) = A\overrightarrow{v}
$$

### Properties of linear functions

$$
\text{Assume that } T: \mathbb{R}^n \rightarrow \mathbb{R}^m \text{ is linear. Then:} \\
T(\overrightarrow{0}) = \overrightarrow{0} \\
T(a\overrightarrow{v} + b\overrightarrow{w}) = a * T(\overrightarrow{v}) + b * T(\overrightarrow{w}) \\
T(c_1\overrightarrow{v}_1 + ... + c_n\overrightarrow{v}_n) = c_1 * T(\overrightarrow{v}_1) + ... + c_n * T(\overrightarrow{v}_n)
$$

## Composition of Linear Functions

$$
\text{Suppose we have linear functions f and g such that } f: \mathbb{R}^n \rightarrow \mathbb{R}^m \text{ and } g: \mathbb{R}^m \rightarrow \mathbb{R}^k \\
\text{We can compose these functions to transfer a vector from } \mathbb{R}^n \text{ to } \mathbb{R}^k \text{ by using the functions like } f(g(\overrightarrow{x})) \text{. This new function is denoted as } g \circ f \text{.}
$$


$$
\text{Theorem: If } T: \mathbb{R}^n \rightarrow \mathbb{R}^m \text{ and } S: \mathbb{R}^m \rightarrow \mathbb{R}^k \text{ are both linear, then so is }
S \circ T: \mathbb{R}^n \rightarrow \mathbb{R}^k \\

(S \circ T)(\lambda \overrightarrow{v}) = S(\lambda T(\overrightarrow{v})) = \lambda S(T(\overrightarrow{v})) = \lambda (S \circ T)(\overrightarrow{v})
$$

Matrix multiplication is a linear function that can be composed, as shown below

$$
\begin{pmatrix}
    0 & 1 \\
    -1 & 0
\end{pmatrix} \text{ and }
\begin{pmatrix}
    1 & 0 & 1 \\
    1 & 1 & -1
\end{pmatrix} \\

\text{Multiplying a vector by the first matrix can be thought of as a function that spans } \mathbb{R}^2 \rightarrow \mathbb{R}^2 \text{ with the second matrix being } \mathbb{R}^3 \rightarrow \mathbb{R}^2 \\

\begin{pmatrix}
    0 & 1 \\
    -1 & 0
\end{pmatrix}
\begin{pmatrix}
    1 & 0 & 1 \\
    1 & 1 & -1
\end{pmatrix}
\begin{pmatrix}a \\ b \\ c \end{pmatrix} = \\

\begin{pmatrix}
    0 & 1 \\
    -1 & 0
\end{pmatrix}
\begin{pmatrix}
    a + c \\
    a + b - c
\end{pmatrix} = \\
\begin{pmatrix}
    a + b - c \\
    -a - c
\end{pmatrix}
$$

You can add linear functions, as well:

$$
\text{If } T: \mathbb{R}^n \rightarrow \mathbb{R}^m \text{ and } S: \mathbb{R}^n \rightarrow \mathbb{R}^m \text{ are both linear, then } \\
S + T: \mathbb{R}^n \rightarrow \mathbb{R}^m \text{ is linear and } (S + T)(\overrightarrow{v}) = S(\overrightarrow{v}) + T(\overrightarrow{v})
$$

This can be used in matrix addition:

$$
(
\begin{pmatrix}
    0 & 1 \\
    -1 & 0
\end{pmatrix} + 
\begin{pmatrix}
    \sqrt{2} & 0 \\
    0 & \frac{1}{\sqrt{2}}
\end{pmatrix}
)
\begin{pmatrix} a \\ b \end{pmatrix} = 

\begin{pmatrix} b \\ -a \end{pmatrix} + 
\begin{pmatrix} a\sqrt{2} \\ \frac{b}{\sqrt{2}} \end{pmatrix} = 

\begin{pmatrix} b + a\sqrt{2} \\ \frac{b}{\sqrt{2}} - a \end{pmatrix}
$$

## Unit Vector With Linear Functions
$$
\text{The unit vector is defined as } \hat{e}_i \in \mathbb{R}^n \\
\hat{e}_i = \begin{pmatrix} 0 \\ \vdots \\ 0 \\ 1 \\ 0 \\ \vdots \\ 0 \end{pmatrix} \text{ where the 1 is in the ith position} \\

\begin{pmatrix} a_1 \\ \vdots \\ a \\ \vdots \\ a_n\end{pmatrix} = \begin{pmatrix} a_1 \\ \vdots \\ 0 \\ \vdots \\ 0\end{pmatrix} +  \begin{pmatrix} 0 \\ \vdots \\ a \\ \vdots \\ 0\end{pmatrix} + \begin{pmatrix}0 \\ \vdots \\ 0 \\ \vdots \\ a_n \end{pmatrix} = a_1\hat{e}_1 + a_i\hat{e}_i + a_n\hat{e}_n
$$

$$
T: \mathbb{R}^n \rightarrow \mathbb{R}^m \\
\overrightarrow{v} = a_1\hat{e}_1 + ... + a_n\hat{e}_n \\
T(\overrightarrow{v}) = T(a_1\hat{e}_1 + ... + a_n\hat{e}_n) = a_1T(\hat{e}_1) + ... + a_nT(\hat{e}_n) = \begin{pmatrix} T(\hat{e}_1) & ... & T(\hat{e}_n)\end{pmatrix} \begin{pmatrix}a_1 \\ \vdots \\ a_n \end{pmatrix}
$$

### Example of how to get matrix multiplication from a function
$$
T \begin{pmatrix}a \\ b \\ c\end{pmatrix} = 
\begin{pmatrix}
    a + 2b - c \\
    3a - 4b + 2c \\
    5a + 7b + c
\end{pmatrix} \\
\hat{e}_1 = \begin{pmatrix}1\\0\\0\end{pmatrix}, \hat{e}_2 = \begin{pmatrix}0\\1\\0\end{pmatrix}, \hat{e}_3 = \begin{pmatrix}0\\0\\1\end{pmatrix} \\
T\begin{pmatrix}1\\0\\0\end{pmatrix} = \begin{pmatrix}1\\3\\5\end{pmatrix}, T\begin{pmatrix}0\\1\\0\end{pmatrix} = \begin{pmatrix}2\\-4\\7\end{pmatrix}, T\begin{pmatrix}0\\0\\1\end{pmatrix} = \begin{pmatrix}-1\\2\\1\end{pmatrix} \\
A_T = 
\begin{pmatrix}
    1 & 2 & -1 \\
    3 & -4 & 2 \\
    5 & 7 & 1
\end{pmatrix}
\begin{pmatrix}a\\ b\\ c\end{pmatrix}

$$

## Matrix Multiplication
$$
\text{Let A represent a matrix.}\\
A * \begin{pmatrix} \overrightarrow{v_1} & ... & \overrightarrow{v_n} \end{pmatrix} =
\begin{pmatrix} A \overrightarrow{v_1} & ... & A \overrightarrow{v_n} \end{pmatrix}
$$

### Examples
$$
\begin{pmatrix}
    1 & 7\\
    2 & 4 
\end{pmatrix}
\begin{pmatrix}
    3 & 3\\
    5 & 2 
\end{pmatrix} = 
\begin{pmatrix}
    1*3 + 7*5 & 1*3 + 7*2\\
    2*3 + 4*5 & 2*3 + 4*2 
\end{pmatrix} =
\begin{pmatrix}
    38 & 17\\
    26 & 14 
\end{pmatrix}
$$

$$
\begin{pmatrix}
    1 & 3 & -4\\
    0 & 1 & -1\\
    0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
    1 & -1 \\
    6 & 2 \\
    -3 & 1
\end{pmatrix} =
(A\begin{pmatrix}1\\6\\-3\end{pmatrix} A\begin{pmatrix}-1\\2\\1\end{pmatrix}) = 
(
\begin{pmatrix}
    1*1 + 3*6 + (-4)(-3) \\
    0*1 + 1*6 + (-1)*(-3) \\
    0*1 + 0*6 + 1*(-3)
\end{pmatrix}
\begin{pmatrix}
    1*(-1) + 3*2 + (-4)*1 \\
    0*(-1) + 1*2 + (-1)*1 \\
    0*(-1) + 0*2 + 1*1
\end{pmatrix}
)
$$