# Linear Algebra Answers 2

## Question 1

We will prove that $T$ and $S\circ T$ are linear transformations, but $S$ is not.

To prove that $T$ is a linear transformation, let $x, y \in \mathbb{R}^2$ where

$$x = \begin{pmatrix}x_1\\x_2\end{pmatrix}, y = \begin{pmatrix}y_1\\y_2\end{pmatrix}.$$

Then

$$
\begin{align*}T(x+y) &= T\left(\begin{pmatrix}x_1\\x_2\end{pmatrix}+\begin{pmatrix}y_1\\ y_2\end{pmatrix}\right) = T\left(\begin{pmatrix}x_1+y_1\\x_2+y_2\end{pmatrix}\right)\\
&=\begin{pmatrix}2(x_1+y_1)+x_2+y_2\\0\end{pmatrix}=\begin{pmatrix}2x_1+x_2\\0\end{pmatrix} + \begin{pmatrix}2y_1+y_2\\0\end{pmatrix}\\
&= T(x) + T(y).
\end{align*}$$

Next, for any $a\in \mathbb{R}$,

$$
\begin{align*}
T(ax) &= T\left(a\begin{pmatrix}x_1\\x_2\end{pmatrix}\right)=T\left(\begin{pmatrix}ax_1\\ax_2\end{pmatrix}\right)\\
&=\begin{pmatrix}2ax_1+ax_2\\0\end{pmatrix}=a\begin{pmatrix}2x_1+x_2\\0\end{pmatrix}\\
&=aT(x).
\end{align*}$$

To prove that $S$ is not a linear transformation, it is sufficient to find two vectors $u$ and $v$ such that

$$S(u + v) \neq S(u) + S(v).$$

Let

$$u = \begin{pmatrix}1\\0\end{pmatrix}, v=\begin{pmatrix}0\\1\end{pmatrix},$$

then

$$S(u+v) = S\left(\begin{pmatrix}1\\0\end{pmatrix}+\begin{pmatrix}0\\1\end{pmatrix}\right)=S\left(\begin{pmatrix}1\\1\end{pmatrix}\right)=\begin{pmatrix}2\\1\end{pmatrix}$$

and

$$S(u) + S(v) = S\left(\begin{pmatrix}1\\0\end{pmatrix}\right)+S\left(\begin{pmatrix}0\\1\end{pmatrix}\right)=\begin{pmatrix}1\\0\end{pmatrix}+\begin{pmatrix}1\\0\end{pmatrix}=\begin{pmatrix}2\\0\end{pmatrix}.$$

Therefore

$$S(u+v)\neq S(u)+S(v).$$

To prove that $S\circ T$ is linear, let

$$x = \begin{pmatrix}x_1\\x_2\end{pmatrix}.$$

$$S\circ T(x) = S\left(T\left(\begin{pmatrix}x_1\\x_2\end{pmatrix}\right)\right) = S\left(\begin{pmatrix}2x_1+x_2\\0\end{pmatrix}\right)=\begin{pmatrix}2x_1+x_2\\0\end{pmatrix}=T(x).$$

Therefore, $S \circ T = T$. We have already shown that $T$ is a linear transformation, therefore $S \circ T$ is a linear transformation.

## Question 2

1\. Reducing $A$ to reduced row echelon form,

$$\begin{pmatrix}1&-1\\0&0\end{pmatrix},$$

we find that the null space of $A$ is $t\begin{pmatrix}1\\1\end{pmatrix}, t\in \mathbb{R}$.

The images of the coordinate vectors under the transformation $x \mapsto Ax$ are:

$$
Ae_1 = \begin{pmatrix}1/\sqrt{2}\\-1/\sqrt{2}\end{pmatrix}, Ae_2 = \begin{pmatrix}-1/\sqrt{2}\\1/\sqrt{2}\end{pmatrix}
$$

```{image} q2_1.jpg
:width: 300px
:align: center
```

