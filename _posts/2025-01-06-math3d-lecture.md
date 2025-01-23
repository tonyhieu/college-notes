---
layout: post
description: MATH 3D
categories: [math3d, lecture, winter25, markdown]
title: Elementary Differential Equations
use-math: true
toc: true
---

## Definitions of Differential Equations

**Differential Equations**: Equations that involve derivatives

$$
\text{Examples:}\\
\frac{dx}{dt} + x = 2 cos(t) \\
\frac{d^2 x}{d t^2} + \frac{dx}{dt} - x = 0
$$

In these examples, x is *dependent* on t; can be considered a function. On the other hand, t is an *independent* variable. Differential equations can also include *parameters* which are constants/coefficients.

$$
\text{Is } x = cost + sint \text{ a solution to } \frac{dx}{dt} + x = 2 cost \text{?} \\
\frac{dx}{dt} + x = \frac{d}{dt} (cost + sint) + cost + sint = (-sint + cost) + cost + sint = 2cost \\
\text{Thus, x is a solution to the equation, and there are many other x that are solutions as well.}
$$

- **Ordinary differential equation**: A differential equation with only one independent varialbe
    - $\frac{dx}{dt} = sin x$
- **Partial differential equation**: A differential equation with several independent variables, using partial derivatives
    - $\frac{\partial u}{\partial x} + \frac{\partial u}{\partial y} + \frac{\partial u}{\partial z} = 1$
- **Linearity**: An equation is linear if and only if the dependent variables and their derivatives appear linearly
    - Linear: $\frac{dx}{dt} + t = 0 \text{ and } \frac{dx}{dt} + sin t = 0$
    - Nonlinear: $e^{dx / dt} = 0 \text{ and } e^x \frac{dx}{dt} + t = 0$
- **Homogeneity**: A linear equation is homogeneous if all terms depend on the dependent variable. Otherwise, it is non- or inhomogeneous
    - Homogeneous: $\frac{d^2x}{dt^2} + e^t \frac{dx}{dt} + x = 0$
    - Inhomogeneous: $\frac{d^2x}{dt^2} - 2 \frac{dx}{dt} + t = 0$
- **Constant Coefficients**: A linear equation has constant coefficients if the coefficients are all constants (except for the inhomogeneity)
    - Example: $5\frac{d^3x}{dt^3} + 4\frac{dx}{dt} + sin(t)cos(t) = 0$
- **Autonomy**: An equation is autonomous if the equation does not depend on the independent variable at all
    - Autonomous: $e^x\frac{dx}{dt} + x = 0$
    - Not autonomous: $\frac{d^2x}{dt^2} + sint = 0$

## Solving First Order ODEs

### Case 1: f only depends on x

$$
\text{Given an equation like } y' = f(x) \text{, we can use the anti-derivative to solve.} \\
\int y'dx = \int f(x)dx \\
y(x) = \int f(x)dx + C \\
\text{We can get rid of the constant given an initial value for y(c) where c is some constant; known as an IVP.}
$$

### Case 2: f only depends on y

$$
\text{Equation: } y' = f(y) \\
\text{Note that } y' = \frac{dy}{dx} = f(y) \text{. Therefore:} \\
\frac{dy}{dx} = f(y) \rightarrow \frac{dx}{dy} = \frac{1}{f(y)} \\
\text{Then, we can use the same method as Case 1, but we set x as the dependent variable and then solve for y.}
$$

- Can also be morphed into case 3

### Case 3: f is depends on x and y (Separable)

$$
\text{Equation: } y' = h(x)g(y) \\
\frac{dy}{dx} = h(x)g(y) \\
\frac{dy}{g(y)} = h(x)dx \\
\int \frac{1}{g(y)} dy = \int h(x)dx + C \\
\text{Note that we might not get a clean definition of y. We can leave y in a more complex form as an \underline{implicit solution.}}

$$

$$
\text{Example:} \\
\frac{dy}{dx} = xy \\
\frac{dy}{y} = xdx \\
\int \frac{1}{y} dy = \int xdx \\
\text{ln} \vert y \vert = \frac{1}{2}x^2 + C \\
\vert y \vert = e^{\frac{1}{2}x^2 + C} \\
y = \pm e^C e^{\frac{1}{2}x^2} \rightarrow y = Ce^{\frac{1}{2}x^2}
$$

