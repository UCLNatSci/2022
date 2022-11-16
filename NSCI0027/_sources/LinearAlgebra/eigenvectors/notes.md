# Eigenvalues and Eigenvectors

## Eigenvalues and Eigenvectors

In this section we will study on of the most important concepts in linear algebra.

```{admonition} Eigenvalues and Eigenvectors
Let $A$ be a square matrix, $v$ a non-zero vector and $\lambda$ a real number such that

$$Av = \lambda v .$$

Then $\lambda$ is an **eigenvalue** and $v$ is an **eigenvector** of the matrix $A$.
```

'Eigen' is a German word which roughly translates into English as 'self' or 'own'. An eigenvector is a vector which is transformed to a multiple of itself by the matrix $A$.

It is not obvious how to calculate the eigenvalues and eigenvectors of a given matrix, and this is a problem we will return to later. However, it is easy to check whether a given vector is an eigenvector simply by applying the definition.


```{admonition} Example
:class: tip

Show that $v = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$ is an eigenvector of the matrix $A = \begin{pmatrix} 2 & 2 \\ -4 & 8 \end{pmatrix}$ and calculate its corresponding eigenvalue.

**Answer**

$$Av = \begin{pmatrix} 2 & 2 \\ -4 & 8 \end{pmatrix}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix}4 \\ 4\end{pmatrix} = 4v$$

Therefore, $v$ is an eigenvalue of $A$ with eigenvalue $\lambda = 4$.
```

```{attention}
1. Eigenvectors and eigenvalues are only defined for *square* matrices.
2. Eigenvectors are never zero but eigenvalues may be zero.
```

```{exercise}
:label: q_check_eigenvector
Let the matrix $A = \begin{pmatrix}0 & 6 & 8 \\ \frac{1}{2} & 0 &0 \\ 0 & \frac{1}{2} & 0\end{pmatrix}$ and vectors $v_1 = \begin{pmatrix} 16 \\ 4 \\ 1 \end{pmatrix}$, $v_2 = \begin{pmatrix} 2 \\ 2 \\ 2 \end{pmatrix}$.

1. Which of $v_1$ and $v_2$ is an eigenvector of $A$?
2. Determine its corresponding eigenvalue.

```
## Eigenspaces

If $v$ is an eigenvector of $A$, it is easy to show that any scalar multiple $cv$ is also an eigenvector:

$$A(cv) = cAv = c\lambda v = \lambda(cv)$$

Thus, geometrically we can picture an eigenvector as a straight line through the origin that is left unchanged by the linear transformation corresponding to the matrix.

```{admonition} Definition
Let $A$ be a square matrix and $\lambda$ an eigenvalue of $A$. Then the **eigenspace** of $A$ corresponding to eigenvalue $\lambda$ is the set of vectors $v$ such that

$$Av = \lambda v.$$

```

```{admonition} Example
:class: tip
Determine the eigenvalues and corresponding eigenspaces of a $\times 3$ dilation (scaling).

**Solution**

A $\times 3$ dilation transforms each vector $x\in \mathbb{R}^n$ to $3x$. Therefore *every* nonzero vector is an eigenvector with eigenvalue $3$.

Therefore $A$ has a single eigenvalue $\lambda = 3$ with eigenspace $\mathbb{R}^n$. Note that this is true regardless of the value of $n$!
```

### Calculating Eigenspaces

We have seen how to check if a given vector is an eigenvector of a square matrix $A$. It is then easy to find its corresponding eigenvalue.

Next we will learn how can to check whether a given real number is an eigenvalue of $A$ and to find its corresponding eigenvector. This is slightly more complicated because there may be multiple eigenvectors corresponding to a single eigenvalue.

Now suppose $A$ is an ($n \times n$) square matrix and $\lambda$ a real number. If $\lambda$ is an eigenvalue then there exists a non-zero vector $v$ which solves the following equation:

$$
Av = \lambda v.
$$ (eqn_eigenvector)

We would like to solve this for $v$. To see how this is possible, let's first examine a concrete example.

