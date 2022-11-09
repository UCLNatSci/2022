# Second Order ODEs

````{admonition} Definition
:class: notice
In general a second order differential equation is of the form: 

```{math}
:label: ode2general
a\,y^{\prime\prime}(x)+b\,y^{\prime}(x)+c\,y(x)=f(x),
```
where $a,\,b,\,c$ are arbitrary constants.


We can also conveniently write these problems using a linear operator:
```{math}
\mathcal{L}=a\frac{\mathrm{d}^2}{\mathrm{d}x^2}+b\frac{\mathrm{d}}{\mathrm{d}x}+c
```

With this definition, the problems may be written as
* $\mathcal{L}(y)=0$ (homogeneous)
* $\mathcal{L}(y)=f(x)$ (inhomogeneous)

````

## Homogeneous problems
Firstly, we consider the case of {eq}`ode2general` when $f(x)=0$, where we obtain the homogeneous problem:

```{math}
:label: ode2hom
a\,y^{\prime\prime}(x)+b\,y^{\prime}(x)+c\,y(x)=0
```

### The trial solution
One way to start with this problem is by using the trial solution (also sometimes called the ansatz):
```{math}
:label: trialsoln1storder
y = e^{\lambda x}
```
where $A_\lambda$ is constant.  If we try this, then the homogeneous problem reduces to a polynomial in $\lambda$:
```{math}
e^{\lambda x}(a\lambda^2+b\lambda +c)=0
```
and so by solving this quadratic in $\lambda$, we can find solutions to {eq}`ode2hom`.   We call this quadratic the auxiliary equation and the nature of the 
solutions depends on the quantity:
```{math}
\Delta= b^2-4ac
```
which if we recall is called the **discriminant**.

````{admonition} Worked example
:class: seealso
For the differential equation:
```{math}
2y^{\prime\prime}(x)-y^{\prime}(x)-y(x)=0
``` 
where we apply the trial solution $y = A_\lambda\,e^{\lambda x}$, the auxiliary equation is:
```{math}
2\lambda^2-\lambda-1=0
```
The quadratic here has roots 
```{math}
\lambda=-\frac{1}{2}, \quad \lambda=1
```
so we have found two particular solutions of the given ODE:
```{math}
y_1 & = e^{-\frac{1}{2}x}\\
y_2 & = e^{x}
```
where the constants $A_1,\,A_2$ are to be found by applying initial or boundary conditions.
````

````{admonition} Some motivation for the ansatz
:class: tip, dropdown
We could motivate the form of the trial solution by solving the problem for the special case where $c=0$, which reduces to:
```{math}
a\,z^{\prime}(x) + b\,z(x)=0,\quad \text{where } z=y^{\prime}
```
This problem can be solved by separation and the result is of the form $y=k_1e^{-bx/a}+k_2$.

Another way is to begin by writing the system in matrix form $\underline{y}^{\prime}=A\,\underline{y}$, where $\underline{y}=[\begin{matrix}y& y^{\prime}\end{matrix}]^T$ :
```{math}
\begin{bmatrix}y\\y^{\prime}\end{bmatrix}^{\prime}=\begin{bmatrix}0&1\\-c_0/c_2& -c_1/c_2\end{bmatrix}
\begin{bmatrix}y\\y^{\prime}\end{bmatrix}
```
The *eigenvalues* of the problem $A\,\underline{y}=\lambda\,\underline{y}$ satisfy the quadratic $a\lambda^2+b\lambda +c=0$ and therefore the solutions to the 
problem $\underline{y}^{\prime}=k\,\underline{y}$ are of an exponential form. 
````

