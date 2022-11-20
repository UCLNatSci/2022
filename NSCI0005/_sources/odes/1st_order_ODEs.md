# First Order ODEs


````{admonition} Definition
:class: notice
In general a first order ordinary differential equation (ODE) is of the form: 

```{math}
:label: ode2general
y^{\prime}(x)=f(x,\,y)
```
where $f(x,\,y)$ is some function, which can in general have $x$ and $y$ dependance.

````

## Separation of variables form
Of all the techniques for solving first order ODEs, separation of variables is the simplest to understand, being essentially a direct application of 
Fundamental Theorem of Calculus.  The technique requires us to take a look at whether the variable dependence can be totally separated on different 
sides of the equation.

````{admonition} Definition
:class: notice
A separable first order ODE is of the form: 

```{math}
:label: ode2general
\frac{\mathrm{d}y}{\mathrm{d}x} = f(x)\,g(y)
```
where we have separated out the $x$ dependance into the function $f(x)$ and $y$ dependance into the function $g(y)$.  Using the FTC we find:
```{math}
\frac{\mathrm{d}y}{g(y)} = f(x)\,\mathrm{d}x 
```
which we can then be integrated:
```{math}
\int\frac{\mathrm{d}y}{g(y)} = \int f(x)\,\mathrm{d}x 
```
and then we would rearrange to (if possible) find $y(x)$.
````

````{amonition} Worked example
To solve the ODE:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = x^2y
```
we can separate the $x$ and the $y$ dependence to give:

```{math}
\frac{1}{y}\frac{\mathrm{d}y}{\mathrm{d}x} = x^2, \quad (y \neq 0)
```

Proceeding with integration of both sides, with respect to $x$, using the chain rule to rewrite:

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}\mathrm{d}x = \mathrm{d}y
```

We can then integrate both sides:

```{math}
\int\frac{1}{y}\mathrm{d}y = \int x^2\mathrm{d}x \quad \longleftrightarrow \quad \ln|y| = \frac{1}{3}x^3 + \text{const}
```

This implicit relationship may be rearranged to obtain a solution for $y$ explicitly in terms of $x$, with the sign of the arbitrary 
constant depending on whether $y > 0$ or $y<0$:

```{math}
y=\displaystyle A\,e^{x^3/3}, \quad A \in \mathbb{R}.
```
````

````{admonition} Practice questions
:class: seealso, dropdown

Decide which of the following expressions are separable, and have a go at solving those that are separable:

1\. $\displaystyle (1+e^x)y\frac{\mathrm{d}y}{\mathrm{d}x} = e^x$

2\. $\displaystyle \frac{\mathrm{d}y}{\mathrm{d}x} = (3x + 2y + 1)^2$

3\. $\displaystyle \frac{1}{x} + x\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{\mathrm{d}y}{\mathrm{d}x}$

4\. $\displaystyle \frac{x}{y}\frac{\mathrm{d}y}{\mathrm{d}x} = x^2 - 1$

5\. $\displaystyle x^2\frac{\mathrm{d}y}{\mathrm{d}x} = y^2 - 1$

6\. $\displaystyle xy\frac{\mathrm{d}y}{\mathrm{d}x} = \ln(x),\   y(1)=0,\ x \geq 1$

7\. The rate of growth of a population 𝑃 is proportional to itself. Set up and solve a differential equation for the population, given that the initial 
population is $P_0$ and it doubles after 10 years.

````

````{admonition} Solutions
:class: seealso, dropdown

1\. Rearranging and separating out variables:
```{math}
\int y \,\mathrm{d}y = \int\frac{e^x}{1+e^x}\,\mathrm{d}x 
```
This can then just be integrated:
```{math}
\frac{y^2}{2} = \ln(e^x+1) + C
```

2\. This problem is not separable.

