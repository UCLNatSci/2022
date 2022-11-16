# Vectors and Vector Algebra

We can think of vectors at their heart as directions being given to get between two points in space.  If we have to move in one, two or three dimensions, along spatially flat or curved surfaces, 
we can attempt to give directions.  At the heart of a any vector system are the <b>basis vectors</b>, these give us the funadmental possible directions within a vector space, which any vector can be
decompsoed into a weighted sum of.

````{admonition} Defintion
In the Cartesian coordinate system, in three dimensions the basis vectors are given as:

```{math}
\hat{\bf x} = \,\begin{pmatrix}
 1 \\
 0 \\
 0 
\end{pmatrix}, \quad 
\hat{\bf y} = \,\begin{pmatrix}
 0 \\
 1 \\
 0 
\end{pmatrix}, \quad 
\hat{\bf z} \,\begin{pmatrix}
 0 \\
 0 \\
 1 
\end{pmatrix}
```
````

When we switch to different coordinate systems, we will consider how these change.  Note that a variety of different letters are employed for the Cartessian system:
```{math}

\hat{\bf x} &=  {\bf e_x} = \vec{x} = \hat{\bf i}\\
\hat{\bf y} &=  {\bf e_y} = \vec{y} = \hat{\bf j}\\
\hat{\bf z} &=  {\bf e_z} = \vec{z} = \hat{\bf k}
```
To see how these visually fit together, see {numref}`CartCoords`.  We note that all the coordinates meet at right angles and that we have defined <em>right handed axes</em>.

```{figure} ../figures/CartesianCoordinateSystem.png
---
name: CartCoords
---

<b>Left Pane</b>: Graphical breakdown of the Cartesian coordinate system with vector path in red,
<b>Right Pane</b>: The differences between left handed (top) and right handed (bottom) axes.
```

We can also write coordinates in so-called <b>index notation</b>:
```{math}
x_i = \left(\hat{\bf x},\, \hat{\bf y},\, \hat{\bf z}\right)
```
where the value of $i = \in \{1,\,2,\,3\}$ denotes the specific basis vector.

## Addition and Scaling of Vectors

If we start with the basis vectors as building blocks of our coordinate system, then we can write any three dimensional Cartesian coordinate in terms of 
weighted basis vectors, we can see this in {numref}`basisvectors`.

```{figure} ../figures/basisvectors.png
---
name: basisvectors
---
Breakdown of vector $\bf a = a_x \,\hat{\bf x} + a_y \,\hat{\bf y} + a_z \,\hat{\bf z}$.
```

As an example we can define two vectors $\bf v_1,\, v_2$
```{math}
{\bf v}_1 &=  \begin{pmatrix}
 3 \\
 4 \\
 12 
\end{pmatrix} = 3\hat{\bf x} + 4\hat{\bf y} + 12\hat{\bf z}\\
{\bf v}_2 &=  \begin{pmatrix}
 5 \\
 12 \\
 13 
\end{pmatrix} = 5\hat{\bf x} + 12\hat{\bf y} + 13\hat{\bf z}
```
Then we can add or sutract these vectors:

```{math}
{\bf v}_1 + {\bf v}_2  &=  \begin{pmatrix}
 3 \\
 4 \\
 12 
\end{pmatrix} + \begin{pmatrix}
 5 \\
 12 \\
 13 
\end{pmatrix} = \begin{pmatrix}
 8 \\
 16 \\
 25 
\end{pmatrix} = 8\hat{\bf x} + 16\hat{\bf y} + 25\hat{\bf z}\\
{\bf v}_2 - {\bf v}_1  &=  \begin{pmatrix}
 5 \\
 12 \\
 13 
\end{pmatrix} - 
\begin{pmatrix}
 3 \\
 4 \\
 12 
\end{pmatrix} = \begin{pmatrix}
 2 \\
 8 \\
 1 
\end{pmatrix} = 2\hat{\bf x} + 8\hat{\bf y} + \hat{\bf z}

```
Likewise we can scale each of the vectors and then proceed to add them:
```{math}
2{\bf v}_1 + 3{\bf v}_2  &=   2\begin{pmatrix}
 3 \\
 4 \\
 12 
\end{pmatrix} + 3\begin{pmatrix}
 5 \\
 12 \\
 13 
\end{pmatrix} = \begin{pmatrix}
 21 \\
 44 \\
 63 
\end{pmatrix} = 21\hat{\bf x} + 44\hat{\bf y} + 49\hat{\bf z}
```

