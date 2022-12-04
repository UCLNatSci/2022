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

````{admonition} Practice questions
:class: seealso, dropdown
1\. Solve the non-linear ODE:
```{math}
\Big(2xy + e^{-x^2}\Big) \,\frac{\mathrm{d}y}{\mathrm{d}x} + y^2 = 2xy\,e^{-x^2}
```
with the condition $y(0) = 1$.

2\. Solve the non-linear ODE:
```{math}
3y^3\,e^{3xy} - 1 + \left(2y\,e^{3xy} + 3x\,y^2\,e^{3xy} \right)\,\frac{\mathrm{d}y}{\mathrm{d}x} = 0
```
with the condition $y(0) = 1$.
````

````{admonition} Solutions
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
this condition is met and so to detemine $f(x,\, y)$:

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

2\. First write in total differential form:
```{math}
\left(3y^3\,e^{3xy} - 1\right)\mathrm{d}x + \left(2y\,e^{3xy} + 3x\,y^2\,e^{3xy} \right)\,\mathrm{d}y &= 0\\
P(x,\,y)\,\mathrm{d}x + Q(x,\,y)\,\mathrm{d}y &= 0
```
then check that this is an exact differential:

```{math}
\frac{\partial P}{\partial y} &= 9y^2\,e^{xy} + 9xy^3\,e^{xy}\\
\frac{\partial Q}{\partial x} &= 6y^2\,e^{sy} + 3y^2\,e^{3xy} + 3x\,y^3\,e^{xy} = 9y^2\,e^{xy} + 9xy^3\,e^{xy}
```
this condition is met and so to detemine $f(x,\, y)$:

```{math}
\frac{\partial f}{\partial x} = 3y^3\,e^{3xy} - 1\Rightarrow f(x,\,y) = \int \Big(3y^3\,e^{3xy} - 1\Big)\,\mathrm{d}x = y^2\,e^{3xy} - x + g(y)
```
We could attempt the same process on $f_y$ however this will involve multiple integration by parts calculations (we could simplify this with a 
reduction formula $\int y^n\,e^{axy}\,\mathrm{d}y$), but here we will instead differentiate this preliminary expression for $f(x,\,y)$ and then 
compare $f_y$ with what is left to figure out the anti-derivative:
```{math}
f   &= y^2\,e^{3xy} - x + g(y) \\
f_y &= 2y\,e^{3xy} + 3x\,y^2\,e^{3xy} + g'(y) \\
Q   &= 2y\,e^{3xy} + 3x\,y^2\,e^{3xy}
```

which tells us that $g'(y) = 0$ hence at most $g(y)$ is a constant, which we can absorb into the constant value for $f(x,\, y)$, therefore:

```{math}
y^2\,e^{3xy} - x  = C
```
where $C$ is a constant.  Given the condition $y(0) = 1$:
```{math}
1^2\,e^{0} - 0 = 1 = C
```
Thus the solution is:
```{math}
y^2\,e^{3xy} - x  = 1
```
Which we have to leave in this form as no simple elementary function solution exists.
````
### Fixing the perfect form

This method relies on the differential given being perfect, if it is not, then we cannot find the function $f(x,\, y)$.  However there is an analagous method for finding 
a multivariable integrating factor, allowing us to *potentially* convert imperfect differentials into a perfect form .

````{admonition} Multivariable integrating factor
Consider an imperfect differential:
```{math}
P(x,\,y)\,\mathrm{d}x + Q(x,\,y)\,\mathrm{d}y = 0\qquad \frac{\partial P}{\partial y} \neq \frac{\partial Q}{\partial x}
```

Lets introduce an integrating factor $M(x,\,y)$, which means now that:
```{math}
M(x,\,y)\,P(x,\,y)\,\mathrm{d}x + M(x,\,y)\,Q(x,\,y)\,\mathrm{d}y = 0 \qquad \frac{\partial (M P)}{\partial y} = \frac{\partial (M Q)}{\partial x}
```

