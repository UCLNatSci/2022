# Multivariable Calculus
 
### First order partial derivatives
We can consider the rate of change of the function, however since it is a function of two variables, we can see there are two possible kinds of derivative we can find:

- along a curve parallel to the $x$-axis, by holding $y$ constant and differentiating with respect to $x$.

- along a curve parallel to the $y$-axis, by holding $x$ constant and differentiating with respect to $y$.

We call these <b>partial derivatives</b>, denoted here by:
```{math}
\frac{\partial f}{\partial x} &=   3x^2 - 2y \quad \textrm{(holding $y$ constant and differentiating with respect to $x$)}\\
\frac{\partial f}{\partial y} &=  -3y^2 - 2x \quad \textrm{(holding $x$ constant and differentiating with respect to $y$)}
```
note that the notation $\partial$ is distinct from the $\mathrm{d}$ used for one variable calculus.  It is <em>partial</em> because we 
consider only variations in one of the two variables here.  The results show the local rate of change parallel to each axis at a point $(x,\,y)$.

The plot shown in {numref}`surf1` is of a function, $f(x,\, y)= x^3 - y^3 - 2xy + 2$, on which curves marked on the surface for lines of constant $x,\,y$:

```{figure} ../figures/surf1.png
---
name: surf1
---
A plot of the $f(x,\, y) = x^3 - y^3 - 2xy + 2$, with lines of constant $(x,\,y)$.
```

Just like the one variable derivative, there is a limit definition for partial derivatives for a function $f = f(x,\,y)$:
```{math}
\frac{\partial f}{\partial x} &=  \lim_{\Delta x \rightarrow 0} \left[\frac{f(x + \Delta x,\, y) - f(x,\, y)}{\Delta x} \right]\\
\frac{\partial f}{\partial y} &=  \lim_{\Delta x \rightarrow 0} \left[\frac{f(x,\, y + \Delta y) - f(x,\, y)}{\Delta y} \right]
```

````{admonition} Problems
:class: seealso, dropdown
Calculate all the first partial derivatives $\partial/\partial x,\, \partial/\partial y$ for the following functions:

1\. $f(x,\,y) = 3x^3 y^2 + 2 y $

2\. $f(x,\,y) = x^2 \ln(3x+y)$ 

3\. $z(x,\,y) = \ln(x+y^2\sin(x))$

````

````{admonition} Solutions
:class: seealso, dropdown

1\. $f(x,\,y) = 3x^3 y^2 + 2 y $

```{math}
\frac{\partial f}{\partial x} &=  9x^2 y^2, \\
\frac{\partial f}{\partial y} &=  6x^3 y+2
```

2\. $f(x,\,y) = x^2 \ln(3x+y)$ 

```{math}
\frac{\partial f}{\partial x} &=  2x\ln(3x+y) + \frac{3x^2}{3x+y}, \\
\frac{\partial f}{\partial y} &=  \frac{x^2}{3x+y}
```

3\. $z(x,\,y) = \ln(x+y^2\sin(x))$
```{math}
\frac{\partial z}{\partial x} &=  \frac{1+y^2\cos(x)}{x+y^2\sin(x)}, \\
\frac{\partial z}{\partial y} &=  \frac{2y\sin(x)}{x+y^2\sin(x)}
```

````


### Second order partial derivatives
The second partial derivatives with respect to $x$ and $y$ are denoted as follows:

```{math}
\frac{\partial^2 f}{\partial x^2} &=  \frac{\partial}{\partial x}\left(\frac{\partial f}{\partial x}\right), \\
\frac{\partial^2 f}{\partial y^2} &=  \frac{\partial}{\partial y}\left(\frac{\partial f}{\partial y}\right)
```

The notation can also be extended to <b>mixed second partial derivative</b>, where we take the $x$ and the $y$ partial derivative:

