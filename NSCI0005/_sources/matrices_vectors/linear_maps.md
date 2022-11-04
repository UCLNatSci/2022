# Linear Transformations

In this section we learn to understand matrices geometrically as functions, or transformations. We briefly discuss transformations in general, then specialize to matrix transformations, which are transformations that come from matrices.

## Linear Transformations

A function is a rule that takes inputs and transforms them to outputs. For example, a function $f:\mathbb{R}\rightarrow\mathbb{R}$,

$$f(x)=x^2$$

is a function that takes a real number $x$ as input and outputs another real number, the square of the input. On the other hand, the function $g:\mathbb{R}^2\rightarrow \mathbb{R}$,

$$g(x, y) = x^2 + y^3$$

is a function which maps 2-dimensional vectors $(x, y) \in \mathbb{R}^2$ to real numbers.

Functions can also be defined geometrically. For example, the following are valid function definitions:

$R_\theta:\mathbb{R}^2\rightarrow\mathbb{R}^2$ corresponding to a $\theta$ anticlockwise rotation around the origin.

$U:\mathbb{R}^2\rightarrow\mathbb{R}^2$ corresponding to a translation by the vector $\begin{pmatrix}1\\-1\end{pmatrix}$.

```{admonition} Definition

Suppose  $f:\mathbb{R}^n \rightarrow \mathbb{R}^m$ is a function such that

$$f(u + v) =f(u) + f(v)$$

and

$$f(au) = af(u)$$

for all $u, v \in\mathbb{R}^n$ and $a\in\mathbb{R}$.

Then $f$ is a **linear transformation**.
```

```{attention}
In mathematics, the words **function**, **map** and **transformation** can be used interchangeably. So 'linear function',
'linear map' and 'linear transformation' all have the same meaning.

In practice, we often prefer the word 'transformation' when we want to emphasise the geometrical nature of a function.
```

You can think of this definition as *the transformation of any linear combination of vectors is the same as the linear combination of the transformed vectors*.

Rotation is an example of a linear transformation:

- We can add vectors $u$ and $v$ and then rotate, or we can rotate $u$ and $v$ and then add, as illustrated in {numref}`linear_transformation`.
- We can scale $u$ and then rotate, or we can rotate $u$ and then scale.

```{figure} linT.gif
---
height: 300px
name: linear_transformation
---
The parallelogram rule for vector addition shows that $R_\theta(u + v) = R_\theta(u) + R_\theta(v)$.
```

```{admonition} Properties of Linear transformations

If $T:\mathbb{R}^n \rightarrow \mathbb{R}^m$ is a linear transformation, then

$$T(0) = 0$$

and for any vectors $v_1,\ldots,v_k \in \mathbb{R}^n$ and scalars $a_1,\ldots a_k \in \mathbb{R}$

$$T(a_1v_1 + \cdots + a_kv_k) = a_1T(v_1) + \cdots + a_kT(v_k).$$
```

The first property $T(0)=0$ follows from the second part of the definition of linearity. Note that here $0$ represents a *vector* and we geometrically we can think of this as saying that a linear transformation takes the origin to the origin.

```{admonition} Example
:class: tip

**1\. A non-linear transformation**

The transformation $T:\mathbb{R} \rightarrow \mathbb{R}$ defined by $T(x) = x + 1$ is *not* a linear transformation.

We can easily prove this by showing that $T$ fails to fix the origin:

$$T(0) = 0 + 1 = 1 \neq 0.$$

Therefore $T$ is not a linear transformation, even though the graph of $T(x)$ is a straight line.

**2\. A linear transformation**

Suppose $U:\mathbb{R}^2 \rightarrow \mathbb{R}^2$ be defined by $U(x) = 2x$.

$U$ is a **dilation** which doubles the size of every vector. We show that this is a linear transformation by checking the definition. Let $u, v \in \mathbb{R}^2$ and $a \in \mathbb{R}$. Then

$$U(u + v) = 2(u+v) = 2u + 2v = T(u) + T(v)$$

and

$$U(au) = 2au=a2u = aT(u).$$
```

```{exercise}
:label: q_linear_transformations

Which of the following functions are linear transformations?

1\. $T:\mathbb{R}^2\rightarrow\mathbb{R}^2$,

$$T(x) = x + \begin{pmatrix}1\\2\end{pmatrix}.$$

2\. $f:\mathbb{R}\rightarrow\mathbb{R}$,

$$f(x) = |x|.$$

3\. $U:\mathbb{R}^3\rightarrow\mathbb{R}^2$,

$$U(x, y, z) = (x, y).$$

```