and we can write the form of $M(x,\,y)$ as:
```{math}
M(x,\,y) = e^{\int G(x)\,\mathrm{d}x}\,e^{\int H(y)\,\mathrm{d}y}
```
````

The form of the multivariable integrating factor means that:
```{math}
M_x &= G(x)\,M \\
M_y &= H(y)\,M
```
Solving the key requirement for a perfect differential:
```{math}
\frac{\partial (M P)}{\partial y} &= M_y\,P + M\,P_y = M(H\,P + P_y)\\
\frac{\partial (M Q)}{\partial x} &= M_x\,Q + M\,Q_x = M(G\,Q + Q_x)\\
&\Rightarrow H(y)\,P + P_y = G(x)\,Q + Q_x
```
our aim here is separate out variables.  If each of $P(x,\,y),\, Q(x,\,y)$ are in a separable form:
```{math}
P(x,\,y) &= p_1(x)\,p_2(y) \\
Q(x,\,y) &= q_1(x)\,q_2(y)
``` 
which means therefore:
```{math}
H(y)\,p_1(x)\,p_2(y) + p_1(x)\,{p_2}'(y) &= G(x)\,q_1(x)\,q_2(y) + {q_1}'(x)\,q_2(y) \\
\Rightarrow p_1(x)\Big(H(y)\,p_2(y) + {p_2}'(y)\Big) &= q_2(y)\Big(G(x)\,q_1(x) + {q_1}'(x)\Big) \\
\frac{H(y)\,p_2(y) + {p_2}'(y)}{q_2(y)} &= \frac{G(x)\,q_1(x) + {q_1}'(x)}{p_1(x)} = C
```
where $C$ is a constant.  We find that this expression is a constant, because although the LHS depends *only* on $y$, the RHS does not, hence the LHS is overall a 
constant in $y$.  A similar argument holds for $x$ and the RHS, meaning that overall the two expressions are constant.  This mean therefore:

```{math}
H(y)\,p_2(y) + {p_2}'(y) &= C\,q_2(y) \Rightarrow H(y) = \frac{C\,q_2(y) - {p_2}'(y)}{p_2(y)} \\
G(x)\,q_1(x) + {q_1}'(x) &= C\,p_1(x) \Rightarrow G(x) = \frac{C\,p_1(x) - {q_1}'(x)}{q_1(x)}
```

````{admonition} Worked example
:class: seealso
Consider the differential:
```{math}
2x\sin(y)\,\mathrm{d}x + x^3\,\cos(y)\,\mathrm{d}y = 0
```
Looking at the derivatives:
```{math}
P_y &= 2x\,\cos(y) \\
Q_x &= 3x^2\,\cos(y)
```
hence this is not an exact differential.  

