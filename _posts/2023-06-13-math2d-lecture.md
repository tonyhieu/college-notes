---
layout: post
description: Math 2D
categories: [math2d, lecture, summer23, markdown]
title: Week 1 Notes
use-math: true
---

## Finding Angle Between Two Vectors

$$
\overrightarrow{u} \cdot \overrightarrow{v} = || \overrightarrow{u} || * || \overrightarrow{v} || cos \theta \\
cos \theta = \frac{\overrightarrow{u} \cdot \overrightarrow{v}}{|| \overrightarrow{u} || * || \overrightarrow{v} ||}
$$

## Direction Cosines

The angle between a vector and the positive x, y, and z axes are alpha, beta, and gamma, respectively.

$$
cos \alpha = \frac{v_1}{|| \overrightarrow{v} ||} \\
cos \beta = \frac{v_2}{|| \overrightarrow{v} ||} \\
cos \gamma = \frac{v_3}{|| \overrightarrow{v} ||} \\
\text{Note that } cos^2 \alpha + cos^2 \beta + cos^3 \gamma = 1
$$

## Projection

$$
Proj_{\overrightarrow{v}} \overrightarrow{u} = \frac{\overrightarrow{v} \overrightarrow{u}}{|| \overrightarrow{v} ||^2} \overrightarrow{v} = \frac{\overrightarrow{v} \overrightarrow{u}}{|| \overrightarrow{v} ||} \hat{v} \\
\text{The vector component orthogonal to u is equal to } \overrightarrow{u} - Proj_{\overrightarrow{v}} \overrightarrow{u} \\

|| Proj_{\overrightarrow{v}} \overrightarrow{u} || = \frac{| \overrightarrow{v} \cdot \overrightarrow{u} |}{|| \overrightarrow{v} ||}
$$

## Work

If a force is being enacted on an object from point P to point Q, then the work can be calculated as follows:

$$
Work = \overrightarrow{F} \cdot \overrightarrow{PQ}
$$

## Cross Product

$$
\text{Let } \overrightarrow{u}, \overrightarrow{v} \in \mathbb{R}^3 \text{. The cross product of u and v is given by the following:} \\
\overrightarrow{u} \times \overrightarrow{v} = \begin{pmatrix}
    u_2 v_3 - u_3 v_2 \\
    u_3 v_1 - u_1 v_3 \\
    u_1 v_2 - u_2 v_1
\end{pmatrix} \\
\overrightarrow{u} \times \overrightarrow{v} \perp \overrightarrow{u}, \overrightarrow{u} \times \overrightarrow{v} \perp \overrightarrow{v} \\
\overrightarrow{u} \times \overrightarrow{v} \text{ is orthogonal to the plane containing u and v.} \\
\overrightarrow{u} \times \overrightarrow{v} = det(\begin{pmatrix}
    i & j & k \\
    u_1 & u_2 & u_3 \\
    v_1 & v_2 & v_3
\end{pmatrix}) =
i * det\begin{pmatrix}
    u_2 & u_3 \\
    v_2 & v_3
\end{pmatrix} - j * det\begin{pmatrix}
    u_1 & u_3 \\
    v_1 & v_3
\end{pmatrix} + k * det\begin{pmatrix}
    u_1 & u_2 \\
    v_1 & v_2
\end{pmatrix} \\
\text{Note: } \overrightarrow{u} \times \overrightarrow{v} = -(\overrightarrow{v} \times \overrightarrow{u}) \text{ (by the right hand rule)}
$$

### Properties of the Cross Product

$$
\overrightarrow{u} \times \overrightarrow{v} = -(\overrightarrow{v} \times \overrightarrow{u}) \\
\overrightarrow{u} \times (\overrightarrow{v} + \overrightarrow{w}) = \overrightarrow{u} \times \overrightarrow{v} + \overrightarrow{u} \times \overrightarrow{w} \\ 
c (\overrightarrow{u} \times \overrightarrow{v}) = (c \overrightarrow{u}) \times \overrightarrow{v} = \overrightarrow{u} \times (c \overrightarrow{v}) \\
\overrightarrow{u} \times \overrightarrow{0} = \overrightarrow{0} \times \overrightarrow{u} = \overrightarrow{0} \\ 
\overrightarrow{u} \times \overrightarrow{u} = \overrightarrow{0} 
$$

### Theorems of the Cross Product

