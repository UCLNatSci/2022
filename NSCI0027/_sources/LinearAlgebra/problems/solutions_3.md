# Linear Algebra Answers 3

## Question 10

1\. Let's start with $K_4$. We will use Gaussian elimination to reduce $K_4$ to triangular form:

$$
\begin{pmatrix}2&-1&0&0\\-1&2&-1&0\\0&-1&2&-1\\0&0&-1&2\\\end{pmatrix} \xrightarrow{r_2+\frac{1}{2}r_1\rightarrow r_2}
\begin{pmatrix}2&-1&0&0\\0&3/2&-1&0\\0&-1&2&-1\\0&0&-1&2\\\end{pmatrix}\\
\xrightarrow{r_3+\frac{2}{3}r_2\rightarrow r_3} \begin{pmatrix}2&-1&0&0\\0&3/2&-1&0\\0&0&4/3&-1\\0&0&-1&2\\\end{pmatrix} \xrightarrow{r_4+\frac{3}{4}r_3\rightarrow r_4} \begin{pmatrix}2&-1&0&0\\0&3/2&-1&0\\0&0&4/3&-1\\0&0&0&5/4\\\end{pmatrix}.
$$

By the [properties of determinants](https://uclnatsci.github.io/Mathematics-for-Natural-Sciences-2/LinearAlgebra/linear_systems_matrices/determinants.html#properties-of-determinants) we know that adding multiples of rows to another row does not affect the determinant (property 5) and that the determinant of a triangular matrix is the product of its diagonal entries (property 7). Therefore,

$$\det(K_4) = 2 \times 3/2 \times 4/3 \times 5/4 = 5.$$

Extending this procedure to $K_n$:

$$\begin{pmatrix}2&-1&&&& \\-1&2&-1&&&\\&-1&2&&&\\&&&\ddots&&\\&&&&2&-1\\&&&&-1&2\end{pmatrix} \xrightarrow{\text{row reduction}} \begin{pmatrix}2&-1&&&\\&3/2&-1&&\\&&4/3&&\\&&&\ddots&\\&&&&\frac{n+1}{n}\end{pmatrix}.$$

Therefore,

$$\det{K_n} = 2 \times 3/2 \times 4/3 \times \cdots \times \frac{n+1}{n} = n + 1.$$

2\. Let's start with $K_2$:

$$\det(K_2) &= \begin{vmatrix}2&-1\\-1&2\end{vmatrix} = 4-1=3.$$

To calculate $\det(K_3)$ use cofactor expansion along the top row:

$$
\det(K_3) = \begin{vmatrix}2&-1&0\\-1&2&-1\\0&-1&2\end{vmatrix} = 2\begin{vmatrix}2&-1\\-1&2\end{vmatrix}-(-1)\begin{vmatrix}-1&-1\\0&2\end{vmatrix} = 2\det(K_2)-2=4.$$

To calculate $\det(K_4)$ use cofactor expansion along the top row to write it as two $3 \times 3$ determinants:

$$\begin{align*}\det(K_4) &= \begin{vmatrix}2&-1&0&0\\-1&2&-1&0\\0&-1&2&-1\\0&0&-1&2\end{vmatrix}\\
 &= 2\begin{vmatrix}2&-1&0\\-1&2&-1\\0&-1&2\end{vmatrix}-(-1)\begin{vmatrix}-1&-1&0\\0&2&-1\\0&-1&2\end{vmatrix}.\end{align*}$$

The first determinant is just $\det(K_3)$. Expand the second along the first column to see that it equals $-\det(K_2)$. Thus:

$$\det(K_4) = 2\det(K_3)-\det(K_2) = 2 \times 4 - 3 = 5.$$

We see that we can write $\det(K_4)$ in terms of $\det(K_3)$ and $\det(K_2)$, and in fact in general

$$\det(K_n) = 2\det(K_{n-1})-\det(K_{n-2}).$$

(If you aren't convinced of this, try calculating $\det(K_5)$ using the same method).

Given $\det(K_2) = 3$ and $\det(K_3) = 4$, applying this iterative formula gives the sequence $3, 4, 5, ...$ so that $\det(K_n) = n+1$. [We can prove this easily using mathematical induction, and you are encouraged to do so if you are familiar with the technique].
