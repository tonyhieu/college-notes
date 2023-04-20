---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Row Theorem and Homogeneous SLEs
use-math: true
---

Example of using Row Theorem to prove a statement


$$
Span\{\begin{pmatrix}1\\1\\0\end{pmatrix}, \begin{pmatrix}1\\0\\1\end{pmatrix}, \begin{pmatrix}0\\1\\1\end{pmatrix} \} = \mathbb{R}^3?\\

\begin{pmatrix}
    1 & 1 & 0 \\
    1 & 0 & 1 \\
    0 & 1 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 1 & 0 \\
    0 & -1 & 1 \\
    0 & 1 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 1 & 0 \\
    0 & -1 & 1 \\
    0 & 0 & 2
\end{pmatrix} \rightarrow \\
\begin{pmatrix}
    1 & 0 & 1 \\
    0 & -1 & 1 \\
    0 & 0 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 0 & 0 \\
    0 & 1 & -1 \\
    0 & 0 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
\end{pmatrix} \\
\text{Because there is a pivot in every row, the span must be equal to } \mathbb{R}^3
$$

## Homogeneous SLE's

$$
\text{A SLE is \underline{homogeneous} if its matrix equation is of the form } A\overrightarrow{x} = \overrightarrow{0} \text{ and is not homogeneous otherwise.} \\
\text{A solution where } \overrightarrow{x} = \overrightarrow{0} \text{ is a \underline{trivial} solution, as it will always solve } A\overrightarrow{x} = \overrightarrow{0} \text{. Any other solution is \underline{nontrivial}.}
$$

### Example

$$
\text{Does }
\begin{cases}
    3x_1 + 5x_2 - 4x_3 = 0 \\
    -3x_1 -2x_2 + 4x_3 = 0 \\
    6x_1 + x_2 - 8x_3 = 0
\end{cases}
\text{ have a nontrivial solution?} \\

\begin{cases}
    3x_1 + 5x_2 - 4x_3 = 0 \\
    -3x_1 -2x_2 + 4x_3 = 0 \\
    6x_1 + x_2 - 8x_3 = 0
\end{cases} \rightarrow

\begin{pmatrix}
    3 & 5 & -4 \\
    -3 & -2 & 4 \\
    6 & 1 & -8
\end{pmatrix}
\begin{pmatrix}
    x_1 \\ x_2 \\ x_3
\end{pmatrix} = 
\begin{pmatrix}
    0 \\ 0 \\ 0
\end{pmatrix} \\

\left( 
    \begin{array}{ccc|c}
        3 & 5 & -4 & 0 \\
        -3 & -2 & 4 & 0 \\
        6 & 1 & -8 & 0 \\
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|c}
        3 & 5 & -4 & 0 \\
        0 & 3 & 0 & 0 \\
        0 & -3 & 0 & 0 \\
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|c}
        3 & 5 & -4 & 0 \\
        0 & 1 & 0 & 0 \\
        0 & 0 & 0 & 0 \\
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{ccc|c}
        1 & 0 & -\frac{4}{3} & 0 \\
        0 & 1 & 0 & 0 \\
        0 & 0 & 0 & 0 \\
    \end{array}
\right) \\
\begin{cases}
    x_1 = \frac{4}{3} \\ 
    x_2 = 0 \\
    x_3 = x_3 \\
\end{cases} =
x_3
\begin{pmatrix}
    \frac{4}{3} \\
    0 \\
    1
\end{pmatrix}
\text{ solves the matrix equation.} \\
\text{Thus, there ARE nontrivial solutions to the system of equations, as the final vector found is not the 0 vector}
$$

$$
A\overrightarrow{x} = \overrightarrow{0} \text{ has nontrivial solutions whenever there are free variables but will not if there are no free variables.}
$$

### Relating b vector to zero vector

$$
\text{The general solution to } A\overrightarrow{x} = \overrightarrow{b} \text{ is } \overrightarrow{x} = \overrightarrow{x_0} + \overrightarrow{x_p} \\
\text{ where } \overrightarrow{x_p} \text{ is a particular solution to } A\overrightarrow{x} = \overrightarrow{b} \text{ and } \overrightarrow{x_0} \text{ is the general solution to } A\overrightarrow{x} = \overrightarrow{0}
$$

### Example

$$
A = 
\begin{pmatrix}
    1 & 0 & 1 & 0 \\
    1 & 2 & 3 & 4 \\
    4 & 8 & 12 & 16 \\
    6 & 12 & 18 & 24
\end{pmatrix} \\
\overrightarrow{b} = 
\begin{pmatrix} 0\\-2\\-8\\-12\end{pmatrix} \\
\text{Suppose we know that } \overrightarrow{x_p} = \begin{pmatrix}1\\0\\-1\\0\end{pmatrix} \text{ solves } A\overrightarrow{x} = \overrightarrow{b} \\
\text{Solve } A\overrightarrow{x} = \overrightarrow{0} \text{ and add } \overrightarrow{x_0} \text{ to } \overrightarrow{x_p} \\

\left( 
    \begin{array}{c|c}
        A & \overrightarrow{0}
    \end{array}
\right) = 
\left( 
    \begin{array}{cccc|c}
        1 & 0 & 1 & 0 & 0\\
        1 & 2 & 3 & 4 & 0\\
        4 & 8 & 12 & 16 & 0\\
        6 & 12 & 18 & 24 & 0
    \end{array}
\right) \rightarrow
\left( 
    \begin{array}{cccc|c}
        1 & 0 & 1 & 0 & 0\\
        0 & 1 & 1 & 2 & 0\\
        0 & 0 & 0 & 0 & 0\\
        0 & 0 & 0 & 0 & 0
    \end{array}
\right) \\
\text{Because there are no pivots in the last two columns, z and w are free variables.} \\
x + z = 0 \rightarrow x = -z \\
y + z + 2w = 0 \rightarrow y = -z - 2w \\
\overrightarrow{x_0} = \begin{pmatrix}x\\ y\\ z\\ w\end{pmatrix} = 
\begin{pmatrix}
    -z \\
    -z - 2w\\
    z\\
    w
\end{pmatrix} =
\begin{pmatrix}
    -z \\
    -z \\
    z\\
    0
\end{pmatrix} + 
\begin{pmatrix}
    0 \\
    -2w \\
    0\\
    w
\end{pmatrix} =
z
\begin{pmatrix}
    -1 \\
    -1 \\
    1\\
    0
\end{pmatrix} + 
w
\begin{pmatrix}
    0 \\
    -2 \\
    0\\
    1
\end{pmatrix} \\

\overrightarrow{x} = \overrightarrow{x_0} + \overrightarrow{x_p} = 
z
\begin{pmatrix}
    -1 \\
    -1 \\
    1\\
    0
\end{pmatrix} + 
w
\begin{pmatrix}
    0 \\
    -2 \\
    0\\
    1
\end{pmatrix} +
\begin{pmatrix}
    1 \\
    0 \\
    -1\\
    0
\end{pmatrix}
$$