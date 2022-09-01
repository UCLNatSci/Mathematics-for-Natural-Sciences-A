# First Order ODEs

In this section we will look at some strategies which are incredible useful for solving first order ODEs. When to apply each of these techniques will depend on the individual problem being tackled, and so gaining familiarity with them by doing practice questions is absolutely vital.

## Separation of variables Technique
Of all the techniques for solving first order ODEs, separation of variables is the simplest to understand, being essentially a direct application of the Fundamental Theorem of Calculus.

The technique requires us to take a look at whether the variable dependence can be totally separated on different sides of the equation.

For example, in the problem
$$\frac{\mathrm{d}y}{\mathrm{d}x} = x^2y$$
we can separate the $x$ and the $y$ dependence to give

$$
\frac{1}{y}\frac{\mathrm{d}y}{\mathrm{d}x} = x^2, \quad (y \neq 0)
$$

Then, we can proceed with integration of both sides:

$$
\int\frac{1}{y}\mathrm{d}y = \int x^2\mathrm{d}x \quad \longrightarrow \quad \ln|y| = \frac{1}{3}x^3 + \text{const}
$$

This implicit relationship may be rearranged to obtain a solution for $y$ explicitly in terms of $x$:

$$
y = e^{\frac{1}{3}x^3 + \textrm{const}} \quad \longrightarrow \quad y=Ae^{\frac{1}{3}x^3}, \quad A \in \mathbb{R}.
$$


```{admonition} Worked Example
:class: seealso
**Question**

Solve the first order ODE $\frac{\textrm{d}y}{\textrm{d}x} = 3x^2e^{-y}$ that satisfies the condition $y(0) = 1$.

**Solution**

First we separate the two variables present to give

$$
\frac{1}{e^{-y}}\textrm{d}y = 3x^2\textrm{d}x \quad \longrightarrow \quad e^y\textrm{d}y = 3x^2\textrm{d}x
$$

Then integrate both sides:

$$
\int e^y \textrm{d}y = e^y, \quad \int 3x^2\textrm{d}x = \frac{3}{3}x^3 + C = x^3 + C
$$

To gain the general solution, all we do is simplify the expression to get:

$$
y = ln(x^3 + C)
$$

Finally, the particular solution is found by using the boundary condition provided, $y(0) = 1$.

$$
y(0) = ln(0 + C) = ln(C) = 1, \quad \longrightarrow \quad C=e
$$
$$
\therefore \quad y = ln(x^3 + e)
$$

```

````{admonition} Practice Questions
:class: seealso, dropdown

1. Decide which of the following expressions are separable, and have a go at solving those that are

    a.  $(1+e^x)y\frac{\mathrm{d}y}{\mathrm{d}x} = e^x$

    b.  $\frac{\mathrm{d}y}{\mathrm{d}x} = (3x + 2y + 1)^2$

    c.  $\frac{1}{x} + x\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{\mathrm{d}y}{\mathrm{d}x}$

    d.  $\frac{x}{y}\frac{\mathrm{d}y}{\mathrm{d}x} = x^2 - 1$

    e.  $x^2\frac{\mathrm{d}y}{\mathrm{d}x} = y^2 - 1$

    f.  $xy\frac{\mathrm{d}y}{\mathrm{d}x} = \ln(x),\   y(1)=0,\ x \geq 1$


2. The rate of growth of a population $P$ is proportional to itself. Set up and solve a differential equation for the population, given that the initial population is $P_0$ and it doubles after 10 years.