```{admonition} Example
Suppose we have an eigenvalue $\lambda$ of the matrix $A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}$. Then an eigenvector of $A$ is a non-zero vector $v = \begin{pmatrix} x_1 \\ x_2 \end{pmatrix}$ which satisfies

\begin{align*} Av &= \lambda v\\
\begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}\begin{pmatrix}x_1 \\ x_2\end{pmatrix} &= \lambda \begin{pmatrix}x_1 \\ x_2\end{pmatrix}.
\end{align*}

This translates to the linear system of equations

\begin{alignat*}{3}
x_1 & {}+{} & 2x_2 & {}={} &  \lambda x_1  \\
3x_1 & {}+{} & 4x_2 & {}={} &  \lambda x_2
\end{alignat*}
\begin{alignat*}{3}
(1-\lambda)x_1 & {}+{} & 2x_2 & {}={} &  0  \\
3x_1 & {}+{} & (4-\lambda)x_2 & {}={} &  0
\end{alignat*}
which is the same as the matrix equation

$$\begin{pmatrix} 1-\lambda & 2 \\ 3 & 4-\lambda \end{pmatrix}\begin{pmatrix}x_1 \\ x_2\end{pmatrix} = \begin{pmatrix}0 \\ 0\end{pmatrix}$$

$$\left(A-\lambda I\right)v = 0$$
```

Thus, introducing the identity matrix $I$ allows us to rearrange {eq}`eqn_eigenvector`:

$$\left(A - \lambda I\right)v = 0.$$

Remember that this is an equation of vectors so the $0$ on the right hand side is a zero vector of length $n$.

Notice that this equation is of the form matrix times vector equals vector - and we already know how to solve such an equation, for example by using row reduction. If any solutions exist then they are eigenvectors of $A$ and $\lambda$ a corresponding eigenvalue.

```{admonition} Calculating Eigenvectors
Given a square matrix $A$ and real number $\lambda$, If

$$\left(A - \lambda I\right)v=0$$

has non-trivial solutions then $\lambda$ is an eigenvalue of $A$ and the general solution is the eigenspace of $A$ corresponding to $\lambda$.
```

```{admonition} Example
:class: tip
For each of the numbers $λ = 1, 3$, decide if $\lambda$ is an eigenvalue of the matrix

$$A = \begin{pmatrix}2 & -4 \\ -1 & -1\end{pmatrix}$$ (eqn_eigenvector_example)

and calculate the corresponding eigenspace.

**Answer**

$\lambda = 1$ is an eigenvalue of $A$ if the equation $\left(A - I\right)v = 0$ has non-zero solutions.

$$A - I = \begin{pmatrix}2 & -4 \\ -1 & -1\end{pmatrix} - \begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}1 & -4 \\ -2 & -1\end{pmatrix}$$

$A - I$ has determinant $6$ and is therefore invertible and $\mathrm{Nul}\left(A-I\right) = 0$.

Therefore there are no non-zero solutions to $\left(A - I\right)v = 0$ and we conclude that $1$ is not an eigenvalue of $A$.

$\lambda = 3$ is an eigenvalue of $A$ if the equation $\left(A - 3I\right)v = 0$ has non-zero solutions.

$$A - 3I = \begin{pmatrix}2 & -4 \\ -1 & -1\end{pmatrix} - 3\begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}-1 & -4 \\ -1 & -4\end{pmatrix}$$

The reduced row echelon form of this matrix is

$$\begin{pmatrix}1 & 4 \\ 0 & 0\end{pmatrix}$$

and the general solution to $\left(A - 3I\right)v=0$ is

$$ v = \begin{pmatrix} x_1 \\ x_2\end{pmatrix} = x_2\begin{pmatrix}-4  \\ 1\end{pmatrix}.$$

Therefore $\lambda = 3$ is an eigenvalue with corresponding eigenvector $v = \begin{pmatrix}-4  \\ 1\end{pmatrix}$.

```

