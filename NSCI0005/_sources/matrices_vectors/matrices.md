# Matrices



## Matrix Definitions

A matrix (plural: matrices) is essentially just an array of values, arranged in rows and columns. 

```{math}
\left(
\begin{array}{cccc}
    a_{1,1} & a_{1,2} & \cdots & a_{1,n}  \\
    a_{2,1} & a_{2,2} & \cdots & a_{2,n}  \\
    \vdots & \vdots & \ddots & \vdots  \\
    a_{m,1} & a_{m,2} & \cdots & a_{m,n} 
\end{array}
\right)
```

In general, the values contained in a matrix could represent anything, although manipulating systems of linear equations is one of the most valuable uses of matrices.

The Gaussian elimination technique that we have looked at is a brute force method for solving a given set of equations, whilst matrix methods are more concerned with 
finding general solutions and simplifications of certain types of problems.

### Notation

Two example matrices are given below

```{math}
:label: square_matrix
\left( \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right) \qquad \left[ \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right]
```

It is important that you do not use commas to separate the elements, which is incorrect notation.

Either square or round brackets can be used to denote a matrix - but you should avoid mixing notation. Other types of brackets cannot be used, so none of the expressions below are matrices. In fact, the third expression has a special meaning, as we will see later.

```{math}
\begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \qquad \left\{ \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right\} \qquad \left| \begin{matrix} 1 & -3 \\ 2 & -1 \end{matrix} \right|	
```

### Terminology

The matrix featured in {eq}`square_matrix` is referred to as a square matrix because it has the same number of rows and columns. We also can say that it is 
a (2x2) matrix, because it has two rows and two columns.

The number of rows must be given first:

$ \left( \begin{matrix} 1 & -3 & 5\\ 2 & -1 & 7\end{matrix} \right) $  is a (2 x 3) matrix, $ \left( \begin{matrix} 1 & -3 \\ 2 & -1 \\ 5 & 7\end{matrix} \right) $ is a (3 x 2) matrix.

This measurement is properly referred to as the **order** of a matrix, but is also often referred to as the **size**.  The individual values in a matrix are called 
**elements**, so in the matrix $ M = \left( \begin{matrix} 1 &2 &3 \\ 4& 5& 6\end{matrix} \right) $ we can say that the element in the $2^{nd}$ row and $3^{rd}$ column 
is the number 6. Subscripts can be used to refer to the elements, by writing $ M_{2,3} = 6$ for example.

The **transpose** of a matrix, written with a superscript letter T, means that we swap the rows and columns,:

$ M = \left( \begin{matrix} 1 &2 &3 \\ 4& 5& 6\end{matrix} \right) \Rightarrow M^T = \left( \begin{matrix} 1 & 4 \\ 2 & 5  \\ 3 & 6\end{matrix} \right)$

In element notation, for any matrix $X$, we can write that $\left(X^T\right)_{i,j} = X_{j,i}$.

That is, the element in the $i^{th}$ row and $j^{th}$ column of $X$ becomes the element in the $j^{th}$ row and $i^{th}$ column of $X^T$.

The order of a matrix is reversed when it it transposed.

In a square matrix, two diagonals are called the **main diagonal** (top-left two bottom right), and the **anti-diagonal** (bottom-left to top-right). Square matrices for which $A_{i,j}=A_{j,i}$ are called **symmetric matrices**.

An **upper-triangular matrix** is a square matrix in which the elements below the main diagonal are all zero, and a **lower-triangular matrix** is one where the elements above the main diagonal are all zero.

A **diagonal matrix** is one in which all of the elements are zero apart from those on the main diagonal. These type of matrices are very special, since they have "nice" properties for the purpose of matrix algebra.    

````{admonition} Practice Questions
:class: seealso, dropdown

1\. What is the order of each of the matrices shown?

$A=\left(\begin{array}{cc}0 & -1 \\2 & 3 \\-1 & 0 \\\end{array}\right)$,   $b=\left(\begin{array}{c}1 \\2 \\3 \\\end{array}\right)$,   $c=0$.

2\. Given the matrix $X=\left(\begin{array}{ccc}-3 & 4 & 0 \\1 & 1 & 2 \\7 & -4 & 3 \\\end{array}\right)$, what element is represented by $(X^T)_{2,3}$ ?

3\. Which of the following matrices is an upper-triangular matrix?

