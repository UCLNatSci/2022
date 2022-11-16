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

$ \left( \begin{matrix} 1 & -3 & 5\\ 2 & -1 & 7\end{matrix} \right) $  is a (2 x 3) matrix, whereas $ \left( \begin{matrix} 1 & -3 \\ 2 & -1 \\ 5 & 7\end{matrix} \right) $ is a (3 x 2) matrix.

This measurement is properly referred to as the **order** of a matrix, but is also often referred to as the **size**.  The individual values in a matrix are called 
**elements**, so in the matrix $ M = \left( \begin{matrix} 1 &2 &3 \\ 4& 5& 6\end{matrix} \right) $ we can say that the element in the $2^{nd}$ row and $3^{rd}$ column 
is the number 6. Subscripts can be used to refer to the elements, by writing $ M_{2,3} = 6$ for example.

The **transpose** of a matrix, written with a superscript letter T, means that we swap the rows and columns,:

```{math}
M = \left( \begin{matrix} 1 &2 &3 \\ 4& 5& 6\end{matrix} \right) \Rightarrow M^T = \left( \begin{matrix} 1 & 4 \\ 2 & 5  \\ 3 & 6\end{matrix} \right)
```

In element notation, for any matrix $X$, we can write that $\left(X^T\right)_{i,j} = X_{j,i}$.  That is, the element in the $i^{th}$ row and $j^{th}$ column of $X$ becomes the element in the $j^{th}$ row and $i^{th}$ column of $X^T$.

The order of a matrix is reversed when it it transposed.

In a square matrix, two diagonals are called the **main diagonal** (top-left two bottom right), and the **anti-diagonal** (bottom-left to top-right). Square matrices for which $A_{i,j}=A_{j,i}$ are called **symmetric matrices**.

An **upper-triangular matrix** is a square matrix in which the elements below the main diagonal are all zero, and a **lower-triangular matrix** is one where the elements above the main diagonal are all zero.

A **diagonal matrix** is one in which all of the elements are zero apart from those on the main diagonal. These type of matrices are very special, since they have "nice" properties for the purpose of matrix algebra.    

````{admonition} Practice Questions
:class: seealso, dropdown

1\. What is the order of each of the matrices shown?

$A=\left(\begin{array}{cc}0 & -1 \\2 & 3 \\-1 & 0 \\\end{array}\right), \quad b=\left(\begin{array}{c}1 \\2 \\3 \\\end{array}\right), \quad c=0$.

2\. Given the matrix:

```{math}
X=\left(\begin{array}{ccc}-3 & 4 & 0 \\1 & 1 & 2 \\7 & -4 & 3 \\\end{array}\right)
```

what element is represented by $(X^T)_{2,3}$ ?

3\. Which of the following matrices is an upper-triangular matrix?

```{math}
A=\left(\begin{array}{cccc}2&8&-1&0\\0&2&2&2\\0&0&1&-5\\0&0&0&3\end{array}\right), \quad B=\left(\begin{array}{cccc}1&-2&5&2\\3&6&-2&0\\8&2&0&0\\-2&0&0&0\end{array}\right), \quad C=\left(\begin{array}{ccc}6&0&0\\-3&-4&0\\2&7&7\end{array}\right)
```
````

````{admonition} Solutions
:class: seealso, dropdown

1\. Order of $A = $ (3x2)
Order of $b = $ (3x1)
Order of $c = $ (1x1)

2\. 
```{math}
X^T=\left(\begin{array}{ccc}-3 & 1 & 7 \\4 & 1 & -4 \\0 & 2 & 3 \\\end{array}\right)
```

Hence $(X^T)_{2,3} = -4$

3\. Matrix $A$ is in upper-triangular form.
````

## Matrix algebra

We will look at how real number algebra, such as addition and multiplication, can be extended to work with matrices. These are entirely human constructs, and you may be easily forgiven for asking why do we do it this way?

However, the best way to appreciate the practicalities is by tackling some problems, and so the definitions will first be introduced without much explanation. From a mathematical perspective, we simply note that the definitions must be consistent and well-determined (unambiguous).

### Multiplication by a scalar

Let $\lambda$ be a scalar (a single number) and $M$ be a matrix. Then $\lambda M$ means that every element in matrix $M$ is multiplied by $\lambda$. This can be written in element notation as follows:

$$ (\lambda M)_{i,j} = \lambda M_{i,j}$$

