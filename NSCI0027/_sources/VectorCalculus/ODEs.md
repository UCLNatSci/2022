
# Solving Ordinary Differential Equations

Whilst we can feel confident about solving first order ODEs that are linear (and in some cases non-linear) as well as second order ODEs with constant coefficients, 
there clearly remain many classes of ODEs which we cannot currently solve.  We can however use a series of generalisations of our current methods to solve more 
complicated problems.  Here we will focus on two such methods, *reduction of order* and *variation of parameters*.

````{admonition} Definition
:class: notice
Recall that in general a linear second order differential equation is of the form: 

```{math}
:label: ode2general
a\,y^{\prime\prime}(x)+b\,y^{\prime}(x)+c\,y(x)=f(x)
```
where $a,\,b,\,c$ are arbitrary constants.

````

## Reduction of order method

Recall the following linear homogeneous second order ODE:
```{math}
a\,y^{\prime\prime}(x)+b\,y^{\prime}(x)+\frac{b^2}{4a}\,y(x)=0
```
which if we solve using our usual ansatz $y = e^{\lambda x}$, we find that we have to solve 
$a\lambda^2 + b\lambda + \frac{b^2}{2a}=0$ and since the discriminant of this quadratic is zero, this 
equation has repeated roots, giving one solution of the form:
```{math}
y_1 = Ae^{-b x/2a}
```
Since we must have two linearly independent solutions to this problem, we think about the form of the final 
solution as:
```{math}
y = y_1 + y_2 = f(x)\,e^{-bx/2a}
```
where $f(x)$ is a function to be found and must have a linear component and a non-linear component.  Using this 
asumption, 
we can solve for $f(x)$ to find that:
```{math}
y = (A + Bx)\,e^{-b x/2a}
```

But can we generalise this method to a more complicated form of second order ODE? Yes, this method is known 
as **reduction of order**.

We can apply this method if we know one of the solutions $y_1(x)$ and are searching for a second linearly 
independent solution $y_2(x)$.  

````{admonition} Definition
We employ this method to solve inhomogeneous linear differential equations of the form:
```{math}
:label: ode2redorder
a(x)\,y'' + b(x)\,y' + c(x)\,y = f(x) \Rightarrow y'' + p(x)\,y' + q(x)\,y  = r(x)
```
where we have relabelled $\displaystyle p(x) = \frac{b(x)}{a(x)},\, q(x) = \frac{c(x)}{a(x)},\, r(x) = \frac{f(x)}{a(x)}$ for simplicity.  

If we know a solution $y_1(x)$ of the homogeneous problem $y_1'' + p\,y_1'+q\,y_1 = 0$, then the solution to 
the inhomogeneous problem will be of the form:
```{math}
y_2(x) = u(x)\,y_1(x)
```
where $u(x)$ can be found from the complicated expression:
```{math}
u(x) = \int \left(\frac{\int y_1\,r\,e^{\int p\,\mathrm{d}x}\,\mathrm{d}x + C}{y_1^2\,e^{\int p\,\mathrm{d}x}}\right)\,\mathrm{d}x
```
and therefore the final solution is of the form:

```{math}
y(x) = y_1(x)\left(1 + \int \left(\frac{\int y_1\,r\,e^{\int p\,\mathrm{d}x}\,\mathrm{d}x  + C}{y_1^2\,e^{\int p\,\mathrm{d}x}}\right)\,\mathrm{d}x
\right)
```
````


