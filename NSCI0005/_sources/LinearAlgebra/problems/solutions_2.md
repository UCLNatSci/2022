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

![](q2_1.jpg)


$A$ represents a projection onto the line $x_1=-x_2$ followed by a stretch $\times \sqrt{2}$ along the line $x_1 = -x_2$.

Alternatively, $A$ represents a dilation (equal stretch in all directions) by $\sqrt{2}$ follwed by a projection onto the line $x_1=-x_2$.



2\. Reducing $A$ to reduced row echelon form,

$$\begin{pmatrix}1&-1&0\\0&0&1\\0&0&0\end{pmatrix},$$

we find that the null space of $A$ is $t\begin{pmatrix}1\\1\\0\end{pmatrix}, t\in \mathbb{R}$.

$$
Ae_1 = \begin{pmatrix}1/\sqrt{2}\\-1/\sqrt{2}\\0\end{pmatrix}, Ae_2 = \begin{pmatrix}-1/\sqrt{2}\\1/\sqrt{2}\\0\end{pmatrix}, Ae_3 = \begin{pmatrix}0\\0\\1\end{pmatrix}
$$

### Question 1

$M=\left(\begin{array}{cc}\cos{2\theta}&\sin{2\theta}\\ \sin{2\theta}&-\cos{2\theta}\end{array}\right)$ with $\theta=\tan^{-1}{\sqrt{3}}=\frac{\pi}{3}$

gives

$$M=\frac{1}{2}\left(\begin{array}{cc}-1&\sqrt{3}\\ \sqrt{3}&1\end{array}\right)$$

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
