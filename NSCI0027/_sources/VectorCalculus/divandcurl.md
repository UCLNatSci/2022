# Variations of Fields

## Divergence

If we start with a vector field ${\bf A(r)} = A_x({\bf r})\,\hat{\bf x} + A_y({\bf r})\,\hat{\bf y} + A_z({\bf r})\,\hat{\bf z} $, then we can define the quantity 
$\nabla\cdot {\bf A(r)}$, i.e. taking the scalar product of the gradient operator with vector field ${\bf A(r)} $ which since the gradient vector is a differential 
operator, means the expression has the form:

```{math}
\nabla\cdot {\bf A(r)} = \partial_x\, A_x + \partial_y\, A_y + \partial_z\, A_z
```

This is often known as the <b>Divergence</b> of ${\bf A}$ or $\text{div}\,{\bf A}$.  Note that in the case of operators we need to be a little careful of the 
ordering of the terms, since ${\bf A(r)}\cdot \nabla$ would give:

```{math}
{\bf A(r)} \cdot \nabla= A_x\,\partial_x  + A_y\,\partial_y  + A_z\,\partial_z  
```

which is also a differential operator, waiting to act on another term, which we apply on the right. 

Lets see the effect of this on two vector fields ${\bf A_1(r)} = \begin{pmatrix} x \\ y \\ 0\end{pmatrix}, \,{\bf A_2(r)} = \begin{pmatrix} y \\ -x \\ 0\end{pmatrix}$:

```{math}
\nabla \cdot {\bf A_1} &=  \partial_x\, x + \partial_y\, y + \partial_z\, 0 = 2 \\
\nabla \cdot {\bf A_2} &=  \partial_x\, y - \partial_y\, x + \partial_z\, 0 = 0 
```
which we can visualise in {numref}`div`.

```{figure} ../figures/div.png
---
name: div
---
Plotting the vector field ${\bf A_1}$ which has non-zero divergence.
```

We can see that the origin here really plays the role of a centre of the divergence, the field lines all appear to flow outwards, becuase here $\nabla \cdot {\bf A} > 0$.  In the case of 
$\nabla \cdot {\bf A} < 0$, field lines would flow into a point and there would be a <em>convergence</em> of the field. 

### Cylindrical coordinate system
In cylindrical polar coordinates, we have the additional complication that the unit vectors:
```{math}
 \hat{\bf r}  = \begin{pmatrix} 
\cos(\theta) \\ 
\sin(\theta) \\ 
0
\end{pmatrix}, \qquad  \hat{\bf \theta } = \begin{pmatrix} 
-\sin(\theta) \\ 
\cos(\theta)\\ 
0
\end{pmatrix},  \qquad \hat{\bf z} = 
\begin{pmatrix} 
0 \\ 
0\\ 
1\end{pmatrix} \\
```
are now not all constant, so in fact when we apply the derivative operator, we need to do any derivatives *ahead* of the dot product:

```{math}
\nabla \cdot {\bf A} &= \left(\hat{\bf r}\, \frac{\partial }{\partial r}  
+ \frac{\hat{\bf \theta }}{r}\,\frac{\partial }{\partial \theta}  
+ \hat{\bf z} \,\frac{\partial }{\partial z} 
 \right) \cdot \left( A_r\,\hat{\bf r} + A_\theta\,\hat{\bf \theta} + A_z\,\hat{\bf z}\right) \\
 &=\hat{\bf r}\cdot \left(\frac{\partial (A_r\,\hat{\bf r})}{\partial r} + \frac{\partial (A_\theta\,\hat{\bf \theta})}{\partial r}  + \frac{\partial (A_z\,\hat{\bf z})}{\partial r} \right) 
\\ &+ \frac{\hat{\bf \theta}}{r}\cdot\left(\frac{\partial (A_r\,\hat{\bf r})}{\partial \theta} + \frac{\partial (A_\theta\,\hat{\bf \theta})}{\partial \theta} + \frac{\partial (A_z\,\hat{\bf z})}{\partial \theta}  \right) 
\\ &+ \hat{\bf z}\cdot \left(\frac{\partial (A_r\,\hat{\bf r})}{\partial z}  + \frac{\partial (A_\theta\,\hat{\bf \theta})}{\partial z} +\frac{\partial (A_z\,\hat{\bf z})}{\partial z}  \right) 
```
So whereas the first and third sets of terms here will not have additional terms, the middle set of terms will be more complicated, because $\hat{\bf r} = \hat{\bf r} (\theta), \, \hat{\bf \theta} = \hat{\bf \theta} (\theta)$.

