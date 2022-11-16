# Differentiation
## Motivations and First Principle Arguments

The equation $y=mx+c$ represents a straight line. In this expression, the constant $m$ tells us how quickly the slope $y$ changes with $x$.

For instance,

* if $m$=1 then 𝑦 increases by 1 unit for every unit of increase in $x$
* if $m$=2 then 𝑦 increases by 2 units for every unit of increase in $x$
* if $m$=−2 then 𝑦 decreases by 2 units for every unit of increase in $x$


````{admonition} Worked Example
:class: seealso
Find the slope of the straight line connecting the points (-3,2) and (5,7).

``` {figure} solution_1.png
---
name: solution
---
Calculating the slope of a straight line
```

The straight line that can be drawn through the points (-3,2) and (5,7).

* the change in $x$ is given by $\Delta x$=(5+3)=8

* the change in $y$ is given by $Δy$=(7−2)=5

So $y$ increases by 5 units for every 8 units of increase in $x$

The rate of change of $y$ with $x$ (the slope) is $\displaystyle\frac{Δy}{\Delta x}$ = $\displaystyle\frac{5}{8}$ (This is the constant $m$ in the equation of the line $y=mx+c$)

Triangles drawn under the line have the same slope. By considering a triangle connecting the point (5,7) to ($x$,$y$), we could write
$\displaystyle\frac{y−7}{x−5}$ = $\displaystyle\frac{5}{8}$, which rearranges to $y$=$\displaystyle\frac{5}{8}x$ + $\displaystyle\frac{31}{8}$.

````

In a curve, the slope is not constant, but we can identify the slope at any point by drawing the tangent to the curve at that point. The tangent is the line that "just touches" the curve, and the normal is the line that is at right angles to the tangent.

```{figure} slope.png
---
name: Tangent_and_Normal
---
The tangent at the point is indicated in blue and the normal is indicated in red.  If the tangent has slope $m$ then the normal has slope −1/$m$.
```
In {numref}`Tangent_and_Normal` we can see that if we moved the point along the curve, both the slope of the tangent line and the normal line change.  We are interested in finding a mathematical expression for the slope of a curve at any given point $x$.


```{figure} height-base.png
---
name: Height_Base
---
The curve shows a hypothetical function $f$, and the black dashed line shows the tangent at the arbitrary point $(x,f(x))$. The slope of this line is the **height:base** ratio in the gray shaded triangle
```
As a first approximation, we construct a secant on the curve by joining $x$ to a nearby point $x+\Delta x$. Here, $\Delta x$ means a small change in the parameter $x$. This result is shown graphically in {numref}`Height_Base`, we consider the secant line joining $(x,f(x))$ to a nearby point $(x+\Delta x,f(x+\Delta x))$

The slope of the secant line is given by:
```{math}
:label: slope_secant
\displaystyle\frac{Δf}{\Delta x}=\displaystyle\frac{f(x+\Delta x)−f(x)}{\Delta x}
```
As we make $\Delta x$ smaller so that the two points are closer together, the secant line approaches the tangent.  We are therefore interested in what happens to {eq}`slope_secant` "as $\Delta x$ approaches zero"


Consider the function $f(x)=x^2$.
Using the definition given in {eq}`slope_secant`, we have

$\displaystyle\frac{Δf}{\Delta x}=\displaystyle\frac{f(x+\Delta x)−f(x)}{\Delta x}=\displaystyle\frac{(x+\Delta x)^2−x^2}{Δ𝑥}=\displaystyle\frac{x^2+2\Delta x+(\Delta x)^2−x^2}{Δ𝑥}=2x+\Delta x$

As $\Delta x$ approaches zero the result approaches $2x$, which we can write as $\displaystyle\frac{Δ𝑓}{Δ𝑥}→2x$  because $\Delta x→0$.

More formally, the result is written as

$\displaystyle \lim_{\Delta x \to 0} \displaystyle\frac{f(x+\Delta x)-f(x)}{\Delta x}=2x$

and we say that "the limit $\Delta x$→0", the result is $2x$.


```{figure} x2.png
---
name: x2
---
A plot of the function $y=x^2$, together with the tangent.  The tangent has slope $2x$.
```

Note that in this example, a factor of $\Delta x$ was cancelled from the numerator and denominator.  The limit is not evaluated at $\Delta x=0$, but as $\Delta x$ approaches $0$. The derivative of a function $f$ with respect to $x$ is given by the result