For example:
```{math}
-3\left( \begin{matrix} 0 & -2 \\ 1 & 5 \\ -1 & 3 \end{matrix} \right) = \left( \begin{matrix} 0 & 6 \\ -3 & -15 \\ 3 & -9 \end{matrix} \right)
```

### Addition

Let $A$ and $B$ be two matrices of the same order. Then,

$$\left(A + B\right)_{i,j} = A_{i,j} + B_{i,j}$$

The expression states that to add two matrices, we add together the corresponding elements. This type of operation on two matrices can be referred to as an element-wise operation.

For example:
```{math}
\left( \begin{matrix} 1 & -3 \\ 3 & 0 \\ 5 & -7 \end{matrix} \right) + \left( \begin{matrix} 0 & 6 \\ -3 & -15 \\ 3 & -9 \end{matrix} \right) 
= \left( \begin{matrix} 1 & 3 \\ 0 & -15 \\ 8 & -16 \end{matrix} \right)
```

The element-wise property means that only matrices of the same order can be added, and the expressions below are both meaningless:

```{math}
\left( \begin{matrix} 1 & 2 \end{matrix} \right) &+ \left( \begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix} \right)\\
\left( \begin{matrix} 1 & 2 \\ 3 & 4 \end{matrix} \right) &+ 1
```

Matrix addition can be combined with multiplication by a scalar to add multiples of one matrix to another.

For example:
```{math}
\left( \begin{matrix} 1 & -3 \\ 3 & 0 \\ 5 & -7 \end{matrix} \right) - 3\left( \begin{matrix} 0 & -2 \\ 1 & 5 \\ -1 & 3 \end{matrix} \right) 
= \left( \begin{matrix} 1 & 3 \\ 0 & -15 \\ 8 & -16 \end{matrix} \right)
```

````{admonition} Practice Questions
:class: seealso, dropdown

Given the matrices:
```{math}
A=\left(\begin{array}{cc}1 & 2 \\-1 & 0 \\3 & 1 \\\end{array}\right), 
\quad B=\left(\begin{array}{cc}-4 & 1 \\1 & 2 \\-2 & 3 \\\end{array}\right), 
\quad C=\left(\begin{array}{cc}0 & 3 \\4 & 2 \\1 & 1 \\\end{array}\right),
\quad D=\left(\begin{array}{cc}5 & 1 \\3 & 2 \\\end{array}\right)
```
What will be the result of the following expressions?

1. $\left(A+B\right)+C$
2. $(C+B)+A$
3. $A-2B+\frac{1}{2}C$
4. $A+D$

````

````{admonition} Solutions
:class: seealso, dropdown

1\.
```{math}
\left(A+B\right)+C=\left(\begin{array}{cc}-3 & 3 \\0 & 2 \\1 & 4 \\\end{array}\right) + \left(\begin{array}{cc}0 & 3 \\4 & 2 \\1 & 1 \\\end{array}\right) = 
\left(\begin{array}{cc}-3 & 6 \\4 & 4 \\2 & 5 \\\end{array}\right)
```

2\.
```{math}
\left(A+B\right)+C=\left(\begin{array}{cc}-4 & 4 \\5 & 4 \\-1 & 4 \\\end{array}\right) + \left(\begin{array}{cc}1 & 2 \\-1 & 0 \\3 & 1 \\\end{array}\right) = 
\left(\begin{array}{cc}-3 & 6 \\4 & 4 \\2 & 5 \\\end{array}\right)
```

3\.
```{math}
A-2B+\frac{1}{2}C = \left(\begin{array}{cc}1 & 2 \\-1 & 0 \\3 & 1 \\\end{array}\right) + \left(\begin{array}{cc}-8 & 2 \\2 & 4 \\-4 & 6 \\\end{array}\right) + 
\left(\begin{array}{cc}0 & 3/2 \\2 & 1 \\1/2 & 1/2 \\\end{array}\right) = \left(\begin{array}{cc}-7 & 11/2 \\3 & 5 \\-1/2 & 15/2 \\\end{array}\right)
```

4\. Cannot add matrices of different orders together.


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

```{math}
A&=\left(\begin{array}{ccc}3 & 1 & -2 \\0 & 2 & 4 \\\end{array}\right), \quad 
B=\left(\begin{array}{cc}2 & 3 \\-3 & 0 \\1 & 1 \\\end{array}\right)\\
C&=\left(\begin{array}{cccc}1 & -8 & 2 & 11 \\0 & 4 & -3 & -7 \\6 & 1 & 8 & 1 \\\end{array}\right),\quad   
D=\left(\begin{array}{ccc}1 & 2 & 3 \\1 & 1 & 1 \\2 & 0 & 1 \end{array}\right)
```

