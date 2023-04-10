---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: TBA
use-math: true
---

**Row Reduced Echelon Form** is a matrix with pivots that have a value of 1 and each of the pivots have 0s above and below them

Examples of reduction:

### Example 1

$$
\left( 
    \begin{array}{ccc|c}
        0 & 1 & 2 & 3 \\
        4 & 5 & 6 & 7 \\
        0 & 9 & 10 & 11
    \end{array}
\right) \\
$$

$$
\left( 
    \begin{array}{ccc|c}
        4 & 5 & 6 & 7 \\
        0 & 1 & 2 & 3 \\
        0 & 9 & 10 & 11
    \end{array}
\right) \\
$$

$$
\left( 
    \begin{array}{ccc|c}
        4 & 5 & 6 & 7 \\
        0 & 1 & 2 & 3 \\
        0 & 0 & -8 & -16
    \end{array}
\right) \\
$$

$$
\left( 
    \begin{array}{ccc|c}
        4 & 5 & 6 & 7 \\
        0 & 1 & 2 & 3 \\
        0 & 0 & 1 & 2
    \end{array}
\right) \\
$$

$$
\left( 
    \begin{array}{ccc|c}
        4 & 5 & 6 & 7 \\
        0 & 1 & 0 & -1 \\
        0 & 0 & 1 & 2
    \end{array}
\right) \\
$$

**Row Reduced Echelon Form:**

$$
\left( 
    \begin{array}{ccc|c}
        1 & 0 & 0 & 0 \\
        0 & 1 & 0 & -1 \\
        0 & 0 & 1 & 2
    \end{array}
\right) \\
$$


### Example 2

$$
\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        1 & -1 & 3 & -2 \\
        3 & 0 & 1 & 4
    \end{array}
\right) \\
$$

As shown in the last lecture, this equals:

$$
\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        0 & -3 & 2 & -2 \\
        0 & 0 & -8 & 8
    \end{array}
\right) \\
$$

$$
\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        0 & -3 & 2 & -2 \\
        0 & 0 & 1 & -1
    \end{array}
\right) \\
$$

$$
\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        0 & -3 & 0 & 0 \\
        0 & 0 & 1 & -1
    \end{array}
\right) \rightarrow

\left( 
    \begin{array}{ccc|c}
        1 & 2 & 1 & 0 \\
        0 & 1 & 0 & 0 \\
        0 & 0 & 1 & -1
    \end{array}
\right)
$$ 

**Row Reduced Echelon Form:**

$$
\left( 
    \begin{array}{ccc|c}
        1 & 0 & 0 & 1 \\
        0 & 1 & 0 & 0 \\
        0 & 0 & 1 & -1
    \end{array}
\right)
$$ 

### Example 3 (Infinitely Many Solutions)

$$
\text{System} = 

\begin{cases}
x + 3y + z + w = 1 \\
-4x - 9y + 2z - w = -1 \\
-3y - 6z - 3w = -3 \\
y + 2z + w = 1 
\end{cases}
$$

$$
\left( 
    \begin{array}{cccc|c}
        1 & 3 & 1 & 1 & 1 \\
        -4 & -9 & 2 & -1 & -1 \\
        0 & -3 & -6 & -3 & -3 \\
        0 & 1 & 2 & 1 & 1
    \end{array}
\right)
$$ 

$$
\left( 
    \begin{array}{cccc|c}
        1 & 3 & 1 & 1 & 1 \\
        -4 & -9 & 2 & -1 & -1 \\
        0 & 1 & 2 & 1 & 1 \\
        0 & 1 & 2 & 1 & 1
    \end{array}
\right)
$$ 

$$
\left( 
    \begin{array}{cccc|c}
        1 & 3 & 1 & 1 & 1 \\
        -4 & -9 & 2 & -1 & -1 \\
        0 & 1 & 2 & 1 & 1 \\
        0 & 0 & 0 & 0 & 0
    \end{array}
\right)
$$ 

$$
\left( 
    \begin{array}{cccc|c}
        1 & 3 & 1 & 1 & 1 \\
        0 & 3 & 6 & 3 & 3 \\
        0 & 1 & 2 & 1 & 1 \\
        0 & 0 & 0 & 0 & 0
    \end{array}
\right) \rightarrow

\left( 
    \begin{array}{cccc|c}
        1 & 3 & 1 & 1 & 1 \\
        0 & 1 & 2 & 1 & 1 \\
        0 & 1 & 2 & 1 & 1 \\
        0 & 0 & 0 & 0 & 0
    \end{array}
\right)
$$ 

$$
\left( 
    \begin{array}{cccc|c}
        1 & 3 & 1 & 1 & 1 \\
        0 & 1 & 2 & 1 & 1 \\
        0 & 0 & 0 & 0 & 0 \\
        0 & 0 & 0 & 0 & 0
    \end{array}
\right)
$$

To get this into reduced row echelon form, we must get rid of some more of the coefficients.

$$
\left( 
    \begin{array}{cccc|c}
        1 & 0 & -5 & -2 & -2 \\
        0 & 1 & 2 & 1 & 1 \\
        0 & 0 & 0 & 0 & 0 \\
        0 & 0 & 0 & 0 & 0
    \end{array}
\right)
$$

$$
\text{New System} = 

\begin{cases}
x + - 5z - 2w = -2 \\
y + 2z + w = 1 \\
0 = 0 \\
0 = 0
\end{cases}
$$

The last two equations show that z and w are free variables, and x and y can be expressed in terms of these free variables (so they are constrained variables).

$$
x = 5z + 2w - 2 \\
y = -2z - w + 1 \\
$$