```{math}
\frac{\partial^2 f}{\partial y \,\partial x} &=  \frac{\partial}{\partial y}\left(\frac{\partial f}{\partial x}\right), \\
\frac{\partial^2 f}{\partial x\, \partial y} &=  \frac{\partial}{\partial x}\left(\frac{\partial f}{\partial y}\right)
```
Notice that we work from the inside out, as with function composition and matrix multiplication.  For any well behaved, differntiable and continuous function, 
these two expressions are <em>always</em> equal.  The proof of this result (called Schwarz's theorem) is quite involved and is beyond the scope of this course.
  
As an example, lets calculate all second partial derivatives of the function $f(x,y)=3x^3y^2+2y$

```{math}
\frac{\partial f}{\partial x} = 9 x^2 y^2, &\quad&\, \frac{\partial f}{\partial y} = 6 x^3 y + 2, \\
\frac{\partial^2 f}{\partial x^2} = 18x y^2, &\quad&\, \frac{\partial^2 f}{\partial y^2} = 6x^3, \\
\frac{\partial^2 f}{\partial y\,\partial x} = 18x^2 y, &\quad&\, \frac{\partial^2 f}{\partial x\,\partial y} = 18x^2 y 
```

````{admonition} A Common Mistake
:class: warning

Lets look at the function $f(x,\, y) = x^2 y^3 + x + y$ at the point $(1,\, 1)$, calculating the mixed partial derivative:
```{math}
\frac{\partial^2}{\partial y\,\partial x}(x^2 y^3 + x + y)
```
we could argue that we follow the process:

- Put $y=1$ into the function and then differentiate with respect to $x$ to obtain:
```{math}
\frac{\partial}{\partial x}(x^2+x+1)=2x
```
- Then put $x=1$ into this function and differentiate with respect to $y$ to obtain: 
```{math}
\frac{\partial}{\partial y}(2)=0
```

<b>The result is wrong</b>, because we took $y=1$ before differentiating with respect to $y$ - to avoid mistakes of this nature, we should always 
perform differentiation first and only substitute in the values in the very last step. The correct result is:
```{math}
\Bigg[\frac{\partial^2}{\partial y\,\partial x}\left(x^2 y^3 +x+y\right)\Bigg]_{(1,1)} 
= \Bigg[\frac{\partial }{\partial y}(2xy^3+1)\Big]_{(1,1)} = \Big[6xy^2\Bigg]_{(1,1)} = 6
```
````

### Notation for partial derivatives
Partial derivatives are commonly denoted using subscript notation:

```{math}
f_x=\frac{\partial f}{\partial x}, &\quad\, f_y=\frac{\partial f}{\partial y}, \\
\quad f_{xx}=\frac{\partial^2 f}{\partial x^2}, &\quad\, f_{yy}=\frac{\partial^2 f}{\partial y^2}
```

For mixed derivatives the order or subscripts is from left to right:

```{math}
f_{xy} &=  (f_x)_y = \frac{\partial^2 f}{\partial y\, \partial x}, \\
f_{yx} &=  (f_y)_x = \frac{\partial^2 f}{\partial x\, \partial y}
```

You will likely come across yet more alternative notations in the literature, another common one being:
```{math}
D_x=\frac{\partial}{\partial x}
```

    

## Multivariable chain rule
We now consider a function $f(x,\,y)$ subjected to small variations in both $x$ and $y$ as shown in {numref}`two_step`.

```{figure} ../figures/two_step.png
---
name: two_step
---
Showing the variations $f(x+\Delta x, \,y+\Delta y)$ in two steps.
```

Loosely speaking, the total change in the function $f(x,\, y)$ is the sum of changes due to each variable:

```{math}
\Delta f = \frac{\partial f}{\partial x}\Delta x + \frac{\partial f}{\partial y}\Delta y
```

If we now suppose that we parameterise $x=x(u,\, v)$ and $y=y(u,\, v)$ then we may similarly write $\Delta x$ and $\Delta y$ as the sum of changes 
due to variables $u$ and $v$:

```{math}
\Delta f = \frac{\partial f}{\partial x}\left[\frac{\partial x}{\partial u}\Delta u +\frac{\partial x}{\partial v}\Delta v\right] 
+ \frac{\partial f}{\partial y}\left[\frac{\partial y}{\partial u}\Delta u +\frac{\partial y}{\partial v}\Delta v\right]
```

Holding $v$ constant in this expression ($\Delta v=0$) gives:

```{math}
\frac{\Delta f}{\Delta u}=\frac{\partial f}{\partial x}\frac{\partial x}{\partial u}+\frac{\partial f}{\partial y}\frac{\partial y}{\partial u}
```

Holding $u$ constant in this expression ($\Delta u=0$) gives:

```{math}
\frac{\Delta f}{\Delta v}=\frac{\partial f}{\partial x}\frac{\partial x}{\partial v}+\frac{\partial f}{\partial y}\frac{\partial y}{\partial v}
```

This was a somewhat <em>hand-waving</em> argument, but the results are valid in the limit $\Delta u\rightarrow 0, \, \Delta v\rightarrow 0$ and can be proved 
using the limit definition of the derivative and from this we obtain the multivariable chain rule.

If $f = f(x,\, y)$ where $x=x(u,\, v)$ and $y=y(u,\, v)$ then:

```{math}
\frac{\partial f}{\partial u} &=  \frac{\partial f}{\partial x}\frac{\partial x}{\partial u} + \frac{\partial f}{\partial y}\frac{\partial y}{\partial u}\\
\frac{\partial f}{\partial v} &=  \frac{\partial f}{\partial x}\frac{\partial x}{\partial v} + \frac{\partial f}{\partial y}\frac{\partial y}{\partial v}
```

Many student's first go at encountering this rule often think that it "can't be right", because replacing the partial derivatives with differences gives:

```{math}
\Delta f = \frac{\Delta f}{\Delta x}\Delta x + \frac{\Delta f}{\Delta y}\Delta y
```

which suggests the result $\Delta f = 2\Delta f$. However, this misunderstanding comes from ambiguity in writing $\Delta f$. 

On the left-hand side it means changes in $f$ dues to variations in both $x$ and $y$, whilst in $f_x$ and $f_y$ the changes are due to only one of these variables, whilst the other 
is held constant. Written formally:

```{math}
\frac{\partial f}{\partial u} &=  \lim_{\Delta u\rightarrow 0}\frac{f(x(u+\Delta u,v),y(u+\Delta u,v))-f(x(u,v),y(u,v))}{\Delta u}, \\
\frac{\partial f}{\partial x} &=  \lim_{\Delta x\rightarrow 0}\frac{f(x+\Delta x,y)-f(x,v)}{\Delta x}\\
&=\lim_{\Delta u\rightarrow 0}\frac{f(x(u+\Delta u,v),y(u,v))-f(x(u,v),y(u,v))}{\Delta u}
```

The lesson here is - <em>it is dangerous to treat partial derivatives as fractions!</em>

### Dependency trees
The multivariate chain rule can be illustrated as a dependency tree, in {numref}`dependency1`, where we examine $f(x,\, y)$ with $x = x(u,\, v)$ and $y = y(u,\, v)$:

```{figure} ../figures/dependency1.png
---
name: dependency1
---
Dependency tree for first derivatives.
```

For instance, if we follow the dependency routes involving $u$, we get $f_u = f_x\, x_u + f_y\, y_u$.

We can do the same thing for the second derivatives (a repeat application of the chain rule), in {numref}`dependency2`.

```{figure} ../figures/dependency2.png
---
name: dependency2
---
Dependency tree for second derivatives.
```

````{admonition} Worked Examples
:class: seealso

1\. Lets look at $f(x,y)=x^2 y+y^2$, if we have $x = u+v$ and $y = u-v$, then we can calculate $f_u,\, f_v$ using dependency trees:
```{math}
f_u = f_x\, x_u + f_y\, y_u\\
f_v = f_x\, x_v + f_y\, y_v
```
meaning that:
```{math}
f_x &=  2xy, \\
f_y &=  x^2+2y \\
x_u=1, &\quad&\, x_v=1, \\
y_u=1, &\quad&\, y_v=-1
```
Putting these results together:
```{math}
f_u = f_x\, x_u + f_y\, y_u &=  2xy+(x^2+2y) = 2(u+v)(u-v)+(u+v)^2+2(u-v)\\
f_v = f_x\, x_v + f_y\, y_v &=  2xy-(x^2+2y) = 2(u+v)(u-v)-(u+v)^2-2(u-v)
```

2\. 
```{math}
f(x,\, y) = \sin\left(x^2+2xy\right)+(x-y)^2
```
To find $f_x$, we can let $u = x^2 + 2xy$, $v = x-y$, then:

```{math}
f_x = f_u\, u_x +f_v\, v_x = \cos(u)(2x+2y)+2v = 2(x+y)\cos(x^2+2xy) + 2(x-y)
```
````

### Total differential
````{admonition} Definition
The total change in a function $f = f(x,\, y,\, \dots)$ based on the changes in each of its variables can be expressed as the **total differential**:

```{math}
\mathrm{d}f = \frac{\partial f}{\partial x}\,\mathrm{d}x + \frac{\partial f}{\partial y}\,\mathrm{d}y + \dots
```
we can therefore express this as a **total derivative**, in terms of one of the variables:
```{math}
\frac{\mathrm{d}f}{\mathrm{d}x} &= \frac{\partial f}{\partial x} + \frac{\partial f}{\partial y}\,\frac{\mathrm{d}y}{\mathrm{d}x} + \dots\\
\frac{\mathrm{d}f}{\mathrm{d}y} &= \frac{\partial f}{\partial x}\,\frac{\mathrm{d}x}{\mathrm{d}y} + \frac{\partial f}{\partial y} + \dots

```
````

If we have a differential in the form:

```{math}
P(x,\,y)\,\mathrm{d}x + Q(x,\, y)\,\mathrm{d}y = 0
```

such that:

```{math}
\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} = \frac{\partial^2 f}{\partial x\,\partial y}

```
then we call this an **exact** or **perfect** differential.  


## Stationary Points

Obviusly we can translate our single variable calculus toolkit for stationary points into a multivbariable toolkit, the key caveat now being that:

1\. when $\displaystyle \frac{\partial f}{\partial x}=0$ the function is stationary (flat) with respect to the $x$-axis,

2\. when $\displaystyle \frac{\partial f}{\partial y}=0$ the function is stationary (flat) with respect to the $y$-axis.

So it is possible that a function can be stationary w.r.t. to one axes and not another, or have one kind of stationary point along one axes and have a different kind along another
(e..g maxima in $x$, minima in $y$).

Recall from the multivariate chain rule:

```{math}
\mathrm{d}f = \frac{\partial f}{\partial x}\mathrm{d}x+\frac{\partial f}{\partial y}\mathrm{d}y
```

then it is apparent that when both $\displaystyle \frac{\partial f}{\partial x}=0$ AND $\displaystyle \frac{\partial f}{\partial y}=0$, then the instantaneous 
rate of change of $f$ is zero in any direction.  

````{admonition} Worked Example
:class: seealso

Think about the function in {numref}`surf1`, $f(x,\, y) = x^3 - y^3 - 2xy + 2$ can be found by solving $f_x = f_y = 0$ simultaneously:

```{math}
3y^2+2x&= 0\\
3x^2-2y&= 0
```

In general, it may be very difficult (or impossible!) to solve nonlinear equations by hand, and so we would need to resort to numerical methods. In this case, 
however, we can proceed by rearranging one of the equations to substitute into the other, to obtain

```{math}
3\left(\frac{3}{2}x^2\right)^2+2x=0 \quad \leftrightarrow\quad x(27x^3+8)=0
```

This equation has solutions $x=0$ and $x=-\frac{2}{3}$, as well as a complex conjugate pair of solutions $\frac{1}{3}(1\pm\sqrt{3}i)$, which we will discard here.  

Hence, the stationary points are $(0,\, 0,\, 2)$ and $\displaystyle \left(-\frac{2}{3},\, \frac{2}{3},\, \frac{62}{27}\right)$, where we write $(x,\, y,\, f)$
````
   
### Classification of Stationary Points
For a function $f(x,\,y)$, we might expect to classify stationary points using $f_{xx}$ and $f_{yy}$. After all:

- $f_{xx}$ tells us the function concavity parallel to the $y$ axis
- $f_{yy}$ tells us the function concavity parallel to the $x$ axis 
- If the function is concave up in both the $x$ and $y$ directions through a stationary point, then intuition tells us that this is a local minimum. 
- If the function is concave down in both the $x$ and $y$ directions through a stationary point, then our intuition tells us that this is a local maximum.

We can examine this through some example functions, 

```{figure} ../figures/bowl1.png
---
name: bowl1
---
Left: Local minimum of a function $f(x,y)$. The red lines illustrate the concave upwards behaviour in the $x$ and $y$ directions $f_{xx}>0$, $f_{yy}>0$. 
The black contours are plotted on the surface at constant height. Notice that they form rings around the stationary point.
Right: Contour plot showing locations in the $(x,y)$ plane where $f(x,y)$ is constant. 
The colour scheme blue$\rightarrow$yellow is used to indicate the height of the contours, with yellow representing points at higher elevation. 
The contour plot shows that the function is increasing in all directions away from the stationary point.
```
    
```{figure} ../figures/hill1.png
---
name: hill1
---
<b>Left Panel:</b> Local maximum of a function $f(x,y)$. The red lines illustrate the concave downwards behaviour in the $x$ and $y$ directions $f_{xx}<0$, $f_{yy}<0$. 
The black contours are plotted on the surface at constant height. Notice that they form rings around the stationary point.
<b>Right Panel:</b> Contour plot showing locations in the $(x,y)$ plane where $f(x,y)$ is constant. The colour scheme blue$\rightarrow$yellow is used to indicate 
the height of the contours, with yellow representing points at higher elevation. The contour plot shows that the function is decreasing in all directions away 
from the stationary point.
```
   

However, a local maximum/minimum is not the only type of stationary point that a surface $f(x,\,y)$ can have. For instance, a surface may have a stationary 
point that sits where the function is concave upwards with respect to one axis and concave downwards with respect to the other axis. This type of point is called 
a saddle point (it looks like a saddle for a horse). The figure below shows an example:

```{figure} ../figures/saddle1.png
---
name: saddle1
---
<b>Left Panel:</b> Saddle point of a function $f(x,\,y)$. The red lines illustrate the concave upwards/downwards behaviour in the $x$ and $y$ directions 
$f_{xx}>0$, $f_{yy}<0$. The black contours are plotted on the surface at constant height. Notice that the contours cross at a saddle point.
<b>Right Panel:</b> Contour plot showing locations in the $(x,\,y)$ plane where $f(x,\,y)$ is constant. The colour scheme blue$\rightarrow$yellow 
is used to indicate the height of the contours, with yellow representing points at higher elevation. The contour plot also shows the function concavity in the 
$x,\, y$ directions.
```
   

We conclude that at a stationary point, if $f_{xx}$ and $f_{yy}$ are opposite sign, then the point is a saddle point. However, the converse is not 
necessarily true! It turns out that we can have a saddle point where $f_{xx}$ and $f_{yy}$ are both the same sign (or even when they are both zero). An example is 
illustrated in the figure below. In this case the saddle point is not aligned squarely with the $(x,\,y)$ coordinate directions.

   
```{figure} ../figures/squish1.png
---
name: squish
---
<b>Left Panel:</b> Saddle point of a function $f(x,y)$ that is not aligned squarely with the $x,\,y$ axes. The red lines illustrate the concave upwards 
behaviour in the $x$ and $y$ directions $f_{xx}>0$, $f_{yy}>0$. The curve has concave down behaviour at approximately $45^{\circ}$ to the $x$-axis.
<b>Right Panel:</b> Contour plot showing locations in the $(x,\,y)$ plane where $f(x,\,y)$ is constant. The colour scheme blue$\rightarrow$yellow is used 
to indicate the height of the contours, with yellow representing points at higher elevation. The competing concave up/down behaviour is apparent from the contour plot.
```

So, it turns outs that the condition for a maximum/minimum is more complicated than we first thought! A valid classification algorithm is presented in the box below.

The result can be proved by utilising a multivariate Taylor series expansion about the stationary point and retaining terms only up to quadratic order 
so that the shape of the function may be inferred from the properties of a quadratic. Neglecting the higher order terms in the expansion is justified in the 
limit approaching the stationary point. We have not studied the multivariate chain rule, so the proof is not presented here.

### Hessian Matrix

At a stationary point, $f_x(x_0,y_0)=f_y(x_0,y_0)$, we calculate the determinant of the Hessian matrix at $H(x_0,\,y_0)$:

```{math}
\det(H) = \begin{vmatrix}
f_{xx}&f_{xy}\\
f_{yx}&f_{yy}
\end{vmatrix}=f_{xx}f_{yy}-(f_{xy})^2
```

This can have a few different outcomes:

- If $\det(H(x_0,\,y_0))>0$ then the point is a local max/min, depending on the signs of $f_{xx}$ and $f_{yy}$.
- If $\det(H(x_0,\,y_0))<0$ then the point is a saddle.
- If $\det(H(x_0,\,y_0))=0$ then the test is inconclusive and further analysis is needed.
  
````{admonition} Worked Example
:class: seealso

Lets classify the stationary points of the function $f=x^3-y^3-2xy+2$, we already found that the stationary points are located at $(0,0,2)$ and 
$\displaystyle \left(-\frac{2}{3},\frac{2}{3},\frac{62}{27}\right)$.

Calculating the Hessian determinant components $f_{xx}=6x, \quad f_{yy}=-6y, \quad f_{xy}=f_{yx}=-2$ and therefore:

```{math}
\det(H(x,y)) = \begin{vmatrix} 
6x &-2 \\ 
-2 &-6y 
\end{vmatrix}=-36xy-4
```

$\det(H(0,0))=-4<0$ so the origin is a saddle point.

$\det\biggr(H\biggr(-\frac{2}{3},\frac{2}{3}\biggr)\biggr)=12>0$ and $f_{xx}\left(-\frac{2}{3},\frac{2}{3}\right)<0$, so the point 
$\left(-\frac{2}{3}\frac{2}{3}\right)$ is a local maximum.

A contour plot of the function, shown in {numref}`example1`, confirms these findings.
```{figure} ../figures/example1.png
---
name: example1
---
Contour plot of $\displaystyle f=x^3-y^3-2xy+2$, showing stationary points clearly.
```
````

````{admonition} Practice questions
:class: seealso, dropdown
1\. Find the stationary points for the surface described by $f(x,y) = x^2 + 3xy^2 + 2y^3$.

2\. Find the stationary points for the surface described by $f(x,y) = x^3 + y^3 - 3xy - 4$.
````

````{admonition} Solutions
:class: seealso, dropdown
1\. Finding the partial derivatives:
```{math}
f_x &= 2x + 3y^2\\
f_y &= 6xy + 6y^2\\
f_{xx} &= 2\\ 
f_{yy} &= 6x + 12y\\
f_{xy} &= f_{yx} = 6y
```

To find the points which satisfy $f_x = f_y = 0$, we have:
```{math}
2x + 3y^2 &= 0\\
6xy + 6y^2 = 6y(x+y) &=0
```

Thus we find $y=0$ as a valid stationary point, this will therefore correspond to $x=0$.  

Another stationary point will be found to satisfy by $y = -x$, hence we have to solve:
```{math}
3x^2 + 2x = x(3x + 2) = 0
```
which has solutions of $x = 0$ (hence $y = 0$) or $x = -2/3$ and therefore from $y = -x$ corresponds to $y = 0$ or $y = 2/3$.  

Therefore we can collect together these points as:

```{math}
&A\Big(0,\,0\Big) \\
&B\Big(-\frac{2}{3},\,\frac{2}{3}\Big)
```
To find the nature of these SP's, we need the Hessian determinant:

```{math}
\det(H) = f_{xx}\,f_{yy} - (f_{xy})^2 = \Big( 2 \Big)\Big( 6x+12y \Big)\Big( 6y \Big) = 72y(x+2y)
```
and hence at each point:
```{math}
H\Big|_A &= 0 \qquad \text{(inconclusive)}\\
H\Big|_B &= -\frac{244}{9} < 0 \qquad\text{(saddle)}\\
```
To examine what happens at $A$, we can look at $f_{x}$ and $f_{y}$ for points $(\pm \delta x, \,\pm\delta y)$ for $\delta x, \delta y \ll 1$
```{math}
f_{x}\Big|_{(\delta x,\, \delta y)} = 3(\delta y)^2 + 2\delta x > 0\\
f_{x}\Big|_{(-\delta x,\, -\delta y)} = 3(\delta y)^2 - 2\delta x< 0\\
f_{y}\Big|_{(\delta x,\, \delta y)} = 6(\delta x)(\delta y) + 6(\delta y)^2 > 0\\
f_{x}\Big|_{(-\delta x,\, -\delta y)} = 6(\delta x)(\delta y) + 6(\delta y)^2 > 0\\
```
In the $y$ direction there is a point of inflection and in the $x$ direction there is a minima, there is a saddle point at $A$.

We can also see this from the contour plot:

```{figure} ./contourplot.gif
---
name: cplot
---
```

2\.
Finding the partial derivatives:
```{math}
f_x &= 3x^2 - 3y\\
f_y &= 3y^2 - 3x\\
f_{xx} &= 6x\\ 
f_{yy} &= 6y\\
f_{xy} &= f_{yx} = -3
```

To find the points which satisfy $f_x = f_y = 0$, we have:
```{math}
3(x^2 - y) &= 0\\
3(y^2 - x) &=0
```
hence this means that $y = x^2$ from the first equation, which pluggin into the second gives:
```{math}
3(x^2)^2 - 3x = 3x(x^3-1) = 0
```
which means that $x = 0$ or $x = 1$ and since $y = x^2$ we find two stationary points:
```{math}
&A(0,\,0) \\
&B(1,\ 1)
```
To find the nature of these SP's, we need the Hessian determinant:

```{math}
\det(H) = f_{xx}\,f_{yy} - (f_{xy})^2 = 6x(6y) - (-3)^2 = 36xy - 9
```
and hence at each point:
```{math}
H\Big|_A &= -9 < 0 \qquad \text{(saddle)}\\
H\Big|_B &= 27 > 0 \qquad\text{(maxima/minima)}\\
```
given that $f_{xx}|_B,\, f_{yy}|_B > 0$ then this a minima.  

We can also see this from the contour plot:

```{figure} ../figures/SPs.png
---
name: SPplot
---
```

````

  