## Magnitude of a Vector

Given some vector, which will take us some distance from two points in space, we can find the shortest path length between the points.  

````{admonition}
A magnitude of a vector ${\bf v}$ with $n$ orthogonal components is:
```{math}
|{\bf v}| &= \sqrt{{v_1}^2 + {v_2}^2 +  + \dots + {v_n}^2} = \sqrt{\sum_{i=1}^n (v_i)^2}
``` 
````

In two dimensions this would just follow Pythagoras's theorem:
```{math}
{\bf v} &= a_x\hat{\bf x} + a_y\hat{\bf y}\\
v_3 &= |{\bf v}| = \sqrt{{a_x}^2 + {a_y}^2}
```

and in three dimensions a similar relation holds (which we can prove geometrically:
```{math}
{\bf v} &= a_x\hat{\bf x} + a_y\hat{\bf y} + a_z\hat{\bf z}\\
v_3 &= |{\bf v}| = \sqrt{{a_x}^2 + {a_y}^2 + {a_z}^2} 
```
As an example lets consider $\bf v_1$:

```{math}
|3\hat{\bf x} + 4\hat{\bf y} + 12\hat{\bf z}| = \sqrt{3^2 + 4^2 + 12^2} = 13
```


## Normalised Vectors
Each of the basis vectors is a normalised vector $|\hat{\bf x}| = |\hat{\bf y}| = |\hat{\bf z}| = 1$, however if we have a more general vector 
${\bf v} = a_x\hat{\bf x} + a_y\hat{\bf y} + a_z\hat{\bf z}$ moving in some direction, we can also construct a normalised vector:
````{admonition} Definition
```{math}
\hat{\bf v} = \frac{\bf v}{|\bf v|} = \frac{a_x\hat{\bf x} + a_y\hat{\bf y} + a_z\hat{\bf z}}{\sqrt{{a_x}^2 + {a_y}^2 + {a_z}^2}}
```
````
````{admonition} Example
:class: seealso
```{math}
\hat{\bf v_1} = \frac{\bf v_1}{|\bf v_1|} = \frac{3\hat{\bf x} + 4\hat{\bf y} + 12\hat{\bf z}}{\sqrt{3^2 + 4^2 + 12^2}} = \frac{1}{13}\left(3\hat{\bf x} + 4\hat{\bf y} + 12\hat{\bf z}\right)
```
````

## Scalar Product / Dot Product
Lets consider two vectors $\bf A,\, B$, as shown in {numref}`scalarprojection`.  We can consider the scalar projection of the vector $\bf B$ on to the vector $\bf A$, where we resolve the 
parallel components of $\bf B$ in the direction of vector $\bf A$.

```{figure} ../figures/scalarprojection.png
---
name: scalarprojection
---
<b>Left Pane</b>: Vectors $\bf A,\, B$ which share a common coordinate and span an angle $\theta$ between them,
<b>Right Pane</b> The scalar projection of the vector $\bf B$ on to the vector $\bf A$, which by trigonometry gives the length $|{\bf B}| \cos\theta$.
```

If we multiply these two distances, this is known as the **scalar** product of the vectors.

````{admonition} Geometric definition
The scalar product (also called the **dot** product) is given by:
```{math}
{\bf A \cdot B} = |{\bf A}||{\bf B}|\cos(\theta)
```
````

So we can calculate the scalar projection of $\bf B$ onto vector $\bf A$ using ${\bf A \cdot B} / |{\bf A}|$.  Likewise we can think about the scalar projection of $\bf A$ onto the vector 
$\bf B$, using $\displaystyle \frac{\bf A \cdot B}{|{\bf B}|}$.

We can also find the magntiude of a vector from $\bf A \cdot A = |A|^2 $.

````{admonition} Algebraic definition
There is another perspective on the scalar product, which is for two vectors with components:
```{math}
{\bf A} &=  a_x\,\hat{\bf x} + a_y\,\hat{\bf y} + a_z\,\hat{\bf z} = \begin{pmatrix}
 a_x \\
 a_y \\
 a_z 
\end{pmatrix} \\
{\bf B} &=  b_x\,\hat{\bf x} + b_y\,\hat{\bf y} + b_z\,\hat{\bf z} = \begin{pmatrix}
 b_x \\
 b_y \\
 b_z 
\end{pmatrix}
```
the dot product can be found algebraically by:
```{math}
{\bf A \cdot B} = a_x\,b_x + a_y\,b_y + a_z\,b_z= \sum_{i=1}^3 a_i\,b_i
```
where the last expression uses the index notation.
````

### Properties of the Dot Product

The dot product of two vectors $\bf a,\, b$ have the following mathematical properties:

1\. *Commutative:*
$\mathbf {a} \cdot \mathbf {b} = \mathbf {b} \cdot \mathbf {a}$

2\. *Distributive over Vector Addition:*
$  \mathbf {a} \cdot (\mathbf {b} +\mathbf {c} )=\mathbf {a} \cdot \mathbf {b} +\mathbf {a} \cdot \mathbf {c}$

3\. *Bilinear:*
$ \mathbf {a} \cdot (r\mathbf {b} +\mathbf {c} )=r(\mathbf {a} \cdot \mathbf {b} )+(\mathbf {a} \cdot \mathbf {c} )$

4\. *Scalar Multiplication:*
$ (c_{1}\mathbf {a} )\cdot (c_{2}\mathbf {b} )=c_{1}c_{2}(\mathbf {a} \cdot \mathbf {b} )$

5\. *Orthogonal:*
Two non-zero vectors $\bf a,\, b$ are orthogonal if and only if $\bf a \cdot b = 0$.

## Vector Product / Cross Product

Unsurprisingly we can also make a vector product that results in a vector, rather than a scalar, this is known as the **Vector** product, also caleed the **Cross** product.

````{admonition} Geometric definition
The cross product can be constructed from the basis vectors:
```{math}
\hat{\bf x} \times \hat{\bf y} &=  \hat{\bf z} \\
\hat{\bf y} \times \hat{\bf z} &=  \hat{\bf x} \\
\hat{\bf z} \times \hat{\bf x} &=  \hat{\bf y} 
```
````
In general however we write the cross product between two vectors as a new vector, normal to the other two (following the right hand rule), as depicted in 
{numref}`VectorProduct`.

```{figure} ../figures/VectorProduct.png
---
name: VectorProduct
---

<b>Left Pane</b>: Graphical depiction of the cross product, producing a vector $\bf a \times b$ which is normal to both $\bf a,\, b$,
<b>Right Pane</b>: The area of the parallogram produced by vectors $\bf a,\, b$ is found from $|\bf a \times b|$
```
This means that if vectors span an angle $\theta$, then we need to resolve the perpendicular component:
```{math}
{\bf a \times b} = {\bf |a||b|}\sin(\theta)\,\hat{\bf n}
```
where $\hat{\bf n}$ is vector which is normal to both $\bf a,\, b$.

Because the cross product follows the right hand rule for axes, it is anti-commutative:
```{math}
\bf a \times b = -\,b \times a
```
We also find the at the cross product is distributive over addition,

```{math}
\mathbf {a} \times (\mathbf {b} +\mathbf {c} )=(\mathbf {a} \times \mathbf {b} )+(\mathbf {a} \times \mathbf {c} )
```

and compatible with scalar multiplication:

```{math}
(r\,\mathbf {a} )\times \mathbf {b} =\mathbf {a} \times (r\,\mathbf {b} )=r\,(\mathbf {a} \times \mathbf {b} )
```

Likewise since the vector magnitude depends on the angle between the two vectors, if we cross a vector with itself (or another vector that is parallel / anti-parallel), 
the answer is zero:

```{math}
\bf a \times a = 0
```
where $\bf 0$ is a zero vector.

Once again there is also an algebraic route to the cross product, this is based on the vector components.  

Since the cross product is distributive over addition we find that:

```{math}
 \mathbf{a}\times\mathbf{b} = {} &(a_x\,\hat{\bf x} + a_y\,\hat{\bf y} + a_z\,\hat{\bf z}) \times (b_x\,\hat{\bf x} + b_y\,\hat{\bf y} + b_z\,\hat{\bf z})\\
                            = {} &a_x\,b_x(\hat{\bf x} \times \hat{\bf x}) + a_x\,b_y(\hat{\bf x} \times \hat{\bf y}) + a_x\,b_z(\hat{\bf x} \times \hat{\bf z}) + {}\\
                                 &a_y\,b_x(\hat{\bf y} \times \hat{\bf x}) + a_y\,b_y(\hat{\bf y} \times \hat{\bf y}) + a_y\,b_z(\hat{\bf y} \times \hat{\bf z}) + {}\\
                                 &a_z\,b_x(\hat{\bf z} \times \hat{\bf x}) + a_z\,b_y(\hat{\bf z} \times \hat{\bf y}) + a_z\,b_z(\hat{\bf z} \times \hat{\bf z})\\
```
If we follow through our rules for computing the cross products of basis vectors, we find this simplifies to:
```{math}
 \mathbf{a}\times\mathbf{b} = {} &a_x\,b_x(0) + a_x\,b_y(\hat{\bf z}) + a_x\,b_z(-\hat{\bf y}) + {}\\
                                 &a_y\,b_x(-\hat{\bf z}) + a_y\,b_y(0) + a_y\,b_z(\hat{\bf x}) + {}\\
                                 &a_z\,b_x(\hat{\bf y}) + a_z\,b_y(-\hat{\bf x}) + a_z\,b_z(0)\\
							= {} &(a_y\,b_z - a_z\,b_y)\hat{\bf x} + (a_z\,b_x - a_x\,b_z)\hat{\bf y} + (a_x\,b_y - a_y\,b_x)\hat{\bf z} 
```

````{admonition} Algebraic definition
Finding the cross product can  be found using a matrix determinant:

```{math}
 \mathbf{a}\times\mathbf{b} = \begin{vmatrix}
 \hat{\bf x} & \hat{\bf y} & \hat{\bf z} \\
 a_x & a_y & a_z \\
 b_x & b_y & b_z
\end{vmatrix}
```
which by the cofactor method along the first row produces:

```{math}
 \mathbf{a}\times\mathbf{b} &=  \begin{vmatrix}
 a_y & a_z \\
 b_y & b_z
\end{vmatrix}\hat{\bf x} - \begin{vmatrix}
 a_x & a_z \\
 b_x & b_z
\end{vmatrix}\hat{\bf y} + \begin{vmatrix}
 a_x & a_y 
 b_x & b_y 
\end{vmatrix}\hat{\bf z} \\
&=  (a_y\,b_z - a_z\,b_y)\hat{\bf x} - (a_x\,b_z - a_z\,b_x)\hat{\bf y} + (a_x\,b_y - a_y\,b_x)\hat{\bf z} 
```
which we find are equivalent definitions.
````

## Triple Vector Products
Now that we have multiplcation of two vectors formalised, we find that multiplying three vectors also leads to some further geometric and algebraic ideas.

### Triple Scalar Product
Here we have three vectors $\bf a, \,b,\,c$ composed so that
```{math}
\bf a \cdot (b \times c)
```
since the combination of $\bf b \times c$ produces a vector, which we can then do a scalar multiplcation with $\bf a$.  Therefore this produces a scalar result.

Geometrically this is related to the parallepiped, as depicted in {numref}`parallepiped`, where the magnitude of this result is the shapes volume:
```{math}
V = |{\bf a \cdot (b \times c)}|
```

```{figure} ../figures/parallepiped.png
---
name: parallepiped
---
A parallepiped, composed from three vectors $\bf a, \,b,\,c$.
```

We can also evaluate the triple scalar product from a matrix determinant:
```{math}
 {\bf a \cdot (b \times c)} = {\bf c}\cdot\mathbf{a}\times\mathbf{b} = {\bf b}\cdot\mathbf{c}\times\mathbf{a} = \begin{vmatrix}
 a_x & a_y & a_z \\
 b_x & b_y & b_z \\
 c_x & c_y & c_z \\
\end{vmatrix}
```

### Triple Vector Product
Unsurprisingly we can also find an expression for the vector product between three vectors $\bf a, \,b,\,c$:
```{math}
\bf a \times (b \times c) = (a\cdot c)b - (a \cdot b)c
```
which is useful particularly when we want to work out results like:
```{math}
\bf \nabla \times \nabla \times A = \nabla(\nabla \cdot A) - (\nabla\cdot \nabla)A = \nabla(\nabla \cdot A) - \nabla^2 A
```
which will be useful later!

## Vector Lines and Planes 

We can identify points in space using their position vectors, which are typically denoted by

```{math}
{\bf r} =\left(\begin{array}{c}x\\y\\z\end{array}\right)
```

This gives us two ways of writing down the equations of lines and planes:

- <b>Vector Form:</b> in terms of the position vector $\bf r$,

- <b>Scalar Form:</b> in terms of the coordinates $x,\, y,\, z$.

In what follows, we will write the equations using both conventions. You will see that sometimes it is easier to work with 
the scalar equations and other times it is easier to work with the vector equations.

    

### Equation of a Line

The vector equation of a line can be obtained from a known point on the line and a known vector parallel to the 
line. Equivalently, two known points on the line can also be used to find a parallel vector.

We obtain the position vector of the other points by a two step process:

- first carrying from the origin to the known point

- secondly carrying along the line in either direction

This principle is illustrated in {numref}`positionvector`

```{figure} ../figures/vector_line.gif
---
name: positionvector
---
The vector equation of a line passing through two points $P,\,Q$. The position vector $\bf r$, shown in red, describes 
an arbitrary point on the line, it can be formed by the sum ${\bf r}={\bf r}_0+\lambda{\bf v}$.
```

An arbitrary scalar parameter $\lambda$ controls how far along the line we move, and if it is negative then the direction is reversed. 
The animation shows how the line is described as the parameter $\lambda$ is varied.

We can also use the vector equation to calculate the corresponding scalar equation. From the vector equation we obtain:

```{math}
\begin{pmatrix} x \\y \\z \end{pmatrix} =
\begin{pmatrix} x_0 \\y_0 \\z_0 \end{pmatrix} + 
\lambda \begin{pmatrix} v_x \\v_y \\v_z \end{pmatrix}
```
Equating components on the left and right and rearranging in each equation for $\lambda$ then gives the result in vector form :

```{math} {\bf r}={\bf r}_0+\lambda{\bf v}
```

or in scalar form:

```{math}
\frac{x-x_0}{v_x}=\frac{y-y_0}{v_y}=\frac{z-z_0}{v_z}
```

where ${\bf r_0}=\begin{pmatrix} x_0\\y_0\\z_0\end{pmatrix}$ is the position vector of a point on the line, and 
${\bf v}=\begin{pmatrix}  v_x\\v_y\\v_z\end{pmatrix}$ is a vector parallel to the line.  Notice that the special case where $z$ is constant 
gives an equation of the form $y = m x+c$

````{admonition} Worked example
:class: seealso 
Find the vector equation of the lines:
```{math} 
\frac{3x+1}{2} = \frac{y−1}{2} = \frac{5−z}{3}
```

By setting each of these equations to equal some constant $\lambda$:

```{math}
\frac{3x+1}{2} = \lambda &\Rightarrow x =  \frac{1}{3}(2\lambda-1) = -\frac{1}{3} + \frac{2}{3}\lambda \\
\frac{y−1}{2} = \lambda &\Rightarrow y =  1 + 2\lambda \\
\frac{5−z}{3} = \lambda &\Rightarrow z =  -(3\lambda -5) = 5 - 3 \lambda
```

we find the vector equation as:

```{math}
{\bf r} = \begin{pmatrix} -1/3\\1\\5\end{pmatrix} + \lambda \begin{pmatrix} 2/3\\2\\-3\end{pmatrix}
```
````

### Equation of a Plane

The vector equation requires either three points (which cannot lie all on the same line), or a point and two non-parallel directions. The vector 
form of the equation is illustrated in {numref}`vectorplane`.

In this description we carry from the origin to the known point identified by ${\bf r}_0$ and then carry along the resultant of 
vectors $\lambda{\bf v}$ and $\mu{\bf w}$, which span a parallelogram within the plane.


```{figure}  ../figures/vector-plane.gif
---
name: vectorplane
---

The position vector ${\bf r}$, shown in red, describes an arbitrary point on the plane. It can be formed by the 
sum ${\bf r}={\bf r}_0+\lambda{\bf v}+\mu{\bf w}$, where ${\bf r}_0=\overrightarrow{OP}$ is a the position vector of one of the known points 
on the line,${\bf v}=\overrightarrow{PQ}$ and ${\bf w}=\overrightarrow{PR}$ are known vectors that points in a different directions 
parallel to the plane. The arbitrary scalar parameters $\lambda$ and $\mu$ control how far along the line we carry. The animation shows how 
the plane is described as the parameters are varied.

```


Written out in scalar form, the vector equation of a plane gives :

```{math}
\lambda v_x +\mu w_x &=  x-x_0\\
\lambda v_y +\mu w_y &=  y-y_0\\
\lambda v_z +\mu w_z &=  z-z_0
```

In principle, we could find the scalar equation for a plane by eliminating the parameters $\lambda,\mu$ between these equations, which would 
lead to a relationship of the form $ax +by+cz=k$. However, we can avoid the messy algebra by obtaining the scalar equation in a different way.

We can find the scalar equation of a plane if we know the position vector $\bf r_0$ of a point on the surface, and a vector $n$ that is normal 
to the surface. Then, ${\bf r}-{\bf r}_0$ lies inside the plane, so it is perpendicular to $n$.


This gives the result that the scalar equation of a plane is given by:

```{math}
({\bf r}-{\bf r}_0)\cdot{\bf n}=0
```

where ${\bf r}_0$ is the position vector of a point in the plane, and ${\bf n}$ is a vector perpendicular to the plane.  We see this depicted 
in {numref}`scalarplane`.  

```{figure}  ../figures/scalar-plane.png
---
name: scalarplane
---
We can find the scalar equation of a plane by using a normal vector ${\bf n}$ and a position vector ${\bf r}_0$.
We have $({\bf r}-{\bf r}_0)\cdot{\bf n}=0$.
```

Expanding out the scalar product gives:

```{math}
n_x x +n_y y + n_z z = k
```

where $k=n_x \,x_0 +n_y \,y_0 + n_z\, z_0$

In the case where we are given two vectors $v,\,w$ lying inside the plane we can, of course, find a normal vector by making use of the vector product!

So, we could write:

```{math}
({\bf r}-{\bf r}_0)\cdot({\bf v}\times {\bf w})=0
```


````{admonition} Worked example
:class: seealso

Find equation of the plane going through the point $(3,\,2,\,7)$ which is perpendicular to the vector:
```{math}
\begin{pmatrix} 1\\-5\\8\end{pmatrix}
```

In the scalar form we can write $({\bf r - r_0})\cdot {\bf n} = 0$ as:
```{math}
\begin{pmatrix} x-3\\y-2\\z-7\end{pmatrix}\cdot \begin{pmatrix} 1 \\-5\\8\end{pmatrix} = 0
```
which gives the scalar equation $x - 5y + 8z = 49$

Equally in the vector form, firstly find two vectors which lie in the plane - we can use our scalar equation to find these, 
e.g. $(1,\,0,\,6)$ and $\displaystyle \Big(0,\,1,\,\frac{27}{4}\Big)$, thus we can find the vectors:
```{math}
{\bf v_1} &=  \begin{pmatrix} x-3 \\ y-2 \\ z-7 \end{pmatrix}\Bigg|_{(1,\,0,\,6)} = \begin{pmatrix} -2 \\ -2 \\ -1\end{pmatrix}\\
{\bf v_2} &=  \begin{pmatrix} x-3 \\ y-2 \\ z-7 \end{pmatrix}\Bigg|_{(0,\,1,\,27/4)} = \begin{pmatrix} -3 \\ -1 \\ -1/4 \end{pmatrix}
```

and therefore we have:
```{math}
{\bf r} = \lambda\begin{pmatrix} -2\\-2\\-1 \end{pmatrix} + \mu\begin{pmatrix} -3\\-1\\-1/4\end{pmatrix} + \begin{pmatrix} 3\\2\\7 \end{pmatrix}
```
which is just one of an infinite number of solutions!
````

### Distance between a Point and a Line

The shortest distance between a point $C$ and a line through points $A,B$ is the perpendicular distance, 
$d=|\overrightarrow{AC}_{\perp}|$, illustrated in {numref}`pointline`

```{figure}  ../figures/point_line.png
---
name: pointline
---
The shortest distance from a point $C$ to a line is given by $d=|\overrightarrow{AC}_{\perp}|$.
```

This distance is equal to the height of the parallelogram spanned by vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$, so 
it can be found using the vector product:

```{math}
d=\frac{|\overrightarrow{AB}\times\overrightarrow{AC}|}{|\overrightarrow{AB}|}
```
    
Alternatively, we could use the scalar product, since

```{math}
\overrightarrow{AC}=\overrightarrow{AC}_{\parallel}+\overrightarrow{AC}_{\perp}
```

in which the parallel component $\overrightarrow{AC}_{\parallel}$ is simply the projection of $\overrightarrow{AC}$ onto $\overrightarrow{AB}$.

````{admonition} Worked example
:class: seealso

Find the shortest distance between the point $C:(5,0,5)$ and the line that passes through the points $A:(1,1,3)$ and 
$B:(3,4,2)$.  

By using the vector product:

```{math}
\overrightarrow{AB}\times\overrightarrow{AC} &=  \begin{vmatrix}\hat{\bf x} & \hat{\bf y} & \hat{\bf z}\\2&3&-1\\4&-1&2\end{vmatrix} =
 5\hat{\bf x} - 8\hat{\bf y} - 14\hat{\bf z} \\
d &=  \frac{|\overrightarrow{AB}\times\overrightarrow{AC}|}{|\overrightarrow{AB}|}=\sqrt{\frac{285}{14}}
```

Or by using the scalar product:

```{math}
\overrightarrow{AB} &=  \begin{pmatrix}2\\3\\-1\end{pmatrix},\quad \overrightarrow{AC} =  \begin{pmatrix}4\\-1\\2\end{pmatrix} \\
|\overrightarrow{AC}_{\parallel}| &=  \overrightarrow{AC}.\frac{\overrightarrow{AB}}{|\overrightarrow{AB}|} = \frac{3}{\sqrt{14}}\\
d &=  \sqrt{|\overrightarrow{AC}|^2-|\overrightarrow{AC}_{\parallel}|^2}=\sqrt{21-\frac{3}{14}}=\sqrt{\frac{285}{14}}
```
````
   

### Shortest Distance to a Plane

The shortest distance between a point $P$ and a plane containing the point $A$ is the perpendicular distance, marked $d$ in {numref}`pointplane`


```{figure}  ../figures/point_plane.png
---
name: pointplane
---
The shortest distance from a point $P$ to a plane through $A$ is the projection of $\overrightarrow{AP}$ onto the unit normal
```


This distance is the given by projecting vector $\overrightarrow{AP}$ onto the unit normal:

```{math}
d=|\overrightarrow{AP}.\hat{{\bf n}}|
```
The shortest distance between a line and a (non-intersecting) plane, two parallel planes, or two skew lines can be found in the same way, 
by picking any point on each line/plane. The case of two skew lines is illustrated in {numref}`skews`

```{figure}  ../figures/skews.png
---
name: skews
---
The shortest distance between two skew lines illustrated.
```
   

````{admonition} Worked example
:class: seealso

Find the shortest distance between the planes:

```{math}
P_1:&&\, 3x-2y+4z=12 \\
P_2:&&\, 6x-4y+8z=8
```

Given that the two planes are parallel, with normal direction:
```{math}
{\bf n}=\left(\begin{array}{c}3\\-2\\4\end{array}\right)
```

We have to pick a point on each plane - e.g. on $P_1$ pick $A:(0,0,3)$ and on $P_2$ pick $B:(0,0,1)$, then the distance between the two planes is 
given by:

```{math}
|\overrightarrow{AB}.\hat{{\bf n}}|=\frac{\left|\begin{pmatrix}0 \\0 \\-2 \end{pmatrix}\cdot \begin{pmatrix} 3 \\ 2 \\-4 \end{pmatrix}\right|}{\sqrt{3^2+2^2+4^2}}=\frac{8}{\sqrt{29}}
```
````