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

### Other coordinate systems
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
+ \hat{\bf \theta }\,\frac{1}{r}\,\frac{\partial }{\partial \theta}  
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
\\ &+ \hat{\bf z}\cdot \left(\frac{\partial (A_r\,\hat{\bf r})}{\partial z}  + \frac{\partial (A_\theta)}{\partial z}\,\hat{\bf \theta} +\frac{\partial (A_z)}{\partial z} \,\hat{\bf z} \right) \\
&= \frac{\partial (A_r)}{\partial r} + \frac{1}{r}\frac{\partial (A_r)}{\partial \theta} + \frac{A_r}{r} + \frac{\partial (A_z)}{\partial z} \\
\Rightarrow \nabla \cdot {\bf A}&= \frac{1}{r}\frac{\partial (r\,A_r)}{\partial r} + \frac{1}{r}\frac{\partial (A_r)}{\partial \theta}  + \frac{\partial (A_z)}{\partial z}
```


## Curl

We can likewise take a vector field ${\bf A(r)} $ and here take the vector product with the gradient operator $\nabla\times {\bf A(r)}$, which has components:

```{math}
\nabla\times {\bf A(r)} = \begin{pmatrix} \partial_y\, A_z - \partial_z\, A_y \\ \partial_z\, A_x - \partial_x\, A_z \\ \partial_x\, A_y - \partial_y\, A_x  \end{pmatrix}
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
\nabla \cdot ({\bf A \times B}) &=  (\nabla \times {\bf A})\cdot {\bf B} - {\bf A}(\nabla \times\cdot {\bf B})\\
\nabla \times ({\bf A \times B}) &=  (\nabla \cdot {\bf B} + {\bf B}\cdot \nabla)\,{\bf A} - (\nabla \cdot {\bf A}+ {\bf A}\cdot \nabla)\,{\bf B}
```

## Second order variations of fields
We can combine two or more gradients in a vector expression, one of the most useful is to find the divergence of the gradient of a scalar field $\phi$, 
```{math}
\textrm{div grad} \,\phi = \nabla \cdot (\nabla \phi) = \nabla^2 \phi = (\partial_x^2 + \partial_y^2 + \partial_z^2)\phi
```
This is sometimes also written as $\Delta\phi = \nabla^2 \phi $ and is known as the Laplacian of $\phi$.  

We can also find the divergence of the curl of a vector field:

```{math}
\text{div}\,\,\text{curl}\,{\bf A} = \nabla \cdot (\nabla \times {\bf A}) = 0
```

which holds for <em>all</em> vector fields.  Thinking again about the fields shown in {numref}`divcurl`,w e can think of these two processes as complementary, 
rotation around a point compared with emergence from / convergence to a point.

Likewise if we look at the curl of a gradient field:
```{math}
\text{curl}\,\,\text{grad}\,\phi = \nabla \times \nabla \phi = 0
```
which is true for <em>all</em> scalar fields.

In general we can write a vector field as having two sets of components, one curl free and one divergence free, this is known as the <b>Helmholtz Decomposition</b> of a vector field:

```{math}
{\bf B} = -\nabla \phi + \nabla \times {\bf A}
```


