
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
:class: seealso, dropdown
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


````