$A=\left(\begin{array}{cccc}2&8&-1&0\\0&2&2&2\\0&0&1&-5\\0&0&0&3\end{array}\right)$, $B=\left(\begin{array}{cccc}1&-2&5&2\\3&6&-2&0\\8&2&0&0\\-2&0&0&0\end{array}\right)$, $C=\left(\begin{array}{ccc}6&0&0\\-3&-4&0\\2&7&7\end{array}\right)$.

````

## Matrix algebra

We will look at how real number algebra, such as addition and multiplication, can be extended to work with matrices. These are entirely human constructs, and you may be easily forgiven for asking why do we do it this way?

However, the best way to appreciate the practicalities is by tackling some problems, and so the definitions will first be introduced without much explanation. From a mathematical perspective, we simply note that the definitions must be consistent and well-determined (unambiguous).

### Multiplication by a scalar

Let $\lambda$ be a scalar (a single number) and $M$ be a matrix. Then $\lambda M$ means that every element in matrix $M$ is multiplied by $\lambda$. This can be written in element notation as follows:

$$ (\lambda M)_{i,j} = \lambda M_{i,j}$$

For example, $ -3\left( \begin{matrix} 0 & -2 \\ 1 & 5 \\ -1 & 3 \end{matrix} \right) = \left( \begin{matrix} 0 & 6 \\ -3 & -15 \\ 3 & -9 \end{matrix} \right) $.

### Addition

Let $A$ and $B$ be two matrices of the same order. Then,

$$\left(A + B\right)_{i,j} = A_{i,j} + B_{i,j}$$

The expression states that to add two matrices, we add together the corresponding elements. This type of operation on two matrices can be referred to as an element-wise operation.

For example, $ \left( \begin{matrix} 1 & -3 \\ 3 & 0 \\ 5 & -7 \end{matrix} \right) + \left( \begin{matrix} 0 & 6 \\ -3 & -15 \\ 3 & -9 \end{matrix} \right) = \left( \begin{matrix} 1 & 3 \\ 0 & -15 \\ 8 & -16 \end{matrix} \right) $.


The element-wise property means that only matrices of the same order can be added, and the expressions below are both meaningless:

$$ \left( \begin{matrix} 1 & 2 \end{matrix} \right) + \left( \begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix} \right) $$

$$\left( \begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix} \right) + 1 $$

Matrix addition can be combined with multiplication by a scalar to add multiples of one matrix to another.

For example, $ \left( \begin{matrix} 1 & -3 \\ 3 & 0 \\ 5 & -7 \end{matrix} \right) - 3\left( \begin{matrix} 0 & -2 \\ 1 & 5 \\ -1 & 3 \end{matrix} \right) = \left( \begin{matrix} 1 & 3 \\ 0 & -15 \\ 8 & -16 \end{matrix} \right) $.

````{admonition} Practice Questions
:class: seealso, dropdown

Given the matrices $A=\left(\begin{array}{cc}1 & 2 \\-1 & 0 \\3 & 1 \\\end{array}\right)$, $B=\left(\begin{array}{cc}-4 & 1 \\1 & 2 \\-2 & 3 \\\end{array}\right)$, $C=\left(\begin{array}{cc}0 & 3 \\4 & 2 \\1 & 1 \\\end{array}\right)$, $D=\left(\begin{array}{cc}5 & 1 \\3 & 2 \\\end{array}\right)$, what will be the result of the following expressions?

1. $\left(A+B\right)+C$
2. $(C+B)+A$
3. $A-2B+\frac{1}{2}C$
4. $A+D$

````

### Matrix multiplication

To multiply two matrices together, their inner dimensions must be the same. That is, to calculate $ \boldsymbol{A}\boldsymbol{B} $, the number of columns in 
$\boldsymbol{A}$ must be the same as the number of rows in $\boldsymbol{B}$. The order of the product matrix is given by the outer dimensions of the two 
matrices. We can represent this result visually:

```{figure} MatrixDimensions.png
---
name: matrixdimensions
---
Two matrices A,B can be multiplied if their inner dimensions agree. The dimensions of the result is given by the outer dimensions of AB.
```


````{admonition} Matrix Multiplication

Given a $(p × r)$ matrix $\boldsymbol{A}$ and a $(r × q)$ matrix $\boldsymbol{B}$, the matrix product $\boldsymbol{A\,B}$ defines a $(p × q)$ matrix, whose elements are given by

