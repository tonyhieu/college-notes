---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Rref Algorithm, Free Variables, and Vectors
use-math: true
---

## Complete Row Reduction Algorithm

1. 
- Ensure that the first row starts with a leftmost nonzero entry, swapping if needed
- Scale (divide) the first row so that the pivit position = 1
- Clear down (make all of the other rows have a 0 in the first/leftmost position using subtraction)
2. 
- Move the leftmost nonzero entry to row 2, swapping if needed
- Scale the second row so the pivot position = 1
- Clear down again
3. 
- Repeat as needed until the matrix reaches row echelon form
4. 
- Clear up so that there are zeroes above the pivots as well

If the last column is a pivot column, then there are no solutions. If it isn't, then if all columns other than the last one are pivot columns, the matrix has only one solution. If neither are true, then the matrix has infinitely many solutions.

## Free Variables

**Free variables** are variables that do not affect the solution to an equation, as the other variables predetermine their values. *The number of columns without pivots (or non-pivot columns) correspond to free variables.*

$$
\left( 
    \begin{array}{cc|c}
        1 & 1 & 2
    \end{array}
\right) \\
\text{corresponds to x + y = 2, where y is a free variable because it is in a column without pivots.}
$$

$$
\left( 
    \begin{array}{cccc|c}
        1 & 1 & 0 & 0 & 2 \\
        0 & 0 & 0 & 0 & 0
    \end{array}
\right) \\
\text{also corresponds to x + y = 2, but because the matrix considers more free space, y, w, and z are all free variables.}
$$

The number of free variables determines the solution set/geometry of the solution. 0 free variables means the solution is a point, 1 means the solution is a line, 2 means its a plane, 3 means its a hyperplane/volume, etc.

## Vectors

$$
\text{Vectors are typically represented as } \mathbb{R}^n \text{, where n represents the number of values in the vector.}\\

\mathbb{R}^n = 
\begin{bmatrix}
a_1 \\
a_2 \\
a_3 \\
\vdots \\
a_n
\end{bmatrix} \\

\text{A vector in } \mathbb{R}^n \text{can be seen as an arrow from the origin to a point.} \\

\begin{bmatrix}
4 \\
3
\end{bmatrix} (0, 0)

\text{ represents an arrow from (0,0) to (4, 3)}
$$

## Vector operations

$$
\overrightarrow{v} = 
\begin{bmatrix}
v_1 \\
\vdots \\
v_n
\end{bmatrix}

\text{ and }

\overrightarrow{w} = 
\begin{bmatrix}
w_1 \\
\vdots \\
w_n
\end{bmatrix}

\text{ in } \mathbb{R}^n \\

\text{Vector addition:} \\
\overrightarrow{v} + \overrightarrow{w} = 
\begin{bmatrix}
v_1 + w_1 \\
\vdots \\
v_n + w_n
\end{bmatrix} \\

\text{Scalar multiplication:} \\
r \cdot \overrightarrow{v} = 
\begin{bmatrix}
rv_1 \\
\vdots \\
rv_n
\end{bmatrix}

\\ \text{Examples:} \\

\text{Note: For vector addition, you cannot add vectors with different sizes.} \\ \\
\begin{bmatrix}
5 \\
3
\end{bmatrix} 

+

\begin{bmatrix}
-11 \\
2
\end{bmatrix}

=

\begin{bmatrix}
-6 \\
5
\end{bmatrix} \\

\begin{bmatrix}
4 \\
0 \\
2
\end{bmatrix} 

+

\begin{bmatrix}
3 \\
4 \\
2
\end{bmatrix}

=

\begin{bmatrix}
7 \\
4 \\
5
\end{bmatrix} \\

2\begin{bmatrix}
5 \\
4
\end{bmatrix} =
\begin{bmatrix}
10 \\
8
\end{bmatrix}
$$

Geometrically, vector addition can be represented as one of the vectors being drawn from the tip of the other arrow. 
![image](https://user-images.githubusercontent.com/54915685/231003671-09af1a91-29f2-441e-a9ca-c4f37b0cfbb7.png)

Scalar multiplication can be represented as a vector being scaled up/down by a given quantity.
![image](https://user-images.githubusercontent.com/54915685/231003902-cdffdf31-59e2-4970-aa12-8b7c9e929fa0.png)

$$
\text{The zero vector is used for every dimension, and is often denoted as:} \\
\overrightarrow{0} = \begin{bmatrix} 0 \\ \vdots \\ 0\end{bmatrix} \\

\text{A vector equation is another way to represent augmented matrices/systems of equations. They look like this:} \\
x_1\overrightarrow{v_1} + ... + x_n\overrightarrow{v_n} = \overrightarrow{b}\\

\text{For example:}\\
x\begin{bmatrix}1 \\ 2 \\ 3\end{bmatrix} + y\begin{bmatrix}4 \\ 5 \\ 6\end{bmatrix} + z\begin{bmatrix}7 \\ 8 \\ 9\end{bmatrix} = \begin{bmatrix}20 \\ 30 \\ 40\end{bmatrix} \rightarrow
\left( 
    \begin{array}{ccc|c}
        1 & 4 & 7 & 20 \\
        2 & 5 & 8 & 30 \\
        3 & 6 & 9 & 40
    \end{array}
\right) \\

\begin{cases}
3x + 2y - z = 4 \\
2x - y + z = 3
\end{cases} \rightarrow
x\begin{bmatrix}3 \\ 2\end{bmatrix} + y\begin{bmatrix}2 \\ -1\end{bmatrix} + z\begin{bmatrix}-1 \\ 1\end{bmatrix} = \begin{bmatrix}4 \\ 3\end{bmatrix} \\

\text{Therefore, a vector equation can be represented as an augmented matrix and solved through row reduction.}
$$