```{exercise}
:label: q_check_eigenvalue

Show that $\lambda=-2$ is an eigenvalue of the matrix {eq}`eqn_eigenvector_example` and calculate its eigenvector.
```
## The Characteristic Polynomial

In the previous section we discussed how to decide whether a given number
$\lambda$ is an eigenvalue of a matrix, and if so, how to find all of the associated eigenvectors. In this section, we will give a method for computing all of the eigenvalues of a matrix.

We saw that $\lambda$ is an eigenvalue of a matrix $A$ if and only the equation $\left(A - \lambda I\right)=0$ has non-zero solutions. But recall that this equation only has non-zero solutions if and only if the the matrix $A - \lambda I$ is invertible, which is the case if and only if its determinant is zero. Therefore, we have the following important theorem.

```{admonition} Theorem
Given a square matrix $A$, a real number $\lambda$ is an eigenvalue of $A$ if an only if

$$\mathrm{det}\left(A - \lambda I\right) = 0.$$

The equation $f(\lambda)=\mathrm{det}\left(A - \lambda I\right)$ is called the **characteristic polynomial** of $A$.
```

## Calculating Eigenvalues

We now have the necessary tool to calculate the eigenvalues and eigenvectors of any square matrix $A$.

```{admonition} Calculating Eigenvalues

Let $A$ be a square matrix. To determine the eigenvalues and eigenvectors of $A$,

1. Calculate the characteristic polynomial $f(\lambda)=\mathrm{det}\left(A - \lambda I\right)$ using the rules for calculating determinants.
2. Solve the degree-$n$ polynomial equation $f(\lambda) = 0$. Each solution $\lambda$ is an eigenvalue of $A$.
3. Determine the corresponding eigenspaces using row-reduction on the matrix $A-\lambda I$ for each eigenvalue $\lambda$.
```

For $(2\times 2)$ matrices, we can always following procedure directly to find the eigenvalues and eigenvectors.

```{admonition} Example: Eigenvalues and Eigenvectors of a $(2\times 2)$ Matrix
:class: tip

Find the eigenvalues and eigenvectors of the matrix

$$A = \begin{pmatrix}5 & 2 \\ 2 & 1\end{pmatrix}.$$

**Answer**

1\. Calculate the characteristic polynomial:

\begin{align*}
f(\lambda) &= \mathrm{det}\left(A - \lambda I\right)\\
           &=  \begin{vmatrix}5 - \lambda & 2 \\ 2 & 1-\lambda\end{vmatrix} \\
           &= (5-\lambda)(1-\lambda) - 4 \\
           &= \lambda^2 - 6\lambda + 1
\end{align*}

2\. Solve $f(\lambda)=0$:

$$\lambda = \frac{6 \pm \sqrt{36-4}}{2} = 3 \pm 2\sqrt{2}$$

Therefore the eigenvalues are $\lambda_1 = 3+2\sqrt{2}$ and $\lambda_2 = 3-2\sqrt{2}$.

3\. Determine the eigenvectors by row-reduction:

$$A - \lambda_1 I = \begin{pmatrix}2-2\sqrt{2} & 2 \\ 2 & -2-\sqrt{2}\end{pmatrix}$$

Reduces to:

\begin{pmatrix}1 & -1-\sqrt{2}\\ 0 & 0\end{pmatrix}

and the general solution to $\left(A - \lambda_1I\right)v=0$ is

$$ v = x_2\begin{pmatrix}1+\sqrt{2}  \\ 1\end{pmatrix}.$$

Therefore $v_1 = \begin{pmatrix}1+\sqrt{2}  \\ 1\end{pmatrix}$ is an eigenvector corresponding to the eigenvalue $\lambda_1 = 3 + 2\sqrt{2}$.

Similarly, we can calculate that $v_2 = \begin{pmatrix}1-\sqrt{2}  \\ 1\end{pmatrix}$ is an eigenvector corresponding to the eigenvalue $\lambda_2 = 3 - 2\sqrt{2}$.

```