```{math}
:label: derivative
\displaystyle\frac{\mathrm{d}𝑓}{\mathrm{d}x}=\displaystyle \lim_{\Delta x \to 0}\displaystyle\frac{f(x+\Delta x)−f(x)}{\Delta x}
```

The derivative $\displaystyle\frac{\mathrm{d}f}{\mathrm{d}x}$ is also written $f'(x)$. The two different notations are known as Newton and Leibniz notation.

The process of calculating the derivative is called "differentiation".

As $\Delta x\rightarrow 0$, both the numerator and denominator of the fraction tend to zero, yet in most cases we will see that their ratio approaches a finite limit.
What determines the limit is how quickly the numerator approaches zero, relative to the denominator.

````{admonition} Practice Questions
:class: seealso, dropdown
1\. 
Calculate $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\Big(\displaystyle\frac{3x}{2+2𝑥}\Big)$ using the limit definition of the derivative.

2\. Differentiate $𝑦=x^4−2x^2$ using first principles, and hence:

a\. Calculate the equation of the tangent to this curve at $x=3$

b\. Calculate the equation of the normal to the curve at $x=3$
````

````{admonition} Solutions
:class: seealso, dropdown
1\. Let $f(x)=3x^2+2x$, then:

```{math}
\frac{\mathrm{d}f}{\mathrm{d}x} &= \lim_{\Delta x \to 0}\frac{f(x+ \Delta x)−f(x)}{\Delta x}\\
&= \lim_{\Delta x \to 0}\frac{(3(x+\Delta x)^2+2(x+\Delta x)−(3x^2+2x))}{\Delta x}\\
&= \lim_{\Delta x \to 0} \frac{(3x^2+6x\Delta x+3(\Delta x)^2+2x+2\Delta x)−(3x^2+2x)}{\Delta x}\\
&=\lim_{\Delta x \to 0}(\frac{6x\Delta x+3(\Delta x)^2+2\Delta x}{\Delta x})\\
&= \lim_{\Delta x \to 0}(6x+2+3\Delta x)=6x+2 
``` 

2\. 
```{math}
y(x+\Delta x) &=(x+\Delta x)^4−2(x+\Delta x)^2\\
&= x^4+4x^3\Delta x+6x^2(\Delta x)^2+...[\text{smaller terms}]...)−2(x^2+2x\Delta x+(\Delta x)^2)\\
y(x+\Delta x)−y(x) &= 4x^3\Delta x+6x^2(\Delta x)^2−4x\Delta x−2(\Delta x)^2+...[\text{smaller terms}]...\\
\frac{\mathrm{d}y}{\mathrm{d}x} &= \lim_{\Delta x \to 0}y(x\Delta x)−y(x)\Delta x))\\
&= \lim_{\Delta x \to 0}(\Delta x(4x^3−4x)+(\Delta x)2(6x^2−2)+...[\text{smaller terms}]... \Delta x)\\
&= \lim_{\Delta x \to 0}(4x^3−4x+\Delta x(6x^2−2)+...[\text{smaller terms}])\\
&=4x^3−4x
```

a\. The slope at $x=3$ is given by putting $x=3$ into the result for $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}$.

We write $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}(x=3) =4(3^3)−4(3)=96 $

The tangent line passing through the point (3,63) is given by:
```{math}
\frac{y−63}{x−3}=96
```
hence $y=96x−225$.

b\. The normal to the curve at the point satisfies
```{math}
\frac{y−63}{x−3}=−1/96
```
hence $y=−(1/96)x+192/96$.

````

## Derivative as a "rate of change"

Differentiation can be thought of as a measure of the rate of change of one variable with respect to another. For instance, $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}$ is a measure of how quickly $y$ changes (instantaneously) as $x$ changes. Here, we call $y$ the dependent variable, and we call $x$ the independent variable.

In many problems the independent variable is time. For example, consider the case of a simple pendulum shown in {numref}`pendulum`, where $\theta(t)$ measures the anticlockwise angle of the pendulum from the downward vertical as a function of time $t$. The pendulum is initially released from rest at a positive angle.  

``` {figure} pendulum.png
---
name: pendulum
---
A pendulum swing diagram, the angle of inclination with the downward vertical is denoted by $\theta$ and is measured in the anti-clockwise direction.  The graph on the 
right shows the rate of change of $\theta$ with respect to time $t$.
```

