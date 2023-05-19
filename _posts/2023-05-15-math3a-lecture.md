---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Applications of Determinants
use-math: true
---

## Shortcut to Calculate 3x3 Determinants

$$
\begin{pmatrix}
    2 & -5 & 3 \\
    1 & 7 & -2 \\
    -1 & 4 & 1
\end{pmatrix} \\

\text{Add the first two columns to the end}\\

\begin{array}{ccc|cc}
    2 & -5 & 3 & 2 & -5\\
    1 & 7 & -2 & 1 & 7 \\
    -1 & 4 & 1 & -1 & 4
\end{array} \\

\text{Add the right-slanting diagonals and subtract the left-slanting diagonals} \\

(2 * 7 * 1) + (-5 * -2 * -1) + (3 * 1 * 4) - (3 * 7 * -1) - (2 * -2 * 4) - (-5 * 1 * 1) = 58

$$

### Extra Example

$$
det(\begin{pmatrix}
    1 & 2 & 3 \\
    1 & 0 & 1 \\
    4 & 5 & 0
\end{pmatrix}) = 
-1 * det(\begin{pmatrix}
    2 & 3 \\
    5 & 0
\end{pmatrix}) - 1 * det(\begin{pmatrix}
    1 & 2 \\
    4 & 5
\end{pmatrix}) = 15 + 3 = 18
$$


## Cramer's Rule

Suppose that A is an n x n matrix such that we know that the determinant is non-zero. Then, Ax = b is uniquely solvable (by the IVT) and the solution is given by coordinates x<sub>i</sub> = det(A<sub>i</sub>)/det(A) where A<sub>i</sub> is the same as A but the ith column is replaced by b

### Example

$$
\text{Cramer's Rule}\\
\begin{cases}
    -5x + 3y = 9 \\
    3x - y = -5
\end{cases} \rightarrow
\begin{pmatrix}
    -5 & 3 \\
    3 & -1
\end{pmatrix} \begin{pmatrix}x \\ y \end{pmatrix} = \begin{pmatrix}9\\-5\end{pmatrix} \\
det(\begin{pmatrix}
    -5 & 3 \\
    3 & -1
\end{pmatrix}) = -4 \\
x = \frac{det(\begin{pmatrix}
    9 & 3 \\
    -5 & -1
\end{pmatrix})}{det(\begin{pmatrix}
    -5 & 3 \\
    3 & -1
\end{pmatrix})} = \frac{6}{-4} = -\frac{3}{2} \\
y = \frac{det(\begin{pmatrix}
    -5 & 9 \\
    3 & -5
\end{pmatrix})}{det(\begin{pmatrix}
    -5 & 3 \\
    3 & -1
\end{pmatrix})} = \frac{-2}{-4} = \frac{1}{2} \\
\overrightarrow{x} = \begin{pmatrix} -\frac{3}{2} \\ \frac{1}{2} \end{pmatrix}
$$

## Determinants as Volume/Areas

A 2x2 matrix has two columns; representing the columns as vectors gives us a parallelogram in two dimensions. The area of this parallelogram is equal to the absolute value of the matrix's determinant.

For example, a parallelogram represented by vectors (-2, 3) and (3, 0) will have an area equal to the determinant of the matrix 

$$
\begin{pmatrix}
    -2 & 3 \\
    3 & 0
\end{pmatrix} \rightarrow abs(-9) = 9 
$$

For a parallelopiped represented by the vectors u, v, and w, the volume will be equal to the absolute value of the determinant of the matrix containing columns u, v, and w.

If we take an area R and transform it using linear transformation T into R', then Area(R') = |det(A<sub>T</sub>)| * Area(R).

### Example

$$
\text{Find the area of a triangle with vertices } \overrightarrow{0}, \begin{pmatrix} 3 \\ -2\end{pmatrix}, \begin{pmatrix} 2 \\ 2\end{pmatrix} \\
\text{We will use the right triangle represented by vertices} \overrightarrow{0}, \begin{pmatrix} 1 \\ 0\end{pmatrix}, \begin{pmatrix} 0 \\ 1\end{pmatrix} \text{ as our first area R} \\
R * \begin{pmatrix}3 & 2 \\ -2 & 2 \end{pmatrix} = R'\\
Area(R) = 0.5, Area(R') = (6 + 4) * 0.5 = 5
$$

### Volume of an Ellipsoid

Vol(R') = |det(A)| * Vol(R)

### Example

$$
\text{Find the volume of the ellipsoid } (\frac{x}{a})^2 + (\frac{y}{b})^2 + (\frac{z}{c})^2 ≤ 1 \\
\text{Use the unit sphere as a basis, with vectors }
\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} \\
\text{The ellipsoid will have the new vectors } \begin{pmatrix} a \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ b \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 0 \\ c \end{pmatrix} \\
\text{This linear transofrmation can be represented by the matrix }
\begin{pmatrix}
    a & 0 & 0 \\
    0 & b & 0 \\
    0 & 0 & c
\end{pmatrix} \\
Vol(R') = abs(det(\begin{pmatrix}
    a & 0 & 0 \\
    0 & b & 0 \\
    0 & 0 & c
\end{pmatrix})) * Vol(R) = abc * \frac{4}{3} \pi = \frac{4}{3} \pi abc

$$