We find that:
```{math}
\frac{\partial \hat{\bf r}}{\partial \theta} = \begin{pmatrix} -\sin(\theta) \\ \cos(\theta)\end{pmatrix} = \hat{\bf \theta}, 
\qquad \frac{\partial \hat{\bf \theta}}{\partial \theta} = \begin{pmatrix} -\cos(\theta) \\ -\sin(\theta)\end{pmatrix} = - \hat{\bf r}
```
which means that:
```{math}
\nabla \cdot {\bf A} &= \hat{\bf r}\cdot \left(\frac{\partial (A_r)}{\partial r}\,\hat{\bf r} + \frac{\partial (A_\theta)}{\partial r} \,\hat{\bf \theta} + \frac{\partial (A_z)}{\partial r} \,\hat{\bf z}\right) 
\\ &+ \frac{\hat{\bf \theta}}{r}\cdot\left(\frac{\partial (A_r)}{\partial \theta}\,\hat{\bf r} + A_r \,\hat{\bf \theta} + \frac{\partial (A_\theta)}{\partial \theta}\,\hat{\bf \theta} - A_\theta\,\hat{\bf r} + \frac{\partial (A_z)}{\partial \theta} \,\hat{\bf z} \right) 
\\ &+ \hat{\bf z}\cdot \left(\frac{\partial (A_r)}{\partial z}\,\hat{\bf r} + \frac{\partial (A_\theta)}{\partial z}\,\hat{\bf \theta} +\frac{\partial (A_z)}{\partial z} \,\hat{\bf z} \right) \\
&= \frac{\partial (A_r)}{\partial r} + \frac{1}{r}\frac{\partial (A_\theta)}{\partial \theta} + \frac{A_r}{r} + \frac{\partial (A_z)}{\partial z} \\
\Rightarrow \nabla \cdot {\bf A}&= \frac{1}{r}\frac{\partial (r\,A_r)}{\partial r} + \frac{1}{r}\frac{\partial (A_\theta)}{\partial \theta}  + \frac{\partial (A_z)}{\partial z}
```

If we consider a vector in cylindrical coordinates, a vector with constant coefficients, e.g. $\displaystyle {\bf A} = \begin{pmatrix} a\\b\\c \end{pmatrix}$ will have non-zero divergence if 
and only if the $A_r \neq 0$, since:
```{math}
\nabla \cdot {\bf A} = \frac{1}{r}\frac{\partial (r\,a)}{\partial r} + \frac{1}{r}\frac{\partial b}{\partial \theta}  + \frac{\partial c}{\partial z} = \frac{a}{r}
```

### Spherical coordinate system
In spherical polar coordinates, we also have the additional complication that the unit vectors:
```{math}
 \hat{\bf r}  = \begin{pmatrix} 
\cos(\theta)\,\sin(\phi) \\ 
\sin(\theta)\,\sin(\phi) \\ 
\cos(\phi)
\end{pmatrix}, \qquad  \hat{\bf \phi } = \begin{pmatrix} 
\cos(\theta)\,\cos(\phi) \\ 
\sin(\theta)\,\cos(\phi) \\ 
-\sin(\phi)
\end{pmatrix},  \qquad \hat{\bf \theta} = 
\begin{pmatrix} 
-\sin(\theta) \\ 
\cos(\theta)\\ 
0
\end{pmatrix} \\
```
are now not all constant, so we need to do any derivatives *ahead* of the dot product:

```{math}
\nabla \cdot {\bf A} &= \left(\hat{\bf r}\, \frac{\partial }{\partial r}  
+ \frac{\hat{\bf \phi }}{r}\,\frac{\partial }{\partial \phi}  
+ \frac{\hat{\bf \theta}}{r\sin(\phi)} \,\frac{\partial }{\partial \theta} 
 \right) \cdot \left( A_r\,\hat{\bf r} + A_\phi\,\hat{\bf \phi} + A_\theta\,\hat{\bf \theta}\right) \\
 &=\hat{\bf r}\cdot \left(\frac{\partial (A_r\,\hat{\bf r})}{\partial r} + \frac{\partial (A_\phi\,\hat{\bf \phi})}{\partial r}  + \frac{\partial (A_\theta\,\hat{\bf \theta})}{\partial r} \right) 
\\ &+ \frac{\hat{\bf \phi}}{r}\cdot\left(\frac{\partial (A_r\,\hat{\bf r})}{\partial \phi} + \frac{\partial (A_\phi\,\hat{\bf \phi})}{\partial \phi} + \frac{\partial (A_\theta\,\hat{\bf \theta})}{\partial \phi}  \right) 
\\ &+ \frac{\hat{\bf \theta}}{r\,\sin(\phi)}\cdot \left(\frac{\partial (A_r\,\hat{\bf r})}{\partial \theta}  + \frac{\partial (A_\phi\,\hat{\bf \phi})}{\partial \theta} +\frac{\partial (A_\theta\,\hat{\bf \theta})}{\partial \theta}  \right) 
```
So whereas the first set of terms here will not have additional terms, the second and third set of terms will be more complicated, because $\hat{\bf r} = \hat{\bf r} (\phi,\, \theta), \, \hat{\bf \phi} = \hat{\bf \phi}(\phi,\,\theta),\, \hat{\bf \theta} = \hat{\bf \theta} (\phi,\,\theta)$.

We find that:
```{math}
\frac{\partial \hat{\bf r}}{\partial \phi} &= \begin{pmatrix} 
\cos(\theta)\,\cos(\phi) \\ 
\sin(\theta)\,\cos(\phi) \\ 
-\sin(\phi)
\end{pmatrix} = \hat{\bf \phi}, 
\qquad 
\frac{\partial \hat{\bf \phi}}{\partial \phi} = \begin{pmatrix} 
-\cos(\theta)\,\sin(\phi) \\ 
-\sin(\theta)\,\sin(\phi) \\ 
-\cos(\phi)
\end{pmatrix} = - \hat{\bf r},
\qquad
\frac{\partial \hat{\bf \theta}}{\partial \phi} = \begin{pmatrix} 
0 \\ 
0 \\ 
0
\end{pmatrix} 
\\
\frac{\partial \hat{\bf r}}{\partial \theta} &= \begin{pmatrix} 
-\sin(\theta)\,\sin(\phi) \\ 
\cos(\theta)\,\sin(\phi)\\ 
0
\end{pmatrix} = \sin(\phi)\,\hat{\bf \theta}, 
\qquad 
\frac{\partial \hat{\bf \phi}}{\partial \theta} = \begin{pmatrix} 
-\sin(\theta)\,\cos(\phi) \\ 
\cos(\theta)\,\cos(\phi)\\ 
0
\end{pmatrix} = \cos(\phi)\,\hat{\bf \theta},\\
\frac{\partial \hat{\bf \theta}}{\partial \theta} &= \begin{pmatrix} 
-\cos(\theta) \\ 
-\sin(\theta) \\ 
0
\end{pmatrix} = - (\sin(\phi)\,\hat{\bf r} + \cos(\phi)\,\hat{\bf \phi}),
```
which means that:
```{math}
\nabla \cdot {\bf A} &= \hat{\bf r}\cdot \left(\frac{\partial (A_r)}{\partial r}\,\hat{\bf r} + \frac{\partial (A_\phi)}{\partial r} \,\hat{\bf \phi} + \frac{\partial (A_\theta)}{\partial r} \,\hat{\bf \theta}\right) 
\\ &+ \frac{\hat{\bf \phi}}{r}\cdot\left(\frac{\partial (A_r)}{\partial \phi}\,\hat{\bf r} + A_r \,\hat{\bf \phi} + \frac{\partial (A_\phi)}{\partial \phi}\,\hat{\bf \phi} - A_\phi\,\hat{\bf r} + \frac{\partial (A_\theta)}{\partial \phi} \,\hat{\bf \theta} \right) 
\\ &+ \frac{\hat{\bf \theta}}{r\,\sin(\phi)}\cdot \left(\frac{\partial (A_r)}{\partial \theta}\,\hat{\bf r} + A_r\,\sin(\phi)\,\hat{\bf \theta} + \frac{\partial (A_\phi)}{\partial \theta}\,\hat{\bf \phi} \right.\\
&\left.\qquad \qquad + A_\phi\,\cos(\theta)\,\hat{\bf \theta} +\frac{\partial (A_\theta)}{\partial \theta} \,\hat{\bf \theta} - A_\theta(\hat{\bf r}\,\sin(\phi) + \hat{\bf \phi}\,\cos(\phi)) \right) \\
&= \frac{\partial (A_r)}{\partial r} + \frac{A_r}{r} + \frac{2}{r}\frac{\partial (A_\phi)}{\partial \phi} + \frac{A_\phi\,\cos(\phi)}{r\,\sin(\phi)} + \frac{1}{r\,\sin(\phi)}\frac{\partial (A_\theta)}{\partial \theta} \\
\Rightarrow \nabla \cdot {\bf A}&= \frac{1}{r^2}\frac{\partial (r^2\,A_r)}{\partial r} + \frac{1}{r\,\sin(\phi)}\,\frac{\partial (\sin(\phi)\,A_\phi)}{\partial \phi}  + \frac{1}{r\,\sin(\phi)}\,\frac{\partial (A_\theta)}{\partial \theta}
```