For larger matrices, calculating eigenvalues by hand can be challenging due to the fact that we have calculate determinants (hard!) and find the roots of polynomials (hard!). In the example below, calculating the determinant is made easier due to the presence of zeros in the off-diagonal entries of the matrix. A little bit of guess-work allows us to find one root of the characterstic polynomial, then we use polynomial division to find the other roots.

In practice however, we need to resort to a numerical methods - implemented on a computer - to find eigenvalues and eigenvectors of large matrices.

```{admonition} Example: Eigenvalues and Eigenvectors of a $(3\times 3)$ Matrix
:class: tip

Find the eigenvalues and eigenvectors of the matrix

$$A = \begin{pmatrix}0 & 6 & 8\\\frac{1}{2} & 0 & 0\\0 & \frac{1}{2} & 0\end{pmatrix}.$$

**Answer**

1\. Calculate the characteristic polynomial:

\begin{align*}
f(\lambda) &= \mathrm{det}\left(A - \lambda I\right)\\
           &=  \begin{vmatrix}- \lambda & 6 & 8 \\ \frac{1}{2} & -\lambda &0\\0 & \frac{1}{2} & -\lambda \end{vmatrix} \\
           &= 8\left(\frac{1}{2}-(0\times-\lambda)\right) - \lambda\left(\lambda^2 - 6\times\frac{1}{2}\right)\\
           &= -\lambda^3 +3\lambda + 2.
\end{align*}

2\. Solve $f(\lambda)=0$:

In general, factorising cubic polynomials is hard. However, in this case (by trial and error) we can determine that $f(2)=0$ and therefore $\lambda-2$ is a root of the characteristic polynomial. To find the other roots, we can use polynomial long division:

$$\frac{-\lambda^3 + 3\lambda+2}{\lambda-2} = -\lambda^2-2\lambda-1=-(\lambda+1)^2.$$

Therefore,

$$f(\lambda) = -(\lambda-1)(\lambda+1)^2,$$

so the only eigenvalues are $\lambda=2, -1$.

3\. The eigenspace corresponding to $\lambda=2$ is the null space of $A-2I$.

$$A-2I = \begin{pmatrix}-2&6&8\\\frac{1}{2}&-2&0\\0&\frac{1}{2}&-2\end{pmatrix}$$

which reduces to

$$\begin{pmatrix}1&0&-16\\0&1&-4\\0&0&0\end{pmatrix}$$

from which we can calculate the special solution

$$\begin{pmatrix}16\\4\\1\end{pmatrix}$$

and so the eigenspace corresponding to eigenvector $\lambda=2$ is

$$t\begin{pmatrix}16\\4\\1\end{pmatrix}, t\in \mathbb{R}.$$

The eigenspace corresponding to $\lambda=-1$ is the null space of $A+I$.

$$A+I = \begin{pmatrix}1&6&8\\\frac{1}{2}&1&0\\0&\frac{1}{2}&1\end{pmatrix}$$

which reduces to

$$\begin{pmatrix}1&0&-4\\0&1&2\\0&0&0\end{pmatrix}$$

from which we can calculate the special solution

$$\begin{pmatrix}4\\-2\\1\end{pmatrix}$$

and so the eigenspace corresponding to eigenvector $\lambda=-1$ is

$$t\begin{pmatrix}4\\-2\\1\end{pmatrix}, t\in \mathbb{R}.$$
```

```{exercise}
:label: calculate_eigenvectors

Find the eigenvalues and eigenvectors of the matrix

$$M = \begin{pmatrix}0&0&1\\0&2&0\\3&0&0\end{pmatrix}.$$
```


## Solutions to Exercises