However since here the functions $P(x,\,y),\, Q(x,\,y)$ are separable, we can find:
```{math}
p_1(x) &= 2x \qquad p_2(y) = \sin(y) \\
q_1(x) &= x^3 \qquad q_2(y) = \cos(y)\\
H(y) &= \frac{C\,q_2(y) - {p_2}'(y)}{p_2(y)} = \frac{C\,\cos(y) - \cos(y)}{\sin(y)} = (C-1)\,\cot(y) \\
G(x) &= \frac{C\,p_1(x) - {q_1}'(x)}{q_1(x)} = \frac{2Cx - 3x^2}{x^3} = \frac{2C - 3x}{x^2}\\
\ln(M) &= \int G(x)\,\mathrm{d}x + \int H(y)\,\mathrm{d}y = (C-1)\ln|\sin(x)| - \frac{2C}{x} - 3 \ln|x|\\
\Rightarrow M(x,\,y) &= \frac{\sin^{C-1}(y)\,e^{-2C/x}}{x^3}
```
This means that our differential function is satisfied by:
```{math}
f_x &= \frac{2\,\sin^{C}(y)\,e^{-2C/x}}{x^2} \\
\Rightarrow f &= \int \frac{2\,\sin^{C}(y)\,e^{-2C/x}}{x^2}\,\mathrm{d}x = \frac{\sin^{C}(y)\,e^{-2C/x}}{C} + K_1(y)\\
f_y &= \sin^{C-1}(y)\,\cos(y)\,e^{-2C/x} \\
\Rightarrow f &= \int \sin^{C-1}(y)\,\cos(y)\,e^{-2C/x}\,\mathrm{d}y =  \frac{\sin^{C}(y)\,e^{-2C/x}}{C} + K_2(x)
```
and so $K_1 = K_2$ are constants here, which we can absorb into the constant for $f(x,\,y)$:
```{math}
\sin^{C}(y)= K\,e^{2C/x}
```
where $K$ will be fixed by initial conditions, however $C$ is a system parameter - it shows that this systems integrating factor is not unique! We could simplify this down to:
```{math}
\sin(y)= K\,e^{2/x}
```
````

## Substitution methods

We sometimes find that we can reduce more complicated (even non-linear) first order differential equations down to a solvable form using a substitution.  

### $y' = f(y/x)$ form

````{admonition} Definition
A **homogeneous** first order differential equation is one of the form:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = f\left(\frac{y}{x}\right)
```
and this is typically one that, through a substitution, can be solved using separation of variables.  Let our substitution here be $u = \displaystyle\frac{y}{x}$:
```{math}
y &= ux\\
\frac{\mathrm{d}y}{\mathrm{d}x} &= \frac{\mathrm{d}u}{\mathrm{d}x}x + u \\
\frac{\mathrm{d}u}{\mathrm{d}x}x + u &= f(u) \\
\Rightarrow \int\frac{\mathrm{d}u}{f(u) - u} &= \int\frac{\mathrm{d}x}{x}
```
and depending on the complexity of this LHS integral, this problem is solvable!
````

````{admonition} Worked example
:class: seealso
Solve the ODE $\displaystyle \frac{\mathrm{d}y}{\mathrm{d}x} = \frac{x^2 + y^2}{xy}$.

Rewriting this to be in the form $y' = f(y/x) = f(u)$, means:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{\mathrm{d}u}{\mathrm{d}x}x + u &= \frac{x}{y} + \frac{y}{x} = u + \frac{1}{u}\\
\Rightarrow \frac{\mathrm{d}u}{\mathrm{d}x}x &=  \frac{1}{u}
```
This is now in a form for separation of variables and integrating:
```{math}
\int u\,\mathrm{d}u &= \int \frac{\mathrm{d}x}{x} \\
\frac{1}{2}u^2 &= \ln|x| + C \\
u &= \sqrt{2 \ln|x| + C}
```
Remember that before finishing the question, we must convert this back into $y(x)$:
```{math}
y = x\sqrt{2 \ln|x| + C}
```
````

````{admonition} Practice questions
:class: seealso, dropdown

1\. Solve the following ODEs:

a\.
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} =\frac{y(x-y)}{x^2}
```
with condition $y(1) = 1$.

b\. 
```{math}
x\frac{\mathrm{d}y}{\mathrm{d}x} = y - x \sin^2\left(\frac{y}{x}\right)
```
with condition $y(1) =\displaystyle  \frac{\pi}{4}$.

````

````{admonition} Solutions
:class: seealso, dropdown

1\. Solve the following ODEs

a\.
Rearrange to get into the form $y' = f(y/x) = f(u)$:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} =\frac{y}{x} - \left(\frac{y}{x}\right)^2 = u - u^2
```
and then use the result $y' = xu' + u$:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x}x + u &= u - u^2 \\
\Rightarrow -\int \frac{\mathrm{d}u}{u^2} &= \int\frac{\mathrm{d}x}{x} \\
\frac{1}{u} &= \ln|x| + C \\
y &= \frac{x}{\ln|x| + C}
```
Using the condition $y(1) = 1$:
```{math}
1 = \frac{1}{0 + C} \Rightarrow C = 1
```
gives the final solution:
```{math}
y = \frac{x}{\ln|x| + 1}
```

b\. 
Rearrange to get into the form $y' = f(y/x) = f(u)$:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{y}{x} - \sin^2\left(\frac{y}{x}\right) = u - \sin^2(u)
```
and then use the result $y' = xu' + u$:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x}x + u &= u - \sin^2(u) \\
\Rightarrow -\int \frac{\mathrm{d}u}{\sin^2(u)} &= \int\frac{\mathrm{d}x}{x} \\
\int (-\text{cosec}^2(u))\,\mathrm{d}u &= \ln|x| + C
```
using the fact that $(\cot(u))' = -\text{cosec}^2(u)$, this means:

```{math}
\cot(u) = \ln|x| + C \Rightarrow \cot\left( \frac{y}{x}\right) = \ln|x| + C 
```
Using condition $y(1) = \displaystyle  \frac{\pi}{4}$:

```{math}
\cot\left(\frac{\pi}{4}\right) = 1 = 0 + C \Rightarrow C = 1
```
gives a  solution:
```{math}
\cot\left( \frac{y}{x}\right) = \ln|x| + 1 
```
and we could simplify further even:

```{math}
\tan\left( \frac{y}{x}\right) &= \frac{1}{\ln|x| + 1}\\
y = x\arctan&\left( \frac{1}{\ln|x| + 1}\right)
```
````

### $y' = f(ax+by)$ form


````{admonition} Definition
A first order differential equation of the form:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = f(ax+by)
```
can also be solved through a substitution which leads to separation of variables.  Let our substitution here be $u = ax+by$:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} = a + b\frac{\mathrm{d}y}{\mathrm{d}x} &= a + b\,f(u)\\
\Rightarrow \int\frac{\mathrm{d}u}{a + b f(u) } &= \int\,\mathrm{d}x
```
and depending on the complexity of this LHS integral, this problem is solvable!
````


````{admonition} Practice questions
:class: seealso, dropdown

1\. Solve the following ODEs:

a\.
```{math}
\frac{1}{2}\frac{\mathrm{d}y}{\mathrm{d}x} - \left(x + \frac{1-y}{4}\right)^2 = 0
```
with condition $y(0) = 2$.

b\. 
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = e^{9y-x}
```
with condition $y(0) = 0$.

````

````{admonition} Solutions
:class: seealso, dropdown

1\. Solve the following ODEs

a\.
Writing this in the form $y' = f(ax+by) = f(u)$:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = \left(4x -y + 1\right)^2
```

means we can pick our substitution to be $u = 4x - y$:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} &= 4 - \frac{\mathrm{d}y}{\mathrm{d}x}= 4 - \left(u + 1\right)^2\\
\Rightarrow \int \frac{\mathrm{d}u}{4 - \left(u + 1\right)^2} &= \int \mathrm{d}x \\
\int \frac{\mathrm{d}u}{u^2 + 2u -3} &= -x + C_1 \\

```

This integrand can be represented in terms of partial fractions:
```{math}
\frac{1}{u^2 + 2u -3} = \frac{1}{(u-1)(u+3)} &= \frac{A}{v-1} + \frac{B}{v+3} \\
&= \frac{A(u+3) + B(u-1)}{(u-1)(u+3)} \\
\Rightarrow  1 &= A(u+3) + B(u-1) 
```
For $u = 1$, $4A = 1 \Rightarrow A = \displaystyle \frac{1}{4}$ and for $u = -3$, $-4B = 1 \Rightarrow B = \displaystyle -\frac{1}{4}$, hence:

```{math}
\frac{1}{u^2 + 2u -3} &= \frac{1}{4}\left( \frac{1}{u-1} - \frac{1}{u+3} \right) \\
\Rightarrow \frac{1}{4}\int \left( \frac{1}{u-1} - \frac{1}{u+3} \right)\,\mathrm{d}u &= C_1 - x \\
\frac{1}{4}\Big(\ln|u-1| - \ln|u + 3|\Big) &= C_1 - x \\
\ln\left|\frac{u-1}{u+3}\right| &= C_2 - 4x
```
We then need to think about converting this back into $u = u(x,\,y)$, so lets try to collect together terms:
```{math}
\frac{u-1}{u+3} &= e^{C_2 - 4x} = C_3\,e^{-4x} \\
u-1 &= C_3\,(u+3)\,e^{-4x} \\
\Rightarrow u(1 - C_3\,e^{-4x}) &= 1 + 3C_3\,e^{-4x} \\
u = \frac{1 + 3C_3\,e^{-4x}}{1 - C_3\,e^{-4x}} &= 4x - y \\
\Rightarrow y &= 4x - \frac{1 + 3C_3\,e^{-4x}}{1 - C_3\,e^{-4x}}
```
and using the condition $y(0) = 2$:
```{math}
2 = 0 - \frac{1+3C_3}{1 - C_3} \Rightarrow C_3 = -3
```
giving a final solution of the form:
```{math}
y = 4x - \frac{1 - 9\,e^{-4x}}{1 + 3\,e^{-4x}}
```

b\. 
Writing in the form $y' = f(ax+by) = f(u)$:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = e^{9y-x}
```
which suggests we pick a substitution $u = 9y - x$:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} &= 9 \frac{\mathrm{d}y}{\mathrm{d}x} - 1 = 9 e^u - 1\\
\int \frac{\mathrm{d}u}{9 e^u - 1} &= \int\,\mathrm{d}x \\
\int \frac{e^{-u}}{9 - e^{-u}}\,\mathrm{d}u &= x + C_1\\
\ln|9 - e^{-u}| &= x + C_1
```
separating out the variables:
```{math}
9 - e^{-u} &= e^{x + C_1} = C_2\,e^x \\
e^{-u} &= 9 - C_2\,e^x \\
u &= -\ln(9 - c_2\,e^x) \\
\Rightarrow y &= \frac{1}{9}\Big( x - \ln(9 - C_2\,e^x)\Big)
```
and using the condition $y(0) = 0$:
```{math}
0 = \frac{1}{9}\Big(0 - \ln(9-C_2)\Big) \Rightarrow C_2 = 8
```
hence the final solution is:
```{math}
y = \frac{1}{9}\Big( x - \ln(9 - 8\,e^x)\Big)
```
````


### Benoulli form

````{admonition} Defintion
A Benoulli differential equation takes the form:
```{math}
:label: benoulliODE
\frac{\mathrm{d}y}{\mathrm{d}x} +P(x)\,y = Q(x)\,y^n,\, n \in \mathbb{R}
```
We see that for $n = 0,\, 1$ this reduces to cases already discussed, but for any other $n$ this equation is clearly non-linear in $y$.  

We can make progress in solving these sorts of ODEs by using the substitution:
```{math}
u = y^{1-n}
```
which transforms {eq}`benoulliODE` into a linear differential equation, since:
```{math}
u = y^{1-n} &\Rightarrow \frac{\mathrm{d}u}{\mathrm{d}x} = (1-n)y^{-n}\frac{\mathrm{d}y}{\mathrm{d}x}\\
\frac{\mathrm{d}y}{\mathrm{d}x} + P(x)\,y = Q(x)\,y^n &\Rightarrow (1-n)y^{-n}\frac{\mathrm{d}y}{\mathrm{d}x} + (1-n)\,P(x)\,y^{1-n} = (1-n)\,Q(x)\\
&\Rightarrow \frac{\mathrm{d}u}{\mathrm{d}x} - (n-1)\,P(x)\,u = -(n-1)\,Q(x)
```
and as this ODE is linear in $u$, it can be solved using the integrating factor method. 
````