* At the maximum height of the swing (amplitude), the pendulum comes to an instantaneous standstill, and so $\displaystyle\frac{\mathrm{d}\theta}{\mathrm{d}t}=0$.
* As the pendulum swings clockwise, $\theta$ is decreasing and so $\displaystyle\frac{\mathrm{d}\theta}{\mathrm{d}t}<0$.
* As the pendulum swings anticlockwise, $\theta$ is increasing and so $\displaystyle\frac{\mathrm{d}\theta}{\mathrm{d}t}>0$.
* On the downswing the pendulum picks up speed.  The angular speed (rate of change of $|\theta|$) is greatest at the mid-point of each swing.

## Second and Higher Derivatives

We can differentiate a function repeatedly.  For example, we might differentiate the function $3x^2+5x^3$ w.r.t. $x$ twice:   

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\Big(\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}(3x^2+5x^3)\Big)=\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}(6x+15x^2)=6+30x
```

We call this result the "second derivative" w.r.t. $x$. and we write
$\displaystyle\frac{\mathrm{d}^2}{\mathrm{d}x^2}(3x^2+5x^3)=6+30x$.
In general, the $n^{th}$ derivative is denoted by $\displaystyle\frac{\mathrm{d}^n}{\mathrm{d}x^n}$. We have already seen that the notation $f'(x)$ can be used to denote the first derivative $\displaystyle\frac{\mathrm{d}f}{\mathrm{d}x}$, and this notation can be extended to higher derivatives:

```{math}
f''(x)=\displaystyle\frac{\mathrm{d}^2}{\mathrm{d}x^2}, \quad f'''(x)=\displaystyle\frac{\mathrm{d}^3}{\mathrm{d}x^3},\quad \text{etc}
```

The dash notation becomes a bit cumbersome for higher derivatives, so we write $f^{(n)}(x)=\displaystyle\frac{\mathrm{d}^nf}{\mathrm{d}x^n}$.

For example, $f^{(4)}(x)=f''''(x)=\displaystyle\frac{\mathrm{d}^4f}{\mathrm{d}x^4}$

There are still more ways to write the derivative of a function, and we will introduce some of them in the chapter of the notes about partial derivatives.   


*Dotty* notation is used for differentiation with respect to time: 
```{math}
\dot{x}=\displaystyle\frac{\mathrm{d}x}{\mathrm{d}t}, \quad \ddot{x}=\displaystyle\frac{\mathrm{d}^2x}{\mathrm{d}t^2}
```

## Stationary Points

````{admonition} Definition
The point ($x_0,f(x_0))$ is a stationary point of $f(x)$ if $f′(x_0)=0$.
````
To classify the stationary points, we can look at the slope of the curve at a smaller distance $\epsilon$ either side of them, as illustrated in the table below:

```{image} table-1.png
---
name: table_for_stat_points
alt: alternative description
align: center
scale: 30%
---
```

Which we can see graphically:

```{figure} StationaryPoints2.png
---
name: StationaryPoints
---
```

### First Derivative Test

````{admonition} Worked Example
:class: seealso
Find and classify the stationary points of $f(x)=-x^3+9x^2−24x+20$:

```{math}
f'(x)=−3x^2+18x−24=−3(x−2)(x−4)
```

The stationary points are at $x=2,4$

Check the sign of the gradient:

| x=1  | x=2  | x=3  | x=4  | x=5 |
|------|------|------|------|-----|
| -    | 0    | +    | 0    | -   |

We know that the gradient changes sign only at the points $x$=2 and $x$=4, so testing the point $x$=3 tells us the sign of the gradient immediately right of $x$=2 and immediately left of $x$=4.

From the table above, we can infer that $x$=2 is a local minimum and $x$=4 is a local maximum.

````

### Second derivative test

The second derivative measures the rate of change of the slope, since

```{math}
\frac{\mathrm{d}^2f}{\mathrm{d}x^2}=\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\displaystyle\frac{\mathrm{d}f}{\mathrm{d}x}=\displaystyle\frac{\mathrm{d}s}{\mathrm{d}x}
```
where $s$ measures the slope.

Thus, the second derivative is a measure of concavity.

* When $\displaystyle\frac{\mathrm{d}^2f}{\mathrm{d}x^2}>0$ the slope is increasing : we say that the function is concave upwards. For example, the 
function $x^2$ is concave upwards on its entire domain. It's slope is always increasing: $\displaystyle\frac{\mathrm{d}^2x^2}{\mathrm{d}x^2}=2>0$ $\forall\, x$
* When $\displaystyle\frac{\mathrm{d}^2f}{\mathrm{d}x^2}<0$ the slope is decreasing : we say that the function is concave downwards. For example, the 
function $−x^2$ is concave downwards on its entire domain. It's slope is always decreasing.
* When $\displaystyle\frac{\mathrm{d}^2f}{\mathrm{d}x^2}=0$ the slope of the function is not changing (it remains constant)