## Curl

We can likewise take a vector field ${\bf A(r)} $ and here take the vector product with the gradient operator $\nabla\times {\bf A(r)}$, which has components:

```{math}
\nabla\times {\bf A(r)} = 
\begin{vmatrix} \hat{\bf x} & \hat{\bf y} & \hat{\bf z}\\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ A_x & A_y & A_z\end{vmatrix}
= \begin{pmatrix} \partial_y\, A_z - \partial_z\, A_y \\ \partial_z\, A_x - \partial_x\, A_z \\ \partial_x\, A_y - \partial_y\, A_x  \end{pmatrix}
```

which is know as the <b>Curl</b> or <b>Rotation</b> of the vector field $\bf A(r)$ or $\text{curl}\,{\bf A(r)}$.

To see the effects of these, lets consider again ${\bf A_1(r)} = \begin{pmatrix} x \\ y \\ 0\end{pmatrix}, \,{\bf A_2(r)} = \begin{pmatrix} y \\ -x \\ 0\end{pmatrix}$:

```{math}
\nabla \times {\bf A_1} &=  \begin{pmatrix} \partial_y\, 0 + \partial_z\, x \\ \partial_z\, y - \partial_x\, 0 \\ \partial_x\, y - \partial_y\, x  \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix} \\
\nabla \times {\bf A_2} &=  \begin{pmatrix} \partial_y\, 0 + \partial_z\, x \\ \partial_z\, y - \partial_x\, 0 \\ \partial_x\, x + \partial_y\, y  \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 2 \end{pmatrix}
```

which we can visualise in {numref}`curl`.  

```{figure} ../figures/curl.png
---
name: curl
---
Plotting the vector field ${\bf A_2}$ which has non-zero curl.
```

We note that "centre" of this rotation is at the origin and that $\nabla \times {\bf A_2}$ points in the $z$ direction.  We define this rotation as following the right 
hand rule, depicted in {numref}`righthandcurl`, curling the fingers on our right hand around and the thumb pointing in the direction of the vector.

```{figure} ../figures/Rhandrule.png
---
name: righthandcurl
---
The right hand rule for a curl field
```

We can see that a linear combination of vector fields $\bf A_1 + A_2$ would produce a vector field with <em>both</em> divergence and curl, which is shown in {numref}`divcurl`.

```{figure} ../figures/divcurl.png
---
name: divcurl
---
The effect of adding a divergence (curl free) field (left hand figure) to a curl (divergence free) field (middle figure) is shown in the right hand figure.
```

We can use the product rule as well as the rules following scalar and vector products to find a vareity of vector calculus relations:
```{math}
\nabla(\phi\,\psi) &=  \psi(\nabla \phi) + \phi(\nabla \psi)\\
\nabla \cdot(\phi {\bf A}) &=  (\nabla \phi)\cdot {\bf A} + \phi(\nabla \cdot {\bf A})\\
\nabla \times(\phi {\bf A}) &=  (\nabla \phi)\times {\bf A} + \phi(\nabla \times {\bf A})\\
\nabla \cdot ({\bf A \times B}) &=  (\nabla \times {\bf A})\cdot {\bf B} - {\bf A}\cdot(\nabla \times {\bf B})\\
\nabla \times ({\bf A \times B}) &=  (\nabla \cdot {\bf B} + {\bf B}\cdot \nabla)\,{\bf A} - (\nabla \cdot {\bf A}+ {\bf A}\cdot \nabla)\,{\bf B}
```