## Matrix Transformations

Now let $A$ be an $(m \times n)$ matrix. Then $A$ defines a function

$$T:\mathbb{R}^n\rightarrow\mathbb{R}^m$$

where

$$T(x) = Ax.$$

In other words, $A$ defines a function which takes a vector $x \in \mathbb{R}^n$ and transforms it to a vector $Ax \in \mathbb{R}^m$. In fact, it turns out that the function defined by multiplication by a matrix is a linear transformation.

```{admonition} Theorem
If $A$ is an $(m \times n)$ matrix $A$ then the function

$$T:\mathbb{R}^n\rightarrow\mathbb{R}^m$$

defined by

$$T(x) = Ax$$

is a linear transformation which takes the vector $x \in \mathbb{R}^n$ to the vector $Ax \in \mathbb{R}^m$.
```

The proof of this follows directly from the definitions of matrix arithmetic:

$$
T(u+v) = A(u+v) = Au + Av = T(u) + T(v)\\
T(au) = A(au) = aAu = aT(u).
$$

There is essentially nothing new here, beyond the notation and a slightly different way of thinking about matrix multiplication. In the next section we will see how thinking of a matrix as a transformation allows us to picture its effect geometrically.

## Geometrical Interpretation of Matrices

Consider the matrix

$$A = \begin{pmatrix}-1 & 0\\0 & 1\end{pmatrix}$$

which defines the linear transformation $T:\mathbb{R}^2 \rightarrow \mathbb{R}^2$ defined by $T(x) = Ax$.

Given a vector $x=\begin{pmatrix}x_1\\x_2\end{pmatrix}$ we can consider the effect of the transformation $T$:

$$T(x) = A\begin{pmatrix}x_1\\x_2\end{pmatrix}=\begin{pmatrix}-1 & 0\\0 & 1\end{pmatrix}\begin{pmatrix}x_1\\x_2\end{pmatrix}=\begin{pmatrix}-x_1\\x_2\end{pmatrix}.$$

Multiplication by $A$ negates the $x_1$ co-ordinate and leaves the $x_2$ co-ordinate unchanged i.e. *it reflects over the $x_2$ axis*.

We can illustrate this by picturing the effect of the transformation on the unit co-ordinate vectors $e_1 = \begin{pmatrix}1\\0\end{pmatrix}$ and $e_2=\begin{pmatrix}0\\1\end{pmatrix}$:

$$T(e_1) = Ae_1 =\begin{pmatrix}-1 & 0\\0 & 1\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix}=\begin{pmatrix}-1\\0\end{pmatrix} $$

$$T(e_2) = Ae_2 = \begin{pmatrix}-1 & 0\\0 & 1\end{pmatrix}\begin{pmatrix}0\\1\end{pmatrix}=\begin{pmatrix}0\\1\end{pmatrix}.$$

```{figure} linear_transformations_2_0.png
---
height: 300px
name: la_fig_1
---
```

Furthermore, once we know the transformed unit vectors, we can use the linearity of the transformation to determine how *any* vector is transformed. Given a vector $x = \begin{pmatrix}x_1\\x_2\end{pmatrix}$, we can write $x$ as a sum of unit co-ordinate vectors:

$$x = \begin{pmatrix}x_1\\x_2\end{pmatrix} = x_1e_1 + x_2e_2$$

and use the linearity property to calculate the result

$$T(x) = Ax = A(x_1e_1 + x_2e_2) = x_1Ae_1 + x_2Ae_2 = x_1T(e_1) + x_2T(e_2).$$

For example, the vector $e_1 + e_2$ is transformed to $T(e_1) + T(e_2)$ so we can use this to draw the image of the unit square which has vertices $0$, $e_1$, $e_2$ and $e_1 + e_2$:

```{figure} linear_transformations_3_0.png
---
height: 300px
name: la_fig_2
---
```

:::{admonition} Example
:class: tip
Determine the geometrical effect of the transformation given by the matrix

$$A = \begin{pmatrix} \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\\ \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}}\end{pmatrix}.$$

**Solution**

$$\begin{align*}Ae_1 &= \begin{pmatrix}\frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\\\frac{1}{\sqrt{2}}& \frac{1}{\sqrt{2}}\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix} = \begin{pmatrix}\frac{1}{\sqrt{2}} \\\frac{1}{\sqrt{2}}\end{pmatrix}\\
Ae_2 &= \begin{pmatrix}\frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\\\frac{1}{\sqrt{2}}& \frac{1}{\sqrt{2}}\end{pmatrix}\begin{pmatrix}0\\1\end{pmatrix} = \begin{pmatrix}-\frac{1}{\sqrt{2}} \\\frac{1}{\sqrt{2}}\end{pmatrix}
\end{align*}
$$

