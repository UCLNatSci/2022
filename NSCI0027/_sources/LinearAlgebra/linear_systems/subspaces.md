# Linear Subspaces

Two important definitions.

## Column Space

```{card} Definition

The **column space** of a matrix $A$ is the span (all linear combinations) of the columns of $A$.

$$\mathrm{Col}(A) = \mathrm{Span}\left(\left\{v_1, \ldots, v_n\right\}\right)$$

where

$$A = \begin{pmatrix}|&|&&|\\v_1&v_2&\cdots&v_n\\|&|&&|\end{pmatrix}.$$

```

```{admonition} Example
:class: tip

Calculate the column space of 
$A = \begin{pmatrix}1&1\\1&1\\1&1\end{pmatrix}$.

**Solution**

$$\mathrm{Col}(A) = \mathrm{Span}\left\{\begin{pmatrix}1\\1\\1\end{pmatrix},\begin{pmatrix}1\\1\\1\end{pmatrix}\right\} = \mathrm{Span}\left\{\begin{pmatrix}1\\1\\1\end{pmatrix}\right\}.$$

The column space of $A$ is a straight line through the origin in the direction $\begin{pmatrix}1\\1\\1\end{pmatrix}$.

```

The column space of an $m \times n$ matrix $A$ is the set of all possible values of $Ax$ for any $x$ in $\mathbb{R}^n$.

## Null Space

```{card} Definition

The **null space** of a matrix $A$ is the set of all solutions to the equation

$$Ax=0.$$

The null space of $A$ is also written $\mathrm{Null}(A)$.
```

```{admonition} Example
:class: tip

Calculate the null space of 
$A = \begin{pmatrix}1&1\\1&1\\1&1\end{pmatrix}$.

**Solution**

The reduced row echelon form of $A$ is $\begin{pmatrix}1&1\\0&0\\0&0\end{pmatrix}$.

This gives the equation $x_1 + x_2 = 0$, or:

$$\begin{align*}
x_1 &= -x_2\\
x_2 &= x_1\end{align*}$$

which results in parametric vector form:

$$\begin{pmatrix}x_1\\x_2\end{pmatrix} = \begin{pmatrix}-1\\1\end{pmatrix}.$$

$$\mathrm{Null}(A) = \mathrm{Span}\left\{\begin{pmatrix}-1\\1\end{pmatrix}\right\}.$$

The null space of $A$ is a straight line through the origin in the direction $\begin{pmatrix}-1\\1\end{pmatrix}$.
```

## Calculating Bases for the Null Space and Column Space

In the example above, we noticed that the column space of $A$ was the span of two vectors, but that because the two vectors were linearly dependent we could more compactly write the column space as the span of a single vector:

$$\mathrm{Col}(A) = \mathrm{Span}\left\{\begin{pmatrix}1\\1\\1\end{pmatrix},\begin{pmatrix}1\\1\\1\end{pmatrix}\right\} = \mathrm{Span}\left\{\begin{pmatrix}1\\1\\1\end{pmatrix}\right\}.$$

In fact, $\left\{\begin{pmatrix}1\\1\\1\end{pmatrix}\right\}$is a basis for the column space of $A$. It turns out that we can write a basis for the column space and null space of a matrix using its reduced row echelon form. 

```{admonition} Basis for the Column Space and Null Space

**The pivot columns of $A$ form a basis for $\mathrm{Col}(A)$.**


**The vectors in the parametric vector form of the general solution to $Ax = 0$ form a basis for $\mathrm{Null}(A)$.**
```

```{admonition} Example
:class: tip

Calculate bases for the column space and null space of

$$A = \begin{pmatrix}1&2&0&-1\\-2&-3&4&5\\2&4&0&-2\end{pmatrix}.$$

**Solution**

$$\begin{pmatrix}1&2&0&-1\\-2&-3&4&5\\2&4&0&-2\end{pmatrix} \xrightarrow{\mathrm{RREF}} \begin{pmatrix}1&0&-8&-7\\0&1&4&3\\0&0&0&0\end{pmatrix}.$$ 

The first two columns are the pivot columns, therefore the first two columns of $A$ form a basis for $\mathrm{Col}(A)$:

$$\left\{\begin{pmatrix}1\\-2\\2\end{pmatrix}, \begin{pmatrix}2\\-3\\4\end{pmatrix}\right\}.$$

To find a basis for the null space, use the RREF to write the solution to $Ax = 0$ in parametric form:

$$x = x_3\begin{pmatrix}8\\-4\\1\\0\end{pmatrix} + x_4\begin{pmatrix}7\\-3\\0\\1\end{pmatrix}$$

which gives the following basis for $\mathrm{Null}(A)$:

$$\left\{\begin{pmatrix}8\\-4\\1\\0\end{pmatrix}, \begin{pmatrix}7\\-3\\0\\1\end{pmatrix}\right\}.$$

```

```{card} Definition

The vectors in the basis of $\mathrm{Null}(A)$ found from the reduced row echelon form of $A$ are called the **special solutions** to $Ax=0$.

```

## Rank-Nullity Theorem

```{card} Definition

The number of vectors in a basis for the column space of $A$ is called the **rank** of $A$.

The number of vectors in a basis for the null space of $A$ is called the **nullity** of $A$.

```

In the previous example we saw that The rank of $A$ is the the same as the number of pivots in the RREF of $A$, and the nullity of $A$ is the same as the number of free variables. The sum of these must be the number of columns in $A$, which gives us a very important result called the **rank-nullity theorem**.

```{card} The Rank-Nullity Theorem

Let $A$ be an $m \times n$ matrix. Then

$$\mathrm{Rank}(A) + \mathrm{Nullity}(A) = n.$$

```