We can therefore use the second derivative to classify local maxima/minima:

If the function is concave upwards at a stationary point, it is a local minimum
If the function is concave downward at a stationary point, it is a local maximum


A point of inflection is a point where the concavity of a function $f$ changes sign. Therefore, at a point of inflection, $f''(x)=0$. However, it is important to 
note that $f''(c)=0$ does guarantee that a point is an inflection, as some concave up/down functions also satisfy this criterion ($f(x)=\cosh(x)$ is an example). In this 
case, further testing using the first derivative test is needed.


## Differentiation Rules

### Sum rule

````{admonition} Definition
:class: note

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(u+v)=\frac{\mathrm{d}u}{\mathrm{d}x}+\frac{\mathrm{d}v}{\mathrm{d}x}
```

This result says that the derivative of a sum is equal to the sum of the derivatives.

For example, $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}(x^5+x^3)=5x^4+3x^2$

````

### Product rule
````{admonition} Definition
:class: note

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(uv)=u\frac{\mathrm{d}v}{\mathrm{d}x}+v\frac{\mathrm{d}u}{\mathrm{d}x}
```

A special case is when one of the functions is a constant $k$. Then, we have

$\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}(kf(x))=k\displaystyle\frac{\mathrm{d}f}{\mathrm{d}x}+0.$

For example, $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}(3x^5)=15x^4.$
````

````{admonition} Worked Example
:class: seealso

Calculate $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}(x^3\sin(x))$:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(x^3\sin(x))=x^3\frac{\mathrm{d}}{\mathrm{d}x}(\sin(x))+\sin(x)\frac{\mathrm{d}}{\mathrm{d}x}x^3=x^3\cos(x)+3x^2\sin(x)
```
````

### Quotient rule

````{admonition} Definition
:class: note

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(\frac{u}{v})=\frac{v\frac{\mathrm{d}u}{\mathrm{d}x}−u\displaystyle\frac{\mathrm{d}v}{\mathrm{d}x}}{v^2}
```

To prove this, let $f(x)=\displaystyle\frac{u(x)}{v(x)}$ and rearrange to give $u(x)=f(x)v(x)$. 

Then differentiate both sides w.r.t. $x$, applying the product rule to calculate the result on the right. 

Rearrange your answer to obtain $f'(x)$ entirely in terms of $u$, $v$ and their derivatives, $u=fv$ gives $u'=fv'+vf'$

and rearranging gives $f'=\displaystyle\frac{u'−fv'}{v}$.  

We can substitute in $f=u/v$ to obtain the final result:

```{math}
f'=\frac{u'−\displaystyle\frac{u}{v}v′}{v}=\frac{u'v-uv'}{v^2}
```
````

````{admonition} Worked Example
:class: seealso

Use the quotient rule to obtain the result for $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\tan(x)$

Let $u=\sin(x)$, $v=\cos(x)$. Then, by the quotient rule,

```{math}
\frac{\mathrm{d}}{\mathrm{d}}(\frac{𝑢}{𝑣})=\frac{v\frac{\mathrm{d}u}{\mathrm{d}x}−u\frac{\mathrm{d}v}{\mathrm{d}x}}{v^2}
=\frac{\cos^2(x)+\sin^2(x)}{\cos^2(x)}=\frac{1}{\cos^2(x)}=\sec^2(x)
```
````

### Chain rule

````{admonition} Definition
:class: note

The chain rule is defined if two functions $f=f(g)$ and $g=g(x)$ are both differentiable then@

```{math}
\frac{\mathrm{d}f}{\mathrm{d}x}=\frac{\mathrm{d}f}{\mathrm{d}g}\displaystyle\frac{\mathrm{d}g}{\mathrm{d}x}
```
An important special case can be deduced by noting that $\displaystyle\frac{\mathrm{d}f}{\mathrm{d}f}=1$, which gives:

```{math}
\frac{\mathrm{d}f}{\mathrm{d}x}\frac{\mathrm{d}x}{\mathrm{d}f}=1
```
This result can be motivated by noting that 
```{math}
\lim_{\Delta x \rightarrow 0}\frac{\Delta f}{\Delta x} = \lim_{\Delta x \rightarrow 0}\frac{\Delta f}{\Delta g}\frac{\Delta g}{\Delta x}
```