```{admonition} Question 1 Solutions
:class: seealso, dropdown

a. $\int y \mathrm{d}y = \int\frac{e^x}{1+e^x}\mathrm{d}x \quad \longrightarrow \quad \frac{y^2}{2} = \ln(e^x+1) + \text{const}$

b. This problem is not separable

c. $\frac{1}{x} = (1-x)\frac{\mathrm{d}y}{\mathrm{d}x} \quad \longrightarrow\quad  \frac{\mathrm{d}y}{\mathrm{d}x}= \frac{1}{x(1-x)} = \frac{1}{x} + \frac{1}{1-x} \quad \longrightarrow\quad  y = \ln\biggr|\frac{x}{1-x}\biggr|$

d. $\int \frac{1}{y}\mathrm{d}y = \int \left(x-\frac{1}{x}\right)\mathrm{d}x \quad \longrightarrow\quad  \ln|y|= \frac{x^2}{2}-\ln|x| \quad \longrightarrow\quad  y= \frac{Ae^{x^2/2}}{x}, \quad A \in \mathbb{R}$

e. $\frac{1}{2}\int \left(\frac{1}{y-1}-\frac{1}{y+1}\right)\mathrm{d}y = \int\frac{1}{x^2}\mathrm{d}x \quad \longrightarrow\quad   \ln\left(\frac{y-1}{y+1}\right)=-\frac{2}{x}+\text{const},\quad -1 < y < 1$

f. $\int{y\mathrm{d}y} = \int \frac{\ln(x)}{x}\mathrm{d}x \quad \longrightarrow\quad  \frac{y^2}{2} = \frac{(\ln(x))^2}{2} + C$

$y(1) = 0 \Rightarrow C = 0$ so, $y^2 = (\ln(x))^2 $
```

```{admonition} Question 2 Solutions
:class: seealso, dropdown
$\frac{\mathrm{d}P}{\mathrm{d}t} = \lambda P \quad \longrightarrow\quad  \int_{P_0}^{P}\frac{1}{P}\mathrm{d}P = \int_{0}^t\lambda \mathrm{d}t \quad \longrightarrow \quad \ln\left(\frac{P}{P_0}\right) = \lambda t \quad\longrightarrow\quad P = P_0e^{\lambda t}$

$P(10) = 2P_0 \Rightarrow \lambda = \frac{1}{10}\ln(2)$, so  $P = P_02^{\frac{t}{10}}$
```
````

## Integrating Factor Technique

An integrating factor is a function that we make use of to allow us to directly integrate the original ODE. We normally term our integrating factor as **$\mu$**, and we use it to multiply both sides of our ODEs. This should result in a nicer form of our original expression that we are able to solve.

### Motivation
Consider the following differential equation:

```{math}
:label: intfexample
\frac{\mathrm{d}y}{\mathrm{d}x}+\frac{1}{x}y=\frac{\cos(x)}{x}, \quad (x\neq 0)
```

A quick check will show that this equation is not separable.
If we try to integrate directly, then we obtain:

$$
\int \mathrm{d}y+\int \frac{1}{x}y \mathrm{d}x = \int \frac{\cos(x)}{x}\mathrm{d}x.
$$

We can deal with the integral on the right (in principle) but the term $\int \frac{y}{x}\mathrm{d}x$ appearing on the left cannot be evaluated without knowing $y$. So, we reached a dead end.

Now, observe that we can multiply equation {eq}`intfexample` throughout by $x$, to obtain

```{math}
:label: intfexample2
x\frac{\mathrm{d}y}{\mathrm{d}x}+y=\cos(x), \quad (x\neq 0)
```

The expression on the left-hand side is an *exact derivative*

$$
\frac{\mathrm{d}}{\mathrm{d}x}(yx)=x\frac{\mathrm{d}y}{\mathrm{d}x}+y
$$

Neat! This means that we can integrate equation {eq}`intfexample2` to obtain

$$
xy=\int\cos(x)\mathrm{d}x
$$

The final solution is

$$
y=\frac{1}{x}(\sin(x)+k)
$$

where $k$ is an arbitrary constant. We can verify that thi solution satisfies equation {eq}`intfexample` now:

$$
\frac{\mathrm{d}y}{\mathrm{d}x}+\frac{1}{x}y=\left[-\frac{1}{x^2}(\sin(x)+k)+\frac{1}{x}\cos(x)\right]+\frac{1}{x^2}(\sin(x)+k)=\frac{\cos(x)}{x}
$$

as required. For this problem, we are multiplying both sides of our ODE by $\mu=x$, where **$\mu$** is our *integrating factor*.  It's role is to cast the left hand side as an exact derivative to make the problem integrable. But can we always do this? And if so, how do we choose the integrating factor?