3\. 
```{math}
\frac{1}{x} = (1-x)\frac{\mathrm{d}y}{\mathrm{d}x} \Rightarrow   \frac{\mathrm{d}y}{\mathrm{d}x}= \frac{1}{x(1-x)} 
```
If we use partial fractions we find that this fraction can be simplified:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{1}{x} + \frac{1}{1-x} 
```
which we can integrate to find:
```{math}
\int\mathrm{d}y &= \int \Big(\frac{1}{x} + \frac{1}{1-x} \Big)\,\mathrm{d}x\\
y &= \ln\Big|\frac{x}{1-x}\Big|+C
```

4\. 
```{math}
\int \frac{1}{y\,}\mathrm{d}y &= \int \left(x-\frac{1}{x}\right)\,\mathrm{d}x\\
\ln|y| &= \frac{x^2}{2}-\ln|x| + \ln A \\
y &= \frac{Ae^{x^2/2}}{x}, \quad A \in \mathbb{R}
```

5\. 
```{math}
\frac{\mathrm{d}y}{y^2 - 1}  = \frac{\mathrm{d}x}{x^2}
```
If we use partial fractions, we can reduce the fraction on the LHS down to:
```{math}
\frac{1}{y^2 - 1} &= \frac{1}{(y - 1)(y+1)}\\
&=\frac{1}{2}\int \left(\frac{1}{y-1}-\frac{1}{y+1}\right)
```
and so to solve:
```{math}
\frac{1}{2}\int \left(\frac{1}{y-1}-\frac{1}{y+1}\right)\,\mathrm{d}y &= \int\frac{1}{x^2}\,\mathrm{d}x \\
\ln\left(\frac{y-1}{y+1}\right) &= -\frac{2}{x} + C,\quad -1 < y < 1
```
which after some rearrangement gives:
```{math}
y = \frac{2}{1-e^{-2/x+C}}-1
```

6\. 
```{math}
\int y\,\mathrm{d}y &= \int \frac{\ln(x)}{x}\,\mathrm{d}x \\
y^2 &= (\ln(x))^2 + C
```
If $y(1) = 0 \Rightarrow C = 0$ so solution is:
```{math}
y = \pm\ln(x)
```

7\.
The differential equation will therefore have the form:
```{math}
\frac{\mathrm{d}P}{\mathrm{d}t} = \lambda P
```
Which can be separated to:
```{math}
\int_{P_0}^{P}\frac{1}{P}\,\mathrm{d}P &= \int_{0}^t\lambda\, \mathrm{d}t \\
\ln P &= \lambda t + \ln P_0\\
P &= P_0e^{\lambda t}
```
If $P(10) = 2P_0 \Rightarrow \lambda = \displaystyle \frac{1}{10}\ln(2)$, so the solution is:
```{math}
P = P_0\,2^{t/10}
```

````



## Integrating factor form

````{admonition} Integrating facor method
Problems which are the following form can be solved by the integrating factor method:

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + f(x)\,y = g(x)
```
If we multiply through by a function $\mu(x) = e^{\int f(x) \,\mathrm{d}x}$, which we call an **integrating factor (IF)**:

```{math}
\mu \,\frac{\mathrm{d}y}{\mathrm{d}x} +  y\,\mu\,f(x)  = \mu\,g(x)
```

and compare this with:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\left(\mu y \right)=\mu \frac{\mathrm{d}y}{\mathrm{d}x}+y\frac{\mathrm{d}\mu}{\mathrm{d}x}
```

By equating these two equations, it can be seen that we can make the integrating factor work 
if we choose $\mu$ to satisfy:

```{math}
\frac{\mathrm{d}\mu}{\mathrm{d}x}=\mu \,f(x)
```

We can solve this equation by separation, the solution is:
```{math}
\mu = e^{\int f(x)\,\mathrm{d}x}
```

This terms role is to cast the left hand side as an exact derivative - in order to make the problem integrable. 
````

The integrating factor technique can be written down in the form of an algorithm:

**1\.** Compute the integrating factor $\displaystyle \mu(x) = e^{\int f(x) \,\mathrm{d}x}$.

**2\.** Multiply the whole ODE by $\mu(x)$:
```{math}
e^{\int{f(x) \mathrm{d}x}}\,\frac{\mathrm{d}y}{\mathrm{d}x} + e^{\int{f(x) \mathrm{d}x}}\,f(x)\,y = e^{\int{f(x) \mathrm{d}x}}\,g(x)
```

**3\.** We find that the left-hand-side can be rewritten as a derivative $\displaystyle \frac{\mathrm{d}}{\mathrm{d}x}(\mu\, y)$:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\Big(y\,e^{\int f(x) \,\mathrm{d}x}\Big) = e^{\int f(x)\, \mathrm{d}x }\,g(x)
```