```{math}
 \left(A B\right)_{i,j} = \sum_k  A_{i,k} B_{k,j} 
```
````

To perform matrix multiplication, we must take elements in a row on the left hand side matrix and multiply with elements in a column on the right hand side matrix. The 
process is illustrate graphically here for a (2 x 2) example:

```{figure} MatrixMultiplicationExpanded.png
---
name: MatrixMultiplication
---
The $(i,\,j)$th element in the product $AB$ is given by the product sum of row $i$ from matrix A with column $j$ of matrix $B$.
```

````{admonition} Practice Questions
:class: seealso, dropdown

Given that

$A=\left(\begin{array}{ccc}3 & 1 & -2 \\0 & 2 & 4 \\\end{array}\right)$,   
$B=\left(\begin{array}{cc}2 & 3 \\-3 & 0 \\1 & 1 \\\end{array}\right)$,   
$C=\left(\begin{array}{cccc}1 & -8 & 2 & 11 \\0 & 4 & -3 & -7 \\6 & 1 & 8 & 1 \\\end{array}\right)$,    
$D=\left(\begin{array}{ccc}1 & 2 & 3 \\1 & 1 & 1 \\2 & 0 & 1 \end{array}\right)$,

1\. Calculate $AB$ and $BA$. Are these results the same?

2\. Explain why the result $A\left(\begin{array}{c}1\\2\end{array}\right)$ cannot be calculated.

3\. What will be the order of the matrix $A C$?

4\. Calculate the element in the second row and third column of $AC$

5\. Calculate the result $D^2$ (this question is a bit boring, but good practice!)
````

````{admonition} Solutions
:class: seealso, dropdown

1\. 

2\.

3\.

4\.
````

### Properties of Matrix Multiplication

Matrix multiplication is **associative**, that is

$$A (B C)\equiv (A B)C$$

This can be proved by showing that the left and right hand sides are the same order, and that $(A(B C))_{i,j}=((A B)C)_{i,j}$.

Matrix multiplication is **NOT commutative**, that is

$$\begin{array}{c}A B\neq B A \end{array}$$

(although the  $AB$ and $BA$ may be equal in some special cases).

```{warning}
For two matrices $A$ and $B$, in general $AB \neq BA$.

Forgetting the matrix multiplication is non-commutative leads to disaster!
```

```{admonition} Worked Example
:class: seealso
**Worked example illustrating non-commutative property**

$$\left(\begin{array}{cc}1 & 2 \\-3 & 0 \end{array}\right) \left(\begin{array}{cc}2 & 1 \\1 & 2 \\\end{array}\right)=\left(\begin{array}{cc}1\ 2+2\ 1 & 1\ 1+2\ 2 \\0\ 1-3\ 2 & 0\ 2-3\ 1\end{array}\right)=\left(\begin{array}{cc}4 & 5 \\-6 & -3 \\\end{array}\right)$$

$$\left(\begin{array}{cc}2 & 1 \\1 & 2 \\\end{array}\right) \left(\begin{array}{cc}1 & 2 \\-3 & 0 \end{array}\right)=\left(\begin{array}{cc}2\ 1+1 (-3) & 2\ 2+1\ 0 \\1\ 1+2 (-3) & 1\ 2+2\ 0 \end{array}\right)=\left(\begin{array}{cc}-1 & 4 \\-5 & 2 \\\end{array}\right)$$
```

## The identity matrix

The identity matrix $I_n$ is the unique $(n \times n)$ matrix which has the property

$$I_n x = x $$

for any $x \in \mathbb{R}^n$.

The identity matrix transforms the vector $x$ to itself. It plays the same role in matrix multiplication as the number 1 does for multiplication of real numbers.

````{admonition} Definition

The **identity matrix**

$$I_n = \begin{pmatrix}1 & 0 & \cdots & 0\\0 & 1 & \cdots & 0\\\vdots & \vdots & \ddots & \vdots\\0& 0 & \cdots & 1\end{pmatrix}.$$

We usually drop the subscript $n$ when working with the identity matrix, because the order can be inferred.
````

````{admonition} Practice Questions
:class: seealso, dropdown
1\. Calculate $I\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}$ and $\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}I$.

2\. Use the identify matrix to factorise 
```{math}
AB+\lambda B
```
where $\lambda$ is a scalar and $A,\,B$ are square matrices.
````