$A$ represents a projection onto the line $x_1=-x_2$ followed by a stretch $\times \sqrt{2}$ along the line $x_1 = -x_2$.

Alternatively, $A$ represents a dilation (equal stretch in all directions) by $\sqrt{2}$ follwed by a projection onto the line $x_1=-x_2$.

2\. Reducing $A$ to reduced row echelon form,

$$\begin{pmatrix}1&-1&0\\0&0&1\\0&0&0\end{pmatrix},$$

we find that the null space of $A$ is $t\begin{pmatrix}1\\1\\0\end{pmatrix}, t\in \mathbb{R}$.

$$
Ae_1 = \begin{pmatrix}1/\sqrt{2}\\-1/\sqrt{2}\\0\end{pmatrix}, Ae_2 = \begin{pmatrix}-1/\sqrt{2}\\1/\sqrt{2}\\0\end{pmatrix}, Ae_3 = \begin{pmatrix}0\\0\\1\end{pmatrix}
$$

```{image} q2_2.jpg
:width: 300px
:align: center
```

$A$ represents a projection onto the plane $t_1\begin{pmatrix}1\\-1\\0\end{pmatrix} + t_2\begin{pmatrix}0\\0\\1\end{pmatrix}$ followed by a stretch $\times \sqrt{2}$ along the line $t_1\begin{pmatrix}1\\-1\\0\end{pmatrix}$.

## Question 3

```{image} q3.jpg
:width: 300px
:align: center
```

M represents an anticlockwise rotation $\pi/4$ followed by a scaling (dilation) $\times \sqrt{2}$.

## Question 4


Using the special triangles with sides $1, 1/2, \sqrt{3}/2$ and internal angles $\pi/2, \pi/3, \pi/6$ as in the image below,

```{image} q4.jpg
:width: 500px
:align: center
```

or using the formula in the notes

$M=\left(\begin{array}{cc}\cos{2\theta}&\sin{2\theta}\\ \sin{2\theta}&-\cos{2\theta}\end{array}\right)$ with $\theta=\tan^{-1}{\sqrt{3}}=\frac{\pi}{3}$

gives

$$M=\frac{1}{2}\left(\begin{array}{cc}-1&\sqrt{3}\\ \sqrt{3}&1\end{array}\right).$$

$$\det{M}=\left(\frac{1}{2}\right)^2(-1-3)=-1$$

so

$$M^{-1}=-\frac{1}{2}\left(\begin{array}{cc}1&-\sqrt{3}\\ -\sqrt{3}&-1\end{array}\right)$$

$$T=NM$$

(transform $M$ is applied first).

Therefore

$$N=TM^{-1}=\frac{1}{4}\left(\begin{array}{cc}-1+2\sqrt{3} & 2+\sqrt{3}\\ \sqrt{3} & 1\end{array}\right)\left(\begin{array}{cc}-1&\sqrt{3}\\ \sqrt{3}&1\end{array}\right)$$

$$=\frac{1}{4}\left(\begin{array}{cc}1-2\sqrt{3}+2\sqrt{3} & -\sqrt{3}+6+2+\sqrt{3}\\-\sqrt{3}+\sqrt{3} & 3+1\end{array}\right)$$

$$=\left(\begin{array}{cc}1&2\\0&1\end{array}\right)$$

This is a shear parallel to the x-axis, scale factor 2.

## Question 5

A vector $x$ is invariant under the transformation $x \mapsto Ax$ if it satisfies the equation

$$Ax = x.$$

(Alternatively, we say that $A$ 'fixes' $x$).

This equation is *not* of the form $Ax = b$ since $x$ appears on both sides of the equation. We need to rearrange and factorise the equation to get $x$ on its own.

$$Ax - x = 0.$$

we are not allowed to write $(A-1)x = 0$ since we cannot subtract a number from a matrix. Instead, use the identity matrix:

$$Ax - Ix = (A-I)x = 0.$$

We just need to find the null space of the matrix $A-I$.