````{admonition} Worked example
:class: seealso
If we want to solve the ODE:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{y}{x} = xy^2
```
we need to put it in the form $y' = f(u,\,x)$:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = xy^2 - \frac{y}{x}
```
as the highest power on the RHS is $n=2$, using the substitution $u = y^{1-n} = y^{-1}$:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} = -\frac{1}{y^2}\frac{\mathrm{d}y}{\mathrm{d}x}
```
and therefore:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} &= -\frac{1}{y^2}\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{1}{xy} - x \\
\frac{\mathrm{d}u}{\mathrm{d}x} &= \frac{u}{x} - x \\
\Rightarrow \frac{\mathrm{d}u}{\mathrm{d}x} - \frac{u}{x} &= - x
```
which we can then solve using the IF method, with $\mu = e^{\int -1/x\,\mathrm{d}x} = e^{-\ln|x|} = \frac{1}{x}$:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\Big(\frac{u}{x}\Big) &=  -1 \\
\frac{u}{x} &= -\int \,\mathrm{d}x \\
\frac{u}{x} &= -x + C \\
u &= x(C - x) \\
y &= \frac{1}{x(C-x)}
```
where we must not forget to return the answer back to the form of $y(x)$ at the end (if possible).
````

````{admonition} Practice questions
:class: seealso, dropdown

1\. 
Solve the following ODEs:

a\.
```{math}
6\frac{\mathrm{d}y}{\mathrm{d}x} - 2y = x\,y^4
```
which satisfies the condition $y(0) = -2$.

b\.
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{y}{x} - \sqrt{y} = 0
```
which satisfies the condition $y(1) = 0$,
````

````{admonition} Solutions
:class: seealso, dropdown

a\. 
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} - \frac{1}{3}y = \frac{1}{6}x\,y^4 
```
since the highest power on the RHS is $n = 4$, this means the substitution we need is $u = y^{1-n} = y^{-3}$ and hence:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} = -3y^{-4}\frac{\mathrm{d}y}{\mathrm{d}x}& \\
\Rightarrow -3y^{-4}\,\frac{\mathrm{d}y}{\mathrm{d}x} + y^{-3} &= -\frac{1}{2}x \\
\frac{\mathrm{d}u}{\mathrm{d}x} + u(x) &= -\frac{1}{2}x
```
which suggests an IF of the form $\mu = \displaystyle e^{\int\,\mathrm{d}x} = e^x$, hence:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x}\,e^x + u(x)\,e^x &= -\frac{1}{2}x\,e^x \\
\frac{\mathrm{d}}{\mathrm{d}x}\left(u\,e^x\right) &= -\frac{1}{2}x\,e^x \\
u\,e^x = -\frac{1}{2}\int x\,e^x\,\mathrm{d}x + C &= -\frac{1}{2}(x-1)\,e^{x} + C \\
u = y^{-3} &= -\frac{1}{2}(x-1) + C\,e^{-x}
```

Using the condition $y(0)=-2$:

```{math}
-\frac{1}{8} = \frac{1}{2} + C \Rightarrow C = -\frac{5}{8}
```

meaning the final solution is:

```{math}
y(x) = -\frac{2}{(4x-4 + 5\,e^{-x})^{1/3}}
```

b\.
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{y}{x} = y^{1/2}
```
since the highest power on the RHS is $n = \frac{1}{2}$, this means the substitution we need is $u = y^{1-n} = y^{1/2}$ and hence:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} = \frac{1}{2}y^{-1/2}\frac{\mathrm{d}y}{\mathrm{d}x}& \\
\Rightarrow \frac{1}{2}y^{-1/2}\,\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{1}{2}\frac{y^{1/2}}{x} &= \frac{1}{2} \\
\frac{\mathrm{d}u}{\mathrm{d}x} + \frac{1}{2x}u(x) &= \frac{1}{2}
```
which suggests an IF of the form $\mu = \displaystyle e^{\int\frac{1}{2x}\,\mathrm{d}x} = e^{\frac{1}{2}\ln|x|} = x^{1/2}$, hence:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x}\,x^{1/2} + u(x) &= \frac{1}{2}x^{1/2} \\
\frac{\mathrm{d}}{\mathrm{d}x}\left(u\,x^{1/2}\right) &= \frac{1}{2}x^{1/2} \\
u\,x^{1/2} = -\frac{1}{2}\int x\,\mathrm{d}x + C &= \frac{1}{2}\frac{2}{3}x^{3/2} + C \\
u = y^{1/2} &= \frac{1}{3}x + C\,x^{-1/2}
```