We have to take great care when treating derivatives like fractions involving finite quantities - the anticipated results do not always hold true, as we will see 
when we study partial differentiation.

````
````{admonition} Worked Example
:class: seealso

Suppose that we wish to differentiate the following function w.r.t. $x$ :

```{math}
f=\sin^2(x)+\displaystyle\frac{1}{\sin(x)}
```
We know how to differentiate $\sin(x)$ w.r.t. $x$ and we know how to differentiate $g^2+\displaystyle\frac{1}{g}$ w.r.t. $g$.

This motivates us to introduce the change of variables $g=\sin(x)$ so that we may write $f=g^2+\displaystyle\frac{1}{g}$.  

Then, we have the results:

```{math}
\frac{\mathrm{d}f}{\mathrm{d}g} &= 2g−1g \\
\frac{\mathrm{d}g}{\mathrm{d}x} &= \cos(x)
```

Intuitively, we hope to combine these two results to find the rate of change of $f$ w.r.t. $x$.

The chain rules gives 
```{math}
\frac{\mathrm{d}f}{\mathrm{d}g} = \Big(2g − \frac{1}{g^2}\Big) \cos(x)
```

where $g = \sin(x)$. Writing the expression fully in terms of $x$ provides the answer:

```{math}
\frac{\mathrm{d}f}{\mathrm{d}g} = \Bigg(2\sin(x) − \frac{1}{\sin^2(x)}\Bigg) \cos(x)
```
````

````{admonition} Practice Questions
:class: seealso, dropdown

1\. Use the chain rule with $f=e^{−x}$, $g=−x$ to calculate:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(e^{−x})
```
Hence, calculate the derivatives of $\sinh(x)$ and $\cosh(x)$

2\. Given that $\displaystyle\frac{\mathrm{d}}{\mathrm{d}t}\ln(t)=\displaystyle\frac{1}{t}$, calculate:

```{math}
\frac{\mathrm{d}}{\mathrm{d}t}\sin(\ln(t))
```

3\. Decide what substitution could be used to differentiate the following functions:

a\. $y=\sin(2x−1)$ w.r.t $x$

b\. $y=(3−x^2)^4$ w.r.t. $x$



4\. The chain rule can be applied repeatedly - use it to differentiate the following complicated functions w.r.t. $x$:

a\. $y=\ln(\cos(2x−1))$

b\. $y=\ln(\ln(\ln(\ln(x))))$

c\. $y=\ln(\sin(x^2))$

````

````{admonition} Solutions
:class: seealso, dropdown

1\. 
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(e^{−x}) = \frac{\mathrm{d}}{\mathrm{d}g}e^g
``` 
where $g=−x$ gives:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}(e^{−x})=−e^g=−e^{−x}
```

Therefore:

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\sinh(x) &= \frac{\mathrm{d}}{\mathrm{d}x}(\frac{1}{2}(e^x-e^{−x}))=\frac{1}{2}(e^x+e^{−x})=\cosh(x)\\
\frac{\mathrm{d}}{\mathrm{d}x}\cosh(x) &= \frac{\mathrm{d}}{\mathrm{d}x}(\frac{1}{2}(e^x+e^{−x}))=\frac{1}{2}(e^x-e^{−x})=\sinh(x)
```

2\. 
Let $x=\ln(t)$, then:
```{math}
\frac{\mathrm{d}}{\mathrm{d}t}\sin(\ln(t))=\frac{\mathrm{d}(\sin(x))}{\mathrm{d}x}\frac{\mathrm{d}x}{\mathrm{d}t}
=\cos(x)\displaystyle\frac{1}{t}=\frac{\cos(\ln(t))}{t}
```
3\. 
a\. Put $u=2x−1$, then:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{\mathrm{d}y}{\mathrm{d}u}\frac{\mathrm{d}u}{\mathrm{d}x}=2\cos(u)=2\cos(2x−1)
```

b\. Put $u=3−x^2$, then:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{\mathrm{d}y}{\mathrm{d}u}\frac{\mathrm{d}u}{\mathrm{d}x}=(4u^3)(−2𝑥)=−8x(3−x^2)^3=8x(x^2−3)^3
```