### Cylindrical coordinate systems

As with the divergence, the variation of the unit vectors causes additional complexity in calculating the curl:
```{math}
\nabla \times {\bf A} = \left(\hat{\bf r}\, \frac{\partial }{\partial r}  
+ \frac{\hat{\bf \theta }}{r}\,\frac{\partial }{\partial \theta}  
+ \hat{\bf z} \,\frac{\partial }{\partial z} 
 \right) \times \left( A_r\,\hat{\bf r} + A_\theta\,\hat{\bf \theta} + A_z\,\hat{\bf z}\right)
```

which given our expressions for variation of unit vectors with coordinate variables means:
```{math}
\nabla \times {\bf A} &= \hat{\bf r}\times \left(\frac{\partial (A_r)}{\partial r}\,\hat{\bf r} + \frac{\partial (A_\theta)}{\partial r} \,\hat{\bf \theta} + \frac{\partial (A_z)}{\partial r} \,\hat{\bf z}\right) 
\\ &+ \frac{\hat{\bf \theta}}{r}\times\left(\frac{\partial (A_r)}{\partial \theta}\,\hat{\bf r} + A_r \,\hat{\bf \theta} + \frac{\partial (A_\theta)}{\partial \theta}\,\hat{\bf \theta} - A_\theta\,\hat{\bf r} + \frac{\partial (A_z)}{\partial \theta} \,\hat{\bf z} \right) 
\\ &+ \hat{\bf z}\times \left(\frac{\partial (A_r)}{\partial z}\,\hat{\bf r} + \frac{\partial (A_\theta)}{\partial z}\,\hat{\bf \theta} +\frac{\partial (A_z)}{\partial z} \,\hat{\bf z} \right) \\
```
Given the cylic nature of unit vectors and their orthongality:
```{math}
\hat{\bf r} \times \hat{\bf \theta} &= \hat{\bf z}\\
\hat{\bf \theta} \times \hat{\bf z} &= \hat{\bf r}\\
\hat{\bf z} \times \hat{\bf r} &= \hat{\bf \theta}\\
\hat{\bf r} \times \hat{\bf r} &= \hat{\bf \theta} \times \hat{\bf \theta} = \hat{\bf z} \times \hat{\bf z} = 0
```
means we find that:
```{math}
\nabla \times {\bf A} &= \left(\frac{\partial (A_\theta)}{\partial r} \,\hat{\bf z} - \frac{\partial (A_z)}{\partial r} \,\hat{\bf \theta}\right) 
+ \left(-\frac{1}{r}\frac{\partial (A_r)}{\partial \theta}\,\hat{\bf z} + \frac{A_\theta}{r}\,\hat{\bf z} + \frac{1}{r}\frac{\partial (A_z)}{\partial \theta} \,\hat{\bf r} \right) \\
&+ \left(\frac{\partial (A_r)}{\partial z}\,\hat{\bf \theta} - \frac{\partial (A_\theta)}{\partial z}\,\hat{\bf r}\right)\\
\Rightarrow \nabla \times {\bf A}&= \left(\frac{1}{r}\,\frac{\partial A_z}{\partial \theta} - \frac{\partial A_\theta}{\partial z} \right)\,\hat{\bf r} + \left(\frac{\partial A_r}{\partial z} - \frac{\partial A_z}{\partial r}\right)\,\hat{\bf \theta} + \frac{1}{r}\left(\frac{\partial (r\,A_\theta)}{\partial r}-\frac{\partial A_r}{\partial \theta}\right)\,\hat{\bf z}
```

### Spherical coordinate systems

