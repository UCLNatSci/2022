# Ordinary Differential Equations

## Introduction and terminology

Any equation that contains derivatives is called a *differential equation*. If the equation contains only one single dependent variable then it is 
known as an **ordinary differential equation** (ODE), otherwise it is called a **partial differential equation** (PDE).

````{admonition} Classifying ODEs
:class: important

ODEs can be classified according to the following:

- *Order:* determined by the highest order derivative, e.g. $\displaystyle \frac{\mathrm{d}y}{\mathrm{d}x}$ is a first order term, 
$\displaystyle \frac{\mathrm{d}^2y}{\mathrm{d}x^2}$ is a second order term.

- *Degree:* the power of the highest order derivative after fractional powers are removed, e.g. $\displaystyle \left(\frac{\mathrm{d}y}{\mathrm{d}x}\right)^2$ is a second 
degree term, whilst $\displaystyle \frac{\mathrm{d}^2y}{\mathrm{d}x^2}$ is a first degree term.

- *Linearity:* linear or non-linear refers to highest power that the dependent variable and its derivatives are raised to.  An ODE is said to be linear if it has the form:

```{math}
a_n(x)\,y^{(n)}+a_{n-1}(x)\,y^{(n-1)} + \dots + a_1(x)\,y^{\prime} + a_0(x)\,y = f(x)
```
where a bracketed superscript $y^{(n)}$ denotes the $n^{th}$ derivative of function $y(x)$.

````

The simplest type differential equation imaginable is a linear first order ODE of the form:

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=f(x)
```

ODEs of this type can be solved by direct integration, for example the ODE:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=3x^2
```
may be integrated to give:
```{math}
y=x^3 + C
```
where $C$ is a constant.  However, the majority of differential equations that we encounter in real world problems are not *directly* integrable, for 
example the Airy equation is an ODE that appears very commonly in physical sciences, which is given by:
```{math}
:label: airyode
\frac{\mathrm{d}^2 y}{\mathrm{d} x^2}=xy
```
We note that the Airy equation is a *second order* differential equation (because the highest derivative in the equation is a second order derivative) as well a first 
degree equation.  However we find that {eq}`airyode` cannot be solved by direct integration, and in fact its relatively innocent appearance hides a wealth of interesting 
mathematics.  The strategy for solving differential equations involves classifying different types of problem that we know how to solve, and building up an 
armoury of techniques.


## Initial and boundary conditions

When we solve a differential equation, we obtain arbitrary (undetermined) constants, this because we are in effect integrating the problem.  If the problem is at first 
order then there will be **one** unknown constant, since the solution to the problem is equivalent to performing a single integration, whilst for a second order 
problem we will obtain **two** unknown constants.  In general, to obtain a fully determined solution to a given problem, we require the number of given 
conditions to match the *degree* of the problem.

````{admonition} Worked example
:class: seealso
For example, suppose that we are given the problem:

```{math}
\frac{\mathrm{d}^2y}{\mathrm{d}t^2}=2t
```
which describes the vertical acceleration of an object at time $t$.

Recall that if $y$ measures displacement then $\displaystyle \frac{\mathrm{d}y}{\mathrm{d}t}$ measures velocity (i.e. rate of change of displacement) and 
$\displaystyle \frac{\mathrm{d}^2y}{\mathrm{d}t^2}$ measures acceleration (i.e. rate of change of velocity).

Integrating once with respect to $t$ gives:

```{math}
:label: firstintegral
\frac{\mathrm{d}y}{\mathrm{d}t}=t^2+k
```
where $k$ is an unknown constant.  Integrating again then gives:

```{math}
:label: secondintegral
y=\frac{t^3}{3}+kt+c,
```
where we have introduced another unknown constant $c$.

The constants can be uniquely determined by providing conditions.  For example, we might specify initial conditions for the displacement and velocity in the 
manner 
```{math}
y(0)=1, \quad y^{\prime}(0)=3
```

Applying the condition $y^{\prime}(0)=3$ to equation {eq}`firstintegral` gives $k=3$, and then applying the condition $y(0)=1$ to equation {eq}`secondintegral` 
gives $c=1$, hence the final result is 
```{math}
y = \frac{t^3}{3} + 3t + 1
```

````

Conditions given when $t=0$ (where $t$ denotes time) are called *initial conditions*

More generally, we use the term *boundary conditions*.  Boundary conditions provide the value of the dependent variable or its derivatives at some 
specified value(s) of the independent variable.

For example, in the Airy ODE we might specify the boundary conditions $y(0)=1$, with a limit such as:
```{math}
\lim_{x\rightarrow\infty}y(x)=0
```

We sometimes call ODEs **autonomous**, that is a system of ODES which do not explicitly depend on the independent 
variable e.g. $x$ and only depend on the dependent variable e.g. $y(x)$. When the variable is time, they are also 
called *time-invariant* systems.  Examples of this could include $y'' = -\omega^2 y$ (the SHM equation) or $y' = y^2$.


````{admonition} Practice questions
:class: seealso, dropdown
1\. Solve the second order problem $y^{\prime\prime}(x)=xe^x$ subject to $y(0)=1,\, y(1)=0$ by direct integration. 

2\. Solve the third order problem $y^{\prime\prime\prime}(x)=e^{x/2}$ subject to $y(0)=1, \,y'(0)=1, \, y''(0) = 1$ by direct integration. 
````

````{admonition} Solution
:class: seealso, dropdown

1\. Integrating once with respect to $x$ (using integration by parts) gives: 
```{math}
y^{\prime}(x)=(x-1)e^x+C_1
```
where $C_1$ is an arbitrary constant.  Integrating again w.r.t. $x$ gives:
```{math}
y(x)=(x-2)e^x+kx+C_2
```
where $C_2$ is an arbitrary constant.  Applying $y(0)=1$ gives $C_2=3$ and applying $y(1)=0$ gives $C_1=e-3$, so the final solution is:
```{math}
y(x) = (x-2)e^x+(e-3)x+3
```

2\. Integrating once with respect to $x$ gives: 
```{math}
y^{\prime\prime}(x) = 2e^{x/2} + C_1
```
where $C_1$ is an arbitrary constant.  Integrating again w.r.t. $x$ gives:
```{math}
y^{\prime}(x) = 4e^{x/2} + C_1 x + C_2
```
where $C_2$ is an arbitrary constant and integrating once more gives:
```{math}
y(x) = 8e^{x/2} + \frac{C_1 x^2}{2} + C_2x + C_3
```
where $C_3$ is an arbitrary constant.  

Applying $y(0)=1$ gives $C_3 = -7$, applying $y'(0)=1$ gives $C_2=-3$ and applying $y''(0)=1$ gives $C_1=-1$, so the final solution is:
```{math}
y(x) = 8e^{x/2} - \frac{ x^2}{2} - 3x - 7
```
````

````{admonition} Real Life Examples
:class: tip
Many of the fundamental laws of science are stated in the form of differential equations, some examples include:

* Simple (and higher order) Harmonic Oscillators
* Newton's Second Law of Motion
* The Schrödinger Equation
* Circuit Equations in Electronics
* Fluid dynamics equations
* Rate Equations in Chemistry
* Growth and decline of infectious diseases
```` 