````{admonition} Solutions
:class: seealso, dropdown
1\. 
```{math}
I\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix} &= \begin{pmatrix}1 & 0\\0 & 1\end{pmatrix}\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix} = \begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}\\
\begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}I &= \begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}\begin{pmatrix}1 & 0\\0 & 1\end{pmatrix} = \begin{pmatrix}1 & 2\\3 & 4\end{pmatrix}\\
```

2\. 
```{math}
AB + \lambda B = AB + \lambda I B = (A+\lambda I)B
```

````
## Matrix equations

In this section we make the connection between matrices and linear systems of equations. Our aim is to find the general solution to the equation

$$Ax = b$$

where $A$ is an $(m \times n)$ matrix and $b \in \mathbb{R}^m$ and $x \in \mathbb{R}^n$ are vectors.

Such an equation is exactly equivalent to a linear system of $m$ equations in $n$ unknowns. For example, we can write the system

```{math}
\begin{alignat*}{4}
2x_1 & {}+{} & 3x_2 & {}-{} & 2x_3 & {}={} & 7 \\
  x_1 & {}-{} & x_2 & {}-{} & 3x_3 & {}={} & 5
\end{alignat*}
```
as the matrix equation

```{math}
\begin{pmatrix} 2 & 3 & -2\\
1 & -1 & -3\end{pmatrix}\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} = \begin{pmatrix}7\\5\end{pmatrix}.
```


````{admonition} Matrix Equation

The linear system of equations
```{math}
a_{1,1} x_1 + a_{1,2} x_2 + a_{1,3} x_3 + \dots + a_{1,n} x_n &= b_1 \\

a_{2,1} x_1 + a_{2,2} x_2 + a_{2,3} x_3 + \dots + a_{2,n} x_n &= b_2\\
                                                                     \vdots \\
 a_{m,1} x_1 + a_{m,2} x_2 + a_{m,3} x_3 + \dots + a_{m,n} x_n &= b_m
```

is equivalent to the matrix equation

$$Ax=b$$

where 
$A=\begin{pmatrix}
a_{1,1} & \cdots & a_{1,n}\\
\vdots & \ddots & \vdots\\
a_{m,1} & \cdots & a_{m,n}
\end{pmatrix}$, $x=\begin{pmatrix}x_1\\ \vdots \\ x_n\end{pmatrix}$ and $b=\begin{pmatrix}b_1\\ \vdots \\b_m\end{pmatrix}$
````

This equivalence means that we can move freely between these two ways of writing and thinking about a linear system.


## Matrix Inverses

Since a matrix represents a linear transformation, which is a function, we can consider if a matrix has an inverse. For example, consider the $(2 \times 2)$ matrix $R_{\pi/2}$ which represents a $\pi/2$ anticlockwise rotation about the origin:

$$R_{\pi/2} = \begin{pmatrix}0 & -1 \\1 & 0\end{pmatrix}.$$

Its inverse is a $\pi/2$ *clockwise* rotation about the origin, represented by the following matrix:

$$R_{3\pi/2} = \begin{pmatrix}0 & 1 \\-1 & 0\end{pmatrix}.$$

In general, if $A$ is an $n \times n$ matrix and $B$ is its inverse, then $B$ is also an $(n \times n)$ matrix which satisfies

$$ABx = x$$

for all $x \in \mathbb{R}^n$.

In other words, $AB$ is a matrix which leaves $x$ unchanged. The only matrix which leaves $x$ unchanged is the identity matrix $I$, and so we have the following definition of the inverse matrix.

```{admonition} Definition

Let $A$ be an $(n \times n)$ square matrix. If there is an $(n \times n)$ matrix $B$ such that

$$AB = BA = I_n$$

then $A$ is **invertible** and $B$ is the **inverse** of A.

We write $B = A^{-1}$.
```

```{figure} linear_transformations_8_0.png
---
width: 600px
name: inverse_transformation
---
If the matrix $A = R_{\pi/2}$ is a $\pi/2$ anticlockwise rotation about the origin then its inverse $A^{-1} = R_{3\pi/2}$ is a $\pi/2$ clockwise rotation about the origin. The matrix $A^{-1}A = I$ represents the identity transformation.
```

```{exercise}
:label: q_matrix_inverse_1

1. Show that $R_{3\pi/2}$ is the inverse of $R_{\pi/2}$.
2. What is the inverse of the matrix $R_{\theta}$ representing an anticlockwise rotation about the origin by $\theta$? Calculate $R_{\theta}R_{\theta}^{-1}$ and show that it equals the identity matrix.
3. Given that $C X D = E$, write down the solution for $X$ explicitly in terms of inverse matrices $C^{-1}$ and $D^{-1}$.
```