In a similar fashion to the cylindrical polar coordinates, we need to consider how the unit vectors change under differentiation first before 
applying the cross product, therefore:
```{math}
\nabla \times {\bf A} &= \left(\hat{\bf r}\, \frac{\partial }{\partial r}  
+ \frac{\hat{\bf \phi }}{r}\,\frac{\partial }{\partial \phi}  
+ \frac{\hat{\bf \theta}}{r\sin(\phi)} \,\frac{\partial }{\partial \theta} 
 \right) \times \left( A_r\,\hat{\bf r} + A_\phi\,\hat{\bf \phi} + A_\theta\,\hat{\bf \theta}\right) \\
 &=\hat{\bf r}\times \left(\frac{\partial (A_r)}{\partial r}\,\hat{\bf r} + \frac{\partial (A_\phi)}{\partial r} \,\hat{\bf \phi} + \frac{\partial (A_\theta)}{\partial r} \,\hat{\bf \theta}\right) 
\\ &+ \frac{\hat{\bf \phi}}{r}\times\left(\frac{\partial (A_r)}{\partial \phi}\,\hat{\bf r} + A_r \,\hat{\bf \phi} + \frac{\partial (A_\phi)}{\partial \phi}\,\hat{\bf \phi} - A_\phi\,\hat{\bf r} + \frac{\partial (A_\theta)}{\partial \phi} \,\hat{\bf \theta} \right) 
\\ &+ \frac{\hat{\bf \theta}}{r\,\sin(\phi)}\times \left(\frac{\partial (A_r)}{\partial \theta}\,\hat{\bf r} + A_r\,\sin(\phi)\,\hat{\bf \theta} + \frac{\partial (A_\phi)}{\partial \theta}\,\hat{\bf \phi} \right.\\
&\left.\qquad \qquad + A_\phi\,\cos(\theta)\,\hat{\bf \theta} +\frac{\partial (A_\theta)}{\partial \theta} \,\hat{\bf \theta} - A_\theta(\hat{\bf r}\,\sin(\phi) + \hat{\bf \phi}\,\cos(\phi)) \right) 
```
Given the cylic nature of unit vectors and their orthongality:
```{math}
\hat{\bf r} \times \hat{\bf \phi} &= \hat{\bf \theta}\\
\hat{\bf \phi} \times \hat{\bf \theta} &= \hat{\bf r}\\
\hat{\bf \theta} \times \hat{\bf r} &= \hat{\bf \phi}\\
\hat{\bf r} \times \hat{\bf r} &= \hat{\bf \phi} \times \hat{\bf \phi} = \hat{\bf \theta} \times \hat{\bf \theta} = 0
```
means we find that:
```{math}
\nabla \times {\bf A} &= \left(\frac{\partial (A_\phi)}{\partial r} \,\hat{\bf \theta} - \frac{\partial (A_\theta)}{\partial r} \,\hat{\bf \phi}\right) 
+ \left(-\frac{1}{r}\frac{\partial (A_r)}{\partial \phi}\,\hat{\bf \theta} + \frac{A_\phi}{r}\,\hat{\bf \theta} 
+ \frac{1}{r}\frac{\partial (A_\theta)}{\partial \phi} \,\hat{\bf r} \right) \\
&+ \left(\frac{1}{r\,\sin(\phi)}\frac{\partial (A_r)}{\partial \theta}\,\hat{\bf \phi} - \frac{1}{r\,\sin(\phi)}\frac{\partial (A_\phi)}{\partial \theta}\,\hat{\bf r} - \frac{A_\theta}{r}\,\hat{\bf \phi} 
+ \frac{A_\theta\,\cos(\phi)}{r\,\sin(\phi)}\,\hat{\bf r}\right)\\
\Rightarrow \nabla \times {\bf A}&= \frac{1}{r\,\sin(\phi)}\left(\frac{\partial (A_\theta\,\sin(\phi))}{\partial \phi} - \frac{\partial A_\phi}{\partial \theta} \right)\,\hat{\bf r} 
\\&+ \frac{1}{r}\left(\frac{1}{\sin(\phi)}\frac{\partial A_r}{\partial \theta} - \frac{\partial (r\,A_\theta)}{\partial r}\right)\,\hat{\bf \phi} 
\\&+ \frac{1}{r}\left(\frac{\partial (r\,A_\phi)}{\partial r}-\frac{\partial A_r}{\partial \phi}\right)\,\hat{\bf \theta}
```