$$A - I = \frac{1}{2}\begin{pmatrix}-3&\sqrt{3}\\\sqrt{3}&-1\end{pmatrix}.$$  

Reducing to echelon form:

$$\begin{pmatrix}1&-\frac{1}{\sqrt{3}}\\0&0\end{pmatrix}.$$

The values of $x$ invariant under $x \mapsto Ax$ is the null space of $A-I$ which is $t\begin{pmatrix}\frac{1}{\sqrt{3}}  \\1\end{pmatrix}, t \in \mathbb{R}$.

The matrix represents a reflection in the line $y = \sqrt{3}x$.

## Question 6

Let $A$ be the matrix representing the linear transformation $T$.

Then

```{math}
:label: eqn_s2_q6
A\begin{pmatrix}1\\1\\1\end{pmatrix} = \begin{pmatrix}1\\0\\1\end{pmatrix}, A\begin{pmatrix}2\\3\\5\end{pmatrix} = \begin{pmatrix}0\\2\\1\end{pmatrix}, A\begin{pmatrix}0\\1\\2\end{pmatrix} = \begin{pmatrix}1\\0\\0\end{pmatrix}.
```

**Method 1**

Writing

$$A = \begin{pmatrix}a_{11}&a_{12}&a_{13}\\a_{21}&a_{22}&a_{23}\\a_{31}&a_{32}&a_{33}\end{pmatrix}$$

We have three linear equations for each of the matrix equations above:

$$
\begin{align*}
a_{11} + a_{12} + a_{13} &= 1\\
a_{21} + a_{22} + a_{23} &= 0\\
a_{31} + a_{32} + a_{33} &= 1\\
\\
2a_{11} + 3a_{12} + 5a_{13} &= 0\\
2a_{21} + 3a_{22} + 5a_{23} &= 2\\
2a_{31} + 3a_{32} + 5a_{33} &= 1\\
\\
a_{12} + 2a_{13} &= 1\\
a_{22} + 2a_{23} &= 0\\
a_{32} + 2a_{33} &= 0\\
\end{align*}
$$

By regrouping equations we arrive at 3 sets of simultaneous equations:

$$
\begin{align*}
a_{11} + a_{12} + a_{13} &= 1\\
2a_{11} + 3a_{12} + 5a_{13} &= 0\\
a_{12} + 2a_{13} &= 1\\
\\
a_{21} + a_{22} + a_{23} &= 0\\
2a_{21} + 3a_{22} + 5a_{23} &= 2\\
a_{22} + 2a_{23} &= 0\\
\\
a_{31} + a_{32} + a_{33} &= 1\\
2a_{31} + 3a_{32} + 5a_{33} &= 1\\
a_{32} + 2a_{33} &= 0\\
\end{align*}
$$

Then writing in matrix form:

$$
\begin{pmatrix}1&1&1\\2&3&5\\0&1&2\end{pmatrix}\begin{pmatrix}a_{11}\\a_{12}\\a_{13}\end{pmatrix}=\begin{pmatrix}1\\0\\1\end{pmatrix}\\
\begin{pmatrix}1&1&1\\2&3&5\\0&1&2\end{pmatrix}\begin{pmatrix}a_{21}\\a_{22}\\a_{23}\end{pmatrix}=\begin{pmatrix}0\\2\\0\end{pmatrix}\\
\begin{pmatrix}1&1&1\\2&3&5\\0&1&2\end{pmatrix}\begin{pmatrix}a_{31}\\a_{32}\\a_{33}\end{pmatrix}=\begin{pmatrix}1\\1\\0\end{pmatrix}
$$

Which is the same as:

$$
\begin{pmatrix}1&1&1\\2&3&5\\0&1&2\end{pmatrix}\begin{pmatrix}a_{11}&a_{12}&a_{13}\\a_{21}&a_{22}&a_{23}\\a_{31}&a_{32}&a_{33}\end{pmatrix}^T = \begin{pmatrix}1&0&1\\0&2&1\\1&0&0\end{pmatrix}\\
$$