## Solving Matrix Equations

Suppose that we are given the definitions below and asked to compute the result for $B$ :

$$A=\left(\begin{array}{cc}1 & 2 \\2 & 1 \end{array}\right), \quad A B=\left(\begin{array}{cc}5 & 3 \\4 & 3 \end{array}\right)$$ (a_ab)

If this was ordinary scalar algebra, then $B$ would be given by $\frac{AB}{A}$, but we have not defined the concept of division for matrices. Indeed, we should recognise a difficulty in doing so, since matrix multiplication is not commutative. The problems $Q X = P$ and $X Q=P$ do not generally have the same solution, and so the expression $X=\frac{P}{Q}$ would be ambiguous.

The difficulty could be addressed by introducing separate concepts of "left-division" and "right-division", and some authors have done exactly this. However, a more fundamental approach is to abandon the idea of division for matrices altogether, and consider what it means for matrix multiplication to be invertible.

To illustrate the use of the inverse matrix, we multiply each side of the equation for $A B$ in {eq}`a_ab` by $A^{-1}$ as follows:

$$A^{-1}(AB)=A^{-1}\left(\begin{array}{cc}5&3\\4&3\end{array}\right)$$ (a_inverse_ab)

It is very important to recognise that we must do exactly the same thing to both sides of the equation. Since we pre-multiply (left multiply) the left-hand side by $A^{-1}$, we must also pre-multiply the right-hand side by $A^{-1}$.

Due to the non-commutative nature of matrix multiplication, the result $A^{-1}(A B)$ is not the same as the result $(A B)A^{-1}$.

Now, since matrix multiplication is associative, the left hand side of {eq}`a_inverse_ab` can be rewritten as $(A^{-1} A)B$, and by the definitions of the inverse and identity matrix, we can write $(A^{-1} A)B=I B=B$ in order to obtain

$$B=A^{-1}\left(\begin{array}{cc}5&3\\4&3\end{array}\right)$$

Thus, the result for $B$ can be determined by performing a matrix multiplication, provided that we can find $A^{-1}$.

```{admonition} Solving $AX=B$ and $XA=B$

Let $A$ be an invertible $(n \times n)$ square matrix and $B$ an ($n \times m)$ matrix. Then

$A X = B$ has solution $X=A^{-1}B $

$X A = B$ has solution $X=B A^{-1}$.
```

## Matrix Inverse
### Calculating the (2x2) inverse

The (2x2) matrix that satisfies the definition $A A^{-1} = A^{-1}A=I$ is outlined in the box below. In section 3.6 we will examine how the result may be derived from first principles, but for now you may simply verify the claim by checking the result of the products $A A^{-1}$ and $A^{-1}A$.

```{admonition} The inverse of a (2x2) matrix

The inverse of a (2x2) matrix $A=\left(\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right)$ is given by

$$A^{-1}=\frac{1}{\mathrm{det}(A)}\mathrm{adj}(A)$$

where

$$\mathrm{det}(A)=\left|\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right|=a_{11} a_{22}-a_{12} a_{21}$$

and

$$\mathrm{adj}(A)=\left(\begin{array}{cc}a_{22} & -a_{12} \\-a_{21} & a_{11} \end{array}\right)$$

Note that $\text{det}(A)$ is a scalar quantity.

$\text{det}(A)$ s referred to as the **determinant** of $A$. For a (2x2) matrix, the determinant is given by subtracting the product of the anti-diagonal elements from the product of the leading diagonal elements.  

$\text{adj}(A)$ is known as the **adjugate matrix**. For a (2x2) matrix, the adjugate is given by swapping the diagonal elements and multiplying the anti-diagonal elements by -1.

Notice the special notation $|A|$ that is used to denote the determinant of $A$.
```

```{exercise}
:label: q_twobytwo_inverse

1\. 	Calculate the determinant of the matrix $M=\left(\begin{array}{cc}2 & -1 \\3 & 4 \end{array}\right)$.

2\. 	Write the equations below in the form $Ax=b$:
\begin{align*}
2x-3y&=1\\
3x-2y&=2
\end{align*}

Calculate the coefficient matrix $A$ and hence obtain the solution for $x$

3\.	Solve the problem given in {eq}`a_ab` to find B.

```

