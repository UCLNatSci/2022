# Linear Algebra Problems 2

## Question 1
<!-- Yutsumura 171 -->

Define two functions $T:\mathbb{R}^2\rightarrow\mathbb{R}^2$ and $S:\mathbb{R}^2\rightarrow\mathbb{R}^2$ by

$$T\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}2x+y\\0\end{pmatrix}, S\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}x+y\\xy\end{pmatrix}.$$

Determine whether $T$, $S$, and the composite $S\circ T$ are linear transformations.

## Question 2

Let

$$A = \begin{pmatrix}1/\sqrt{2}&-1/\sqrt{2}\\-1/\sqrt{2}&1/\sqrt{2}\end{pmatrix}.$$

1\. By reducing to echelon form, calculate the null space of $A$.

2\. Describe the geometrical effect of linear transformation defined by $A$. Sketch the null space and the image of the standard co-ordinate vectors $e_1$ and $e_2$ on the same graph.

3\. Repeat for the matrix $B$.

$$B = \begin{pmatrix}1/\sqrt{2}&-1/\sqrt{2}&0\\-1/\sqrt{2}&1/\sqrt{2}&0\\0&0&1\end{pmatrix}.$$

## Question 3

1\. Draw a triangle $ABC$ with vertices $A(2,1), B(7,1)$ and $C(2,4)$.

2\. Find the image of $ABC$ under the transformation defined by the matrix $M$ and draw the image on the same diagram.

$$M = \begin{pmatrix}1 &-1\\1 &1\end{pmatrix}.$$

3\. The transformation is a rotation followed by a scaling. Calculate the angle of rotation and the scale factor of the scaling.

## Question 4

1\. Write down the 2D transformation matrix $M$ for a reflection in the line $y=\sqrt{3}x$.

2\. This transform is followed by another linear transform represented by matrix $N$. The composite transform $M$ followed by $N$ is given by

$$T=\frac{1}{2}\left(\begin{array}{cc}-1+2\sqrt{3} & 2+\sqrt{3}\\ \sqrt{3} & 1\end{array}\right).$$

Use this information to calculate the transformation matrix $N$.

## Question 5

Identify the set of points in the plane that are invariant (do not change) under the transformation matrix

$$A=\begin{pmatrix}-\frac{1}{2}&\frac{\sqrt{3}}{2}\\\frac{\sqrt{3}}{2}&\frac{1}{2}\end{pmatrix}.$$

What transformation is represented by this matrix?

## Question 6

Let $T$ be a linear transformation from $\mathbb{R}^3$ to $\mathbb{R}^3$ satisfying

$$T(\begin{pmatrix}1\\1\\1\end{pmatrix})=\begin{pmatrix}1\\0\\1\end{pmatrix}, T(\begin{pmatrix}2\\3\\5\end{pmatrix})=\begin{pmatrix}0\\2\\1\end{pmatrix}, T(\begin{pmatrix}0\\1\\2\end{pmatrix})=\begin{pmatrix}1\\0\\0\end{pmatrix}.$$

Find the $(3 \times 3)$ matrix for $T$.

## Question 7

Determine whether the following statements are true or false. If true, provide a justification. If false, provide a counterexample.

1. If $AB$ = $B$ then $A$ is the identity matrix.
2. If the coefficent matrix $A$ of the system $Ax=b$ is invertible, then the system has infinitely many solutions.
3. If $A$ is invertible, then $ABA^{-1}=B$.
4. If $x_1=0, x_2=0, x_3=1$ is a solution to a homogeneous system of linear equations, then the system has infinitely many solutions.

## Question 8

Let

$A = \begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix}$, $B = \begin{pmatrix}\frac{\sqrt{3}}{2}&-\frac{1}{2}\\\frac{1}{2}&\frac{\sqrt{3}}{2}\end{pmatrix}$ and $C = \begin{pmatrix}\frac{7}{8}&-\frac{3\sqrt{3}}{8}\\-\frac{3\sqrt{3}}{8}&\frac{13}{8}\end{pmatrix}$.

1\. Calculate $Ae_1$ and $Ae_2$, sketch the image of the unit square under the linear transformation $x \mapsto Ax$ and describe its geometrical effect.

2\. Show that $B$ is a rotation matrix, determine its angle of rotation $\theta$, and write down the matrix $B^{-1}$.

3\. Show that

$$C = BAB^{-1}$$

and describe the linear transformation  defined by $C$.

4\. Calculate $A^2$ and write down a formula for $C^2$ in terms of matrices $A^2$ and $B$.

5\. *The punchline*. How would you calculate $C^{10}$ and what transformation does it represent?


<!--

## Yutsumura 368 or Problem 324



## Yutsumura Problem 44


## Projection matrix

-->