### Principle of linear superposition
The general second order homogeneous ODE given is linear, meaning that it has no products of terms involving the dependent variable $y$. As a result of this fact, any 
linear combination of solutions will also be a solution:
```{math}
\mathcal{L}(k_1y_1+k_2y_2)&=k_1\left[a y_1^{\prime\prime}+by_1^{\prime}+c y_1\right]+k_2\left[a y_2^{\prime\prime}+by_2^{\prime}+c y_2\right]\\
&=k_1\mathcal{L}(y_1)+k_2\mathcal{L}(y_2)\\
&=0+0 \quad \text{ if $y_1$ and $y_2$ are solutions.}\\
&=0
```
We call this solution the complemtary function.

````{admonition} Worked example
:class: seealso
For the differential equation:
```{math}
2y^{\prime\prime}(x)-y^{\prime}(x)-y(x)=0
``` 
the solutions are found to be:
```{math}
y_1 = e^{-x/2},\quad y_2 = e^{x}
```
By superposition, we can combine these two solutions to obtain a more general solution:
```{math}
y = A_1\,e^{-x/2} + A_2\,e^{x}
```
where $A_1,\, A_2$ are constants to be found.  

You are encouraged to check this solution to confirm that it works!
````

### Applying conditions
Since the results we obtain from solving the auxillary equation and then making a linear superposition of solutions have two arbitrary constants, it generates a 
family of solution curves. We can fix the solution to one of these curves by providing **conditions** for either $y$ or its derivatives at two different $x$ values - these 
 often go by many different names such as *initial coditions* or *boundary conditions*.  For practical problems, the conditions tell us about a particular state 
 of the system. For instance, applying Newton's second law to the motion of a pendulum gives a second order differential equation for the angular displacement 
 $\theta$ from the downward vertical. Conditions for $\theta(0)$ and $\dot{\theta}(0)$ specify the initial displacement and the initial angular velocity. These 
 types of condition, specified at time $t=0$ are called *initial conditions*. For some other types of problem we may have conditions specified at two end-points of an 
 interval. Such types of condition are called *boundary conditions*.


````{admonition} Practice questions
:class: seealso, dropdown
The solutions to the ODE:
```{math}
2y^{\prime\prime}(x)-y^{\prime}(x)-y(x)=0
```
is given by:
```{math}
y = A_1\,e^{-x/2} + A_2\,e^{x}
```

1\. Find the particular solution that satisfies $y(0)=2,\, y^{\prime}(0)=1$

2\. Find the particular solution that satisfies $y(0)=3,\, y(1)=e^{-1/2}+2e$
````

````{admonition} Solutions
:class: seealso, dropdown
Given the general solution to the ODEs, we can find the first derivative:
```{math}
y &= A_1\,e^{-x/2} + A_2\,e^{x} \\
y^{\prime} &= -\frac{1}{2}\,A_1\,e^{-x/2} + A_2\,e^x
```

1\. Substituting for the given conditions:

$ y(0)=1\Rightarrow k_1+k_2=2$

$ y^{\prime}(0)=1 \Rightarrow -\frac{1}{2}k_1+k_2=1$

Solving these two equations simultaneously gives $k_1=\frac{2}{3}$, $k_2=\frac{4}{3}$.

The solution satisfying the given conditions is therefore given by
$y(x)=\frac{2}{3}e^{-\frac{1}{2}x}+\frac{4}{3}e^x$

2\. Substituting for the given conditions:

$ y(0)=3\Rightarrow k_1+k_2=3$

$ y(1)=e^{-1/2}+2e \Rightarrow k_1e^{-1/2}+k_2e=e^{-1/2}+2e$

Solving these two equations simultaneously gives $k_1=1$, $k_2=2$.

The solution satisfying the given conditions is therefore given by
$y(x)=e^{-\frac{1}{2}x}+2e^x$
````