### What it means if $\det(A)=0$

The value of the determinant can be used to infer whether a given linear system has a unique solution. If the determinant is zero then the matrix $A$ is not **invertible** and the problem will not have a unique solution.

To illustrate, we will consider two examples of a system of two equations in two unknowns:

$$\begin{array}{c}2 x-3 y&=1 \\9 y-6 x&=3 \end{array}$$ (inconsistent_1)
$$\begin{array}{c}2 x-3 y&=1 \\9 y-6 x&=-3 \end{array}$$ (inconsistent_2)

Both sets of equations can be written in the form $Ax=b$, where $A=\left(\begin{array}{cc}2 & -3 \\-6 & 9 \end{array}\right)$. In that case, $\det(A)=18-18=0$, which means that the inverse matrix cannot be calculated and the problems do not have a unique solution for $x$.

The two equations in {eq}`inconsistent_1` are inconsistent, and so there is no solution, whilst the two equations in {eq}`inconsistent_2` have an infinite number of solutions satisfying $y=\frac{2}{3}x-\frac{1}{3}$.

You can also think about this problem graphically. In general, the determinant of a (2x2) matrix $A$ is zero if and only if the second row is a constant multiple of the first row. For a problem of the form $Ax=b$, this means that the two lines have the same gradient. Either the equations represent distinct parallel lines, with no common points, or they represent the same line, with all points in common. In this example, both lines have gradient 2/3.

This brings us to an important theorem which ties together a lot of the ideas we have studied so far.

### Derivation of the (2x2) inverse from first principles

Consider the problem $A X = I$, which has solution $X=A^{-1}$. We can solve this problem applying row reduction operations (Gaussian elimination) to the augmented matrix $\biggr[\begin{array}{c|c}A&I\end{array}\biggr]$.

The algorithm proceeds as follows:

```{math}
\biggr[\begin{array}{c|c}A&I\end{array}\biggr]\quad \rightarrow \quad \biggr[\begin{array}{c|c}U&L\end{array}\biggr] \quad 
\rightarrow \quad \biggr[\begin{array}{c|c}I&A^{-1}\end{array}\biggr]
```
in which $U$ is an upper-diagonal matrix and $L$ is a lower-diagonal matrix.

For the (2x2) problem we start with the augmented matrix:

$$A=\left(\begin{array}{cc|cc}a_{11} & a_{12} & 1 & 0 \\a_{21} & a_{22} & 0 & 1 \\\end{array}\right)$$

the following row operations can be used:

1. $\hat{r}_2=r_2-r_1 a_{21}/a_{11}$
1. $\hat{r}_1=r_1/a_{11}$,    $\hat{r}_2=r_2 a_{11}/(a_{11}a_{22}-a_{12}a_{21})$
1. $\hat{r}_1=r_1-r_2 a_{12}/a_{11}$

We obtain

```{math}
\left[\begin{array}{cc|cc}a_{11}&a_{12}&1&0\\a_{21}&a_{22}&0&1\end{array}\right] \quad 
\Rightarrow \quad \left[\begin{array}{cc|cc}1&0&\frac{a_{22}}{a_{11}a_{22}-a_{12}a_{21}}&\frac{-a_{12}}{a_{11}a_{22}-a_{12}a_{21}}\\0&1&\frac{-a_{21}}{a_{11}a_{22}-a_{12}a_{21}}&\frac{a_{11}}{a_{11}a_{22}-a_{12}a_{21}}\end{array}\right]
```

from which the following result for the inverse matrix $A^{-1}$ is inferred:

$$A^{-1}=\frac{1}{a_{11} a_{22}-a_{12} a_{21}}\left(\begin{array}{cc}a_{22} & -a_{12} \\ -a_{22} & a_{11} \end{array}\right)$$

The steps that were carried out here were purely algebraic manipulations, and so we can see that the result for $A^{-1}$ can always be computed, 
providing that $a_{11} a_{22}-a_{12} a_{21}\neq 0$.

### The (3x3) inverse

We can extend the method used in the previous section to calculate the inverse of higher order matrices. For example, you could have a go at calculating the inverse of a general (3x3) matrix by Gaussian elimination. The algebra would get very tedious.

However, given the systematic nature of Gaussian elimination, you may not be surprised that there is a pattern that can be spotted, which allows the inverse to be calculated by a recursive method. The result is given in the box below.