Let

$$M = \begin{pmatrix}1&1&1\\2&3&5\\0&1&2\end{pmatrix}, B = \begin{pmatrix}1&0&1\\0&2&1\\1&0&0\end{pmatrix}$$

then

$$MA^T = B$$

so

$$A^T = M^{-1}B$$

Using any method to calculate the inverse (e.g. cofactor expansion),

$$M^{-1} = \begin{pmatrix}-1&1&-2\\4&-2&3\\-2&1&-1\end{pmatrix}$$

therefore

$$A^T = \begin{pmatrix}-1&1&-2\\4&-2&3\\-2&1&-1\end{pmatrix}\begin{pmatrix}1&0&1\\0&2&1\\1&0&0\end{pmatrix} = \begin{pmatrix}-3&2&0\\7&-4&2\\-3&2&-1\end{pmatrix}$$

$$A = \begin{pmatrix}-3&7&-3\\2&-4&2\\0&2&-1\end{pmatrix}$$

**Method 2**

Notice that we can rewrite {eq}`eqn_s2_q6` as a single matrix equation:

$$A\begin{pmatrix}1&2&0\\1&3&5\\1&5&2\end{pmatrix}=\begin{pmatrix}1&0&1\\0&2&0\\1&1&0\end{pmatrix}$$

so

$$AM^T=B^T$$

which we can solve by calculating $M^{-1}$ as before

$$A = B(M^T)^{-1} = B^T(M^{-1})^T.$$

## Question 7

1. False. For example set $B=0$ then $AB=B$ for any matrix $A$.
2. False. If $A$ in invertible then there is a single solution $x = bA^{-1}$.
3. False. For example $A$ is any nonzero rotation and $B$ is a reflection.
4. True. If $x$ is a solution to $Ax = 0$ then so is $tx$ for any $t \in \mathbb{R}$.

## Question 8

1\.

$$Ae_1 = \begin{pmatrix}\frac{1}{2}\\0\end{pmatrix}, Ae_2 = \begin{pmatrix}0\\2\end{pmatrix}$$

$A$ represents a stretch $\times \frac{1}{2}$ along the $x$-axis and $\times 2$ along the $y$-axis.

```{image} q8.jpg
:width: 200px
:align: center
```

2\.

$$B = \begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}$$

where $\theta = \pi/3$. (You can show this geometrically using special triangles).

$B^{-1}$ is a rotation $\theta = -\pi/3$

$$B^{-1} = \begin{pmatrix}\cos\theta&\sin\theta\\-\sin\theta&\cos\theta\end{pmatrix} = \begin{pmatrix}\frac{\sqrt{3}}{2}&\frac{1}{2}\\-\frac{1}{2}&\frac{\sqrt{3}}{2}\end{pmatrix}.$$

3\. Showing $C=BAB^{-1}$ is just a case of multiplying out the matrices on the right hand side of the equation. $C$ represents a stretch $\times \frac{1}{2}$ along the line $y=(\tan\theta)x$ and $\times 2$ along the line perpendicular to $y=(\tan\theta)x$.

4\.

$$A^2 = \begin{pmatrix}\frac{1}{4}&0\\0&4\end{pmatrix},$$

$$C^2 = \left(BAB^{-1}\right)^2 = BAB^{-1}BAB^{-1} = BA^2B^{-1}.$$

5\.

$$C^{10} = \left(BAB^{-1}\right)^{10} = BAB^{-1}BAB^{-1} \ldots BAB^{-1} = BA^{10}B = B\begin{pmatrix}\frac{1}{2^{10}}&0\\0&2^{10}\end{pmatrix}B^{-1}.$$

$C^{10}$ represents a stretch $\times \frac{1}{2^{10}}$ along the line $y=(\tan\theta)x$ and $\times 2^{10}$ along the line perpendicular to $y=(\tan\theta)  x$.
