---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Linear Combinations of Vectors
use-math: true
---

$$
\text{A system of vectors:} \\
\overrightarrow{v_1}, ..., \overrightarrow{v_n} \in \mathbb{R}^m \\
\text{And a system of scalars:} \\
c_1, ..., c_n \in \mathbb{R} \\
\text{Can combine to create one unique vector:} \\
c_1\overrightarrow{v_1} + ... + c_n\overrightarrow{v_n}
$$

$$
\text{Example:}\\
2\begin{bmatrix}-1 \\ 0 \\ 1\end{bmatrix} + 1\begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix} - 3\begin{bmatrix}0 \\ 1 \\ 1\end{bmatrix} = 
\begin{bmatrix}-2 \\ 0 \\ 2\end{bmatrix} + \begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix} \begin{bmatrix}0 \\ -3 \\ -3\end{bmatrix} = 
\begin{bmatrix}-2 \\ -2 \\ -1\end{bmatrix}
$$

## Vector Equations

What if, instead of specific numbers, we replaced the values of vectors/scalars with variables?

$$
\text{Variables are denoted as such: } x_1, x_2, ..., x_n \\
\text{Vectors are denoted as such: } \overrightarrow{v_1}, \overrightarrow{v_2}, ..., \overrightarrow{v_n}, \overrightarrow{b} \in \mathbb{R}^m \text{ where b represents constants.}\\
\text{The corresponding vector equation would be: } x_1\overrightarrow{v_1} + x_2\overrightarrow{v_2} + ... + x_n\overrightarrow{v_n} = \overrightarrow{b}
$$

$$
\text{Example: } \\
x\begin{bmatrix}-1 \\ 0 \\ 1\end{bmatrix} + y\begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix} + z\begin{bmatrix}0 \\ 1 \\ 1\end{bmatrix} = \begin{bmatrix}-2 \\ -2 \\ -1\end{bmatrix} \\
\text{has a solution of x = 2, y = 1, z = -3 as shown above.}
\\
\text{We can also rewrite this as } \begin{bmatrix}-x\\ y + z\\ x + z\end{bmatrix} = \begin{bmatrix}-2\\-2\\-1\end{bmatrix} \text{ using vector addition.}
$$

## Solving Vector Equations

$$
\text{We can rewrite a vector equation into an augmented matrix where each of the columns are represented by the vectors.} \\
\overrightarrow{v_1}, \overrightarrow{v_2}, ..., \overrightarrow{v_n}, \overrightarrow{b} \in \mathbb{R}^m \\

\left( 
    \begin{array}{cccc|c}
        \overrightarrow{v_1} & \overrightarrow{v_2} & ... & \overrightarrow{v_n} & \overrightarrow{b}
    \end{array}
\right) \\
$$

For example,

$$
x\begin{bmatrix}-1 \\ 0 \\ 1\end{bmatrix} + y\begin{bmatrix}0 \\ 1 \\ 0\end{bmatrix} + z\begin{bmatrix}0 \\ 1 \\ 1\end{bmatrix} = \begin{bmatrix}-2 \\ -2 \\ -1\end{bmatrix} \\
\text{can be converted into} \\
\left( 
    \begin{array}{ccc|c}
        -1 & 0 & 0 & -2 \\
        0 & 1 & 1 & -2 \\
        1 & 0 & 1 & -1
    \end{array}
\right) \rightarrow 

\left( 
    \begin{array}{ccc|c}
        1 & 0 & 1 & -1 \\
        0 & 1 & 1 & -2 \\
        -1 & 0 & 0 & -2 \\
    \end{array}
\right) \rightarrow

\left( 
    \begin{array}{ccc|c}
        1 & 0 & 1 & -1 \\
        0 & 1 & 1 & -2 \\
        0 & 0 & 1 & -3 \\
    \end{array}
\right) \rightarrow

\left( 
    \begin{array}{ccc|c}
        1 & 0 & 0 & 2 \\
        0 & 1 & 0 & 1 \\
        0 & 0 & 1 & -3 \\
    \end{array}
\right)

$$

## The Span of a System of Linear Equations

$$
\text{Let some vectors be defined as } \overrightarrow{v_1}, \overrightarrow{v_2}, ..., \overrightarrow{v_n} \in \mathbb{R}^m \\

Span\{\overrightarrow{v_1}, \overrightarrow{v_2}, ..., \overrightarrow{v_n}\} = 
\text{The set of all combinations in the form } c_1\overrightarrow{v_1} + ... + c_n\overrightarrow{v_n} = 
\text{The set of all } \overrightarrow{b} \text{ such that } c_1\overrightarrow{v_1} + ... + c_n\overrightarrow{v_n} = \overrightarrow{b} \text{ is consistent (has a solution).}
$$


$$
\text{Examples: }\\
\text{This span represents a single line: x = 1} \\
Span\{\begin{bmatrix}1\\0\end{bmatrix}\} \subset \mathbb{R}^2 = \text{Set of } t\begin{bmatrix}1\\0\end{bmatrix} = \begin{bmatrix}t\\0\end{bmatrix}\\
\text{This span represents a single line: x = y } \\
Span\{\begin{bmatrix}1\\1\end{bmatrix}\} \subset \mathbb{R}^2 = \text{Set of } t\begin{bmatrix}1\\1\end{bmatrix}\\

\text{This span represents the entire x, y plane} \\
Span\{\begin{bmatrix}1\\0\end{bmatrix}, \begin{bmatrix}1\\1\end{bmatrix}\} \\
\text{Proof:} \\
\text{Let any point on the x, y plane be represented by the vector } \begin{pmatrix}x \\ y\end{pmatrix} \\
\begin{pmatrix}x \\ y\end{pmatrix} \\
= \begin{pmatrix}x \\ 0\end{pmatrix} + \begin{pmatrix}0 \\ y\end{pmatrix} \\
= x\begin{pmatrix}1 \\ 0\end{pmatrix} + y\begin{pmatrix}0 \\ 1\end{pmatrix} \\
= x\begin{pmatrix}1 \\ 0\end{pmatrix} + y[\begin{pmatrix}1 \\ 1\end{pmatrix} - \begin{pmatrix}1 \\ 0\end{pmatrix}] \\
= (x - y)\begin{pmatrix}1 \\ 0\end{pmatrix} + y\begin{pmatrix}1 \\ 1\end{pmatrix}\\

\text{Therefore, any point (x,y) can be rewritten as a combination of vectors defined by the span.} \\
\text{Intuitively, this proof shows that you can "adjust x" according to your y value to get any point on the plane.}
$$

The span of n vectors does NOT have to necessarily span n dimensions; if there is redundant/not enough information, the span can cover fewer dimensions. Also, spans might not be unique; muiltple combinations of vectors can have the same span. 

Two vectors that inhabit the same line are said to be **colinear**. That is, if two vectors are a scalar multiple of one another, then they are colinear.

$$
Span\{\overrightarrow{v_1}, \overrightarrow{v_2}\} \text{ will either be a line if colinear or a plane if not.}
$$