
# ODE Methods - Reduction of Order

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

## Euler Equations

As a warm up, lets try to solve problems of the form:
```{math}
:label: EulerEqn
ax^2\,y′′+bx\,y′+cy=0
```
We do so by using an ansatz of the form $y = x^n$, which means that:
```{math}
x^{n}\left( an(n-1) + bn + c\right) = 0
```
A quadratic (which we call the characteristic equation) that we can solve:
```{math}
an^2 + (b-a)n + c = 0 \Rightarrow n = \frac{a-b \pm \sqrt{b^2-2ab + a^2 - 4ac}}{2a}
```
which means there are three distinct cases to solve for here (to begin with assume $x > 0$ to avoid any additional complications with complex solutions)

1\. *Two distinct, real roots $n = n_1,\, n_2$*

Since the ODE {eq}`EulerEqn` here is linear, we can find the superposition of solutions:
```{math}
y = A\,x^{n_1} + B\,x^{n_2},\, \qquad n_1,\, n_2 \in \mathbb{R}
```

2\. *One repeated, real root $n$*

We find that solving the characteristic equation, the only root is:
```{math}
n = \frac{a-b}{2a}
```
giving a solution $y_1 = Ax^n$.  But there should be two solutions to the ODE {eq}`EulerEqn`, so we can use an ansatz of the form:
```{math}
y_2 = x^{n}\,f(x)
```
to find $y_2$, by solving for $f(x)$.  We can think of $f(x)$ here is a **bridging** function between the different solutions $y_1,\,y_2$.  

