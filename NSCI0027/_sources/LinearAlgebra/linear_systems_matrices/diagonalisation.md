# Matrix Diagonalisation

## Motivation

Recall that a diagonal matrix is a square matrix with zeros everywhere except the main diagonal. Multiplying a vector by a diagonal matrix $D$ is easy. Just multiply each entry of the vector by the the element in the corresponding position of the diagonal matrix:

$$\begin{pmatrix}d_{1}&0&\cdots&0\\0&d_{2}&\cdots&0\\\vdots&\vdots&\ddots&\vdots\\0&0&\cdots&d_{n}\end{pmatrix}\begin{pmatrix}x_1\\x_2\\\vdots\\x_n\end{pmatrix} = \begin{pmatrix}d_{1}x_1\\d_{2}x_2\\\vdots\\d_{n}x_n\end{pmatrix}.$$


In fact, for diagonal matrices we immediately have the eigenvalues and eigenvectors! The eigenvalues are the diagonal entries $d_i$ and the eigenvectors are the standard coordinate vectors $e_i$:

$$De_i = d_ie_i.$$

Multiplying by a diagonal matrix is easy because any vector is a linear sum of coordinate vectors. The diagonal entries of $D$ act separately on each of the components of the vector $x$.

$$\begin{align*}
Dx &= D(x_1e_1 + \cdots + Dx_ne_n)\\
&= x_1De_1 + \cdots + x_nDe_n\\
&= (x_1d_1)e_1 + \cdots + (x_nd_n)e_n
\end{align*}$$

What about general (non-diagonal) square matrices? If $x$ is an eigenvector of a square matrix $A$ and $\lambda$ its eigenvalue, then we have

$$Ax = \lambda x.$$

If $x$ is an eigenvector, $A$ behaves like a diagonal matrix. Instead of writing $x$ as a sum of coordinate vectors $e_i$, we write it as a sum of eigenvectors $v_i$:

$$ x = a_1v_1 + \cdots + a_nv_n,$$

Then

$$ Ax = a_1\lambda_1v_1 + \cdots + a_n\lambda_nv_n.$$

We just need to find the values $a_i$. It turns out that these are just the inverse of the matrix of eigenvectors, as we will see in the next section.

## Diagonalisation $A = X\Lambda X^{-1}$

```{admonition} Matrix Diagonalisation

Let $A$ be an $(n \times n)$ matrix with $n$ eigenvectors $v_i$ and corresponding eigenvalues $\lambda_i$. Let

$$X = \begin{pmatrix}|&&|\\v_1&\cdots&v_n\\|&&|\end{pmatrix}$$

be the matrix of eigenvectors and

$$\Lambda = \begin{pmatrix}\lambda_1 &&\\&\ddots&\\&&\lambda_n\end{pmatrix} $$

the diagonal matrix of eigenvalues. If $X$ is invertible, then

$$X^{-1}AX = \Lambda$$

and

$$A = X\Lambda X^{-1}.$$

```

Note that we use capital lambda $\Lambda$ to represent the matrix of eigenvalues.

To see why the above result is true, note $X^{-1}AX=\Lambda$ and $A = X\Lambda X^{-1}$ are both exactly equivalent to:

$$AX = X\Lambda.$$

Then the left hand side $AX$ is $A$ times the eigenvectors:

$$AX = A\begin{pmatrix}|&&|\\v_1&\cdots&v_n\\|&&|\end{pmatrix} = \begin{pmatrix}|&&|\\\lambda_1v_1&\cdots&\lambda_nv_n\\|&&|\end{pmatrix}$$

because $Av_i= \lambda_iv_i$.

Whereas right hand side $X\Lambda$ is the eigenvectors times the eigenvalues:

$$X\Lambda = \begin{pmatrix}|&&|\\v_1&\cdots&v_n\\|&&|\end{pmatrix}\begin{pmatrix}\lambda_1 &&\\&\ddots&\\&&\lambda_n\end{pmatrix} = \begin{pmatrix}|&&|\\\lambda_1v_1&\cdots&\lambda_nx_n\\|&&|\end{pmatrix}.$$

Thus we see that $AX=X\Lambda$.