c\. Put $x=\sin(u)$, then:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{\mathrm{d}y}{\mathrm{d}u}\frac{\mathrm{d}u}{\mathrm{d}x}=\frac{1}{x}\cos(u)=\frac{\cos(u)}{\sin(u)}=\cot(u)
```

4\.  
a\.
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}&=\frac{\mathrm{d}\ln(\cos(2x−1))}{\mathrm{d}\cos(2x−1)}\frac{\mathrm{d}(2x−1)}{\mathrm{d}x}\\
&=−2\frac{\sin(2x−1)}{\cos(2x−1)}=−2\tan(2x−1)
```

b\.
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{1}{\ln(\ln(\ln(x)))}\frac{1}{\ln(\ln(x))}\frac{1}{\ln(x)}\frac{1}{x}
```

c\. 
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x} = \frac{2x\,\cos(x^2)}{\sin(x^2)}
```

````

## Parametric Differentiation

We can express the equation of a circle in the form $x=\cos(t)$, $y=\sin(t)$. This is known as a parametric representation. By varying the parameter $t$, the 
entire circle is mapped out.  In principle, any curve can be parameterised in terms of a single parameter, regardless of the number of coordinates. To describe a 
surface, two parameters are required. For example, the surface of a sphere can be described by varying two parameters such as the latitude and longitude.

According to the chain rule, we can write:

```{math}
:label: parametric
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{\mathrm{d}y}{\mathrm{d}t}\displaystyle\frac{\mathrm{d}t}{\mathrm{d}x}=
\frac{\mathrm{d}y}{\mathrm{d}t}\Bigg/ \frac{\mathrm{d}x}{\mathrm{d}t}
```

So, we obtain a result for $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}$ in terms of the rate of change of each variable w.r.t. parameter $t$. This result is known as 
parametric differentiation. The result is obtained fully in terms of the parameter.

````{admonition} Worked Example
:class: seealso

For the unit circle parameterisation, calculate $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}$ using parametric differentiation. 

Verify your answer by using implicit differentiation using the equation relating $y$ and $x$.

For $x=\cos(t)$, $y=\sin(t)$,

$\displaystyle\frac{\mathrm{d}x}{\mathrm{d}t}=−\sin(t)$, $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}t}=\cos(t)$

So, $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}=−\cot(t)$

In this case it is straightforward to write the result in terms of $x$ and $y$

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=−\frac{x}{y}
```

The equation relating $x$ and $y$ is $x^2+y^2=1$

Differentiating throughout w.r.t. $x$ we obtain:

```{math}
2x+2y\frac{\mathrm{d}y}{\mathrm{d}x}=0
```

and rearranging provides again the result $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}=-\displaystyle\frac{x}{y}$
````

## Derivatives of Inverse Functions

In this scenario we wish to calculate $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}$ where $y = f^{-1}(x)$ and we know how to differentiate function $f$.

````{admonition} Worked example 
:class: seealso

Calculate $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\ln(x)$

We let $y=\ln(x)$ such that $x=e^y$, this means that $\displaystyle\frac{\mathrm{d}x}{\mathrm{d}y}=e^y$ and by the chain rule:

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=1\Big/\frac{\mathrm{d}x}{\mathrm{d}y}=\frac{1}{e^y} = e^{-y}
```

This is not an acceptable result because the derivative has been given in terms of the dependent variable - we need to rewrite in terms of the independent variable $x$. 

For some problems of this type, it can be quite difficult, but here is is easy since $e^y=x$.

Thus the final result is:
```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\Big(\ln(x)\Big)=\frac{1}{x}
```
another important (and familar) result.
````

````{admonition} Practice Questions
:class: seealso, dropdown

1. Calculate $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\arcsin(x)$, given the function looks like:


![arcsin](arcsin.png)


2. Calculate $\displaystyle\frac{\mathrm{d}}{\mathrm{d}t}\mathrm{arccosh}(t)$, given the function looks like:


![arccosh](arccosh.png)

````