Using this ansatz, the ODE takes the form:
```{math}
y &= x^n\,f \\
y' &= nx^{n-1}\,f + x^n\,f' \\
y'' &= n(n-1)x^{n-2}\,f + 2nx^{n-1}\,f' + x^{n}f''\\
\Rightarrow ax^2\,y′′+bx\,y′+cy &= ax^{n+1}\,f'' + (2an+b)\,x^{n+1}\,f' + (an(n-1) + bn + c)\,x^n\,f = 0
```
This can be simplified straight away since we are using the value of $n$ which satisfies the characteristic equation $an(n-1) + bn + c = 0$, therefore the equation reduces to:
```{math}
ax^{n+1}\,f'' + (2an+b)\,x^{n+1}\,f' = 0 
```
using the fact that $\displaystyle n = \frac{a-b}{2a} \Rightarrow 2an + b = a$ means:
```{math}
ax^{n+1}\left(xf'' + f'\right) = 0
```
which can be solved as a linear 1st order ODE in $f'$:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\left( xf'\right) = 0 \Rightarrow xf' = A 
```
which means the form of $f(x)$ is given by:
```{math}
f(x) = A\ln(x) + B
```
and therefore the solution here is:
```{math}
y = x^n\,\left(A \ln(x) + B\right)
```

3\. *Two complex roots $n = \lambda \pm i\mu$*

We can solve the characteristic equation here, with the proviso $(b-a)^2 - 4ac < 0$:
```{math}
n = \frac{(a-b)\pm i\sqrt{4ac-(b-a)^2}}{2a} = \lambda \pm i \mu,\qquad \lambda,\, \mu \in \mathbb{R}
```
If we look at the solutions here, lets start with $n = \lambda + i \mu$:
```{math}
y_1 = Ax^{\lambda + i\mu} = Ae^{\ln(x^{\lambda + i \mu}} = Ae^{(\lambda + i\mu)\ln(x)} = Ax^{\lambda}\left( \cos(\mu\ln(x)) + i \sin(\mu\ln(x))\right)
```
where we have used the Ruler function to convert this expression into one with trigonometric and power law functions.  We could do a similar exercise with $y_2$, the 
only difference here being a $-$ sign in the middle, so the overal solution $y = y_1 + y_2$ can be written as:
```{math}
y = y_1 + y_2 = x^{\lambda}\left(A\cos(\mu\ln(x)) + B \sin(\mu\ln(x))\right)
```
where $A,\, B \in \mathbb{C}$ in general, but with real boundary conditions they will turn out to be real.  

### Other ranges of $x$

So far we have taken $x>0$ to ensure all of our solutions here are real, however if we look again at {eq}`EulerEqn`, taking a coordinate transformation $t = -x$ and 
defining a function $z$ such that:
```{math}
z(t) = y(x) = y(-t)
```
then this means that:
```{math}
\frac{\mathrm{d}}{\mathrm{d}t} z(t) = \dot{z}(t) &= - \frac{\mathrm{d}}{\mathrm{d}x} y(x) = y'(x)\\
\frac{\mathrm{d}^2}{\mathrm{d}t^2} z(t) = \ddot{z}(t)&= + \frac{\mathrm{d}^2}{\mathrm{d}x^2} y(x) = y''(x)
```
and therefore {eq}`EulerEqn` reads as:
```{math}
a(-t)^2\ddot{z} + b(-t)(-\dot{z}) + cz &= 0 \\
\Rightarrow at^2\ddot{z} + bt\dot{z} + cz = 0
```
This shows that for $t>0$ we can still have real solutions to this ODE, there would follow the same form as those found for $>0$ - but this range corresponds to $x<0$!

Looking at how this could change the solutions, say for case (1) with real, distinct roots in $n$:
```{math}
z(t) = At^{n_1} + Bt^{n_1} \Rightarrow y(x) = A(-x)^{n_1} + B(-x)^{n_2}, \qquad x < 0
```

Therefore the argument of these solutions is always $|x|$ irrespective of whether $x<0$ or $x > 0$, therfore we modify our solutions to be of the form:

1\. $y = A\,x^{n_1} + B\,x^{n_2} \longrightarrow y = A\,|x|^{n_1} + B\,|x|^{n_2}$

2\. $y = x^n\,\left(A \ln(x) + B\right) \Longrightarrow y = |x|^n\,\left(A \ln|x| + B\right)$

3\. $y = x^{\lambda}\left(A\cos(\mu\ln(x)) + B \sin(\mu\ln(x))\right) \longrightarrow y = |x|^{\lambda}\left(A\cos(\mu\ln|x|) + B \sin(\mu\ln|x|)\right)$

We notice that $x=0$ is not covered by these solutions as it corresponds to $cy=0$.

By a similar principle, we could define a variable of the form $t = x - s$, with predicably similar behaviour, therefore we can also shift the ODe to be of the form:
```{math}
a(x-s)^2y'' + b(x-s)y' + cy = 0
```
giving solutions of the form:
1\. $y = A\,x^{n_1} + B\,x^{n_2} \longrightarrow y = A\,|x-s|^{n_1} + B\,|x-s|^{n_2}$

2\. $y = x^n\,\left(A \ln(x) + B\right) \Longrightarrow y = |x-s|^n\,\left(A \ln|x-s| + B\right)$

3\. $y = x^{\lambda}\left(A\cos(\mu\ln(x)) + B \sin(\mu\ln(x))\right) \longrightarrow y = |x-s|^{\lambda}\left(A\cos(\mu\ln|x-s|) + B \sin(\mu\ln|x-s|)\right)$

however it is also clear here that this solution cannot contain the point $x=s$.

````{admonition} Worked example
:class: seealso, 
Solve the following ODE:
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
````


````{admonition} Further worked examples
:class: seealso, dropdown
1\. Solve the ODE $x^2y'' - 2y = 0, \qquad x >0$

Using the ansatz $y = x^n$:
```{math}
x^n \Big(n(n-1) - 2\Big) = 0 \Rightarrow n^2 - n - 2 = (n-2)(n+1) = 0
```
which has roots of $n = -1,\, 2$ and hence
```{math}
y = Ax^2 + Bx^{-1}
```

2\. Solve the ODE $x^2\,y'' - 3x\,y' + 4y = 0, \qquad x >0$

Using the ansatz $y = x^n$:
```{math}
x^{n}\Big(n(n-1)-3n+4 \Big) &= 0 \Rightarrow n^2-4n+4 = 0 \\
(n-2)^2 &= 0
```
which has a repeated root of $n=2$, so one of the solutions is $y = Ax^2$.  We can then use:
```{math}
y &= x^2 \,f(x) \\
y' &= 2x\,f + x^2\,f' \\
y'' &= 2\,f + 2x\,f' + 2x\,f' + x^2\,f'' = 2\,f + 4x\,f' + x^2\,f''
```
substituting these results in we find:
```{math}
x^2\,y'' - 3x\,y' + 4y = x^4\,f''+ (4x^3-3x^3)\,f' + (2x^2-6x^2+4x^2)\,f = 0 
```
which means we have to solve:
```{math}
x^4\,f'' + x^3\,f' = 0 \Rightarrow f'' + \frac{1}{x}f' = 0
```
Using the integrating factor method, with $\mu = e^{\int \frac{1}{x}\,\mathrm{d}x} = x$ we find:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\left(x\,f' \right) = 0 \Rightarrow x\,f' = C 
```
and so the solution is found as:
```{math}
f' = \frac{C}{x} \Rightarrow f(x) = C\ln(x)+D
```
where $C,\, D$ are constants to be found, so the final solution is:
```{math}
y = x^2(A + B\ln(x))
```

3\. Find the solution to the following differential equation on any interval not containing $x = - 6$:
```{math}
3 ( x + 6 )^2 y'' + 25 ( x + 6 ) y' - 16 y = 0
```
Using the ansatz $y = |x+6|^n$ we find:
```{math}
|x+6|^n\left(3n(n-1) + 25n - 16 \right) = 0 \Rightarrow 3n^2 + 22n - 16 = 0
```
which is solved for $(3n - 2)(n + 8) = 0$ nd so $n = \frac{2}{3}, \,-8$, meaning that the general solution is of the form:
```{math}
y = A|x+6|^{2/3} + B|x+6|^{-8}
```
````



## Reduction of Order
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
a(x)\,y'' + b(x)\,y' + c(x)\,y = f(x) \longrightarrow y'' + p(x)\,y' + q(x)\,y  = r(x)
```
where we have relabelled $\displaystyle p(x) = \frac{b(x)}{a(x)},\, q(x) = \frac{c(x)}{a(x)},\, r(x) = \frac{f(x)}{a(x)}$ for simplicity.  

If we know a solution $y_1(x)$ of the homogeneous problem $y_1'' + p\,y_1'+q\,y_1 = 0$, then the solution to 
the homogeneous problem will be of the form:
```{math}
y_2(x) = u(x)\,y_1(x)
```
where $u(x)$ can be found from the complicated expression:
```{math}
u(x) = \int \left(C\,y_1^{-2}\,e^{-\int p\,\mathrm{d}x}\right)\,\mathrm{d}x
```
and for the inhomogeneous problem will be of the form:
```{math}
u(x) = \int \left(\frac{\int y_1\,r\,e^{\int p\,\mathrm{d}x}\,\mathrm{d}x + C}{y_1^2\,e^{\int p\,\mathrm{d}x}}\right)\,\mathrm{d}x
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
and for the homogeneous problem, where $r=0$, we find:
```{math}
u(x) = \int \left(C\,y_1^{-2}\,e^{-\int p\,\mathrm{d}x}\right)\,\mathrm{d}x
```

## Fundamental sets of solutions
One issue to contend with is what after all the work of bridging function we find that $y_2 = \alpha\,y_1,\, \alpha \in \mathbb{C}$ - i.e. the two solutions are just multipes of each other.  

We really need a way to consider the distinct-ness of any solutions we find or if we switch representation of solutions that they form a fundamental set, e.g. $\sin(x),\, \cos(x)$ could be 
considered to be a fundamental set, as could $e^{ix},\, e^{-ix}$, but if we mix the two $\cos(x),\, e^{ix}$ then this is not a fundamental set and we run the risk of having 
duplicte solutions.  

Lets start with a 2nd order system which has two fundamental solutions $y_1,\, y_2$ and has to satisy initial conditions $y(x_0) = y_0,\, y'(x_0) = y_0$:
```{math}
y(x) = Ay_1(x) + By_2(x) \Rightarrow \,&\, y(x_0) = y_0 = Ay_1(x_0) + By_2(x_0)\\
y'(x) = A{y_1}'(x) + B{y_2}'(x) \Rightarrow \,&\, y'(x_0) = {y_0}' = A{y_1}'(x_0) + B{y_2}'(x_0)
```
This means we have two equations to find two unknowns $A,\,B$, we could therefore to solve for these simultaneously, however a different method is to use a 2x2 matrix:
```{math}
\begin{pmatrix} y_0 \\ {y_0}' \end{pmatrix} = \begin{pmatrix} y_1 & y_2 \\ {y_1}' & {y_2}'\end{pmatrix}\,\begin{pmatrix} A \\ B \end{pmatrix}
```
which means to find $A,\,B$ we can use a matrix inverse:
```{math}
\frac{1}{y_1\,{y_2}' - {y_1}'\,y_2}\begin{pmatrix} {y_2}' & -y_2 \\ -{y_1}' & y_1\end{pmatrix}\,\begin{pmatrix} y_0 \\ {y_0}' \end{pmatrix} = \begin{pmatrix} A \\ B \end{pmatrix}
```
Therefore in order for $A,\,B$ to *exist*, the matrix determinant must be non-zero - this is feature here that tells us if we have a funamental set of solutions:
```{math}
W(y_1,\,y_2)(x) = \begin{vmatrix} y_1 & y_2 \\ {y_1}' & {y_2}'\end{vmatrix}
```
We call this determinant the **Wronskian**.

````{admonition} Worked example
:class: seealso

Show that the functions $y_1 = e^{\lambda x}$ and $y_2 = x\,e^{\lambda x}$ form a fundamental set of solutions.
```{math}
W(y_1,\,y_2)(x) = \begin{vmatrix} y_1 & y_2 \\ {y_1}' & {y_2}'\end{vmatrix} &= 
\begin{vmatrix} e^{\lambda x} & x\,e^{\lambda x} \\ \lambda\,e^{\lambda x} & \lambda\,x\,e^{\lambda x} + e^{\lambda x}\end{vmatrix}\\
&= e^{2\lambda x} (\lambda x + 1 - \lambda x) = e^{2\lambda x} 
```
and clearly for any finite $x$, $W \neq 0$, hence we have a fundamental set.
````

````{admonition} Further worked examples
:class: seealso, dropdown
1\. Show that the functions $y_1 = x^{n_1}$ and $y_2 = x^{n_2}$ form a fundamental set of solutions for $x > 0$

Lets switch to $y_1 = e^{n_1\,\ln(x)},\, y_2 = e^{n_2\,\ln(x)}$

```{math}
W(y_1,\,y_2)(x) = \begin{vmatrix} y_1 & y_2 \\ {y_1}' & {y_2}'\end{vmatrix} &= 
\begin{vmatrix} e^{n_1\,\ln(x)} & e^{n_2\,\ln(x)} \\ \frac{n_1}{x}\,e^{n_1\,\ln(x)} & \frac{n_2}{x}\,e^{n_2\,\ln(x)} \end{vmatrix}\\
&= e^{(n_1+n_2)\,\ln(x)} \left(\frac{n_2}{x} - \frac{n_1}{x}\right) = (n_1 - n_1)\,x^{n_1+ n_2 - 1}
```
and clearly for any finite $x$ and $n_1 \neq n_2$, $W \neq 0$, hence we have a fundamental set.


2\. Show that the functions $y_1 = x^{\lambda + \mu i} = e^{(\lambda + \mu i)\ln (x)}$ and 
$y_2 = x^{\lambda - \mu i}= e^{(\lambda - \mu i)\ln (x)}$ form a fundamental set of solutions, where $x > 0$ 

```{math}
W(y_1,\,y_2)(x) = \begin{vmatrix} y_1 & y_2 \\ {y_1}' & {y_2}'\end{vmatrix} &= 
\begin{vmatrix} e^{(\lambda + \mu i)\ln (x)} & e^{(\lambda - \mu i)\ln (x)} \\ \frac{(\lambda + \mu i)}{x}e^{(\lambda + \mu i)\ln (x)} & \frac{(\lambda - \mu i)}{x}e^{(\lambda - \mu i)\ln (x)}\end{vmatrix}\\
&= e^{(\lambda^2 + \mu^2)\ln(x)}\left(\frac{\lambda - \mu i}{x} - \frac{\lambda + \mu i}{x} \right) \\
&= -\frac{2\mu\,i\,e^{(\lambda^2 + \mu^2)\ln(x)}}{x} = -2\mu\,i\,x^{\lambda^2 + \mu^2-1}
```
and clearly for any finite $x > 0$, $W \neq 0$, hence we have a fundamental set.


````