$$
|| \overrightarrow{u} \times \overrightarrow{v} || = || \overrightarrow{u} || * ||\overrightarrow{v} || * sin \theta \\
\overrightarrow{u} \times \overrightarrow{v} = 0 \iff \overrightarrow{u} = c \overrightarrow{v}, c \in \mathbb{R} \\
|| \overrightarrow{u} \times \overrightarrow{v} || = \text{ The area of the parallelogram with u and v as adjacent sides}
$$

## The Triple Scalar Product

$$
\text{For } \overrightarrow{u}, \overrightarrow{v}, \overrightarrow{w} \in \mathbb{R}^3 \text{, the triple scalar product is } \\
\overrightarrow{u} \cdot (\overrightarrow{v} \times \overrightarrow{w}) = det \begin{pmatrix}
    u_1 & u_2 & u_3 \\
    v_1 & v_2 & v_3 \\
    w_1 & w_2 & w_3
\end{pmatrix}
$$

The absolute value of the triple scalar product gives the volume of a parallelopiped where u, v, and w are adjacent edges.

## 3D Equations of a Line

$$
\text{A line L parallel to a vector } v = <a, b, c> \text{and passing through the point } P(x_1, y_1, z_1) \text{ is represented by the following parametric equations: } \\
x = x_1 + at, y = y_1 + bt, z = z_1 + ct \\
\text{a, b, and c are the direction numbers, and t is the parameter. You can find any point on the line by changing t.}
$$

<hr>

$$
\text{Symmetric equations are the same as parametric except they are in terms of t.} \\
t = \frac{x - x_1}{a}, t = \frac{y - y_1}{b}, \frac{z - z_1}{c}
$$

## Vector Normal to a Plane

Given a point P(x, y, z) and a line in symmetric/parametric form, the equation of the plane is given by the following equations:

$$
\text{General form: } a(x - x_1) + b(y - y_1) + c(z - z_1) = 0 \\
\text{Standard form: } ax + by + cz = d \text{ where } d = ax_1 + by_1 + cz_1 \\
\text{The normal vector to the plane is given by } <a, b, c>
$$

## Angle Between Two Normal Vectors

To get the angle between two planes, you can use the angles between their two normal vectors

## Distance Between a Point and a Plane

$$
\text{The distance between a plane and a point Q not in the plane is } \\
D = || proj_{\overrightarrow{n}} \overrightarrow{PQ} || = \frac{|\overrightarrow{PQ} \cdot \overrightarrow{n} |}{|| \overrightarrow{n} ||} \\
\text{where P is a point on the plane and n is a vector normal to the plane}
$$

## Equations of Surfaces in Space

$$
\text{Ellipsoid: } \frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1 \\

\text{Hyperboloid of One Sheet: } \frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = 1 \\ 
\text{ (one of the terms must be negative, and the hyperbeloid goes along the axis made negative)} \\

\text{Hyperboloid of Two Sheets: } \frac{x^2}{a^2} - \frac{y^2}{b^2} - \frac{z^2}{c^2} = 1 \\ 
\text{ (two of the terms must be negative, and the hyperbeloid goes along the axis made positive)} \\

\text{Elliptic Cone: } \frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = 0 \\ 
\text{ (one of the terms must be negative, and the cone goes along the axis made negative)} \\

\text{Elliptic Paraboloid: } z = \frac{x^2}{a^2} + \frac{y^2}{b^2} \\ 
\text{ (the single variable denotes which direction it goes in; can be equal to x or y as well)} \\

\text{Hyperbolic Paraboloid: } z = \frac{x^2}{a^2} - \frac{y^2}{b^2} \\ 
\text{ (the single variable denotes which direction it goes in; can be equal to x or y as well)} \\
$$

![image](https://github.com/tonyhieu/college-notes/assets/54915685/1b3648e0-a8ab-43e3-9763-a3d7d1f2eac4)

![image](https://github.com/tonyhieu/college-notes/assets/54915685/1e9dbf48-8dd4-49fa-8cf3-2171d62d2cdb)

## Distance Between a Point and a Line

$$
\text{The distance between a line and a point P is } \\
D = \frac{|| \overrightarrow{PQ} \times \overrightarrow{v} ||}{|| \overrightarrow{v} ||} \\
\text{where v is a direction vector of the line and P is a point on the line}
$$