````{admonition} Solutions
:class: seealso, dropdown
1\. Let $y=\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\arcsin(x)$. Then $x=\sin(y)$.

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=1\Big/\frac{\mathrm{d}x}{\mathrm{d}y}=\frac{1}{\cos(y)}=\frac{1}{\pm\sqrt{1-\sin^2(y)}}
=\pm\frac{1}{\sqrt{1-x^2}}
```

To choose the correct sign $\pm$ we can look at the graph of $\arcsin(x)$ on the domain $[−1,\,1]$.  The graph is monotonic increasing (always increasing) 
and so $\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}>0 \forall\, x \in [−1,\, 1]$.    We therefore choose the positive root, which gives:


```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\arcsin(x)=\frac{1}{\sqrt{1−x^2}}
```

Notice that at $x = \pm 1$ the slope of the curve is infinite (the curve is parallel to the y-axis).  These points are stationary points w.r.t $y$, 
since $\displaystyle\frac{\mathrm{d}x}{\mathrm{d}y}=0$.  There are no points where the curve is parallel to the $x$-axis.

2\. Let $𝑦=\mathrm{arccosh(y)}$. Then $𝑡=\cosh(y)$

```{math}
\frac{\mathrm{d}t}{\mathrm{d}y}=1\Big/\frac{\mathrm{d}y}{\mathrm{d}t}=\frac{1}{\sinh(y)}=\frac{1}{\pm \sqrt{\cosh^2(y)−1}}
=\pm \frac{1}{\sqrt{t^2−1}}
```

Recall that for the function $\mathrm{arccosh}$ we select the positive branch. On this branch the function is monotonic increasing, so we again select the 
positive square root.

```{math}
\frac{\mathrm{d}}{\mathrm{d}t}\mathrm{\arccosh}(t)=\frac{1}{\sqrt{t^2−1}}
```

````

## Implicit Differentiation

Up to now, we have been calculating the derivatives of functions given explicitly in terms of the dependent variable in the manner $y=y(x)$.
However, there are many occasions where we want to calculate the derivative of a function $y$ that is implicitly related to the dependent variable $x$ in the manner $f(x,y)=0$.

In that case, we differentiate the entire expression with respect to the independent variable and apply the chain rule to differentiate terms involving the dependent variable.

````{admonition} Worked Example
:class: seealso

Lets calculate the result $\displaystyle\frac{\mathrm{d}}{\mathrm{d}x}\Big(x^n\Big)$ for $n \in \mathbb{R}$.

As usual, we let $y=x^n$ and then we rearrange to a convenient form.

In this case we take the natural logarithm of both sides, $\ln(y)=n\ln(x)$

Then we differentiate the whole expression w.r.t. $x$

```{math}
\frac{\mathrm{d}}{\mathrm{d}x}\ln(y)=\frac{n}{x}
```

We apply the chain rule to the left-hand-side: 
```{math}\frac{\mathrm{d}}{\mathrm{d}x}\ln(y)=\frac{\mathrm{d}}{\mathrm{d}y}\ln(y)\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{1}{y}\frac{\mathrm{d}y}{\mathrm{d}x}
```

Combining the two results and rearranging gives:

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=n\frac{y}{x}
```

and finally, rewriting all in terms of $x$ gives:

```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=n\frac{x^n}{x}=nx^{n-1}
```

````

````{admonition} Practice questions
:class: seealso, dropdown

1\. Use implicit differentiation to calculate $\displaystyle\frac{\mathrm{d}x}{\mathrm{d}y}$ where $e^y+e^x=ye^y$, giving your answer in terms of the dependent variable $y$.

2\. Calculate $\displaystyle\frac{\mathrm{d}a}{\mathrm{d}b}$ where $a=4^b$ and $a>0$, giving your answer in terms of $b$.

3\. Find the equation of the tangent to the curve $x^2+(y-x)^3=9$ passing through (1,3).

4\. Use implicit differentiation to find the derivative of $y=\arcsin(x)$.

````

````{admonition} Solutions
:class: seealso, dropdown
1\. Differentiate the whole expression w.r.t. $y$, using the product rule to differentiate the term $ye^y$:

```{math}
e^y + e^x \frac{\mathrm{d}x}{\mathrm{d}y}=e^y+ye^y
```

Rearranging:

```{math}
\frac{\mathrm{d}x}{\mathrm{d}y}=\frac{ye^y}{e^x}=\frac{ye^y}{(y−1)e^y}=\frac{y}{y−1}
```

2\. Since $a>0$ we can take the natural log of both sides: $\ln(a)=b\ln(4)$ and then differentiate w.r.t. $b$.

```{math}
\frac{1}{a}\displaystyle\frac{\mathrm{d}a}{\mathrm{d}b}=\ln(4)
```
which gives:

```{math}
\frac{\mathrm{d}a}{\mathrm{d}b}=\ln(4)a=4^b\ln(4)
```

3\. Differentiate the whole expression w.r.t. $x$, using the chain rule to differentiate the second term:

```{math}
2x+3(y−x)^2(\displaystyle\frac{\mathrm{d}y}{\mathrm{d}x}−1)=0
```
At the point (1,3) we have:

