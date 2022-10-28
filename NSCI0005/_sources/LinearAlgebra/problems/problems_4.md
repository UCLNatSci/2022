# Linear Algebra Problems 4

<!-- https://textbooks.math.gatech.edu/ila/diagonalization.html Example (A diagonalisable 2 x 2 matrix) -->

<!--
Diagonalise the matrix

$$A = \begin{pmatrix}4&-3&0\\2&-1&0\\1&-1&1\end{pmatrix}.$$
-->
## Question 1

Let

$$H = \begin{pmatrix}\frac{7}{8}&-\frac{3\sqrt{3}}{8}\\-\frac{3\sqrt{3}}{8}&\frac{13}{8}\end{pmatrix}.$$

1\. Calculate the eigenvalues and eigenvectors of $H$.

2\. Write down an invertible matrix $X$ and diagonal matrix $\Lambda$ such that

$$H = X\Lambda X^{-1}$$

3\. Describe in words the geometrical effect of each of the matrices $X^{-1}$, $\Lambda$ and $X$.

## Question 2

<!-- https://yutsumura.com/two-matrices-with-the-same-characteristic-polynomial-diagonalize-if-possible/ -->

Let

$$A = \begin{pmatrix}1&3&3\\-3&-5&-3\\3&3&1\end{pmatrix}$$

and

$$B = \begin{pmatrix}2&4&3\\-4&6&-3\\3&3&1\end{pmatrix}.$$

1. Show that $1$ and $2$ are eigenvalues of both matrices.
2. Calculate the characteristic polynomials of $A$ and $B$ and show that they are equal [you don't need to calculate a determinant to solve this - check the notes for a useful trick].
3. Find all eigenvectors of $A$.
4. Find all eigenvectors of $B$.
5. Which of $A$ and $B$ is diagonalisable?
6. Diagonalise the matrix stated in 5.

## Question 3

<!-- https://yutsumura.com/diagonalize-the-upper-triangular-matrix-and-find-the-power-of-the-matrix/#more-5074 -->

Let

$$A = \begin{pmatrix}a&b-a\\0&b\end{pmatrix}.$$

1. Find the eigenvalues of $A$.
2. For each eigenvalue of $A$, determine the eigenvectors.
3. Diagonalise $A$.
4. Calculate $A^k$ for $k\in \mathbb{N}$.

## Question 4

Let

$$M = \begin{pmatrix}a&b\\c&d\end{pmatrix}.$$

Recall that $\mathrm{tr}(M)$ is the sum of the diagonal entries of $M$.

1. Derive an expression for the eigenvalues of $M$ in terms of $\mathrm{tr}(M)$ and $\det(M)$.
2. Hence find conditions on $\mathrm{tr}(M)$ and $\det(M)$ such that $A$ has
    (a) two distinct real eigenvalues
    (b) exactly one real eigenvalue
    \(c\) no real eigenvalue.

## Question 5

The *Fibonacci Sequence* is the sequence

$$0, 1, 2, 3, 5, 8, 11, \ldots$$

where each element $F_i$ is the sum of the previous two. That is,

$$F_{i} = F_{i-2} + F_{i-1}$$

where $F_0 = 0$ and $F_1 = 1$.

Let $u_i$ be a vector comprising two consecutive elements:

$$u_i = \begin{pmatrix}F_{i+1}\\F_{i}\end{pmatrix}.$$

1\. Determine the $(2 \times 2)$ matrix $A$ such that

$$u_{i+1} = A u_i.$$

2\. Calculate the two eigenvalues $\lambda_1$ and $\lambda_2$ and show that the corresponding eigenvectors are

$v_1 = \begin{pmatrix}\lambda_1\\1\end{pmatrix}$ and $v_2 = \begin{pmatrix}\lambda_2\\1\end{pmatrix}$.

3\. Write down an invertible matrix $X$ and diagonal matrix $\Lambda$ such that

$$A = X\Lambda X^{-1}.$$

4\. Show that

$$u_{100}=\frac{\lambda_1^{100}v_1 - \lambda_2^{100}v_2}{\lambda_1-\lambda_2}.$$

5\. Argue that $\lambda_2^{100} \approx 0$ and hence show that the 100th Fibonacci number $F_{100}$ is the nearest whole number to $\frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{100}$.

6\. Calculate the value of the limit

$$\lim_{i\to \infty}F_{i+1}/F_i.$$

## Question 6

Let

$$A = \begin{pmatrix}5&4\\4&5\end{pmatrix}\qquad\mathrm{and}\qquad B=\begin{pmatrix}4&5\\5&4\end{pmatrix}.$$

1\. Find invertible matrices $X_A$ and $X_B$ and diagonal matrices $\Lambda_A$ and $\Lambda_B$ such that

$$A = X_A\Lambda_AX_A^{-1}\qquad\mathrm{and}\qquad B = X_B\Lambda_BX_B^{-1}.$$

2\. A *matrix square root* of a matrix $M$ is a matrix $S$ such that $S^2=M$. Find the matrix square root of $A$. Why is there no real matrix square root of $B$?