1\. Calculate $AB$ and $BA$, are these results the same?

2\. Explain why the result $A\left(\begin{array}{c}1\\2\end{array}\right)$ cannot be calculated.

3\. What will be the order of the matrix $A C$?

4\. Calculate the element in the second row and third column of $AC$

5\. Calculate the result $D^2$ (this question is a bit boring, but good practice!)
````

````{admonition} Solutions
:class: seealso, dropdown

1\. 
```{math}
AB &= \begin{pmatrix}3 & 1 & -2 \\0 & 2 & 4 \end{pmatrix}\begin{pmatrix}2 & 3 \\-3 & 0 \\1 & 1 \end{pmatrix}
= \begin{pmatrix} 1 & 7  \\ -2 & 4 \end{pmatrix}\\
BA &= \begin{pmatrix}2 & 3 \\-3 & 0 \\1 & 1 \end{pmatrix}\begin{pmatrix}3 & 1 & -2 \\0 & 2 & 4 \end{pmatrix}
= \begin{pmatrix} 2 & 8 & 10\\ -9 & -3 & 6\\ 3 & 3 & 2\end{pmatrix}
```
Hence $AB \neq BA$!

2\. The nunber of columns in $A$ do not match the number of rows in $\left(\begin{array}{c}1\\2\end{array}\right)$, so 
it is unclear what to do with the additional numbers in $A$!

3\. $AC$ is a $(2 \times 3) \times (3 \times 4) = (2 \times 4)$ matrix.

4\. $A_{2,3} = 4$

5\.
```{math}
D^2=\left(\begin{array}{ccc}1 & 2 & 3 \\1 & 1 & 1 \\2 & 0 & 1 \end{array}\right)\left(\begin{array}{ccc}1 & 2 & 3 \\1 & 1 & 1 \\2 & 0 & 1 \end{array}\right)
= \left(\begin{array}{ccc}10 & 3 & 8 \\4 & 3 & 5 \\4 & 4 & 7 \end{array}\right)
```
````

### Properties of matrix multiplication

Matrix multiplication is **associative**, that is:

```{math}
A (B C)\equiv (A B)C
```

This can be proved by showing that the left and right hand sides are the same order, and that 
```{math}
(A(B C))_{i,j}=((A B)C)_{i,j}
```

````{warning}
Matrix multiplication is **NOT commutative**, that is
```{math}
\begin{array}{c}A B\neq B A \end{array}
```
although $AB$ and $BA$ may be equal in some special cases, but not in general!
````

````{admonition} Worked Example
:class: seealso

```{math}
\left(\begin{array}{cc}1 & 2 \\-3 & 0 \end{array}\right) \left(\begin{array}{cc}2 & 1 \\1 & 2 \\\end{array}\right)
&=\left(\begin{array}{cc}1\ 2+2\ 1 & 1\ 1+2\ 2 \\0\ 1-3\ 2 & 0\ 2-3\ 1\end{array}\right)=\left(\begin{array}{cc}4 & 5 \\-6 & -3 \\\end{array}\right) \\
\left(\begin{array}{cc}2 & 1 \\1 & 2 \\\end{array}\right) \left(\begin{array}{cc}1 & 2 \\-3 & 0 \end{array}\right)
&=\left(\begin{array}{cc}2\ 1+1 (-3) & 2\ 2+1\ 0 \\1\ 1+2 (-3) & 1\ 2+2\ 0 \end{array}\right)=\left(\begin{array}{cc}-1 & 4 \\-5 & 2 \\\end{array}\right)
```
````

## The identity matrix

````{admonition} Definition

The **identity matrix**

$$I_n = \begin{pmatrix}1 & 0 & \cdots & 0\\0 & 1 & \cdots & 0\\\vdots & \vdots & \ddots & \vdots\\0& 0 & \cdots & 1\end{pmatrix}.$$

We usually drop the subscript $n$ when working with the identity matrix, because the order can be inferred.
````
The identity matrix $I_n$ is the unique $(n \times n)$ matrix which has the property

$$I_n x = x $$

for any $x \in \mathbb{R}^n$.

The identity matrix transforms the vector $x$ to itself. It plays the same role in matrix multiplication as the number 1 does for multiplication of real numbers.



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


## Matrices and simultaneous equations

We can make the connection between matrices and linear systems of equations, our aim is to find the general solution to the equation:

```{math}
Ax = B
```

where $A$ is an $(m \times n)$ matrix and $b \in \mathbb{R}^m$ and $x \in \mathbb{R}^n$ are vectors.

Such an equation is exactly equivalent to a linear system of $m$ equations in $n$ unknowns. For example, we can write the system

```{math}
\begin{alignat*}{4}
2x_1 & {}+{} & 3x_2 & {}-{} & 2x_3 & {}={} & 7 \\
  x_1 & {}-{} & x_2 & {}-{} & 3x_3 & {}={} & 5 \\
  -x_1 & {}-{} & 2x_2 & {}-{} & x_3 & {}={} & 1 \\
\end{alignat*}
```
as the matrix equation

```{math}
\begin{pmatrix} 
2 & 3 & -2\\
1 & -1 & -3\\
-1 & 2 & 1
\end{pmatrix}
\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} 
= \begin{pmatrix}
7\\
5\\
1
\end{pmatrix}.
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

where:
$A=\begin{pmatrix}
a_{1,1} & \cdots & a_{1,n}\\
\vdots & \ddots & \vdots\\
a_{m,1} & \cdots & a_{m,n}
\end{pmatrix}$, $x=\begin{pmatrix}x_1\\ \vdots \\ x_n\end{pmatrix}$ and $b=\begin{pmatrix}b_1\\ \vdots \\b_m\end{pmatrix}$
````

This equivalence means that we can move freely between these two ways of writing and thinking about a linear system.

## Matrix determinant

The determinant is a single number calculated from a square matrix. The determinant tells us whether the matrix is invertible, as well as a lot of other 
useful information about the matrix.  We find that calcualtign the determinant for (2×2) and (3×3) matrices most useful with a number of direct applications, 
in this section we will study properties of the determinant and methods for calculating it.


````{admonition} (2x2) Determinant
For a (2x2) matrix, the determinant is given by subtracting the product of the anti-diagonal elements from the product of the leading diagonal 
elements. 

Thus the determinant of a (2x2) matrix $A$: 
```{math}
A=\left(\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right)
``` 
is given by:
```{math}
\mathrm{det}(A)=\left|\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right|=a_{11} a_{22}-a_{12} a_{21}
```
This is also written as $\text{det}(A)$ and/or with the notation $|A|$.

We note that $\text{det}(A)$ is a scalar quantity.
````
````{admonition} (3x3) Determinant
For a (3x3) matrix $A$:
```{math}
A=\left(\begin{array}{ccc}a_{11} & a_{12} &a_{13}\\a_{21} & a_{22}& A_{23} \\ a_{31} & a_{23} & a_{33}\end{array}\right)
``` 
the matrix determinant can be found by finding the determinants of each minor of the matrix $A$:
```{math}
\begin{align}
  |A| = \begin{vmatrix} a & b & c \\ d & e & f \\ g & h & i \end{vmatrix}
     &= a\,\begin{vmatrix} e & f \\ h & i \end{vmatrix} -
        b\,\begin{vmatrix} d & f \\ g & i \end{vmatrix} +
        c\,\begin{vmatrix} d & e \\ g & h \end{vmatrix} \\[3pt]
     &= a(ei - fh) + b(fg - di) + c(dh - eg)
\end{align}
```
This represents just one way to find the minor matrices, we could also pick any other row, column (or even diagonal) and construct the matrix of minors from $A$ 
and then find these determinants.
````



### Properties of matrix determinants

Let $A$ be an $(n \times n)$ matrix:

1\. The determinant of the identity matrix is always 1.

2\. The determinant reverses sign when any two rows are exchanged.

3\. The determinant is a linear function of each of the rows.

4\. If one row is equal to another row then $\det(A)=0$.

5\. Adding a multiple of one row to another row leaves $\det(A)$ unchanged.

6\. If $A$ has a zero row then $\det(A)=0$.

7\. If $A$ is triangular then $\det(A)$ is the product of the diagonal elements.

8\. $A$ is invertible if and only if $\det(A)\neq 0$.

9\. $\det(AB) = \det(A)\det(B)$.

10\. $\det(A^{T}) = \det(A).$



## Matrix Inverses


```{admonition} Definition

Let $A$ be an $(n \times n)$ square matrix. If there is an $(n \times n)$ matrix $B$ such that

$$AB = BA = I_n$$

then $A$ is **invertible** and $B$ is the **inverse** of A.