```{admonition} Example
:class: tip

Diagonalise the $(2 \times 2)$ matrix

$$A = \begin{pmatrix}0 &-1 \\ -1 &  0\end{pmatrix}.$$

**Solution**

This matrix represents a reflection in the line $y=-x$ so we can immediately write down two eigenvalues and corresponding eigenvectors:

$$\lambda_1 = 1, \quad v_1 = \begin{pmatrix}1\\-1\end{pmatrix},\\
\lambda_2 = -1, \quad v_2 = \begin{pmatrix}1\\1\end{pmatrix}.$$

Therefore we can write the matrix of eigenvectors $X$ and matrix of eigenvalues $\Lambda$:

$$\begin{align*}X &= \begin{pmatrix}1 & 1\\-1&1\end{pmatrix},\\
\Lambda &= \begin{pmatrix}1&0\\0&-1\end{pmatrix}.\end{align*}$$

To complete the diagonalisation we need to calculate $X^{-1}$:

$$X^{-1} = \frac{1}{\det (X)  } \mathbb{adj}(X) = \frac{1}{2}\begin{pmatrix}1&-1\\1&1\end{pmatrix} = \begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{pmatrix}.$$

Then

$$A = X\Lambda X^{-1} = \begin{pmatrix}1 & 1\\-1&1\end{pmatrix}\begin{pmatrix}1&0\\0&-1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{pmatrix}.$$

```

The matrix of eigenvectors $X^{-1}$ is also called the *change of basis* matrix. Multiplying a vector $x$ by $X^{-1}$ transforms it from standard coordinates $e_1, \ldots, e_n$  to eigenvector coordinates $v_1, \ldots, v_n$.

Suppose $x$ is written as a sum of eigenvectors with coefficients $a_i$:

$$x = a_1v_1 + \cdots + a_nv_n = X\begin{pmatrix}a_1\\\vdots\\a_n\end{pmatrix}$$

then left-multiplying by $X^{-1}$ gives the vector of coefficients $a_i$:

```{math}
:label: eq_two_by_two_diag
\begin{pmatrix}a_1\\\vdots\\a_n\end{pmatrix}= X^{-1}x.
```

```{note}

**Diagonalisation is not unique**

1\. If we write the eigenvalues and eigenvectors in a different order, we get a different matrix $X$. Swapping $v_1$ and $v_2$ we get another way to write {eq}`eq_two_by_two_diag`:

$$A = \begin{pmatrix}1 & 1\\1&-1\end{pmatrix}\begin{pmatrix}-1&0\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&\frac{1}{2}\\\frac{1}{2}&-\frac{1}{2}\end{pmatrix}.$$

However it is important that the order of the eigenvalues is the same as the order of the eigenvectors. If you swap the eigenvectors, you must remember to also swap the eigenvalues!

2\. Any eigenvector can be multiplied by a constant. For example replacing $v_1$ by $2v_1$ in {eq}`eq_two_by_two_diag`:

$$A = \begin{pmatrix}2 & 1\\-2&1\end{pmatrix}\begin{pmatrix}1&0\\0&-1\end{pmatrix}\begin{pmatrix}\frac{1}{4}&-\frac{1}{4}\\\frac{1}{2}&\frac{1}{2}\end{pmatrix}.$$

3\. The eigenvalues *are* unique, although different diagonalisations may result in a different order.
```

```{exercise}
:label: diagonalise_2_by_2

Diagonalise the matrix

$$A = \begin{pmatrix}\frac{1}{2}&\frac{3}{2}\\\frac{3}{2}&\frac{1}{2}\end{pmatrix}.$$

```

## About Diagonalisation

Not all matrices can be diagonalised. To diagonalise a matrix, the matrix of eigenvectors $X$ must be invertible. In this section we will investigate conditions under which this is the case.

Recall that if $v$ is an eigenvector then so is any multiple $av$. Suppose a $(2 \times 2)$ matrix has eigenvector $v$. Then the vector $2v$ is also an eigenvector, but the eigenvector matrix

$$X = \begin{pmatrix}|&|\\v&2v\\|&|\end{pmatrix}$$

is not invertible since the second column is a multiple of the first (and therefore its determinant is zero).