```{admonition} The (3x3) inverse formula

The inverse of a (3x3) matrix $A$ is given by

$$A^{-1}=\frac{1}{\mathrm{det}(A)}\mathrm{adj}(A)=\frac{1}{\mathrm{det}(A)}C_A^T$$

where $\mathrm{adj}(A)$ is called the **adjugate** matrix and $C_A$ is the (3x3) matrix of cofactors given by

$$(C_A)_{i,j}=(-1)^{i+j}M_{i,j}.$$

The **minors** $M_{i,j}$ are the determinants of the (2x2) matrices formed by deleting the $i$th row and $j$th column of $A$.

The determinant satisfies both of the following results, so you can choose either:

$\displaystyle\mathrm{det}(A)=\sum_{j=1}^3{a_{i,j}C_{i,j}}$ for any choice of row $i$     (expansion by the ith row)

$\displaystyle\mathrm{det}(A)=\sum_{i=1}^3{a_{i,j}C_{i,j}}$ for any choice of row $j$     (expansion by the jth column)
```

Let's unpack this complicated definition by considering an example for

$$A=\left(\begin{array}{ccc}3 & -2 & 4 \\2 & -2 & 3 \\5 & -1 & 7 \end{array}\right)$$

Then, we have the following cofactors:

$${\scriptsize C_{1,1}=(-1)^{1+1}\left|\begin{array}{cc}-2&3\\-1&7\end{array}\right|=-11, \quad C_{1,2}=(-1)^{1+2}\left|\begin{array}{cc}2&3\\5&7\end{array}\right|=1, \quad C_{1,3}=(-1)^{1+3}\left|\begin{array}{cc}2&-2\\5&-1\end{array}\right|=8,}$$

$${\scriptsize C_{2,1}=(-1)^{2+1}\left|\begin{array}{cc}-2&4\\-1&7\end{array}\right|=10, \quad C_{2,2}=(-1)^{2+2}\left|\begin{array}{cc}3&4\\5&7\end{array}\right|=1, \quad C_{2,3}=(-1)^{2+3}\left|\begin{array}{cc}3&-2\\5&-1\end{array}\right|=-7,}$$

$${\scriptsize C_{3,1}=(-1)^{3+1}\left|\begin{array}{cc}-2&4\\-2&3\end{array}\right|=2, \quad C_{3,2}=(-1)^{3+2}\left|\begin{array}{cc}3&4\\2&3\end{array}\right|=-1, \quad C_{3,3}=(-1)^{3+3}\left|\begin{array}{cc}3&-2\\2&-2\end{array}\right|=-2.}$$

We can find the determinant by expansion of any row or column.

For instance, if we choose to expand by the first row (i=1), we obtain

$\mathrm{det}(A)=a_{1,1}C_{1,1}+a_{1,2}C_{1,2}+a_{1,3}C_{1,3} = 3(-11) -2(1) +4(8)=-3$

You may pick any other row or column to expand and you will obtain the same result. For instance, expanding by the third column gives

$\mathrm{det}(A)=a_{1,3}C_{1,3}+a_{2,3}C_{2,3}+a_{3,3}C_{3,3} = 4(8) +3(-7) +7(-2)=-3$

The inverse matrix is given by

$A^{-1}=\frac{-1}{3}\left(\begin{array}{ccc}-11&10&2\\1&1&-1\\8&-7&-2\end{array}\right)$

```{exercise}
:label: three_by_three_inverse

Calculate the inverse of the matrices $A$ and $B$. Check your answer by checking that $A^{-1}A=I$ and $B^{-1}B=I$.

1\.

$$A = \begin{pmatrix}3&0&2\\2&0&-2\\
0&1&1\end{pmatrix}$$

2\.

$$B = \begin{pmatrix}0&4&1\\0&2&1\\
1&1&1\end{pmatrix}$$
```

### Inverse of the Matrix Product

By associativity of matrix multiplication,

$$(A^{-1}B^{-1})(BA) = A^{-1}(B^{-1}B)A = A^{-1}IA=A^{-1}A=I$$

Therefore,

$$(BA)^{-1} = A^{-1}B^{-1}$$

This result satisfies the "common sense" idea (seen in function composition) that inversion comes in reverse order. If transform B follows transform A then we have to reverse transform B before reversing A. We remove the outer operation first.

We can liken the result to the operation of getting dressed/undressed: If you put your socks on before your shoes, you have to take your shoes off before you can remove your socks!