Using $y_2(x) = u(x)\,y_1(x)$, we can find the derivatives:
```{math}
y_2' &= u'\,y_1 + u\,y_1' \\
y_2'' &= u''\,y_1 + 2u'\,y_1+ f\,y_1'' 
```
and sustituting these into {eq}`ode2redorder`:
```{math}
y_1\,u'' + (2y_1' + p\,y_1)\,u' + (y_1''+p\,y_1'+q\,y_1)\,u = r
```
but since $y_1$ satisfies $y_1'' + p\,y_1' + q\,y_1 = 0$, then this reduces do:
```{math}
y_1\,u'' + (2y_1' + p\,y_1)\,u' = r
```
which is a linear first order differential equation in $f'$:
```{math}
u'' + \left(\frac{2y_1'}{y_1} + p\right)f' = \frac{r}{y_1}
```
We call this method reduction of order because we have reduced a second order problem down to a first order one, 
if we started with an $n^{th}$ order ODE, this equation would be an $(n-1)^{th}$ order ODE.  Using the relevant integrating factor:
```{math}
\mu = \exp\left[\int\left(\frac{2y_1'}{y_1} + p\right)\,\mathrm{d}x\right] = \exp\left(2\ln|y_1| + \int p\,\mathrm{d}x\right) = y_1^2\,e^{\int p\,\mathrm{d}x}
```
which leaves us to solve:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\left( u'\,y_1^2\,e^{\int p\,\mathrm{d}x}\right) &= y_1\,r\,e^{\int p\,\mathrm{d}x}\\
\Rightarrow u'(x) &= \frac{\int y_1\,r\,e^{\int p\,\mathrm{d}x}\,\mathrm{d}x + C}{y_1^2\,e^{\int p\,\mathrm{d}x}}\\
u(x) &= \int \frac{\int y_1\,r\,e^{\int p\,\mathrm{d}x}\,\mathrm{d}x + C}{y_1^2\,e^{\int p\,\mathrm{d}x}}\,\mathrm{d}x
```
### Finding homogeneous solutions
If the form of $p(x),\, q(x)$ are just polynomial, then finding homogeneous solution(s) to ODEs of the form {eq}`ode2redorder` can be done, 
using the ansatz $y = x^n$.  Obviously this may only work for one of the solutions, however for the reduction of order method this is exactly what 
is required.  

To see this in action, lets pick the example:
```{math}
x^2\,y'' + xy' - y = 0
```
Using the ansatz $y = x^n$, then:
```{math}
y(x) &= x^n \\
y'(x) &= nx^{n-1}\\
y''(x) &= n(n-1)x^{n-2}
```
which means that the ODE can be written as:
```{math}
x^{n}\Big(n(n-1)+n - 1 \Big) = 0 \Rightarrow n^2 - 1 = 0
```
which means that $n = \pm 1$ and therefore the solution will be of the form:
```{math}
y = Ax^1 + Bx^{-1}
```

If one of $p,\,q$ are *NOT* polynomial, then we only hope to apply a series solution method to solve these sorts of 
problems $y = \sum_{n=1}^\infty a_n\,x^n$.



````{admonition} Worked examples
:class: seealso
1\. Solve the ODE $x^2y'' - 2y = 0$

Using the ansatz $y = x^n$:
```{math}
x^n \Big(n(n-1) - 2\Big) = 0 \Rightarrow n^2 - n - 2 = (n-2)(n+1) = 0
```
which has roots of $n = -1,\, 2$ and hence
```{math}
y = Ax^2 + Bx^{-1}
```

2\. Solve the ODE $x^2\,y'' - 3x\,y' + 4y = 0$

Using the ansatz $y = x^n$:
```{math}
x^{n}\Big( \Big) = 0
```

````


## Variation of parameters method

Whilst the method of undetermined coefficients works for specific set of source terms $f(x)$ (i.e. those of certain elementary functions with symmetries 
in their derivatives), we could ask what is the more general method for solving these sorts of ODEs?
````{admonition} Definition
The variation of parameters method can be used to solve $n^{th}$ degree linear  ODEs of the form:
```{math}
y^{(n)}(x) + \sum^{n-1}_{i=0} a_i(x)\,y^{(i)}(x) = f(x)
```
which can be shown to have the solution:
```{math}
\sum_{i=1}^{n} u_i(x)\, \int \frac{W_i(x)}{W(x)}\,\mathrm{d}x
```
where $u_i(x),\, i \in \{1,\, 2,\, \dots,\, n\}$ are the the homogeneous solutions of the ODE, $W(x)$ is the Wronskian of these homogeneous solutions:
```{math}
W \Big(u_{1}, \ldots ,u_{n}\Big)=
\begin{vmatrix}
u_{1}(x) & u_{2}(x) & \cdots & u_{n}(x)\\
u_{1}'(x) & u_{2}'(x) & \cdots & u_{n}'(x)\\
\vdots &\vdots &\ddots &\vdots \\
u_{1}^{(n-1)}(x) & u_{2}^{(n-1)}(x) & \cdots & u_{n}^{(n-1)}(x)
\end{vmatrix}
```
and $W_i(x)$ is the reduced Wronskian:
```{math}
W_i(x) = \begin{vmatrix}
u_{1}(x) & u_{2}(x) & \cdots & 0 & \cdots & u_{n}(x)\\
u_{1}'(x) & u_{2}'(x) & \cdots & 0& \cdots & u_{n}'(x)\\
\vdots &\vdots &\ddots &\vdots &\vdots &\vdots \\
u_{1}^{(n-1)}(x) & u_{2}^{(n-1)}(x) & \cdots & f(x)& \cdots & u_{n}^{(n-1)}(x)
\end{vmatrix}
```
where the $i^{th}$ column of the Wronskian $W(x)$ has been replaced with:
```{math} 
\begin{pmatrix}
0 \\ 0 \\ \vdots \\ f(x)
\end{pmatrix}
```

````
### First order systems
If we start with a general first order linear ODE:
```{math}
:label: inhomofirstorder
y’ + p(x)\,y = q(x)
```
we can think of this a sourced first order problem, so the homogenous equation is:
```{math}
y’ + p(x)\,y = 0
```
which we can solve, for instance with separation of variables:
```{math}
\int \frac{1}{y}\,\mathrm{d}y &= - \int p\,\mathrm{d}x\\
\ln(y) &= - \int p\,\mathrm{d}x + \ln(y_0) \\
y_h &= y_0\,e^{- \int p\,\mathrm{d}x}
```
where $y_0$ is a constant.

Now we can use this homogeneous solution $y_h(x)$ to solve for the inhomogeneous case $y_p(x)$, by multiplying this solution with a (yet unknown) function $C(x)$:
```{math}
y_p = C(x)\,e^{- \int p\,\mathrm{d}x}
```
If we substitute this back into {eq}`inhomofirstorder` we will find:
```{math}
& C’(x)\,e^{- \int p\,\mathrm{d}x} - C(x)\,p(x)\,e^{- \int p\,\mathrm{d}x} + p(x)\, C(x)\,e^{- \int p\,\mathrm{d}x} = q(x)\\
& \Rightarrow C’(x)\,e^{- \int p\,\mathrm{d}x} = q(x)
```
which by straight integration means that:
```{math}
C(x) &= \int q(x)\, e^{\int p\,\mathrm{d}x}\,\mathrm{d}x \\
\Rightarrow y_p &= e^{- \int p\,\mathrm{d}x}\,\int q(x)\, e^{\int p\,\mathrm{d}x}\,\mathrm{d}x
```
and so the final solution is given by the sum of:
```{math}
y = y_h + y_p =  e^{- \int p\,\mathrm{d}x}\,\Big(\int q(x)\, e^{\int p\,\mathrm{d}x}\,\mathrm{d}x + y_0\Big)
```
which we have seen before with integrating factors for first order systems.

### Second order systems
Let’s begin again with the form of the inhomogeneous second order ODE in {eq}`ode2order`:
```{math}
L\,y(x) = y^{\prime\prime}(x)+p(x)\,y^{\prime}(x)+q(x)\,y(x) = r(x)
```
firstly we aim to solve the homogeneous equation:
```{math}
L\,y(x) = y^{\prime\prime}(x)+p(x)\,y^{\prime}(x)+q(x)\,y(x) = 0
```
which will admit solutions $u_1(x),\, u_2(x)$. Hence we will construct a solution to the general equation of the form:
```{math}
:label: cond1
y(x) = A(x)\,u_1(x) + B(x)\,u_2(x)
``` 
We note that if $A(x),\, B(x)$ here were just constants, then this would be a linear superposition of the homogeneous solutions - therefore in general these 
should contain some additive constant with each function.  In order to have two equations with two unknowns, we need to enforce a separate condition on $A(x),\, B(x)$, 
as we will see the most helpful condition to simplify later algebra turns out to be:
```{math}
:label: cond2
A'(x)\,u_1(x) + B'(x)\,u_2(x) = 0
```
If we try to constuct the form of {eq}`ode2general` using {eq}`cond1`, we will find:
```{math}
y'(x) &= \Big(A(x)\,u_1(x) + B(x)\,u_2(x)\Big)' \\
&= A'(x)\,u_1(x) + B'(x)\,u_2(x) + A(x)\,u_1'(x) + B(x)\,u_2'(x)\\
&= A(x)\,u_1'(x) + B(x)\,u_2'(x)
```
where we have used our condition {eq}`cond2` to reach the final line.  Likewise for second derivatives:
```{math}
y''(x) = A(x)\,u_1''(x) + B(x)\,u_2''(x) + A'(x)\,u_1'(x) + B'(x)\,u_2'(x)
```
and so using the linear derivative operator:
```{math}
L\, y(x) &= A(x)\,u_1''(x) + B(x)\,u_2''(x) + A'(x)\,u_1'(x) + B'(x)\,u_2'(x) \\ &+ p(x)\,(A(x)\,u_1'(x) + B(x)\,u_2'(x)) \\ &+ q(x)\,(A(x)\,u_1(x) + B(x)\,u_2(x)) = f(x)\\
&= A(x)(u''(x) + u'(x) + u(x)) + B(x)(u''(x) + u'(x) + u(x)) \\
&+ A'(x)\,u_1'(x) + B'(x)\,u_2'(x)\\
&= A'(x)\,u_1'(x) + B'(x)\,u_2'(x) + A'(x)\,L\,u_1(x) + B'(x)\,L\,u_2(x)\\
&= A'(x)\,u_1'(x) + B'(x)\,u_2'(x)
```
where we have used the fact that the terms with $A(x),\, B(x)$ coefficients are actually just the homogeneous equations, hence they equal zero.  So this leaves a coupled ODE system:
```{math}
A'(x)\,u_1(x) + B'(x)\,u_2(x) &= 0\\
A'(x)\,u_1'(x) + B'(x)\,u_2'(x) &= r(x)
```
which if we write as a matrix system $W(x)\,a = b$:
```{math}
\begin{pmatrix}
u_1(x) & u_2(x) \\
u_1'(x) & u_2'(x)
\end{pmatrix}
\begin{pmatrix}
A'(x) \\
B'(x)
\end{pmatrix} = 
\begin{pmatrix}
0 \\
r(x)
\end{pmatrix}
```
where $W(x)$ is the Wronskian of the system. 

So to find the solutions $a = W^{-1}\,b$ we can invert this matrix as:
```{math}
\begin{pmatrix}
A'(x) \\
B'(x)
\end{pmatrix} = \frac{1}{W}\begin{pmatrix}
u_2'(x) & -u_2(x) \\
-u_1'(x) & u_1(x)
\end{pmatrix}
\begin{pmatrix}
0 \\
f(x)
\end{pmatrix} = \frac{1}{W}\begin{pmatrix}
-u_2(x)\,r(x) \\
u_1(x)\,r(x)
\end{pmatrix}
```
which means the final solutions can be found from:
```{math}
:label: varparsolns
A(x) &= -\int \frac{1}{W}\,u_2(x)\,r(x) \,\mathrm{d}x \\
B(x) &= \int \frac{1}{W}\,u_1(x)\,r(x) \,\mathrm{d}x \\
```

````{admonition} Worked example
:class: seealso
Lets try and solve the ODE:
```{math}
y'' + 4y' + 3y = \cosh(2x)
```
subject to the conditions $y(0) = -\frac{7}{15}, \,y'(0)=\frac{1}{15}$.  We note that this could be solved with method of undetermined coefficients, but this 
means we can double check our results later!

The solutions to the homoegenous ODE can be found from the ansatz $y = e^{\lambda\,x}$:

```{math}
\lambda^2 + 4\lambda + 3 = 0 &\Rightarrow \lambda = -1,\, -3 \\
u_1(x) &= e^{-x} \\
u_2(x) &= e^{-3x}
```
which means that in order to construct the full solution:
```{math}
y(x) = A(x)\,u_1(x) + B(x)\,u_2(x)
```
We need the Wronskian $W(x)$ of the system, here given by:
```{math}
W = \begin{vmatrix} 
e^{-x} & e^{-3x} \\
-e^{-x} & -3e^{-3x}
\end{vmatrix} = -3e^{-4x} - (-e^{-4x}) = -2e^{-4x}
```
and so using {eq}`varparsolns`:
```{math}
A(x) &= \frac{1}{2}\int e^{4x}\,e^{-3x}\,\cosh(2x) \,\mathrm{d}x  = \frac{1}{4}\int \Big(e^{3x}+e^{-x}\Big) \,\mathrm{d}x = \frac{1}{4}\Big(\frac{1}{3}e^{3x} - e^{-x}\Big) + C_1 \\
B(x) &= -\frac{1}{2}\int e^{4x}\,e^{-x}\,\cosh(2x) \,\mathrm{d}x = -\frac{1}{4}\int \Big(e^{5x} + e^{x}\Big) \,\mathrm{d}x = -\frac{1}{4}\Big(\frac{1}{5}e^{5x} + e^{x}\Big) + C_2
```
wher $C_1,\, C_2$ are constants.  This means the final solution is given by:
```{math}
y &= \Big(\frac{1}{12}e^{3x} - \frac{1}{4}e^{-x}\Big)e^{-x} - \Big(\frac{1}{20}e^{5x} - \frac{1}{4}e^{x}\Big)e^{-3x} + \Big(C_1\,e^{-x} + C_2\,e^{-3x}\Big) \\
&= \frac{1}{12}e^{2x} - \frac{1}{4}e^{-2x} - \frac{1}{20}e^{2x} - \frac{1}{4}e^{-2x} + \Big(C_1\,e^{-x} + C_2\,e^{-3x}\Big)\\
&= \frac{1}{60}\Big(2e^{2x} - 30e^{-2x} \Big) + \Big(C_1\,e^{-x} + C_2\,e^{-3x}\Big)
```
Given the initial conditions, we find that:
```{math}
y(0) &= \frac{-28}{60} + \Big(C_1 + C_2\Big) = -\frac{7}{15} \Rightarrow C_1 + C_2 = 0\\
y'(x) &= \frac{1}{60}\Big(4e^{2x} + 60e^{-2x} \Big) + \Big(-C_1\,e^{-x} -3 C_2\,e^{-3x}\Big)\\
y'(0) &= \frac{64}{60} + \Big(-C_1 - 3C_2\Big) = \frac{1}{15} \Rightarrow -C_1 - 3C_2 = -1
```
which we can solve as $C_1 = 1/2,\, C_2 = -1/2$, which gives final solutions as:
```{math}
y(x) = \frac{1}{30}\Big(e^{2x} - 15e^{-2x} +15e^{-x} - 15 \,e^{-3x}\Big)
```
which we can check gives the right answer as:
```{math}
y(x) &= \frac{1}{30}\Big(e^{2x} - 15e^{-2x} +15e^{-x} - 15 \,e^{-3x}\Big)\\
y'(x) &= \frac{1}{30}\Big(2e^{2x} + 30e^{-2x} - 15e^{-x} + 45 \,e^{-3x}\Big)\\
y''(x) &= \frac{1}{30}\Big(4e^{2x} - 60e^{-2x} + 15e^{-x} - 135 \,e^{-3x}\Big) \\
\Rightarrow y'' + 4y' + 3y &= \frac{1}{30}\Big[(4+8+3)e^{2x} + (-60 + 120 -45) e^{-2x} \\
&+ (15-60+45)e^{-x} + (-135+180-45)\,e^{-3x}\Big] \\
&= \frac{1}{30}\Big(15e^{2x} + 15 e^{-2x}\Big) = \cosh(2x)
```
and so the solutions are correct!
````