Using the condition $y(1)=0$:

```{math}
0 = \frac{1}{3} + C \Rightarrow C = -\frac{1}{3}
```

meaning the final solution is:

```{math}
y(x) = \left(\frac{1}{3}x - \frac{1}{3}x^{-1/2} \right)^2 = \frac{x^3-2x^{3/2}+1}{9x}
```


````

### Riccati form
````{admonition} Defintion
A Riccati differential equation takes the form:
```{math}
:label: riccatiODE
\frac{\mathrm{d}y}{\mathrm{d}x} = p(x)\,y^2(x) + q(x)\,y(x) + r(x)
```
which we can recast in terms of a variable $u(x)$, which satisfies an ODE:
```{math}
\frac{\mathrm{d}^2 u}{\mathrm{d}x^2} - R\,\frac{\mathrm{d}u}{\mathrm{d}x} + S\,u =0, \quad R = q + \frac{1}{p}\frac{\mathrm{d}p}{\mathrm{d}x}, \quad S = r\,p
```
and we can solve to find $y(x)$:
```{math}
y = -\frac{1}{p\,u}\frac{\mathrm{d}u}{\mathrm{d}x}
```
````
Using the transformation $v = p\,y$ we find:
```{math}
\frac{\mathrm{d}v}{\mathrm{d}x} &= \frac{\mathrm{d}p}{\mathrm{d}x}\,y + p\,\frac{\mathrm{d}y}{\mathrm{d}x} \\
p\,\frac{\mathrm{d}y}{\mathrm{d}x} &= p^2\,y^2 + q\,p\,y + p\,r \\
\Rightarrow \frac{\mathrm{d}v}{\mathrm{d}x} &= v^2 + q\,v + p\,r + y\,\frac{\mathrm{d}p}{\mathrm{d}x} = v^2 + v\left(q + \frac{1}{p}\frac{\mathrm{d}p}{\mathrm{d}x} \right) + p\,r 
```
and then switching to the variable $u(x)$, where $v = -\displaystyle \frac{1}{u}\frac{\mathrm{d}u}{\mathrm{d}x}$ means:
```{math}
\frac{\mathrm{d}v}{\mathrm{d}x} &= \frac{1}{u^2}\left(\frac{\mathrm{d}u}{\mathrm{d}x}\right)^2 - \frac{1}{u}\frac{\mathrm{d}^2 u}{\mathrm{d}x^2} 
= v^2 - \frac{1}{u}\frac{\mathrm{d}^2 u}{\mathrm{d}x^2} \\
v^2 - \frac{1}{u}\frac{\mathrm{d}^2 u}{\mathrm{d}x^2} &= v^2 - \frac{1}{u}\frac{\mathrm{d}u}{\mathrm{d}x}\left(q + \frac{1}{p}\frac{\mathrm{d}p}{\mathrm{d}x} \right) + p\,r \\
\Rightarrow \frac{\mathrm{d}^2 u}{\mathrm{d}x^2} &= \left(q + \frac{1}{p}\frac{\mathrm{d}p}{\mathrm{d}x} \right)\frac{\mathrm{d}u}{\mathrm{d}x} - p\,r\,u\\
\frac{\mathrm{d}^2 u}{\mathrm{d}x^2} &- R\,\frac{\mathrm{d}u}{\mathrm{d}x} + S\,u = 0\\
R(x) &= q + \frac{1}{p}\frac{\mathrm{d}p}{\mathrm{d}x}, \quad S(x) = r\,p
```
We see that if $r=0$, then this just reduces to a Benoulli equation with $n=2$ and if $p=0$, then this is just in integrating form factor, so this 
equation can be thought of as a hybrid between the two.