```{solution} q_check_eigenvector

$$Av_1 =\begin{pmatrix}0 & 6 & 8 \\ \frac{1}{2} & 0 &0 \\ 0 & \frac{1}{2} & 0\end{pmatrix}\begin{pmatrix} 16 \\ 4 \\ 1 \end{pmatrix} = \begin{pmatrix} 32 \\ 8 \\ 2 \end{pmatrix} = 2v_1.$$

Therefore $v_1$ is an eigenvector of $A$ with eigenvalue $\lambda_1 = 2$

$$Av_2 =\begin{pmatrix}0 & 6 & 8 \\ \frac{1}{2} & 0 &0 \\ 0 & \frac{1}{2} & 0\end{pmatrix}\begin{pmatrix} 2 \\ 2 \\ 2 \end{pmatrix} = \begin{pmatrix} 28 \\ 1 \\ 1 \end{pmatrix}$$

is not a scalar multiple of $v_2$ therefore $v_2$ is not an eigenvector of $A$.
```


```{solution} q_check_eigenvalue
$\lambda = -2$ is an eigenvalue of $A$ if the equation $\left(A + 2I\right)v = 0$ has non-zero solutions.

$$A + 2I = \begin{pmatrix}2 & -4 \\ -1 & -1\end{pmatrix} + 2\begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}4 & -4 \\ -1 & 1\end{pmatrix}$$

The reduced row echelon form of this matrix is

$$\begin{pmatrix}1 & -1 \\ 0 & 0\end{pmatrix}$$

and the general solution to $\left(A + 2I\right)v=0$ is

$$ v = \begin{pmatrix}1  \\ 1\end{pmatrix}.$$

Therefore $\lambda = -2$ is an eigenvalue with corresponding eigenvector $v = \begin{pmatrix}1  \\ 1\end{pmatrix}$.

```

```{solution} calculate_eigenvectors

1\. Calculate the characteristic polynomial.

$$\begin{align*}
f(\lambda) &= \det(M-\lambda I)\\
&= \begin{vmatrix}-\lambda&0&1\\0&2-\lambda&0\\3&0&-\lambda\end{vmatrix}\\
&= (2-\lambda)\begin{vmatrix}-\lambda&1\\3&-\lambda\end{vmatrix}\\
&= (2-\lambda)(\lambda^2-3)\\  
&= (2-\lambda)(\lambda-\sqrt{3})(\lambda+\sqrt{3})
\end{align*}$$

2\. Solve $f(\lambda) = 0$:

Eigenvalues are $\lambda_1=2, \lambda_2=\sqrt{3}, \lambda_3=-\sqrt{3}$.

3\. The eigenspace corresponding to $\lambda_1=2$ is the null space of

$$M-2I = \begin{pmatrix}-2&0&1\\0&0&0\\3&0&-2\end{pmatrix}.$$

Reducing to reduced row echelon form:

$$\begin{pmatrix}1&0&0\\0&0&1\\0&0&0\end{pmatrix}$$

so the corresponding eigenvector is

$$v_1 = \begin{pmatrix}0\\1\\0\end{pmatrix}.$$

The eigenspace corresponding to $\lambda_2=\sqrt{3}$ is the null space of

$$M-\sqrt{3}I = \begin{pmatrix}-\sqrt{3}&0&1\\0&2-\sqrt{3}&0\\3&0&-\sqrt{3}\end{pmatrix}.$$

Reducing to reduced row echelon form:

$$\begin{pmatrix}1&0&-\frac{1}{\sqrt{3}}\\0&1&0\\0&0&0\end{pmatrix}$$

so the corresponding eigenvector is

$$v_2 = \begin{pmatrix}1\\0\\\sqrt{3}\end{pmatrix}.$$

The eigenspace corresponding to $\lambda_2=-\sqrt{3}$ is the null space of

$$M+\sqrt{3}I = \begin{pmatrix}\sqrt{3}&0&1\\0&2+\sqrt{3}&0\\3&0&\sqrt{3}\end{pmatrix}.$$

Reducing to reduced row echelon form:

$$\begin{pmatrix}1&0&\frac{1}{\sqrt{3}}\\0&1&0\\0&0&0\end{pmatrix}$$

so the corresponding eigenvector is

$$v_3 = \begin{pmatrix}1\\0\\-\sqrt{3}\end{pmatrix}.$$
```