```{figure} linear_transformations_6_0.png
---
height: 300px
name: la_fig_5
---
```

$A$ represent a rotation anticlockwise by $\pi/4$.
:::

```{exercise}
:label: q_geometrical_description

Describe the geometrical effect of the following matrices:

1\. $A = \begin{pmatrix}\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}}\\\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}}\end{pmatrix}$

2\. $B = \begin{pmatrix}k & 0\\0 & 1\end{pmatrix}$

3\. $C = \begin{pmatrix}1 & k\\0 & 1\end{pmatrix}$
```

## The Matrix of a Linear Transformation

In this section will learn that *all* linear transformations are matrix transformations - in other words, any function $T$ which satisfies the linearity properties can be written as a matrix $T(x) = Ax$. Before doing so, we need the following important notation.

```{admonition} Definition
The **standard coordinate vectors** in $\mathbb{R}^n$ are the $n$ vectors

$$e_1 = \begin{pmatrix}1\\0\\\vdots\\0\end{pmatrix},~e_2 = \begin{pmatrix}0\\1\\\vdots\\0\end{pmatrix},\ldots,~e_n = \begin{pmatrix}0\\0\\\vdots\\1\end{pmatrix}.$$
```

The standard coordinate vectors are useful because of the following property:

**Multiplying a matrix by the standard co-ordinate vector $e_i$ selects the $i$th column of the matrix**.

Suppose that an $(m \times n)$ matrix $A$ is composed of the $n$ column vectors $v_1, v_2, \ldots, v_n$. Then,

$$\begin{pmatrix}| & | & & | \\v_1 & v_2 & \cdots & v_n\\| & | & & |\end{pmatrix}e_i = v_i.$$

For example,

$$\begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9\end{pmatrix}\begin{pmatrix}1 \\ 0 \\ 0\end{pmatrix} =\begin{pmatrix}1 \\ 4 \\ 7\end{pmatrix}.$$

```{admonition} Theorem

Let $T:\mathbb{R}^n \rightarrow \mathbb{R}^m$ be a linear transformation. Then the $(m \times n)$ matrix

$$A = \begin{pmatrix}| & | & & | \\T(e_1) & T(e_2) & \cdots & T(e_n)\\| & | & & |\end{pmatrix}$$

is the matrix corresponding to the transformation $T$ and $T(x)=Ax$.
```

Using this theorem, we can write down the matrix of *any* linear transformation.

:::{admonition} Example
:class: tip

Determine the matrix of the linear transformation $T:\mathbb{R}^2 \rightarrow \mathbb{R}^2$ corresponding to reflection across the line $x_2 = -x_1$.

**Solution**

First, determine the transformation of the unit coordinate vectors.

```{figure} linear_transformations_4_0.png
---
height: 300px
name: la_fig_3
---
```

$$T(e_1) = \begin{pmatrix}0\\-1\end{pmatrix}\\
T(e_2) = \begin{pmatrix}-1\\0\end{pmatrix}$$

Therefore the matrix,

$$A = \begin{pmatrix}| & |\\T(e_1) & T(e_2) \\| & | \end{pmatrix} = \begin{pmatrix}0 & -1 \\-1 &0\end{pmatrix}$$

is the matrix of the transformation $T$.

:::

```{exercise}
:label: q_transformation_matrix

1\. Find the transformation of the basis vectors under reflection in the line $y=kx, k\in\mathbb{R}$, giving your answer in terms of the angle between the line and the $x$-axis. Hence, find the image of the triangle with vertices $(1,3)$, $(3,1)$, $(2,2)$ under reflection in the line $y=\sqrt{3}x$.

2\. Sketch the image of the unit square with vertices $(0,0)$, $(0,1)$, $(1,0)$, $(1,1)$ under the linear transform $\left(\begin{array}{cc}1 & 0 \\3 & 1 \\\end{array}\right)$. Try to describe this transformation in words.

```

## Rotation matrices in 2D

Suppose the linear transformation $T:\mathbb{R}^2 \rightarrow \mathbb{R}^2$ corresponds to an anticlockwise rotation by an angle $\theta$ around the origin. Then we can use trigonometry to determine the destination of the coordinate vectors under $T$:

```{figure} linear_transformations_5_0.png
---
height: 300px
name: la_fig_4
---
```