We write $B = A^{-1}$.
```
In general, if $A$ is an $n \times n$ matrix and $B$ is its inverse, then $B$ is also an $(n \times n)$ matrix which satisfies

$$ABx = x$$

for all $x \in \mathbb{R}^n$.

In other words, $AB$ is a matrix which leaves $x$ unchanged. The only matrix which leaves $x$ unchanged is the identity matrix $I$.


### Solving Matrix Equations

Suppose that we are given the definitions below and asked to compute the result for $B$ :

```{math}
:label: a_ab
A=\left(\begin{array}{cc}1 & 2 \\2 & 1 \end{array}\right), \quad A B=\left(\begin{array}{cc}5 & 3 \\4 & 3 \end{array}\right)
``` 

If this was ordinary scalar algebra, then $B$ would be given by $\displaystyle \frac{AB}{A}$, but we have not defined the concept of division for matrices. 

Indeed, we should recognise a difficulty in doing so, since matrix multiplication is not commutative. The problems $Q X = P$ and $X Q=P$ do not generally 
have the same solution, and so the expression $\displaystyle X=\frac{P}{Q}$ would be ambiguous.  

This difficulty could be addressed by introducing separate concepts of "left-division" and "right-division", and some authors have done exactly this. However, a more 
fundamental approach is to abandon the idea of division for matrices altogether, and consider what it means for matrix multiplication to be invertible.  To illustrate 
the use of the inverse matrix, we multiply each side of the equation for $A B$ in {eq}`a_ab` by $A^{-1}$ as follows:

```{math}
:label: a_inverse_ab
A^{-1}(AB)=A^{-1}\left(\begin{array}{cc}5&3\\4&3\end{array}\right) 
```

It is very important to recognise that we must do exactly the same thing to both sides of the equation. Since we pre-multiply (left multiply) the 
left-hand side by $A^{-1}$, we must also pre-multiply the right-hand side by $A^{-1}$.  Due to the non-commutative nature of matrix multiplication, the 
result $A^{-1}(A B)$ is not the same as the result $(A B)A^{-1}$.  Now, since matrix multiplication is associative, the left hand side of {eq}`a_inverse_ab` can be 
rewritten as $(A^{-1} A)B$, and by the definitions of the inverse and identity matrix, we can write $(A^{-1} A)B=I B=B$ in order to obtain

```{math}
B=A^{-1}\left(\begin{array}{cc}5&3\\4&3\end{array}\right)
```

Thus, the result for $B$ can be determined by performing a matrix multiplication, provided that we can find $A^{-1}$.

```{admonition} Solving $AX=B$ and $XA=B$

Let $A$ be an invertible $(n \times n)$ square matrix and $B$ an ($n \times m)$ matrix. Then:

$A X = B$ has solution $X=A^{-1}B $

$X A = B$ has solution $X=B A^{-1}$.
```

````{admonition} Worked example
:class: seealso

Given that $C\, X\, D = E$, write down the solution for $X$ explicitly in terms of inverse matrices $C^{-1}$ and $D^{-1}$.

```{math} 
C\,X\,D &= E\\
C^{1} C\,X\,D &= X\,D = C^{-1}\,E\\
X\,D\,D^{-1} &= X = C^{-1}\,E\,D^{-1}
```
````

### Calculating the (2x2) inverse matrix
````{admonition} The inverse of a (2x2) matrix

The inverse of a (2x2) matrix $A=\left(\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right)$ is given by

$$A^{-1}=\frac{1}{\mathrm{det}(A)}\mathrm{adj}(A)$$

and

$$\mathrm{adj}(A)=\left(\begin{array}{cc}a_{22} & -a_{12} \\-a_{21} & a_{11} \end{array}\right)$$

$\text{adj}(A)$ is known as the **adjugate matrix**. For a (2x2) matrix, the adjugate is given by swapping the diagonal elements and 
multiplying the anti-diagonal elements by -1.

````

````{admonition} Practice Questions
:class: seealso, dropdown

1\. 	Calculate the determinant of the matrix $M=\left(\begin{array}{cc}2 & -1 \\3 & 4 \end{array}\right)$.

2\. 	Write the equations below in the form $Ax=b$:
```{math}
\begin{align*}
2x-3y&=1\\
3x-2y&=2
\end{align*}
```
Calculate the coefficient matrix $A$ and hence obtain the solution for $x$
````

````{admonition} Solutions
:class: seealso, dropdown

1\. 	
```{math}
\det(M)=\left|\begin{array}{cc}2 & -1 \\3 & 4 \end{array}\right| = 2\times 4 - (-1)\times 3 = 11
```

2\. 	
```{math}
\begin{pmatrix}
2 & -3 \\
3 & -2 
\end{pmatrix}
\begin{pmatrix}
x \\
y
\end{pmatrix}
= \begin{pmatrix}
1 \\
2
\end{pmatrix} 
```
```{math}
A^{-1} = \frac{1}{3}\begin{pmatrix}
-2 & 3 \\
-3 & 2
\end{pmatrix} \Rightarrow 
\begin{pmatrix}
x \\
y
\end{pmatrix} = A^{-1} = \frac{1}{5}\begin{pmatrix}
-2 & 3 \\
-3 & 2
\end{pmatrix} \begin{pmatrix}
1 \\
2
\end{pmatrix} =
\begin{pmatrix}
4/5 \\
1/5
\end{pmatrix} 

