---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Linear Independence
use-math: true
---

## Linear Dependence

$$
v_1, ..., v_n \in \mathbb{R}^m \text{are \underline{Linearly Dependent (LD)} if there are numbers } c_1, ..., c_n \\ \text{ such that \underline{not} all } c_i = 0 \text{ and } c_1\overrightarrow{v_1} + ... + c_n\overrightarrow{v_n} = \overrightarrow{0} 
$$

This relates to the idea of homogenous system of linear equations.

$$
\{\overrightarrow{0}\} \text{ is Linearly Dependent because } 1 * \overrightarrow{0} = \overrightarrow{0}
$$

$$
\text{In } \mathbb{R}^2 \text{: } \{\begin{pmatrix}2\\3\end{pmatrix}, \begin{pmatrix}1\\0\end{pmatrix}, \begin{pmatrix}0\\1\end{pmatrix}\} \\
1 * \begin{pmatrix}2\\3\end{pmatrix} + 2 * \begin{pmatrix}1\\0\end{pmatrix} - 3 * \begin{pmatrix}0\\1\end{pmatrix} = \overrightarrow{0} \\
\text{This set is therefore linearly dependent.}
$$

## Linear Indepdence

$$
v_1, ..., v_n \in \mathbb{R}^m \text{are \underline{Linearly Independent (LI)} if } c_1\overrightarrow{v_1} + ... + c_n\overrightarrow{v_n} = \overrightarrow{0} \implies c_1 = c_2 = ... = c_n = 0
$$


### Examples
**Example 1**
$$
\text{Is }  \{\begin{pmatrix}1\\0\\0\end{pmatrix}, \begin{pmatrix}1\\1\\0\end{pmatrix}, \begin{pmatrix}1\\1\\1\end{pmatrix}\} \text{ LI?} \\
a * \begin{pmatrix}1\\0\\0\end{pmatrix} + b * \begin{pmatrix}1\\1\\0\end{pmatrix} + c * \begin{pmatrix}1\\1\\1\end{pmatrix} = \overrightarrow{0} \\
\begin{cases}
    a + b + c = 0 \\
    b + c = 0 \\
    c = 0
\end{cases} \implies
\begin{cases}
    a = 0 \\
    b = 0 \\
    c = 0
\end{cases}
$$

**Example 2**
$$
\{\begin{pmatrix}1\\2\\0\\1\end{pmatrix}, \begin{pmatrix}-1\\0\\1\\2\end{pmatrix}, \begin{pmatrix}-1\\4\\3\\7\end{pmatrix} \}\\
\left( 
    \begin{array}{ccc|c}
        1 & -1 & -1 & 0 \\
        2 & 0 & 4 & 0 \\
        0 & 1 & 3 & 0 \\
        1 & 2 & 7 & 0 \\
    \end{array}
\right) \\
\left( 
    \begin{array}{ccc|c}
        1 & -1 & -1 & 0 \\
        0 & 1 & 3 & 0 \\
        0 & 0 & 1 & 0 \\
        0 & 0 & 0 & 0 \\
    \end{array}
\right) \implies
\begin{cases}
    a = 0 \\
    b = 0 \\
    c = 0
\end{cases}
$$

In Example 2, we know that there can ONLY be a trivial solution because there is a pivot in every column, meaning that there are no free variables. Thus, the set of vectors are linearly independent.

Linear independence/dependence can help determine the size of a set.

## Column Theorem

$$
\overrightarrow{v_1}, ..., \overrightarrow{v_n} \in \mathbb{R}^m \\
A = (\overrightarrow{v_1} ... \overrightarrow{v_n})
$$

The following statements are equivalent (all of them are true or none of them are true):

$$
\{\overrightarrow{v_1}, ..., \overrightarrow{v_n}\} \text{ is Linearly Independent} \\
A\overrightarrow{x} = \overrightarrow{0} \implies \overrightarrow{x} = \overrightarrow{0} \\
\text{A has a pivot in every column}
$$

### Examples

**Example 1**
$$
\text{Is } \{\begin{pmatrix}1\\0\\-1\end{pmatrix}, \begin{pmatrix}1\\2\\3\end{pmatrix}, \begin{pmatrix}1\\1\\1\end{pmatrix}\} \text{ LI?} \\
\begin{pmatrix}
    1 & 1 & 1\\
    0 & 2 & 1\\
    -1 & 3 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 1 & 1\\
    0 & 2 & 1\\
    0 & 4 & 2
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 1 & 1\\
    0 & 2 & 1\\
    0 & 0 & 0
\end{pmatrix} \\
\text{Because there are only pivots in two of the columns, the set of vectors cannot be linearly independent.}
$$


**Example 2**

$$
\text{For which } h \in \mathbb{R} \text{ is } \{\begin{pmatrix}1\\1\\ h \end{pmatrix}, \begin{pmatrix}1\\ h \\1\end{pmatrix}, \begin{pmatrix}h \\1\\1\end{pmatrix}\} \text{ LI?} \\

\begin{pmatrix}
    1 & 1 & h \\
    1 & h & 1 \\
    h & 1 & 1
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 1 & h \\
    0 & h - 1 & 1 - h \\
    0 & 1 - h & 1 - h^2
\end{pmatrix} \rightarrow
\begin{pmatrix}
    1 & 1 & h \\
    0 & h - 1 & 1 - h \\
    0 & 0 & 2 - h - h^2
\end{pmatrix} \\
2 - h - h^2 = (1 - h)(2 + h) = 0 \text{ (To see what values make the vectors linearly independent)}\\
h \neq 1, -2
$$

The tricky part is to realize that you have to subtract h * Row 1 from Row 3

### Linear (In)dependence and Spans

$$
\text{A set of vectors } \{\overrightarrow{v_1}, ..., \overrightarrow{v_n}\} \text{ is LD if and only if one of the vectors is in the span of the others.} \\
\text{Therefore, } \{\overrightarrow{v_1}, ..., \overrightarrow{v_n}\} \text{ is LI if and only if for all } 2 \le k \le n \text{, }
\overrightarrow{v_k} \notin Span\{\overrightarrow{v_1}, ..., \overrightarrow{v_{k-1}}\}
$$