$$T(e_1) = \begin{pmatrix}\cos\theta\\\sin\theta\end{pmatrix}\\
T(e_2) = \begin{pmatrix}-\sin\theta\\\cos\theta\end{pmatrix}$$

```{admonition} Rotation Matrix
The matrix corresponding to an anticlockwise rotation by $\theta$ degrees around the origin is given by:

$$R_\theta = \begin{pmatrix}\cos\theta & -\sin\theta\\\sin\theta & \cos\theta\end{pmatrix}.$$

```

## The identity matrix

The identity matrix $I_n$ is the unique $(n \times n)$ matrix which has the property

$$I_n x = x $$

for any $x \in \mathbb{R}^n$.

The identity matrix transforms the vector $x$ to itself. It plays the same role in matrix multiplication as the number 1 does for multiplication of real numbers.

```{admonition} Definition

The **identity matrix**

$$I_n = \begin{pmatrix}1 & 0 & \cdots & 0\\0 & 1 & \cdots & 0\\\vdots & \vdots & \ddots & \vdots\\0& 0 & \cdots & 1\end{pmatrix}.$$

We usually drop the subscript $n$ when working with the identity matrix, because the order can be inferred.
```

```{exercise}
:label: q_matrix_identity

1. Calculate $I\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}$ and $\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}I$.
2. Use the identify matrix to factorise $AB+\lambda B$ where $\lambda$ is a scalar and $A,B$ are square matrices.
```



## Composition of Linear Transformations

Given two linear transformations $T:\mathbb{R}^n\rightarrow\mathbb{R}^m$ and $U:\mathbb{R}^p\rightarrow\mathbb{R}^n$, the function $T \circ U:\mathbb{R}^p\rightarrow\mathbb{R}^m$ is the composition of the two functions. That is, the function corresponding to applying first the function $U$, then the function $T$.

$$(T\circ U)(x) = T(U(x))$$

If $T$ and $U$ are linear transformations with matrices $A$ and $B$ respectively, then the product matrix $AB$ represents the composition function $(T\circ U)$.

For example, suppose matrices $A$ and $B$ represent reflection in the $y$- and $x$-axis respectively:

$$A = \begin{pmatrix}-1 &0\\0&1\end{pmatrix}, \quad B = \begin{pmatrix}1 &0\\0&-1\end{pmatrix}.$$

Then the matrix $AB$ represents a rotation by $\pi$ around the origin:

$$AB = \begin{pmatrix}-1 &0\\0&1\end{pmatrix}\begin{pmatrix}1 &0\\0&-1\end{pmatrix}=\begin{pmatrix}-1 &0\\0&-1\end{pmatrix}.$$

:::{admonition} Example
:class: tip

In {ref}`q_transformation_matrix` we reflected a set of points in the line through the origin at angle $\theta$ with the $x$-axis. An equivalent way to do this would be to rotate clockwise by angle $\theta$, reflect in the line $y=0$ and then rotate back!

```{figure} three-step.png
---
height: 300px
name: three_step
---
Reflection in a line as a three-step process. Equivalent to a reflection in the dashed line, we can 1\) rotate clockwise by angle $\theta$ 2\) reflect in the horizontal axis 3\) rotate anti-clockwise by angle $\theta$.
```

The transformation matrix for reflection in the line $y=0$ is just $\left(\begin{array}{cc}1 & 0 \\0 & -1 \\\end{array}\right)$, since $x\mapsto x $, $y\mapsto -y$.

Therefore, in matrix terms, we have

$$
\begin{align*}
A &=
\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}
\begin{pmatrix}1&0\\0&-1\end{pmatrix}
\begin{pmatrix}\cos\theta&\sin\theta\\-\sin\theta&\cos\theta\end{pmatrix}\\
&=
\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}
\begin{pmatrix}\cos\theta&\sin\theta\\\sin\theta&-\cos\theta\end{pmatrix}\\
&=
\begin{pmatrix}\cos 2\theta&\sin 2\theta\\\sin 2\theta&-\cos 2\theta\end{pmatrix}
\end{align*}
$$

which is the result given previously.

:::

```{exercise}
:label: q_transformation_composition

Use a composition of three matrix transformations to calculate the 2-d transformation matrix for a stretch, scale factor $k$ parallel to the line $y=\tan(\theta)x$.
```

## Solutions

```{solution} q_linear_transformations
1\. and 2\. Non-linear.

3\. Linear.
```