```{admonition} Worked Example
:class: seealso
Consider the problem

$$
-\sinh(x)y+\cosh(x)\frac{\mathrm{d}y}{\mathrm{d}x}=\sinh(2x)
$$

**Solution**

The left hand side is not an exact derivative, so we must use the integrating factor method.

If we multiply throughout by a factor $\mu= \textrm{sech}^2(x)$ then we obtain

$$
\text{sech}(x)\frac{\mathrm{d}y}{\mathrm{d}x}-\text{sech}(x)\tanh(x)y=2\tanh(x)
$$

Now the LHS can be written as an exact derivative:

$$
\frac{\mathrm{d}}{\mathrm{d}x}(\text{sech}(x)y)
$$

and so the problem can be solved by direct integration.
```

### Technique
We will apply an integrating factor technique to solve problems of the special form

$$
\frac{\mathrm{d}y}{\mathrm{d}x} + f(x)y = g(x)
$$

The technique can be written down in the form of an algorithm:

```{admonition} Definition
:class: Note
**The Integrating Factor Algorithm**
1. Compute the integrating factor $\mu(x) = e^{\int{f(x) \mathrm{d}x}}$
2. Multiply the whole ODE by $\mu(x)$
3. You should find that the left-hand-side can be rewritten as $\frac{\mathrm{d}}{\mathrm{d}x}(\mu y)$
4. Integrate both sides with respect to $x$
````

We will first look at a couple of examples of how it's done, and then we'll take a look at why it works.

```{admonition} Worked Example 1
:class: seealso
**Question**

$$
x\frac{dy}{dx} + 2y = 4x^2
$$

**Solution**

First we need to put the ODE into the correct form, by dividing throughout by $x$,assuming that $x \neq 0$

$$
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{2}{x}y = 4x
$$

Comparing this form to the template equation we see that $f(x) = \frac{2}{x}$ and so

$$
\int f(x)\mathrm{d}x=\int$$\frac{2}{x}\mathrm{d}x=2\ln(x)=\ln(x^2)+C
$$

The integrating factor is $\mu = e^{\ln(x^2)}=x^2$. Multiplying through this factor gives

$$
x^2\frac{\mathrm{d}y}{\mathrm{d}x}+2xy=4x^3
$$

We've achieved something! The left-hand side is an exact derivative of $(x^2y)$. We can write the modified equation as

$$
\frac{\mathrm{d}}{\mathrm{d}x}(x^2y)=4x^3
$$

Finally, integrating both sides with respect to $x$ gives

$$
x^2y = x^4 + K \quad \longrightarrow \quad y = x^2 + \frac{K}{x^2}
$$

where $K$ is an arbritary constant.

You can verify that the solution works by substituting it into the original ODE.
```

```{admonition} Worked Example 2
:class: seealso, dropdown

Consider the following:

$$
x^2\frac{dy}{dx}+3xy=e^{3x}
$$

**Solution**

Rearrange to give:

$$
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{3}{x}y = \frac{1}{x^2}e^{3x}
$$

The integrating factor to use is $\mu(x) = e^{\int{f(x) \mathrm{d}x}} = e^{3ln(x)} = x^3$

Multiplying through by the integrating factor gives:

$$
x^3\frac{\mathrm{d}y}{x} + 3x^2y = xe^{3x} \quad \longrightarrow \quad \frac{\mathrm{d}}{\mathrm{d}x}(x^3y) = xe^{3x}
$$

Integrate with respect to x to solve:

$$
x^3y = \frac{e^{3x}}{3}\left(x-\frac{1}{3}\right) + K \quad \longrightarrow \quad y = \frac{1}{3x^3}

e^{3x}\left(x-\frac{1}{3}\right) + \frac{K}{x^3}
$$
```

**So how does it work?**

Multiplying the LHS of the general form by $\mu(x)$ gives

```{math}
:label: eq1compare
\mu \frac{\mathrm{d}y}{\mathrm{d}x}+ y \mu f(x)
```

Compare with

```{math}
:label: eq2compare
\frac{\mathrm{d}}{\mathrm{d}x}\left(\mu y \right)=\mu \frac{\mathrm{d}y}{\mathrm{d}x}+y\frac{\mathrm{d}\mu}{\mathrm{d}x}
```

By equating {eq}`eq1compare` with {eq}`eq2compare` it can be seen that we can make the integrating factor work if we choose $\mu$ to satisfy

```{math}
\frac{\mathrm{d}\mu}{\mathrm{d}x}=\mu f(x)
```

Can you solve this equation by separation? The solution is
$\mu = e^{\int f(x)\mathrm{d}x}$
