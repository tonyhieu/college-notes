---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Solving Systems of Linear Equations
use-math: true
---

## Inefficient Way of Solving SLEs

$$
\begin{cases}
R_1 = x + 2y + 3z = 6 \\
R_2 = 2x - 3y + 2z = 14 \\
R_3 = 3x + y - z = 2
\end{cases} \\

\text{Subtract } R_1 \text{ from } R_2 \text{ and } R_3 \\

\begin{cases}
R_1 = x + 2y + 3z = 6 \\
R_2 - 2R_1 = -7y - 4z = 2 \\
R_3 - 3R_1 = -5y - 10z = -20 = -5(y + 2z = 4)
\end{cases} \\

\text{Swap row 2 and row 3 for simplicity, and divide out the -5 from the new row 2.} \\

\begin{cases}
R_1 = x + 2y + 3z = 6 \\
R_2 = y + 2z = 4 \\
R_3 = -7y - 4z = 2
\end{cases} \\

\text{From here, you can isolate the y and x variables and solve for them.} \\

\begin{cases}
R_1 = x + 2y + 3z = 6 \\
R_2 = y + 2z = 4 \\
R_3 + 7R_2 = 10z = 30 \rightarrow z = 3
\end{cases} \\

\text{Use back substitution to solve for other variables.} \\

R_2 = y + 2(3) = 4 \rightarrow y = -2 \\
R_1 = x + 2(-2) + 3(3) = 6 \rightarrow x = 1 \\

\text{Thus, the answer is: } x = 1, y = -2, z = 3
$$

## Solving SLEs with matrices

$$
\text{First, convert the system to an augmented matrix, augmented meaning that there is a line separating variables from constants.} \\

\begin{cases}
x + 2y + z = 0 \\
x - y + 3z = -2 \\
3x - z = 4
\end{cases} \rightarrow

\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        1 & -1 & 3 & -2 \\
        3 & 0 & -1 & 4
    \end{array}
\right) \\

\text{Use the same process of removing one coefficient at a time.}\\

R_2 - R_1, R_3 - 3R_1\\
\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        0 & -3 & 2 & -2 \\
        0 & -6 & -4 & 4
    \end{array}
\right) \\ \\

R_3 - 2R_1 \\
\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        0 & -3 & 2 & -2 \\
        0 & 0 & -8 & 8
    \end{array}
\right) \\

\text{Convert back into system of equations and perform back substitution}\\

\begin{cases}
x + 2y + z = 0 \\
-3y + 2z = -2 \\
-8z = 8 \rightarrow z = -1
\end{cases}\\

-3y + 2(-1) = -2 \rightarrow y = 0\\
x + 2(0) + (-1) = 0 \rightarrow x = 1\\

\text{Thus, the answer is } x = 1, y = 0, z = -1

$$

In this method, we use Elementary Row Operations which include the following:
1. Exchanging two rows
$$
\begin{bmatrix}
    2 & 3 & 2\\
    1 & 0 & 4\\
    1 & 1 & 1
\end{bmatrix} \rightarrow

\begin{bmatrix}
    2 & 3 & 2\\
    1 & 1 & 1\\
    1 & 0 & 4
\end{bmatrix}
$$

2. Multiplying or dividing a row by a non-zero constant
$$
\begin{bmatrix}
    2 & 3 & 2\\
    1 & 0 & 4\\
    5 & 5 & 5
\end{bmatrix} \rightarrow

\begin{bmatrix}
    2 & 3 & 2\\
    1 & 0 & 4\\
    1 & 1 & 1
\end{bmatrix}
$$

3. Add or subtract a multiple of one row from another
$$
R_1 - 2R_2
\begin{bmatrix}
    2 & 3 & 2\\
    1 & 0 & 4\\
    1 & 1 & 1
\end{bmatrix} \rightarrow

\begin{bmatrix}
    0 & 3 & -6\\
    1 & 0 & 4\\
    1 & 1 & 1
\end{bmatrix}
$$

All are used to solve systems of linear equations, and importantly, *all operations are reversible*.

## Pivots
In reducing a matrix that represents a system, our goal is to have as many **pivots** as possible and get the matrix down to **row echelon form**. A matrix in row echelon form looks like the following:

$$
\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        0 & -3 & 2 & -2 \\
        0 & 0 & -8 & 8
    \end{array}
\right) \\
$$

As shown above, row echoleon forms have a pivot in every row. A pivot is a value where either everything before (left of) it is a zero and everything below it is a zero (so 1, -3, and -8). It is also effective to reduce down the matrix to a form such as this:

$$
\left( 
    \begin{array}{ccc|c}
        1 & 0 & 0 & x \\
        0 & 1 & 0 & y \\
        0 & 0 & 1 & z
    \end{array}
\right) \\
$$

This is **reduced row echelon form** and is easy to reach when you have the row echelon form.

If the row echelon form has zeroes at the bottom but a nonzero constant such as this:

$$
\left( 
    \begin{array}{ccc|c}
        0 & 1 & 4 & -5 \\
        1 & 3 & 5 & -2 \\
        0 & 0 & 0 & -10
    \end{array}
\right) \\
$$

There are no solutions. 

If the bottom instead looks something like this:

$$
\left( 
    \begin{array}{ccc|c}
        0 & 1 & 4 & -5 \\
        1 & 3 & 5 & -2 \\
        0 & 0 & 0 & 0
    \end{array}
\right) \\
$$

There are infinitely many solutions.