```{solution} q_geometrical_description

1\. $A = \begin{pmatrix}\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}}\\\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}}\end{pmatrix}$

$A$ *projects* vectors onto the line $y=x$.

2\. $B = \begin{pmatrix}k & 0\\0 & 1\end{pmatrix}$

$B$ stretches vectors parallel to the $x$-axis by a scale factor $k$.

3\. $C = \begin{pmatrix}1 & k\\0 & 1\end{pmatrix}$

$C$ represents a vertical *shear* by a factor $k$.
```

:::{solution} q_transformation_matrix

1\. The transformation of the basis vectors, shown in the graphic below is:

$$\left(\begin{array}{c}1 \\0 \\\end{array}\right)\mapsto\left(\begin{array}{c}\text{cos2$\theta $} \\\text{sin2$\theta $} \\\end{array}\right),\quad \left(\begin{array}{c}0 \\1\end{array}\right)\mapsto\left(\begin{array}{c}\cos\left(\frac{\pi}{2}-2\alpha\right)\\\sin\left(\frac{\pi}{2}-2\alpha\right)\end{array}\right)=\left(\begin{array}{c}\text{sin2$\theta $} \\-\text{cos2$\theta $} \\\end{array}\right)$$

```{figure} refl.png
---
width: 500px
name: reflection
---
reflection of basis vectors in the line $y=\mathrm{tan}(\theta)x$.
```

and so the transformation matrix is $T=\left(\begin{array}{cc}\cos 2\theta & \sin 2\theta \\ \sin 2\theta & -\cos 2 \theta \end{array}\right)$

For the line $y=\sqrt{3}x$ we have $\theta=\frac{\pi}{3}$, so $T=\left(\begin{array}{cc}\cos(2\frac{\pi}{3})&\sin(2\frac{\pi}{3})\\\sin(2\frac{\pi}{3})&-\cos(2\frac{\pi}{3})\end{array}\right)=\frac{1}{2}\left(\begin{array}{cc}-1 & \sqrt{3} \\\sqrt{3} & 1 \\\end{array}\right)$.

The transformation of the given points is

$$\frac{1}{2}\left(\begin{array}{cc}-1 & \sqrt{3} \\\sqrt{3} & 1 \\\end{array}\right)\left(\begin{array}{ccc}1 & 3 & 2 \\1 & 1 & 2 \\\end{array}\right)=\left(\begin{array}{ccc}-\frac{1}{2}+\frac{\sqrt{3}}{2} & -\frac{3}{2}+\frac{\sqrt{3}}{2} & -1+\sqrt{3} \\\frac{1}{2}+\frac{\sqrt{3}}{2} & \frac{1}{2}+\frac{3 \sqrt{3}}{2} & 1+\sqrt{3} \\\end{array}\right)$$

A plot of the reflection is shown below.

```{figure} triangles.png
---
width: 300px
name: reflected triangle
---
reflected triangle.
```

2\.

The image below shows the unit square under the transform $\left(\begin{array}{cc}1&0\\k&1\end{array}\right)$ as the constant $k$ is adjusted between 0 and 3.

```{figure} vshear.gif
---
width: 300px
name: vertical shear
---
vertical shear.
```

Note that we can write this transform as $\left(\begin{array}{cc}1 & 0 \\0 & 1 \\\end{array}\right)+\left(\begin{array}{cc}0 & 0 \\k & 0 \\\end{array}\right)$.

The first term is just the identity matrix that maps points to themselves, and the second term transforms the y coordinate of each point by an amount proportional to the $x$ coordinate, so points that are further from the $y$-axis are stretched more. This type of transform is known as a vertical shear.

We can achieve the same effect parallel to the horizontal axis by taking the transform (known as horizontal shear by taking the transform $\left(\begin{array}{cc}1&k\\0&1\end{array}\right)$.

:::

```{solution} q_matrix_identity

1. $I\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}=\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}I = \begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}$.
2. $AB+\lambda B = (A+\lambda I)B$.
```

```{solution} q_transformation_composition

We can describe this transformation as a rotation by $\theta$ followed by a scale 2 stretch parallel to the $x$-axis followed by a rotation by $-\theta$.

$$
\begin{align*}
A &=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}\begin{pmatrix}2&0\\0&1\end{pmatrix}\begin{pmatrix}\cos\theta&\sin\theta\\-\sin\theta&\cos\theta\end{pmatrix}\\
&=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}\begin{pmatrix}2\cos\theta&2\sin\theta\\-\sin\theta&\cos\theta\end{pmatrix}\\
&=\begin{pmatrix}k\cos^2\theta+\sin^2\theta & \frac{k-1}{2}\sin 2\theta\\\frac{k-1}{2}\sin 2\theta & k\cos^2\theta+\sin^2\theta\end{pmatrix}
\end{align*}
$$
```