We can extend this idea to $(3 \times 3)$ matrices. Suppose we have two independent eigenvectors $v_2$ and $v_2$ and a third eigenvector $v_3$ such that $v_3 = av_1 + bv_2$ for some scalars $a$ and $b$. Then the matrix of eigenvectors

$$X = \begin{pmatrix}|&|&|\\v_1&v_2&v_3\\|&|&|\end{pmatrix}$$

is not invertible. To extend this idea to the general case, we need to introduce the important concept of *linear independence*.

## Linear Independence

A set of vectors is linearly dependent if one vector can be written as a linear sum of the other vectors.

```{admonition} Definition
Let $v_1, \ldots, v_n \in \mathbb{R}^m$ be a set of vectors.

The vectors are **linearly independent** if the equation

$$a_1v_1 + \cdots + a_nv_n = 0$$

has only the trivial solution

$$a_1 = \cdots = a_n = 0.$$

Otherwise, we say the vectors are **linearly dependent**.
```

```{exercise}
:label: linear_dependence
Show that a set of vectors is linearly dependent if (and only if) one of the vectors is a linear sum of the others.

```

If we have $n$ linearly dependent vectors $v_i \in \mathbb{R}^n$ then it is easy to show that the matrix

$$X = \begin{pmatrix}|&&|\\v_1&\cdots &v_n\\|&&|\end{pmatrix}$$

is not invertible. Therefore we can extend the invertible matrix theorem with two more equivalent conditions for invertibility:

```{admonition} Invertible Matrix Theorem (II)

Let $A$ be an $(n \times n)$ matrix. Then the following statements are equivalent:

1. $A$ is invertible.
2. $\mathrm{det}(A) \neq 0$.
3. $A$ has $n$ pivots.
4. The null space of $A$ is 0.
5. $Ax=b$ has a unique solution for every $b \in \mathbb{R}^n$.
6. **The columns of $A$ are linearly independent.**
7. **The rows of $A$ are linearly independent.**

```

## More Eigenvalues

```{admonition} Theorem
Eigenvectors $v_1, \ldots, v_n$ corresponding to distinct eigenvalues are linearly independent.

An $(n \times n)$ matrix with $n$ distinct eigenvalues is diagonalisable.
```

To prove this, suppose that $v_1$ and $v_2$ are linearly dependent eigenvectors of the matrix $A$ with distinct eigenvalues $\lambda_1$ and $\lambda_2$.

```{math}
:label: eq_indep
v_2 = av_1
```
for some $a\neq 0$.

Multiply by A:

$$\lambda_2v_2 = a\lambda_1v_1$$

then divide by $\lambda_2$ (since they are distinct we can assume that at least one of the eigenvalues is nonzero).

```{math}
:label: eq_indep_2
v_2 = \frac{a\lambda_1}{\lambda_2}v_2.
```

Comparing {eq}`eq_indep` and {eq}`eq_indep_2` we see that $\lambda_1/\lambda_2=1$ and so

$\lambda_1 = \lambda_2$.

We have shown that two linearly dependent eigenvectors must have identical eigenvalues. We will not show it here, but it is not difficult to extend this to the general case: eigenvectors from distinct eigenvalues are linearly independent.

We can conclude that if an $(n \times n)$ matrix has $n$ distinct eigenvalues then it has $n$ linearly independent eigenvectors. By the invertible matrix theorem  we can therefore can conclude that its matrix of eigenvectors $X$ is invertible, and the matrix is invertible.

```{admonition} Example
:class: tip

Determine the characteristic equation of each of the following matrices and identify which are diagonalisable:

$$A = \begin{pmatrix}0&-1\\-1&0\end{pmatrix}, \quad B=\begin{pmatrix}1&1\\1&1\end{pmatrix}, \quad  C=\begin{pmatrix}1&1\\0&1\end{pmatrix}.$$

**Solution**

$A$ has characteristic polynomial $\lambda^2 - 1 = (\lambda-1)(\lambda+1)$. It has two distinct eigenvalues $\lambda_1=1$,$\lambda_2=-1$ and therefore two independent eigenvectors. It is diagonalisable and we already calculated $A = X\Lambda X^{-1}$ {eq}`eq_two_by_two_diag`.

$B$ has characteristic polynomial $\lambda^2-2\lambda = \lambda(\lambda - 2)$. It has two distinct eigenvalues $\lambda_1=0$,$\lambda_2=2$ and therefore has two independent eigenvectors and is diagonalisable.

$C$ has characteristic polynomial $\lambda^2-2\lambda+1 = (\lambda-1)^2$. It has a single eigenvalue $\lambda_1=1$. To determine if $C$ is diagonalisable, we need to check if there are two independent eigenvectors in the eigenspace of $\lambda_1$.

$$\mathrm{Null}(C - \lambda_1I) = \mathrm{Null}\begin{pmatrix}0&1\\0&0\end{pmatrix} = \begin{pmatrix}1\\0\end{pmatrix}.$$

$C$ has only one linearly independent eigenvector and therefore it is not diagonalisable.
```