$$
\text{Newton's Cooling Law Example:} \\
T(0) = 89, T(1) = 85, A = 22 \\
\frac{dT}{dt} = -k(T - A) = -kT + kA = -kT + 22k \\
\frac{1}{-k(T - 22)}dT = dt \\
- t + C = \frac{1}{k} ln \vert (T - A) \vert \\
\vert (T - A) \vert = e^{-kt + C} = Ce^{-kt} \\
k(T - A) = Ce^{-kt} \\
\text{General solution: } T = Ce^{-kt} + A \\
89 = C + 22 \rightarrow C = 67 \\
85 = 67e^{-k} + 22 \rightarrow k = - ln(63/67) \\
T(t) = 67e^{ln(63/67)t} + 22 \\
60 = 67e^{ln(63/67)t} + 22 \rightarrow t \approx 9.21 \text{ minutes}
$$

### First Order Linear ODEs

$$
\text{Given the following sample linear ODE: } \\
a_1(x)y' + a_0(x)y = b(x) \\
$$

- If b(x) = 0, then the equation is homogenous
- If b(x) != 0, then the equation is inhomogeneous
- When $a_1(x) \neq 0$, then we can simplify this as $y' + \frac{a_0(x)}{a_1(x)}y = \frac{b_0(x)}{a_1(x)} \rightarrow y' + p(x)y = f(x)$
    - If p(x) = 0, then $y' = f(x)$ which is the same as Case 1
    - If f(x) = 0, then $y' + p(x)y = 0$ which can be written as a separable equation; Case 3
- If p and f are nonzero, then $y' + p(x)y = f(x)$

$$
y' + p(x)y = f(x) \\
\text{To solve, we want to find a factor r(x) such that } r(x)(y' + p(x)y) = r(x)f(x) \rightarrow \frac{d}{dx} (r(x)y)\\
r(x)y = \int r(x)f(x)dx + C \\
y = r(x)^{-1} (\int r(x)f(x)dx + C) \\
\text{Finding r(x):} \\
r(x)(y' + p(x)y) = \frac{d}{dx}(r(x)y) = \frac{dr}{dx}y + r(x)\frac{dy}{dx} \\
r(x)p(x)y = \frac{dr}{dx}y \rightarrow \frac{dr}{dx} = r(x)p(x) \text{ (Separable equation)} \\
\frac{1}{r} dr = p(x)dx \\
r = C e^{\int p(x)dx} \text{, AKA the integrating factor}
$$

#### Examples

$$
y' + 2xy = e^{x-x^2} \\
r(x) = e^{\int 2xdx} = e^{x^2}\\
e^{x^2} (y' + 2xy) = \frac{d}{dx} (e^{x^2}y) = e^{x^2}e^{x-x^2} = e^x \\
e^{x^2}y = e^x + C \rightarrow y = e^{x - x^2} + \frac{C}{e^{x^2}} \text{ (General Solution)} \\
-1 = 1 + \frac{C}{1} \rightarrow C = -2 \\
y = e^{x - x^2} - \frac{2}{e^{x^2}} \text{ (Particular Solution)}
$$

$$
\frac{1}{x} \frac{dy}{dx} - \frac{2y}{x^2} = x cos(x) \\
\frac{dy}{dx} - \frac{2}{x}y = x^2 cos(x) \\
r(x) = e^{\int p(x)dx} = e^{-2 ln \vert x \vert} =  e^{ln (\vert x \vert)^{-2}} = \frac{1}{x^2} \\
\frac{d}{dx} [\frac{1}{x^2} y] = \frac{1}{x^2} x^2 cos(x) = cos(x) \\
\frac{1}{x^2} y = sin x + C \rightarrow y = x^2(sin(x) + C) \\
$$

### Substitution

$$
\text{Example: } y' = (x + y + 1)^2 \\
\text{Let } u = x + y + 1 \rightarrow u(x) = x + y(x) + 1 \\
\frac{du}{dx} = u' = (x + y + 1)' = 1 + y' \\
y' = u' - 1 \\
\text{New equation: } u' - 1 = u^2 \rightarrow \frac{du}{dx} = u^2 + 1 \\
\text{Degenerates into case 2: } \frac{dx}{du} = \frac{1}{u^2 + 1} \\
x = \int \frac{1}{u^2 + 1} du + C \\
x = arctan(u) + C \rightarrow u = tan(x - C) = tan(x + C) \\
y = tan(x + C) - x - 1
$$

- Possible substitutions

| Form | Method | Replacement |
| --- | --- | --- |
| $yy'$ | $u = y^2, u' = 2yy'$ | $yy' = \frac{1}{2}u'$ |
| $y^2y'$ | $u = y^3, u' = 3y^2y'$ | $y^2y' = \frac{1}{3}u'$ |
| $cos(y)y'$ | $u = sin(y), u' = cos(y)y'$ | $cos(y)y' = u'$ |
| $sin(y)y'$ | $u = cos(y), u' = -sin(y)y'$ | $sin(y)y' = -u'$ |
| $e^yy'$ | $u = e^y, u' = e^yy'$ | $e^yy' = u' $ |

$$
2yy' + 1 = y^2 + x \\
\text{Let} u = y^2 \\
u' = 2yy' \\
u' + 1 = u + x \rightarrow u' - u = x - 1 \\
\frac{d}{dx} [e^{-x} u] = e^{-x} (x-1) \\
e^{-x} u = \int e^{-x}(x-1)dx + C \\
= -e^{-x}(x-1) - \int -e^{-x} dx + C \\
= -e^{-x}(x-1) - e^{-x} + C \\
u = -(x-1) - 1 + Ce^x = -x + Ce^x \\
y = \pm(-x + Ce^x)^{0.5}
$$

- Bernoulli equation is the first-order ODE of the form $y' + p(x)y = q(x)y^n$
    - For n > 2, this equation would not be linear
    - Strategy: multiply the entire equation by $y^{-n}$ to turn it into $y^{-n}y' + p(x)y^{1-n} = q(x)$
        - Substitute using $u = y^{1-n}, u' = (1-n)y^{-n}y'$

### Homogenous Equations

- Homogenous equations can be given by the form $\frac{dy}{dx} = F(\frac{y}{x})$
- Can be solved using a substitution $u = \frac{y}{x}$
    - $\frac{dy}{dx} = F(\frac{y}{x})$ becomes $u + xu' + F(u)$
- This new equation is separable; $\frac{1}{F(u) - u}du = \frac{1}{x}dx$

#### Example

$$
x^2y' = y^2 + xy \text{, } y(1) = 1 \\
y' = \frac{y^2}{x^2} + \frac{y}{x} \\
u = \frac{y}{x}, y' = u + xu' \\
u + xu' = u + u^2 \\
xu' = u^2 \\
u^{-2}du = x^{-1}dx \\
-\frac{1}{u} = ln \vert x \vert + C \\
u = - \frac{1}{ln \vert x \vert + C} \\
\frac{y}{x} = - \frac{1}{ln \vert x \vert + C} \\
y = - \frac{x}{ln \vert x \vert + C} \\
1 = - \frac{1}{C} \rightarrow C = -1 \\
y = - \frac{x}{ln \vert x \vert -1} 
$$

### Autonomous Equations

- Autonomous equations are given by $y' = f(y)$
- A **critical point** of $x' = f(x)$ is defined as a point $x_0$ such that $f(x) = 0$
- A solution $x(t)$ of $x' = f(x)$ is called an equilibrium solution if $x(t) = x_0$
- For example, the critical points of $x' = x(3 - x)$ are 0 and 3, so the equilibrium solutions are $x(t) = 3, x(t) = 5$

## Slope Fields
- **Slope fields** are drawn by calculating the slope at different points and drawing them
    - Given an equation $y' = f(x, y)$, find the slope of y at various points and draw the slope as a line segment
- Slope fields can be used to determine the shapes of solutions depending on an initial value
    - There are various functions that you can find from a slope field; how do we know if a function exists or is unique?

### Picard's Theorem
$$
\text{Definition. Consider the initial value problem } y' = f(x, y), y(x_0) = y_0 \\
\text{If the following two conditions are met:} \\
f(x, y) \text{ is continuous near } (x_0, y_0) \\
\frac{\partial f}{\partial y} \text{ exists and is continuous near } (x_0, y_0) \\
\text{then a solution to this IVP exists and is unique for (at least) some x near } (x_0, y_0)
$$


## Common Differential Equations + General Solutions

$$
\frac{dx}{dt} = kx \rightarrow x(t) = Ce^{kt}
$$

### Newton's Cooling Law
$$
\frac{dT}{dt} = -k(T - A)
$$