```{math}
& 2+12\Big(\frac{\mathrm{d}y}{\mathrm{d}x}−1\Big)=0\\
& m = \Big(\frac{\mathrm{d}y}{\mathrm{d}x}\Big)x-1=\frac{5}{6}
```

The tangent has equation $\displaystyle\frac{y−3}{x−1}=\displaystyle\frac{5}{6}$, which rearranges to

```{math}
y = \frac{5}{6}x+\frac{13}{6}
```

4\.  Put $x=\sin(y)$ and then differentiate w.r.t. $x$:

```{math}
1=\cos(y)\frac{\mathrm{d}y}{\mathrm{d}x}
```
This gives:
```{math}
\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{1}{\cos(y)}=\frac{1}{\sqrt{1−x^2}}
```
which is the same result we obtained in the examples earlier, where it was also explained why the positive square root is chosen here.
````



````{admonition} Further practice questions
:class: seealso, dropdown

1\. Given that $x(t)=2^t$, calculate $\ddot{x}$.

2\. Given that $y=e^2k\ln(k)$, calculate $\displaystyle\frac{\mathrm{d}^2y}{\mathrm{d}k^2}$.

3\. Given the unit circle parameterisation 
```{math}
x=\cos(\theta), \quad y=\sin(\theta)
```

calculate $\displaystyle\frac{\mathrm{d}^2y}{\mathrm{d}x^2}$ using parametric differentiation.

````

````{admonition} Solutions
:class: seealso, dropdown
1\. Rearrange: $\ln(x)=t\ln(2)$

Differentiate the expression w.r.t. $t$

```{math}
\frac{1}{x}\dot{x}=\ln(2)
```

You could write this all in terms of 𝑡 before continuing, but here I'll just go right ahead and differentiate again w.r.t. $t$:

```{math}
−\displaystyle\frac{1}{x^2}\dot{x}\dot{x}+\frac{1}{x}\ddot{x}=0
```

Rearrange and write in terms of $t$ :

```{math}
\ddot{x}=\frac{1}{x}\dot{x}\dot{x}=\ln(2)^22^t
```
2\. 
```{math}
\frac{\mathrm{d}^2y}{\mathrm{d}k^2} &= \frac{\mathrm{d}}{\mathrm{d}k}(e^{2k}\frac{\mathrm{d}}{\mathrm{d}k}(\ln(k))+\ln(k)\frac{\mathrm{d}}{\mathrm{d}k}(e^{2k}))\\
&=\frac{\mathrm{d}}{\mathrm{d}k}(e^{2k}(2\ln(k)+\frac{1}{k}))\\
&=e^{2k}\frac{\mathrm{d}}{\mathrm{d}k}(2\ln(k)+\frac{1}{k})+(2\ln(k)+\frac{1}{k})\frac{\mathrm{d}}{\mathrm{d}k}(2^{2k})\\
&=e^{2k}(−\frac{1}{k^2}+\frac{4}{k}+4\ln(k))
```

3\. 
```{math}
\frac{\mathrm{d}x}{\mathrm{d}t}&=−\sin(t), \quad \frac{\mathrm{d}y}{\mathrm{d}t}=\cos(t) \Rightarrow \frac{\mathrm{d}y}{\mathrm{d}x}= −\cot(x)\\
\frac{\mathrm{d}^2y}{\mathrm{d}x^2} &= \frac{\mathrm{d}}{\mathrm{d}t}\Big(\frac{\mathrm{d}y}{\mathrm{d}x}\Big)\Big/\frac{\mathrm{d}x}{\mathrm{d}t}\\
&=\frac{\frac{\mathrm{d}}{\mathrm{d}t}(−\cot(t))}{\sin(t)}=\frac{−\sin^2(t)−\cos^2(t)}{\sin(t)}\frac{1}{\sin(t)}=−\mathrm{cosec}^3(t)
```
Or, written in terms of $x$ and $y$, 
```{math}
\frac{\mathrm{d}^2y}{\mathrm{d}x^2}=−\frac{1}{y^3}
```

We can check this answer with implicit differentiation:

```{math}
\frac{\mathrm{d}^2y}{\mathrm{d}x^2}&=\frac{\mathrm{d}}{\mathrm{d}x}(−xy)=\frac{−1}{y}+\frac{x}{y^2}\frac{\mathrm{d}y}{\mathrm{d}x}\\
&=\frac{−1}{y}+e\frac{x}{y^2}(−\frac{x}{y})=\frac{−1}{y^3}\Big(y^2+x^2\Big)=−\frac{1}{y^3}
```

````