```

Calculate the coefficient matrix $A$ and hence obtain the solution for $x$


````

### A derivation of the (2x2) matrix inverse 

Consider the problem $A X = I$, which has solution $X=A^{-1}$. To see how this arises in the (2x2) case, lets think back to simultaneous equations, trying to solve $Ax = B$:

```{math}
:label: simuleq
\begin{alignat*}{3}
a_{11}x_1 & {}+{} & a_{12}x_2 & {}={} & b_1 \\
a_{21}x_1 & {}+{} & a_{22}x_2 & {}={} & b_2 \\
\end{alignat*}
```
which we can write as a matrix equation:

```{math}
\left(\begin{array}{cc}a_{11} & a_{12} \\a_{21} & a_{22} \end{array}\right)\,\begin{pmatrix}x_1\\x_2\end{pmatrix} 
= \begin{pmatrix}
b_1\\
b_2
\end{pmatrix}
```
Therefore to solve for $x = A^{-1}B$ we could just invert the siultaneous equations to find the solutions - in general this is best done with the process of row reduction 
operations (also called Gaussian elimination), but you will study more on this in future courses.

Taking {eq}`simuleq` and multiplying between lines to have a common factor in the $x_1$ term:
```{math}
\begin{alignat*}{3}
a_{11}\,a_{21}x_1 & {}+{} & a_{12}\,a_{21}x_2 & {}={} & a_{21}\,b_1 \\
a_{21}\,a_{11}x_1 & {}+{} & a_{22}\,a_{11}x_2 & {}={} & a_{11}\,b_2 \\
\end{alignat*}
```
and then subtracting:
```{math}
x_2 = \frac{-a_{21}\,b_1+a_{11}\,b_2}{a_{11}\,a_{22}-a_{12}\,a_{21}}
```
and doing the same procedure to the $x_2$ term:
```{math}
\begin{alignat*}{3}
a_{11}\,a_{22}x_1 & {}+{} & a_{12}\,a_{22}x_2 & {}={} & a_{22}\,b_1 \\
a_{21}\,a_{12}x_1 & {}+{} & a_{22}\,a_{12}x_2 & {}={} & a_{12}\,b_2 \\
\end{alignat*}
```
and then subtracting:
```{math}
x_1 = \frac{a_{22}\,b_1-a_{12}\,b_2}{a_{11}\,a_{22}-a_{12}\,a_{21}}
```
where we recognise that $\det(A) = a_{22}\,a_{11} - a_{12}\,a_{21}$ and therefore rewriting this as a set of matrix equations:

```{math}
\begin{pmatrix}x_1\\x_2\end{pmatrix} 
= \frac{1}{\det{A}}\left(\begin{array}{cc}a_{22} & -a_{12} \\-a_{21} & a_{11} \end{array}\right)\,\begin{pmatrix}
b_1\\
b_2
\end{pmatrix}
```

which is indeed the matrix inverse for a $(2x2)$ matrix.



### Inverse of the Matrix Product

By associativity of matrix multiplication:

```{math}
(A^{-1}B^{-1})(BA) = A^{-1}(B^{-1}B)A = A^{-1}IA=A^{-1}A=I
```

Therefore we can see that:

```{math}
(BA)^{-1} = A^{-1}B^{-1}
```

This result satisfies the "common sense" idea (seen in function composition) that inversion comes in reverse order. If transform $B$ follows transform $A$ 
then we have to reverse transform B before reversing A. We remove the outer operation first.

We can liken the result to the operation of getting dressed/undressed: If you put your socks on before your shoes, you have to take your shoes off before 
you can remove your socks!

