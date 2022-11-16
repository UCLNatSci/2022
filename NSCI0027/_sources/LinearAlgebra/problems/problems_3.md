# Linear Algebra Problems 3

## Question 1

Use row operations to verify the $3$ by $3$ 'Vandermonde determinant'

$$\begin{vmatrix}1 & a & a^2\\1 & b & b^2\\1 & c & c^2\end{vmatrix} = (b-a)(c-a)(c-b).$$

## Question 2

<!-- Strang Linear Algebra and its Applications Ch4 Q29 -->

A box has edges from $(0,0,0)$ to $(3,1,1)$, $(1,3,1)$ and $(1,1,3)$. Find its volume and find the area of each parallelogram face.

## Question 3

*[Corrected 24/02/22]*.

<!-- https://metric.ma.ic.ac.uk/metric_public/matrices/eigenvalues_and_eigenvectors/eigenvalues2.html -->

Let

$$M = \begin{pmatrix}-2 &−2& 4 \\−4 &1 &2 \\2 &2& 5\end{pmatrix}.$$

1. Show that $\lambda_1=3$ is an eigenvalue and find its corresponding eigenspace.
2. Find the other two eigenvalues and their corresponding eigenspaces.
3. What is the geometrical effect of $M$ on vectors in $\mathbb{R}^3$?

## Question 4

Find the null space and all four eigenvalues and corresponding eigenvectors for the following matrices:

$A = \begin{pmatrix}1&1&1&1\\1&1&1&1\\1&1&1&1\\1&1&1&1\end{pmatrix}$ and $B = \begin{pmatrix}0&1&0&1\\1&0&1&0\\0&1&0&1\\1&0&1&0\end{pmatrix}$.

## Question 5

<!-- https://www.sheffield.ac.uk/polopoly_fs/1.892866!/file/eignval_eignvec_basics_HELM.pdf -->

If $\lambda_1, \ldots, \lambda_n$ are the eigenvalues of a matrix $A$, prove the following:

1. $A^T$ has eigenvalues $\lambda_1, \ldots, \lambda_n$.
2. If $A$ is upper triangular, then its eigenvalues are exactly the main diagonal entries.
3. The inverse matrix $A^{-1}$ has eigenvalues $\frac{1}{\lambda_1}, \ldots, \frac{1}{\lambda_n}$.
4. The matrix $A-kI$ has eigenvalues $\lambda_1-k, \ldots, \lambda_n-k$.
5. The matrix $A^2$ has eigenvalues $\lambda_1^2, \ldots, \lambda_n^2$.
6. The matrix $A^k$ where $k \in \mathbb{N}$ has eigenvalues has eigenvalues $\lambda_1^k, \ldots, \lambda_n^k$.

## Question 6

*[Correction 24/02/22: $P = \sout{u^Tu}5 uu^T$*.
<!-- Strang Linear Algebra and its Applications Ch5 Q23 -->

Let

$$u = \begin{pmatrix}\frac{1}{6}\\\frac{1}{6}\\\frac{3}{6}\\\frac{5}{6}\end{pmatrix}.$$

1. Calculate the $4 \times 4$ matrix $P = uu^T$.
2. Without further calculation, explain how you know that $P$ is not invertible.
3. Show that $u$ is an eigenvector of $P$ and calculate its eigenvalue.
4. If $v$ is perpendicular to $u$ show that $Pv = 0$.
5. Find three independent eigenvectors of $P$ with eigenvalue $\lambda = 0$

## Question 7

<!-- yutsumura 593 -->

Given a nonzero vector $v_0 \in \mathbb{R}^3$ we define a function $T:\mathbb{R}^3 \rightarrow \mathbb{R}^3$ by

$$T(x) = v_0 \times x$$

where $\times$ represents the vector (cross) product.

1. Show that $T:\mathbb{R}^3\rightarrow \mathbb{R}^3$ is a linear transformation.
2. Determine the eigenvalues and eigenvectors of $T$.


## Question 8

1. Write down the matrix for an anticlockwise $\pi/2$ rotation around the origin.

2. Calculate the characteristic polynomial and solve it to find two complex-valued eigenvalues.

3. Find the two corresponding complex-valued eigenvectors.

## Question 9

<!-- yutsumura 550 -->

Let

$$A = \begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}$$

for some $\theta \in \mathbb{R}$.

1. Find the characteristic polynomial of $A$.
2. Find the eigenvalues of $A$.
3. Determine the corresponding eigenvectors.

## Question 10

Define $K_n$ to be the matrix with $2$s on the main diagonal and $-1$s on the subdiagonal and superdiagonal. $K_4$ is shown below:

$$K_4 = \begin{pmatrix}2&-1&0&0\\-1&2&-1&0\\0&-1&2&-1\\ 0&0&-1&2\end{pmatrix}.$$

Show that $\det(K_n) = n + 1$ using the following two different methods:

1. Using row operations to reduce the matrix to a triangular matrix [the first row operation is $r_2\rightarrow r_2+\frac{1}{2}r_1$ which leaves $r_2 = (0, \frac{3}{2}, -1, 0, \ldots$). Continue the row operations and spot the pattern].
2. Using the cofactor formula [start by writing $\det(K_n)$ in terms of $\det(K_{n-1})$ and $\det(K_{n-2})$]

## Question 11

Find $(2 \times 2)$ matrices with

1. Two distinct eigenvalues and two independent eigenvectors.
2. Two distinct eigenvalues but only one independent eigenvector.
3. A single eigenvalue and two independent eigenvectors.
4. A single eigenvalue with one independent eigenvector.

[Two vectors are dependent if they are multiples of each other.]

[One of these is impossible! Which, and why?]