**4\.** Integrate both sides with respect to $x$:
```{math}
y\,e^{\int f(x)\, \mathrm{d}x} = \int \Big(e^{\int f(x)\, \mathrm{d}x}\,g(x)\Big)\,\mathrm{d}x
```

**5\.** Rearrange to find $y(x)$:
```{math}
:label: intfactorsoln
y(x) = \Big[\int \Big( e^{\int f(x)\, \mathrm{d}x}\,g(x)\Big)\,\mathrm{d}x + C\Big]\,e^{-\int f(x)\, \mathrm{d}x}
```
where $C$ is a constant.





````{admonition} Worked example
:class: seealso

Consider the following differential equation:
```{math}
:label: intfexample
\frac{\mathrm{d}y}{\mathrm{d}x}+\frac{y}{x}=\frac{\cos(x)}{x}, \quad (x\neq 0)
```
A quick check will show that this equation is not separable.  If we try to integrate directly, then we obtain:

```{math}
\int \,\mathrm{d}y + \int \frac{1}{x}y \,\mathrm{d}x = \int \frac{\cos(x)}{x}\,\mathrm{d}x
```

We can deal with the integral on the right (in principle) but the term $\displaystyle \int \frac{y}{x}\mathrm{d}x$ appearing on the left cannot be evaluated 
without knowing $y$, so this is a dead end.  

But observe that we can multiply equation {eq}`intfexample` throughout by $x$, to obtain:

```{math}
:label: intfexample2
x\frac{\mathrm{d}y}{\mathrm{d}x}+y=\cos(x), \quad (x\neq 0)
```

The expression on the left-hand side is an *exact derivative*:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(yx)=x\frac{\mathrm{d}y}{\mathrm{d}x}+y
```

Neat - this means that we can integrate equation {eq}`intfexample2` to obtain:

```{math}
xy=\int\cos(x)\mathrm{d}x
```

The final solution therefore is:

```{math}
y=\frac{1}{x}(\sin(x)+k)
``` 
where $k$ is an arbitrary constant. 

If we want to verify that the solution satisfies equation {eq}`intfexample`:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}+\frac{y}{x} &= \left[-\frac{1}{x^2}(\sin(x)+k)+\frac{1}{x}\cos(x)\right]+\frac{1}{x^2}(\sin(x)+k)\\
&=\frac{\cos(x)}{x}
```
````

````{admonition} Practice questions
:class: seealso, dropdown

In each of the following, determine whether the left-hand side is in the form of an exact derivative. If it is, then go ahead and solve 
the problem by direct integration. If the left hand side is not an exact differential then you do not have to solve the problem.

1\. 
```{math}
-\sin(x)\,y\,e^{\cos(x)}+e^{\cos(x)}\,\frac{\mathrm{d}y}{\mathrm{d}x}=x
```

2\. 
```{math}
-\sinh(x)\,y+\cosh(x)\,\frac{\mathrm{d}y}{\mathrm{d}x}=\sinh(2x)
```

3\. 
```{math}
\tan(x)\,\frac{\mathrm{d}y}{\mathrm{d}x}+\sec^2(x)\,y=\ln(x)
```

Solve the following ODE problems using the integrating factor technique:

4\. 
```{math}
x\frac{dy}{dx} + 2y = 4x^2
```

5\. 
```{math}
\displaystyle x^2\frac{dy}{dx}+3xy=e^{3x}
```

````

````{admonition} Solutions
:class: seealso, dropdown

1\. The LHS is given by the exact derivative $\displaystyle \frac{\mathrm{d}}{\mathrm{d}x}\left(y\, e^{\cos(x)}\right)$ and so the solution to this problem can be found by 
direct integration. The result is;
```{math}
y\,e^{\cos(x)}=\frac{x^2}{2}+k
```
where $k$ is an arbitrary constant.

2\. The LHS is not an exact derivative.

However if we multiply throughout by a factor $\mu = \text{sech}^2(x)$ then we obtain:

```{math}
\text{sech}(x)\frac{\mathrm{d}y}{\mathrm{d}x}-\text{sech}(x)\tanh(x)y=2\tanh(x)
```