```{exercise}
:label: q_diagonalise_matrix

1. Diagonalise the matrix $B$ in the example above.
2. Find a diagonalisable matrix with only one distinct eigenvalue.
```

```{attention}
Diagonalisability is *not* related to invertibility. Non-invertible matrices can be diagonalisable, as in $B$ above. Likewise, non-diagonalisable matrices can be invertable as in $C$ above.
```

## Algebraic and Geometric Multiplicity

The eigenvalues of a $(n \times n)$ square matrix are the roots of its characteristic polynomial $f(\lambda)$. We have already seen that if there are $n$ distinct roots then there are $n$ linearly independent eigenvectors and the matrix is diagonalisable. For example a $(3 \times 3)$ matrix with the following characteristic polynomial is diagonalisable.

$$f(\lambda) = (\lambda-1)(\lambda-2)(\lambda-3)$$

If there are fewer then $n$ distinct roots then at least one of the roots must be *repeated*. For example, the characteristic polynomial

```{math}
:label: eq_repeated_root
f(\lambda) =(\lambda-2)(\lambda-1)^2
```

results in two distinct eigenvalues $\lambda_1=2$ and $\lambda_2=1$. $\lambda_2$ is a repeated root with multiplicity $2$ since the factor $(\lambda-1)$ divides the polynomial twice. To determine whether the matrix is diagonalisable, we need to determine how many independent eigenvectors there are in the eigenspace of each of the eigenvectors.

```{admonition} Theorem

Let $A$ be a square matrix and $\lambda$ an eigenvalue of $A$. Then,

**geometric multiplicity of $\lambda$ $\leq$ algebraic multiplicity of $\lambda$**

where the **algebraic multiplicity** of $\lambda$ is its multiplicity as a root of the characteristic polynomial of $A$ and the **geometric multiplicity** of $\lambda$ is the number of independent eigenvectors in the eigenspace of $\lambda$.
```

This means that for {eq}`eq_repeated_root` there could be one or two independent eigenvectors in the eigenspace of $\lambda_2$. If there are two, then the matrix is diagonalisable; if only one then it is not diagonalisable. To check, we have to calculate the null space of $A-\lambda_2I$.

<!--
```{admonition} Example
:class: tip

TODO

matrix with repeated root and dimension 1 or 2 null space.
```
-->

## Matrix Powers $A^k$

The eigenvector matrix $X$ produces $A=X\Lambda X^{-1}$. This factorisation is useful for computing powers because $X^{-1}$ multiplies with $X$ to get $I$:

$$\begin{align*}A^2 &= X\Lambda X^{-1}X\Lambda X^{-1} = X\Lambda I\Lambda X^{-1}=X\Lambda^2X^{-1}\\
A^3 & = X\Lambda^2X^{-1}X\Lambda X^{-1} = X\Lambda^3X^{-1}\end{align*}$$

and so on. Because $\Lambda$ is a diagonal matrix, its powers $\Lambda^k$ are easy to calculate.

```{admonition} Theorem

Let $A$ be a diagonalisable square matrix with $A = X\Lambda X^{-1}$ and $k\in \mathbb{N}$. Then

$$A^k = X\Lambda^k X^{-1} = X\begin{pmatrix}\lambda_1^k&&\\&\ddots&\\&&\lambda_n^k \end{pmatrix}X^{-1}.$$

```

## Complex Eigenvalues

We have seen that from a square matrix $A$ we can calculate the characteristic polynomial $f(\lambda)$. For an $(n \times n)$ matrix the polynomial is degree $n$:

$$f(\lambda) = \lambda^n + a_{n-1}\lambda^{n-1} + \cdots + a_1\lambda + a_0$$

where $a_i$ are real numbers.

By the fundamental theorem of algebra, $f(\lambda)$ can be factorised into $n$ factors $\lambda - \lambda_i$ (some of which may be repeated):

$$f(\lambda) = (\lambda - \lambda_1)(\lambda - \lambda_2) \cdots (\lambda - \lambda_n).$$

The roots $\lambda_i$ are the eigenvalues of the matrix.

In this section we consider the case where some of the roots are not real numbers.

### Rotations in 2D

Let $A$ be the matrix of an anticlockwise rotation $\pi/2$ around the origin:

$$A = \begin{pmatrix}0&-1\\1&0\end{pmatrix}.$$

The characteristic polynomials is $\det(A-\lambda I)$ which equals

$$\begin{vmatrix}-\lambda&-1\\1&-\lambda\end{vmatrix} = \lambda^2+1.$$

The polynomial $\lambda^2+1$ does not have real roots. Its roots are $\pm i$ where $i$ is the imaginary number $\sqrt{-1}$:

$$\lambda^2+1 = (\lambda+i)(\lambda-i)$$

resulting in two complex eigenvalues $\lambda_1 = i$ and $\lambda_2= -i$.

We also find that the eigenvectors contain the imaginary number $i$:

$$A - \lambda_1I = \begin{pmatrix}-i&-1\\1&-i\end{pmatrix} \underrightarrow{\mathrm{~RREF~}} \begin{pmatrix}1&-i\\0&0\end{pmatrix}$$

and hence the eigenvector corresponding to the eigenvalue $\lambda_1 = i$ is

$$v_1 = \begin{pmatrix}i\\1\end{pmatrix}.$$

Likewise the eigenspace corresponding to the eigenvalue $\lambda_2 = -i$ is

$$v_2 = \begin{pmatrix}-i\\1\end{pmatrix}.$$

```{admonition} Example

Find the eigenvalues of an anticlockwise rotation by an angle $\theta$.

**Solution**

The matrix

$$A = \begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}$$

represents an anticlockwise rotation by an angle $\theta$. The characteristic polynomial $f(\lambda)$ is given by

$$\begin{align*}\det(A-\lambda I) &= \begin{vmatrix}\cos\theta-\lambda&-\sin\theta\\\sin\theta&\cos\theta-\lambda\end{vmatrix}\\
&= (\cos\theta - \lambda)^2+\sin^2\theta.\end{align*}$$

Setting this to zero and solving for $\lambda$ gives eigenvalues

$$\lambda = \cos\theta\pm i\sin\theta = e^{\pm i\theta}.$$

```

```{exercise}
:label: q_complex_eigenvector

Find the complex eigenvectors corresponding to the two complex eigenvalues of

$$A = \begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}.$$

```

## Trace and Determinant

Calculating eigenvalues is (in general) a difficult problem. However, in some cases we can use some 'tricks' to help find them.

```{admonition} Definition

The **trace** of a matrix is the sum of the diagonal entries. Given a matrix $A$ with entries $a_{ij}$:

$$\mathrm{tr}(A) = a_{11} + \cdots +a_{nn}.$$
```

```{admonition} Theorem

Let $A$ be an $(n \times n)$ matrix with eigenvalues $\lambda_1, \ldots, \lambda_n$. Then

$$\lambda_1 + \cdots + \lambda_n = \mathrm{tr}(A)$$

and

$$\lambda_1\lambda_2 \cdots \lambda_n = \det(A).$$

The sum of the eigenvalues is the sum of the diagonal entries of $A$. The product of the eigenvalues is the determinant of $A$.
```

```{admonition} Example
:class: tip
Calculate the determinant of the matrix

$$A = \begin{pmatrix}1&1&1\\1&1&1\\1&1&1\end{pmatrix}.$$

**Solution**

This matrix is clearly not invertible, and so has zero determinant and at least one zero eigenvalue.

In fact there are two independent eigenvectors in the zero eigenspace (check this!). This means that we have $\lambda_1=\lambda_2=0$. To find the third eigenvalue, use the identity

$$\lambda_1 + \lambda_2 + \lambda_3 = \mathrm{tr}(A)$$

to determine that $\lambda_3=3$.

```

