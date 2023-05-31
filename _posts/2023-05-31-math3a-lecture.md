---
layout: post
description: Math 3A
categories: [math3a, lecture, spring22-23, markdown]
title: Dot Products and Length
use-math: true
---

## Definition of Dot Product
$$
\overrightarrow{v}, \overrightarrow{w} \in \mathbb{R}^n \\
\overrightarrow{v} \cdot \overrightarrow{w} = <\overrightarrow{v}, \overrightarrow{w}> = \overrightarrow{v}^T \overrightarrow{w} = v_1 w_1 + v_2 w_2 + ... + v_n w_n \\
\text{Example: } \overrightarrow{v} = \begin{pmatrix} 1 \\ 2 \end{pmatrix}, \overrightarrow{u} = \begin{pmatrix} 3 \\ 4 \end{pmatrix}, \overrightarrow{u} \cdot \overrightarrow{v} = 1 * 3 + 2 * 4 = 11 \\
$$

## Properties of Dot Products

$$
\overrightarrow{v} \cdot \overrightarrow{w} = \overrightarrow{w} \cdot \overrightarrow{v} \\
(\overrightarrow{u} + \overrightarrow{v}) \cdot \overrightarrow{w} = \overrightarrow{u} \cdot \overrightarrow{w} + \overrightarrow{v} \cdot \overrightarrow{w} \\
(\lambda \overrightarrow{u}) \cdot \overrightarrow{v} = \lambda (\overrightarrow{u} \cdot \overrightarrow{v}) \\
\overrightarrow{v} \cdot \overrightarrow{v} \geq 0, \overrightarrow{v} \cdot \overrightarrow{v} = 0 \iff \overrightarrow{v} = 0
$$

## Dot Products as Lengths/Norms

$$
|| \overrightarrow{v} || = \sqrt{\overrightarrow{v} \cdot \overrightarrow{v}} = \sqrt{v_1^2 + v_2^2 + ... + v_n^2} \\
\text{Examples: } \\
\overrightarrow{v} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, ||\overrightarrow{v}|| = \sqrt{1^2 + 2^2 + 3^2} = \sqrt{14} \\
\overrightarrow{u} = \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}, ||\overrightarrow{u}|| = \sqrt{1^2 + 1^2 + 1^2} = \sqrt{3} \\
\overrightarrow{w} = \begin{pmatrix} 3 \\ 4 \end{pmatrix}, ||\overrightarrow{w}|| = \sqrt{3^2 + 4^2} = \sqrt{25} = 5 \\
$$

## Applications

$$
\overrightarrow{v} \in \mathbb{R}^n, \text{ the \underline{normalized vector} } \hat{v} = \frac{1}{||\overrightarrow{v}||} \cdot \overrightarrow{v} \\
||\hat{v}|| = || \frac{1}{||\overrightarrow{v}||} \cdot \overrightarrow{v} || = \frac{1}{||\overrightarrow{v}||} \cdot ||\overrightarrow{v}|| = 1 \\
\text{Example: } \overrightarrow{u} = \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}, \hat{u} = \frac{1}{\sqrt{3}} \cdot \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} \\
\text{Note that } || \lambda \overrightarrow{v} || = | \lambda | \cdot || \overrightarrow{v} || \\

\text{For } \overrightarrow{v}, \overrightarrow{w} \in \mathbb{R}^n, \text{ the distance between v and w is } ||  \overrightarrow{v} - \overrightarrow{w} ||
$$

## Orthogonal Vectors

$$
\overrightarrow{v}, \overrightarrow{w} \in \mathbb{R}^n \text{ are orthogonal if } \overrightarrow{v} \cdot \overrightarrow{w} = 0 \text{, often denoted as } \overrightarrow{v} \perp \overrightarrow{w} \\

\text{Example: }
\overrightarrow{v} = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \overrightarrow{w} = \begin{pmatrix} 1 \\ -1 \end{pmatrix}, \overrightarrow{v} \cdot \overrightarrow{w} = 1 * 1 - 1 * 1 = 0; \overrightarrow{v} \perp \overrightarrow{w}
$$

## Important Inequalities and Equalities

$$
\text{Traingle Inequality: } || \overrightarrow{v} + \overrightarrow{w} || \leq || \overrightarrow{v} || + || \overrightarrow{w} || \\
\text{Pythagorean Theorem: If } \overrightarrow{v} \perp \overrightarrow{w} \text{, then } || \overrightarrow{v} + \overrightarrow{w} ||^2 = || \overrightarrow{v} ||^2 + || \overrightarrow{w} ||^2 \\
\text{Parallelogram Law: } || \overrightarrow{v} + \overrightarrow{w} ||^2 + || \overrightarrow{v} - \overrightarrow{w} ||^2 = 2|| \overrightarrow{v} ||^2 + 2|| \overrightarrow{w} ||^2 \\
\text{Cauchy-Schwarz Inequality: } | \overrightarrow{v} \cdot \overrightarrow{w} | \leq || \overrightarrow{v} || \cdot || \overrightarrow{w} ||
$$