Now the LHS can be written as an exact derivative $\frac{\mathrm{d}}{\mathrm{d}x}(\text{sech}(x)y)$ and so the problem can be solved by direct integration.


3\. The LHS is given by the exact derivative $\displaystyle \frac{\mathrm{d}}{\mathrm{d}x}(\tan(x)y)$ and so the solution to the problem is:
```{math}
\tan(x)y=x\ln(x)=x+k
```
where $k$ is an arbitrary constant.

4\.

First divide through by $x$ to put the ODE into the correct form, assuming that $x \neq 0$:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{2}{x}y = 4x
```

Comparing this form to the template equation we see that $\displaystyle f(x) = \frac{2}{x}$ and so:

```{math}
\int\,f(x)\,\mathrm{d}x = \int\frac{2}{x}\,\mathrm{d}x=2\ln(x)=\ln(x^2)+C
```

The IF is
```{math}
\mu = e^{\ln(x^2)}=x^2
```
and multiplying through by the IF gives:

```{math}
x^2\frac{\mathrm{d}y}{\mathrm{d}x}+2xy=4x^3
```

The left-hand side is now an exact derivative of $(x^2y)$! We can write the modified equation as:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(x^2y)=4x^3
```

Finally, integrating both sides with respect to $x$ gives:

```{math}
x^2y = x^4 + K \Rightarrow y = x^2 + \frac{K}{x^2}
```

where $K$ is an arbritary constant.  We can verify that the solution works by substituting it into the original ODE.

5\. 
Firstly rearrange this equation to:

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{3}{x}y = \frac{1}{x^2}e^{3x}
```

The IF is:
```{math}
\mu(x) = e^{\int f(x)\, \mathrm{d}x} = e^{\int 3/x\,\mathrm{d}x} = e^{3\ln(x)} = e^{\ln(x^3)} = x^3
```

Multiplying through by the IF gives:

```{math}
x^3\frac{\mathrm{d}y}{x} + 3x^2y = xe^{3x} \Longrightarrow \frac{\mathrm{d}}{\mathrm{d}x}(x^3y) = xe^{3x}
```

Integrating with respect to $x$ to solve:

```{math}
x^3y = \frac{e^{3x}}{3}\left(x-\frac{1}{3}\right) + K \Longrightarrow y = \frac{1}{3x^3} e^{3x}\left(x-\frac{1}{3}\right) + \frac{K}{x^3}
```
where $K$ is an arbritary constant.
````





## Benoulli form

````{admonition} Defintion
A Benoulli differential equation takes the form:
```{math}
:label: benoulliODE
\frac{\mathrm{d}y}{\mathrm{d}x} +P(x)\,y = Q(x)\,y^n,\, n \in \mathbb{R}
```
We see that for $n = 0,\, 1$ this reduces to cases already discussed, but for any other $n$ this equation is clearly non-linear in $y$.  We can 
however make progress using the substitution:
```{math}
u = y^{1-n}
```
which transforms {eq}`benoulliODE` into a linear differential equation of the form:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x}- (n-1)\,P(x)\,u = -(n-1)\,Q(x)
```
which can then be solved using the integrating factor method.
````

````{admonition} Worked example
:class: seealso
If we want to solve the ODE:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{y}{x} = xy^2
```
using the substitution $u = y^{-1}$ here (as the highest power on the RHS is $n=2$):
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} = -\frac{1}{y^2}\frac{\mathrm{d}y}{\mathrm{d}x} \Rightarrow \frac{\mathrm{d}y}{\mathrm{d}x} = -\frac{1}{u^2}\frac{\mathrm{d}u}{\mathrm{d}x}
```
and therefore:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{y}{x} &= -\frac{1}{u^2}\frac{\mathrm{d}u}{\mathrm{d}x} + \frac{x}{u} \\
xy^2 &= \frac{x}{u^2}
```
substituing these results in to the ODE:
```{math}
\Rightarrow -\frac{1}{u^2}\frac{\mathrm{d}u}{\mathrm{d}x} + \frac{x}{u} &= \frac{x}{u^2} \\
\frac{\mathrm{d}u}{\mathrm{d}x} - x\,u &= -x
```
which we can then solve using the IF method, with $\mu = e^{-x^2/2}$:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\Big(e^{-x^2/2}\,u\Big) &=  e^{-x^2/2}\,x \\
e^{-x^2/2}\,u &= \int \Big(e^{-x^2/2}\,x\Big)\,\mathrm{d}x 
```
Using a subsitution (or inspection) we can integrate this RHS term to find:
```{math}
e^{-x^2/2}\,u &= -e^{-x^2/2} + C \\
u(x) &= -1 + Ce^{x^2/2} \\
y(x) &= \frac{1}{Ce^{x^2/2}-1}
```
where we must not forget to return the answer back to the form of $y(x)$ at the end.
````