```{exercise}
:label: diagonal_eigenvalues

Show that the eigenvalues of a triangular matrix are its diagonal entries.
```


## Solutions to Exercises

```{solution} diagonalise_2_by_2

First find the eigenvalues and eigenvectors of $A$. The characteristic polynomial is given by:

$$f(\lambda) = \det(A-\lambda I) = \lambda^2-\lambda-2 = (\lambda+1)(\lambda-2)$$

therefore the two eigenvalues are $\lambda_1 = -1$ and $\lambda_2=2$.

To find the corresponding eigenvectors, calculate the nullspace of $A - \lambda I$ for each eigenvalue. For $\lambda_1$:

$$A +1I = \begin{pmatrix}\frac{3}{2}&\frac{3}{2}\\\frac{3}{2}&\frac{3}{2}\end{pmatrix} \underrightarrow{\mathrm{~RREF~}} \begin{pmatrix}1&1\\0&0\end{pmatrix}$$

Therefore $v_1 = \begin{pmatrix}-1\\1\end{pmatrix}$ is an eigenvector corresponding to eigenvalue $\lambda_1=-1$.

For $\lambda_2$:

$$A - 2I = \begin{pmatrix}-\frac{3}{2}&\frac{3}{2}\\\frac{3}{2}&-\frac{3}{2}\end{pmatrix} \underrightarrow{\mathrm{~RREF~}} \begin{pmatrix}1&-1\\0&0\end{pmatrix}$$

Therefore $v_2 = \begin{pmatrix}1\\1\end{pmatrix}$ is an eigenvector corresponding to eigenvalue $\lambda_2=2$.

The matrix of eigenvectors is

$$X = \begin{pmatrix}|&|\\v_1&v_2\\|&|\end{pmatrix} = \begin{pmatrix}-1&1\\1&1\end{pmatrix}$$

and its inverse

$$X^{-1} = \begin{pmatrix}-\frac{1}{2}&\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{pmatrix}.$$

The matrix of eigenvalues is

$$\Lambda = \begin{pmatrix}-1&0\\0&2\end{pmatrix}$$

and so

$$A = X\Lambda X^{-1} = \begin{pmatrix}-1&1\\1&1\end{pmatrix}\begin{pmatrix}-1&0\\0&2\end{pmatrix}\begin{pmatrix}-\frac{1}{2}&\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{pmatrix}.$$


```

```{solution} q_diagonalise_matrix

1\. Eigenvalues are $\lambda_1 = 0$, $\lambda_2=1$.

$B-\lambda_1I = \begin{pmatrix}1&1\\1&1\end{pmatrix}\underrightarrow{\mathrm{~RREF~}}\begin{pmatrix}1&1\\0&0\end{pmatrix}$

Therefore $v_1 = \begin{pmatrix}1\\-1\end{pmatrix}$.

$B-\lambda_2I = \begin{pmatrix}-1&1\\1&-1\end{pmatrix}\underrightarrow{\mathrm{~RREF~}}\begin{pmatrix}-1&1\\0&0\end{pmatrix}$

Therefore $v_2 = \begin{pmatrix}1\\1\end{pmatrix}$.

$$X = \begin{pmatrix}1&1\\-1&1\end{pmatrix}$$

and

$$X^{-1} = \begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{pmatrix}.$$

$$B = X\Lambda X^{-1} = \begin{pmatrix}1&1\\-1&1\end{pmatrix}\begin{pmatrix}0&0\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\\frac{1}{2}&\frac{1}{2}\end{pmatrix}.$$

*The eigenvalue matrix $\Lambda$   has a zero on the diagonal because one of the eigenvalues is zero.*

2\. A matrix of the form

$$\begin{pmatrix}a&0\\0&a\end{pmatrix}$$

has characteristic polynomial

$$ (a-\lambda)^2 $$

and therefore a single repeated eigenvalue $\lambda=a$.

But it is diagonalisable (it is diagonalised by the identity matrix). In fact, every vector $v \in \mathbb{R}^2$ is an eigenvector of the matrix.

```