### Complex conjugate roots $\Delta < 0$
If the discriminant is negative, then the auxiliary equation will have complex conjugate solutions of the form 
```{math}
\lambda=\alpha\pm i\omega
```
In this case we can write the general solution a bit differently. We make use of our knowledge of complex numbers (Euler's theorem) to rewrite:
```{math}
\begin{align}y&=e^{\alpha x}\left[(A_1+A_2)\cos(\omega x)+i(A_1-A_2)\sin(\omega x)\right]\\&=e^{\alpha x}\left[B_1\cos(\omega x)+B_2\sin(\omega x)\right]\end{align}
```
upon relabelling the constants $A_1,\, A_2 \rightarrow B_1,\, B_2$.  This is a much nicer form of the solution, because all parts of it are real, and 
so we expect that the coefficients $B_1,\ B_2$ will be real as well. It also shows us clearly that the solution consists of an exponentially 
growing/decaying amplitude combined with wavy oscillations of frequency $\omega$.

````{admonition} Worked example
:class: seealso
Find the general solution of the problem 
```{math}
y^{\prime\prime}(x)-2y^{\prime}(x)+2y(x)=0
```

By inserting the trial solution, we find the auxiliary equation:
```{math}
\lambda^2-2\lambda+2=0
```
has roots $\lambda=1\pm i$.  Therefore the general form of the solution is:
```{math}
y=e^{x}\left[B_1\cos(x)+B_2\sin(x)\right]
```
````
### Repeated roots $\Delta = 0$
If the discriminant is zero, then the auxiliary equation will only have one distinct solution $e^{\lambda x}$, where 
```{math}
\lambda=-\frac{b}{2a}
```
We will look for another solution of the form:
```{math}
y=f(x)e^{\lambda x}
```
In this expression, $f(x)$ could be any function, so this step is perfectly legitimate. But we have done it because it will allow us to reduce 
the order of the differential equation by making use of the known solution. We obtain:

```{math}
\mathcal{L}(f e^{\lambda x}) = \mathcal{L}(e^{\lambda x})f+e^{\lambda x}\left[(2a\lambda+b )f^{\prime}+a f^{\prime\prime}\right]
```

The first term disappears since $e^{\lambda x}$ is a solution, and so to satisfy the problem we require:
```{math}
(2a\lambda+b )f^{\prime}+a f^{\prime\prime} = 0
```
Using the result for the repeated root $\lambda$ reduces this equation to $f^{\prime\prime}=0$, which has a solution of the form:
```{math}
f(x)=Ax+B
```
We can choose $A=1,\, B=0$, thus we have found another solution $x e^{\lambda x}$ and we can form the general solution from a linear combination:
```{math}
y=(k_1x+k_2)e^{\lambda x}.
```
It is very important you recognise that the only reason $x e^{\lambda x}$ has been found as a solution here is because $\lambda$ is a repeated root, which 
makes the term involving $2a\lambda+b$ drop out. If you tried the same technique using one of the solutions to a problem with distinct roots it 
would not give you a result of the form $xe^{\lambda x}$ (in fact after some messy first order integration you would simply recover the solution involving the other root).

````{admonition} Practice Questions
:class: seealso, dropdown
For the problem:
```{math}
y^{\prime\prime}(x)-4y^{\prime}(x)+4y(x)=0
```

1\. Find the general solution and verify by substituting into the ODE that your solution works.

2\. Find the particular solution that satisfies $y(0)=1,\, y^{\prime}(0)=3$.

````

````{admonition} Solutions
:class: seealso, dropdown

1\. The auxiliary equation is $\lambda^2 - 4\lambda + 4 = 0$, with repeated root $\lambda=2$.

Hence, the general solution is given by $y=e^{2x}(A_1\,x + A_2)$, where $k_1$ and $k_2$ are constants.

2\. $y(0)=1\Rightarrow k_1=1$,

$y^{\prime}(0)=3 \Rightarrow 2k_1+k_2=3$

The solution satisfying the given conditions is $y-e^{2x}(x+1)$
````



### Existence of a particular solution:
The general solution:
```{math}
y(x)=A_1 \,y_1(x) + A_2\, y_2(x)
```
can be made to satisfy arbitrary initial conditions $y(x_0)=y_0,\ y^{\prime}(x_0)=y^{\prime}_0$ if and only if:

```{math}
:label: linindepend
y_1^{\prime}(x_0)y_2(x_0)-y_2^{\prime}(x_0)y_1(x_0)\neq 0
```
This condition is met if $y_2 \neq \alpha y_1$, where $\alpha$ would be a constant - we say that these solutions are *linearly independent*. 

To prove that this is true, start by applying the given conditions:
```{math}
y_1(x_0)\,A_1+y_2(x_0)\,A_2 &= y_0\\
y_1^{\prime}(x_0)\,A_1+y_2^{\prime}(x_0)\,A_2 &=y_0^{\prime}
```
This is a set of two simultaneous equations in two unknowns $A_1,\, A_2$ - a unique solution exists if and only if the condition {eq}`linindepend` is met.



````{admonition} Summary
The general solution of the homogeneous second order ODE is given by:
```{math}
y=\begin{cases}\begin{array}{lll} 
A_1e^{\lambda_1 x} + A_2 e^{\lambda_2 x} &\text{where $\lambda_{1,2}=\frac{-b\pm\sqrt{\Delta}}{2a}$} & \text{if $\Delta >0$}\\
e^{\alpha x}(A_1\cos(\omega x) + A_2\sin(\omega x))&\text{where $\alpha=-\frac{b}{2a}$, $\omega =\sqrt{\Delta}$}&\text{if $\Delta < 0$}\\
(A_1\,x + A_2)\,e^{\lambda x} &\text{where $\lambda=-\frac{b}{2a}$}&\text{if $\Delta=0$}\end{array}\end{cases}
```
where $\Delta=b^2-4ac$.
````

## Inhomogeneous problems

Now we will be concerned with the solution of a general problem of the form:

```{math}
\mathcal{L}(y) = ay^{\prime\prime}(x)+by^{\prime}(x)+cy(x)=f(x),
```
where $a,\,b,\,c$ are arbitrary constants.

### The method of undetermined coefficients
This method is a fancy name for educated guesswork - it requires us to pose a trial solution (an ansatz), based on our observation of what $f(x)$ looks like. We will only 
be able to apply this method for some specific types of function $f(x)$, we will be restricted to polynomials, exponentials and trigonometric functions. The method gets its 
name because we guess the form of the solution without giving the values of the coefficients. We find the values of the undetermined coefficients by substituting our
 guess into the ODE and equating terms.  

````{admonition} Method of undetermined coefficients
- Polynomial Form:
```{math} 
f(x) = ax^n \Rightarrow y_{p} = A + Bx^1 + \dots + C x^n
```

- Exponential Form:
```{math} 
f(x) = a \,e^{\alpha x} \Rightarrow y_{p} = A\,e^{\alpha x}
```
If we find the that homogeneous solution has a term of the form $y = A_1\, e^{\alpha x}$, then the particular integral has the form:
```{math}
y_p = A_1\,x\,e^{\alpha x}
```

- Trigonometric Form:
```{math} 
f(x) = a \cos(x)  &\Rightarrow y_{p} = A \cos(x) + B \sin(x)\\
f(x) = b \sin(x)  &\Rightarrow y_{p} = C \cos(x) + D \sin(x)
```
where we *must* include *both* of $\sin(x)$ and $\cos(x)$ in our solution.


- Hyperbolic Form:
```{math}
f(x) = c \cosh(x) &\Rightarrow y_{p} = E \cosh(x) + F \sinh(x)\\
f(x) = d \sinh(x) &\Rightarrow y_{p} = G \cosh(x) + H \sinh(x)
```
where we *must* include *both* of $\sinh(x)$ and $\cosh(x)$ in our solution.
````

````{admonition} Worked example
:class: seealso
We will start by considering the following problem:
```{math}
y^{\prime\prime}+4y^{\prime}+5y=e^x
```
Since we are trying to *make* terms like $e^x$, we will guess a solution of the form $y_p=Ae^x$. Substituting this guess into the equation gives
```{math}
10Ae^x=e^x \Rightarrow y_p=\frac{1}{10}e^x
```
We call this function a particular integral. It is not the most general solution to the given problem, as it does not contain any free constants. We will be able to use 
our particular integral together with the solution to the corresponding homogeneous problem to construct the full result.
````

````{admonition} Practice questions
:class: seealso, dropdown
Find solutions to the following inhomogeneous problems:

1\. 
```{math}
y^{\prime\prime}+4y^{\prime}+5y=\sin(2x)
```

2\. 
```{math}
y^{\prime\prime}+4y^{\prime}+5y=3x^2+4
```

3\. 
```{math}
y^{\prime\prime}+4y^{\prime}+5y=e^x\cos(3x)
```

4\. 
```{math}
2\ddot{x}-\dot{x}-x=3e^{t}
```

````


````{admonition} Solutions
:class: seealso, dropdown

1\. Here we want to *make* terms like $\sin(2x)$ so there will be some of those in our trial guess. However, when we substitute this guess into the 
ODE we will have some $\cos(2x)$ terms appearing on the left and so to balance them we will need some of those terms too.  Our ansatz is:

```{math}
y=A\sin(2x)+B\cos(2x)
```

Substituting this into the ODE gives:
```{math}
(8A+B)\cos(2x)+(A-8B)\sin(2x)=\sin(2x)
```

Equating coefficients of cosine and sine terms gives:
```{math}
8A+B=0, \quad A-8B=1 \Rightarrow A=\frac{1}{65},\quad B=-\frac{8}{65}
```

Our particular integral is:
```{math}
y_p=\frac{1}{65}(\sin(2x)-8\cos(2x))
```

2\. Here we want to *make* terms like $3x^2+4$ so we will need a trial solution involving $x^2$ and its derivatives.  Taking:
```{math}
y_p=Ax^2+bx+c
```
and equating coefficients of $x^2$, $x$ and constant terms in the ODE gives:

```{math}
y_p=\frac{1}{125}(75x^2-120x+166)
```

3\. Here we will need an ansatz involving $e^x\cos(3x)$ and its derivatives.  We will take 
```{math}
y_p=e^{x}(A\cos(3x)+B\sin(3x))
```

Substituting in and equating coefficients of $e^{x}\cos(3x)$ and $e^x\sin(3x)$ gives:

```{math}
y_p=\frac{e^x}{325}(\cos(3x)+18\sin(3x))
```

4\.
Following the technique that we have used previously, we would think to try the ansatz:
```{math}
x_p=A\,e^{t}
```
However, if you substitute this into the left hand side of the equation you will find that it simply gives zero. Our desired ansatz here is a solution of the 
homogeneous problem also!  If (and only if) you encounter this problem, you can fix it by multiplying your ansatz by the differentiation variable, here $t$. The reason 
this works is similar to the derivation of the linearly independent result that was given in the case of homogeneous problems with a repeated eigenvalue.  So here we try:
```{math}
x_p=A\,t\,xe^{t}
```
and equating coefficients of $e^t$ on the left and right sides gives $A=1$.

````

### Constructing the full solution
The general solution to the inhomogeneous problem can be constructed by combining the homogenous solution $y_h$ and the particular integral $y_p$:
```{math}
y(x) = y_h(x) + y_p(x)
```
This works because of the linearity property:
```{math}
\mathcal{L}(y_h+y_p) = \mathcal{L}(y_h)+\mathcal{L}(y_p) = 0+f(x) = f(x)
```

The general solution contains two arbitrary constants so it can be made to satisfy a given set of two conditions. The values of the constants will depend on the 
particular integral you found. There are an infinite number of different particular integrals possible, but they all will differ only be an amount equal to a 
linear combination of the basis solutions.

We *MUST* construct the full solution before employing the given conditions to find constant terms. For example, if you erroneously make $y_h(0)=y_0$ then we will find 
mathematically:
```{math}
y(0)=y_h(0)+y_p(0) = y_0+y_p(0),
```
which is not what we want.

````{admonition} Worked example
:class: seealso
Find the solution to the problem:
```{math}
y^{\prime\prime}+4y^{\prime}+5y=e^x, \quad y(0)=1, \quad y^{\prime}(0)=2
```
The homogenous solution solves:
```{math}
y^{\prime\prime}+4y^{\prime}+5y=0
```
which given the trial solutions $y = e^{\lambda x}$ gives:
```{math}
\lambda^2 + 4\lambda + 5 = 0 \Rightarrow \lambda_\pm = -2\pm i
```
which means that the solution can be written as:
```{math}
y=e^{-2x}\,(A_1\cos(x)+A_2\sin(x))
```
The particular integral for this problem will have the form:
```{math}
y_p = B\,e^{x}
```
which means that:
```{math}
y_p=\frac{1}{10}e^x
```

Therefore the general solution is:

```{math}
y=e^{-2x}(A_1\cos(x)+A_2\sin(x))+\frac{1}{10}e^x
```

Substituting for the initial conditions gives:

```{math}
A_1+\frac{1}{10}=1 &\Rightarrow A_1=\frac{9}{10}\\
A_2-2A_1+\frac{1}{10}=2 &\Rightarrow A_2=\frac{37}{10}
```

The final solution therefore is:
```{math}
y=\frac{1}{10}e^{-2x}(9\cos(x)+37\sin(x))+\frac{1}{10}e^x
```
````

````{admonition} Summary
In order to solve an inhomogeneous problem:
```{math}
a\,y'' + b\,y' + c\,y = f(x)
```
we can apply the following steps:

1\. Solve homogeneous problem first, to find $y_h$, which will include two arbitrary constants:
```{math}
a\,y'' + b\,y' + c\,y = 0 \Rightarrow y_h = g(A_1,\, A_2, \lambda_1\, \lambda_2,\, x)
```

2\. Find a particular integral $y_p$, by the method of undetermined coefficients:
```{math}
a\,y_p'' + b\,y_p' + c\,y_p = f(x)
```
this should include coefficients that are fixed by the form of the ODE and $f(x)$.


3\. Form a composite solution for $y(x)$:
```{math}
y(x) = y_h(x) + y_p(x)
```
in accordance with the principle of superposition of solutions for linear problems.

4\. Find constants satisfying any given conditions (this step MUST be done last).
e.g. given $y(0) = \alpha_1,\, y'(0) = \alpha_2$:
```{math}
y(0) = y_h(0) + y_p(0) &= \alpha_1 \\
y'(0) = y_h'(0) + y_p'(0) &= \alpha_2 \\
```
````

### A note about the limitations of undeterminded coefficients
The method can only be used to solve problems where there is a finite pattern of derivatives for $f(x)$. So it would not be usable for problems such as:
```{math}
f(x)=\ln(x)
``` 
since the ansatz would need to have an infinite number of terms. To balance the derivative of the logarithm would need a term like $1/x$, 
which would need a term like $1/x^2$ and so forth.  There is a method that can be used to solve more general types of inhomogeneous problem, which is called **variation of 
parameters**.  It uses a similar technique to what was done in the derivation of the homogeneous result for repeated real roots - employing known partial solutions to 
construct the full solution,  it assumes a solution of the form 
```{math}
y=u(x)y_1(x)+v(x)y_2(x)
```
where $y_1$ and $y_2$ are the homogeneous basis solutions and the functions $u(x),\,v(x)$ are to be determined.


## Solving separable PDEs
Once we extend calculus to many variables, ODEs can become PDEs and then there techniques required to 


## Variation of parameters method