## Second order variations of fields
We can combine two or more gradients in a vector expression, one of the most useful is to find the divergence of the gradient of a scalar field $\phi$, 
```{math}
\textrm{div grad} \,\phi = \nabla \cdot (\nabla \phi) = \nabla^2 \phi = \left(\frac{\partial}{\partial_x^2} + \frac{\partial}{\partial_y^2} + \frac{\partial}{\partial_z^2}\right)\phi
```
This is sometimes also written as $\Delta\phi = \nabla^2 \phi $ and is known as the Laplacian of $\phi$.  

We can also find the divergence of the curl of a vector field:

```{math}
\text{div}\,\,\text{curl}\,{\bf A} = \nabla \cdot (\nabla \times {\bf A}) = 0
```

which holds for <em>all</em> vector fields.  Thinking again about the fields shown in {numref}`divcurl`, we can think of these two processes as complementary, 
rotation around a point compared with emergence from / convergence to a point.

Likewise if we look at the curl of a gradient field:
```{math}
\text{curl}\,\,\text{grad}\,\phi = \nabla \times \nabla \phi = 0
```
which is true for <em>all</em> scalar fields.

Also we sometimes find the curl of the curl a useful quantity:
```{math}
\nabla \times \left(\nabla \times {\bf A}\right) = \nabla \left(\nabla \cdot {\bf A} \right) - \nabla^2 {\bf A}
```

In general we can write a vector field as having two sets of components, one curl free and one divergence free, this is known as the <b>Helmholtz Decomposition</b> of a vector field:

```{math}
{\bf B} = -\nabla \phi + \nabla \times {\bf A}
```



## Conservative vector fields

Recall the concept of a perfect (or exact) differential where the following property holds:

```{math}
P(x,\,y)\,\mathrm{d}x + Q(x,\,y)\,\mathrm{d}y = 0 \Longleftrightarrow \frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} 
```
where this holds because there is some function $f(x,\,y)$ which is constant such that $\mathrm{d}f = 0$ and so this expression 
is really just:
```{math}
\mathrm{d}f = \frac{\partial f}{\partial x}\,\mathrm{d}x + \frac{\partial f}{\partial y}\,\mathrm{d}y = 0
```
and the expression calculated is just:
```{math}
\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}  = \frac{\partial^2 f}{\partial x\,\partial y}
```
There is a vector calculus generalisation of this sort of scalar function, known as the **conservative vector field**.

````{admonition} Definition
:class: notice
A conservative vector field ${\bf v}$ is one which is formed solely from the gradient of some function $f(x,\,y,\,z)$:
```{math}
{\bf v} = \nabla f
```

Such a vector field is therefore curl free:
```{math}
\nabla \times {\bf v} = \nabla \times \nabla f = 0
```

Such a vector field also has a path independent line integral (more on this property later).
````

Lets examine the case of a vector field $\bf v$ formed from the function $f(x,\,y,\,z) = xyz$, the gradient of this function is given by:
```{math}
{\bf v} = \nabla f = \begin{pmatrix} yz \\ xz \\ xy \end{pmatrix}
```

and if we take the curl of such a vector field:
```{math}
\nabla \times {\bf v} &= \begin{vmatrix} \hat{\bf x} & \hat{\bf y} & \hat{\bf z} \\ \partial_x & \partial_y & \partial_z \\ yz & xz & xy\end{vmatrix} \\
&= (x - x)\,\hat{\bf x} + (y - y)\,\hat{\bf y} + (z - z)\,\hat{\bf z} = 0
```
Likewise if we started with some vector field and wanted to work out if it is conservative (and if so which scalar field sourced it), we could examine 
each component and integrate, for instance if:
```{math}
{\bf v} = \begin{pmatrix} 2x\sin(y) \\ x^2\cos(y) \\ 2 \end{pmatrix}
```
then examining each component we find:
```{math}
v_x = 2x\sin(y) &\Rightarrow \phi = \int 2x\sin(y)\,\mathrm{d}x = x^2\sin(y) + a(y,\,z) \\
v_y = x^2\cos(y) &\Rightarrow \phi = \int 2x\sin(y)\,\mathrm{d}x = x^2\sin(y) + b(x,\,z) \\
v_z = 2 &\Rightarrow \phi = \int 2\,\mathrm{d}z = 2z + c(x,\,y) 
```
Comparing all three expressions we find that $f = x^2\sin(y) + 2z$ and hence ${\bf v} = \nabla f$.  