### Riccati form
````{admonition} Defintion
A Riccati differential equation takes the form:
```{math}
:label: riccatiODE
\frac{\mathrm{d}y}{\mathrm{d}x} = q_0(x) + q_1(x)\,y(x) + q_2(x)y^2(x)
```
which we can recast in terms of a variable $u(x)$, which satisfies an ODE:
```{math}
u'' - R\,u' + S\,u =0, \quad R = q_1 + \frac{q_2'}{q_2}, \quad S = q_0\,q_2
```
and we can solve to find $y(x)$:
```{math}
y = -\frac{u'}{q_2\,u}
```
````

We see that if $q_0=0$, then this just reduces to a Benoulli equation with $n=2$ and if $q_2=0$, then this is just in integrating form factor, so this 
equation can be thought of as a hybrid between the two.

````{admonition} Worked example
:class: seealso
Consider the ODE:
```{math}
y' - \frac{2y}{x} = - x^2\,y^2 \\
```
this equation can be rewritten as:
```{math}
y' = \frac{2y}{x}-x^2\,y^2
```
and then transformed into the 2nd order ODE:
```{math}
u'' - R\,u' + S\,u &= 0 \\
R = \frac{4}{x}\,\quad & S = 0 \\
\Rightarrow u'' -\frac{4}{x} \,u' &= 0
```
which we can solve using an IF method, with $\mu = e^{-\int 4/x\,\mathrm{d}x} = x^{-4}$:
```{math}
x^{-4}\,u'' - 4\,x^{-5} \,u' &= 0 \\
\Big(x^{-4}\,u'\Big)^\prime &= 0
```
Since the derivative of a constant is zero, this means:
```{math}
u' &= C_1\,x^4 \\
u &= \frac{C_1\,x^5}{5} + C_2 \\
\Rightarrow y &= -\frac{C_1\,x^2}{\frac{C_1x^5}{5} + C_2}\\
```
where $C_1,\, C_2$ are constants, we can tidy this expression up:
```{math}
y = -\frac{5x^2}{x^5 + C_3}
```
where $C_3$ is a constants.
````


## Perfect differential form 
If we are struggling to find a first order ODE method that works and has clearly integrable terms, we can try the perfect differential test.  

Recall from the multivariable change rule, the total differential of a function $f(x,\,y)$ is:

```{math}
\mathrm{d}f = \frac{\partial f}{\partial x}\,\mathrm{d}x + \frac{\partial f}{\partial y}\,\mathrm{d}y 
```

now if we examine the most general form of a first order ODE:

```{math}
Q(x,\,y)\,\frac{\mathrm{d}y}{\mathrm{d}x} + P(x,\, y) = 0
```

which we can rewrite as:

```{math}
 P(x,\, y)\,\mathrm{d}x + Q(x,\,y)\,\mathrm{d}y = 0
```

we can see that these bear a striking resembalance and remember that if:
```{math}
\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} 
```

then this is a perfect differential, where here $\mathrm{d}f = 0$ and so:
```{math}
f(x,\,y) = C 
```
where $C$ is a constant.  

````{admonition} Worked example
:class: seealso
Lets try to solve the non-linear, first order ODE:
```{math}
2x^2\,y\,\frac{\mathrm{d}y}{\mathrm{d}x} + 2x\,y^2 = 1
```
we find that we can identify:

```{math}
P(x,\,y) &= 2x\,y^2-1\\
Q(x,\,y) &= 2x^2\,y
```
so we check that the partial derivatives agree:
```{math}
\frac{\partial P}{\partial y} = 4xy \\
\frac{\partial Q}{\partial x} = 4xy
```
which they do and therefore we want to obtain the function $f(x,\, y)$:
```{math}
P(x,\,y) &= \frac{\partial f}{\partial x} = 2x\,y^2-1 \Rightarrow f(x,\,y) = \int (2x\,y^2-1)\,\mathrm{d}x = x^2\,y^2 - x + g(y)\\
Q(x,\,y) &= \frac{\partial f}{\partial y} = 2x^2\,y \Rightarrow f(x,\,y) = \int (2x^2\,y)\,\mathrm{d}y = x^2\,y^2 + h(x)\\
```
which we can see will agree if $g(y) = 0,\, h(x) = -x$:
```{math}
f(x,\,y) = x^2\,y^2 - x
```
and given that here $f(x,\,y) = C$, where $C$ is a constant, this means that we have:

```{math}
x^2\,y^2 - x &= C \\
y &= \pm\sqrt{\frac{1}{x} + \frac{C}{x^2}}
```
````

````{admonition} Practice question
:class: seealso, dropdown
1\. Solve the non-linear ODE:
```{math}
\Big(2xy + e^{-x^2}\Big) \,\frac{\mathrm{d}y}{\mathrm{d}x} + y^2 = 2xy\,e^{-x^2}
```
with the condition $y(0) = 1$.
````

````{admonition} Solution 
:class: seealso, dropdown
1\. First write in total differential form:
```{math}
\Big(y^2 - 2xy\,e^{-x^2}\Big)\,\mathrm{d}x + \Big(2xy + e^{-x^2}\Big)\,\mathrm{d}y &= 0\\
P(x,\,y)\,\mathrm{d}x + Q(x,\,y)\,\mathrm{d}y &= 0
```
then check that this is an exact differential:

```{math}
\frac{\partial P}{\partial y} &= 2y - 2xe^{-x^2}\\
\frac{\partial Q}{\partial x} &= 2y - 2xe^{-x^2}
```
and so it is!  So to detemine $f(x,\, y)$:

```{math}
\frac{\partial f}{\partial x} &= y^2 - 2xy\,e^{-x^2} \Rightarrow f(x,\,y) = \int \Big(y^2 - 2xy\,e^{-x^2}\Big)\,\mathrm{d}x = xy^2 + y\,e^{-x^2} + g(y)\\
\frac{\partial f}{\partial y} &= 2xy + e^{-x^2} \Rightarrow f(x,\,y) = \int \Big(2xy + e^{-x^2}\Big)\,\mathrm{d}y = xy^2 + y\,e^{-x^2} + h(x)\\
```
which agree if $g(y) = h(x) = 0$, therefore:

```{math}
xy^2 + y\,e^{-x^2} = C
```
where $C$ is a constant.  Given the condition $y(0) = 1$:
```{math}
xy^2 + y\,e^{-x^2} = 1
```
which we could then solve to find $y(x)$, as this is quadratic $xy^2 + y\,e^{-x^2} - 1 = 0$:

```{math}
y = \frac{-e^{-x^2} \pm \sqrt{e^{-2x^2}+4x}}{2x}
```

````

## Modelling systems with ODEs


````{admonition} Worked example
:class: seealso
The number of species S living on an island or habitat fragment of area A can be modelled as 
$S = cA^z$, where $z > 0$. We can measure area in units that make $c = 1$, simplifying this equation into 
$S = A^z$. A common value for $z$ is approximately 0.45 (found by data fitting). 

Find the critical value when $\frac{\mathrm{d}S}{\mathrm{d}A} = 1$: and explain the significance of this 
for biodiversity conservation.

Given that:
```{math}
\frac{\mathrm{d}S}{\mathrm{d}A} = 0.45\,A^{-0.55}
```
then we can aim to find the critical value when $\frac{\mathrm{d}S}{\mathrm{d}A} = 1$:
```{math}
0.45\,{A_c}^{-0.55} = 1 \Rightarrow A_c = \left(\frac{9}{20}\right)^{20/11} \simeq 0.234\dots
```
For $A < A_c$, any loss of habitat results in a proportionally greater loss of species, as we can see from:
```{figure} SvA.png
---
name: SpeciesArea
---
```


````