````{admonition} Worked example
:class: seealso
Consider the ODE:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} - \frac{2y}{x} = - x^2\,y^2 \\
```
this equation can be rewritten as:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{2y}{x}-x^2\,y^2
```
and then transformed into the 2nd order ODE:
```{math}
\frac{\mathrm{d}^2 u}{\mathrm{d} x^2} - R\,\frac{\mathrm{d}u}{\mathrm{d}x} + S\,u &= 0 \\
R = \frac{4}{x}\,\quad & S = 0 \\
\Rightarrow \frac{\mathrm{d}^2 u}{\mathrm{d} x^2} -\frac{4}{x} \,\frac{\mathrm{d}u}{\mathrm{d}x} &= 0
```
which we can solve using an IF method, with $\mu = e^{-\int 4/x\,\mathrm{d}x} = x^{-4}$:
```{math}
x^{-4}\,\frac{\mathrm{d}^2 u}{\mathrm{d} x^2} - 4\,x^{-5} \,\frac{\mathrm{d}u}{\mathrm{d}x} &= 0 \\
\Big(x^{-4}\,\frac{\mathrm{d}u}{\mathrm{d}x}\Big)^\prime &= 0
```
Since the derivative of a constant is zero, this means:
```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} &= C_1\,x^4 \\
u &= \frac{C_1\,x^5}{5} + C_2 \\
\Rightarrow y &= \frac{C_1\,x^2}{\frac{C_1x^5}{5} + C_2}\\
```
where $C_1,\, C_2$ are constants.  We can tidy this expression up:
```{math}
y = \frac{5x^2}{x^5 + C_3}
```
and $C_3$ is a constant.

We note that this problem has $r(x) = 0$, therefore is also a Bernoulli type expression, with highest power $y^2$, so $u = y^{1-2} = y^{-1}$:

```{math}
\frac{\mathrm{d}u}{\mathrm{d}x} = -\frac{1}{y^2} \frac{\mathrm{d}y}{\mathrm{d}x}\\
-\frac{1}{y^2}\frac{\mathrm{d}y}{\mathrm{d}x} + \frac{2}{xy} &= x^2  \\
\frac{\mathrm{d}u}{\mathrm{d}x} + \left(\frac{2u}{x}\right) &= x^2
```
which is also solveable using an IF, $\mu = \displaystyle e^{\int \frac{2}{x}\,\mathrm{d}x} = x^2$:
```{math}
x^2\frac{\mathrm{d}u}{\mathrm{d}x} + 2x\,u &= x^4 \\
\frac{\mathrm{d}}{\mathrm{d}x}\left(x^2\,u\right) &= x^4 \\
x^2\,u &= \frac{1}{5}x^5 + C \\
\Rightarrow u = \frac{1}{5}x^3 + Cx^{-2} &= \frac{x^5 + C}{5x^2}\\
y &= \frac{5x^2}{x^5 + C}
```
which agrees with the earlier result.
````

Whilst this method is good at converting a non-linear 1st order ODE into a linear 2nd order ODE, most of the time the 
resulting equation will need some quite powerful techinques to solve, especially if $R(x)$ and $S(x)$ are both functions of $x$.
