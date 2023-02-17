# Linear Systems of Equations

## Gaussian Elimination

The technique studied here makes solving large systems of equations (e.g. 200 equations in 200 unknowns) practical, and it can be implemented on a computer in a basic programming language. You might be surprised to learn that it is necessary to solve vast systems of linear equations as a matter of routine in many practical scientific applications.

### Motivation

Gaussian elimination is a systematic technique for solving systems of linear equations, which are of the form

\begin{align}
a_{1,1} x_1 + a_{1,2} x_2 + a_{1,3} x_3 + \dots + a_{1,n} x_n &= b_1 \\

   a_{2,1} x_1 + a_{2,2} x_2 + a_{2,3} x_3 + \dots + a_{2,n} x_n &= b_2\\
                                                                     \vdots \\
 a_{m,1} x_1 + a_{m,2} x_2 + a_{m,3} x_3 + \dots + a_{m,n} x_n &= b_m
\end{align}


where $a_{i,j}$ are constants. Usually there are the same number of equations as unknowns, so $m = n$.  If $m < n$ then the system is undetermined, if $m > n$, the system is over constrained.

```{admonition} Example
:class: tip
\begin{align}4 x_1 - x_2 &= 1\\ -2 x_1 + 3 x_2 &= 12 \end{align}
Each equation here defines a line, and we are looking for a point which satisfies both equations, which means that the lines intersect.

From the first line we obtain $x_2 = 4 x_1 - 1$, and by substituting this into the second line, we obtain $x = \frac{3}{2}$, $y = 5$. Two equations with two unknowns will always give a unique solution, unless the lines are parallel (and so the equations are just a scaling of each other).

-	If they are parallel and distinct, there are no solutions because there are no points that lie on both lines.
-	If they are parallel and coincident (same line), there are an infinite number of solutions.

```
(gaussian-elimination)=
### A systematic technique for solving systems of equations

We will begin by finding a solution to the following system:

% ![](Picture1.png)

\begin{alignat*}{5}
(r_1) &\qquad&  x_1 & {}+{} &  x_2 & {}+{} & 2x_3 & {}={} &  2  \\
(r_2) &\qquad&     2x_1 & {}+{} &  3x_2 & {}-{} & 4x_3 & {}={} &  1  \\
(r_3) &\qquad&  -x_1 & {}+{} &  x_2 & {}+{} & x_3 & {}={} & 3
\end{alignat*}

The equations have been labelled $r_1,r_2,r_3$.

First, we will use $r_1$ to eliminate $x_1$ from $r_2$ and $r_3$. This gives two equations in two unknowns. Then, we will use $r_2$ to eliminate $x_2$ from $r_3$.

The steps are written out below:    

\begin{alignat*}{7}
&&&& (r_1) &\qquad&  x_1 & {}+{} &  x_2 & {}+{} & 2x_3 & {}={} &  2  \\
&&&& (r_2) &\qquad&     2x_1 & {}+{} &  3x_2 & {}-{} & 4x_3 & {}={} &  1  \\
&&&& (r_3) &\qquad&  -x_1 & {}+{} &  x_2 & {}+{} & x_3 & {}={} & 3\\
\\  
&&&& (r_1) &\qquad&  x_1 & {}+{} &  x_2 & {}+{} & 2x_3 & {}={} &  2   \\
r_2 & {}-{} & 2r_1 &\quad\longrightarrow\quad& (r_2) &\qquad&      &  &  x_2 & {}-{} & 8x_3 & {}={} &  -3  \\
r_3 & {}+{} & r_1 &\quad\longrightarrow\quad& (r_3) &\qquad&   &  &  2x_2 & {}+{} & 3x_3 & {}={} & 5  \\
  \\
&&&& (r_1) &\qquad&  x_1 & {}+{} &  x_2 & {}+{} & 2x_3 & {}={} &  2   \\
&&&& (r_2) &\qquad&      &  &  x_2 & {}-{} & 8x_3 & {}={} &  -3  \\
r_3 & {}-{} & 2r_2 &\quad\longrightarrow\quad& (r_3) &\qquad&   &  &  & & 19x_3 & {}={} & 11

\end{alignat*}

The solution for $x_3$ can now be read off from $r_3$, $x_2$ can be obtained from $r_2$ using the result for $x_3$ and $x_1$ can be obtained from $r_1$ using the results for $x_1$ and $x_2$. This is known as **back-substitution**.  

These manipulations can be conveniently done by looking only at the coefficients, which we collect together in a form called the augmented matrix:

$$
\begin{array}{rc}
\begin{array}{r}
 (r_1)\\
 (r_2)\\
 (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 2 \\
2 & \boxed{3} & -4 & 1 \\
-1 & 1 & \boxed{1} & 3
\end{array}
\right)\\ \\
\begin{array}{ccr}
 & & (r_1)\\
r_2-2r_1 & \longrightarrow & (r_2) \\
r_3+r_1 & \longrightarrow & (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 2 \\
0 & \boxed{1} & -8 & -3 \\
0 & 2 & \boxed{3} & 5
\end{array}
\right) \\ \\
\begin{array}{ccr}
 & & (r_1)\\
& & (r_2) \\
r_3-2r_2 & \longrightarrow & (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 2 \\
0 & \boxed{1} & -8 & -3 \\
0 & 0 & \boxed{19} & 11
\end{array}
\right)
\end{array}
$$


We can see that the algorithm (described in the box below) works by eliminating the coefficients below the leading diagonal, which is highlighted.

```{admonition} Naive Gaussian elimination algorithm (obtaining upper triangular form)
**Step 1** Choose initial pivot

We choose the first element from the leading diagonal as the pivot element.

**Step 2** Row reduction step

Add multiples of the pivot row to the rows below, to obtain zeros in the pivot column below the leading diagonal.

**Step 3** Choose new pivot

The pivot moves to the next element on the leading diagonal.  

**Repeat**
Repeat from Step 2 until the matrix is in upper triangular form (containing all zeros below the leading diagonal).

The solutions can then be obtained by back-substitution.
```

```{exercise}
:label: q_elimination

Write the following system as an augmented matrix then solve it using the Naive Gaussian elimination algorithm.

$$
\begin{alignat*}{4}
 x & {}-{} &  2y & {}+{} & z & {}={} &  0  \\
2x & {}+{} &  y & {}-{} & 3z & {}={} &  5  \\
4x & {}-{} &  7y & {}+{} & z & {}={} & -1
\end{alignat*}
$$
```

### Generalisation
The naive algorithm introduced here can be generalised to include additional row operations. In general, the acceptable row operations that we can perform are:
-	multiplication of any row by a constant (e.g. $\frac{1}{2}r_1 \rightarrow r_1$)
-	addition of (a multiple of) any row to any other (e.g. $r_2 + 2r_1 \rightarrow r_2$)
-	swapping any two rows (e.g. $r_1 \leftrightarrow r_2$)

It is often possible to apply these steps creatively to get a result with greater efficiency than using the naive algorithm described above.

It is also not necessary to stop at upper triangular form. Once the last row has been fully simplified, it can be used to obtain zeros above the main diagonal in the last column. Then, the second-last row is used to obtain zeros in the second-last column above the main diagonal, and so-on until the only non-zero elements remaining are on the main diagonal. Then the solutions can be simply read off from each row.
For instance, continuing with the naive row reduction for the example shown in the previous section, we obtain:

$$
\begin{array}{rc}
\begin{array}{ccr}
 & & (r_1)\\
 & & (r_2)\\
 \frac{1}{19}r_3 & \longrightarrow & (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
\boxed{1} & 1 & 2 & 2 \\
0 & \boxed{1} & -8 & -3 \\
0 & 0 & \boxed{1} & \frac{11}{19}
\end{array}
\right)\\ \\
\begin{array}{ccr}
r_1-2r_3 & \longrightarrow & (r_1)\\
r_2+8r_3 & \longrightarrow & (r_2) \\
 & & (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
\boxed{1} & 1 & 0 & \frac{16}{19} \\
0 & \boxed{1} & 0 & \frac{31}{19} \\
0 & 0 & \boxed{1} & \frac{11}{19}
\end{array}
\right) \\ \\
\begin{array}{ccr}
r_1 - r_2 & \longrightarrow & (r_1)\\
& & (r_2) \\
& & (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
\boxed{1} & 0 & 0 & -\frac{15}{19} \\
0 & \boxed{1} & 0 &  \frac{31}{19}\\
0 & 0 & \boxed{1} & \frac{11}{19}
\end{array}
\right)
\end{array}
$$

We have obtained row-reduced form and the solutions for $x_1,x_2,x_3$ can now be read off from the final column.

## Row Echelon Form

In this section we present an algorithm for solving a linear system of equations. The system algorithm works for any linear system of equations, regardless of whether there are zero, one or infinitely many solutions. It works by converting system of equations to **reduced row echelon form**.

```{admonition} Definition

A matrix is in **row echelon form** if:

1. All zero rows are at the bottom.
2. The first nonzero entry of a row is to the right of the first nonzero entry of the row above.
3. Below the first nonzero entry of a row, all entries are zero.

\begin{pmatrix}
\boxed{\star} & \star &\star &\star &\star \\
0     & \boxed{\star} &\star &\star &\star \\
0     &  0    & 0    & \boxed{\star} &\star \\
0 & 0 & 0 & 0 & 0           \end{pmatrix}
$\star=$ any number  
$\boxed{\star}=$ any non-zero number.

A **pivot** is the first nonzero entry of a row of a matrix in row echelon form.

A matrix is in **reduced row echelon form** if it is in row echelon form, and:

1. Each pivot is equal to 1.
2. Each pivot is the only nonzero entry in its column.

\begin{pmatrix}
1 & 0 &\star & 0 &\star \\
0     & 1 &\star &0 &\star \\
0     &  0    & 0    & 1 &\star \\
0 & 0 & 0 & 0 & 0           \end{pmatrix}
$\star=$ any number
```

```{exercise}
:label: q_row_echelon_form

Which of the following matrices are in (a) row echelon form (b) reduced row echelon formed?

$$
\begin{align*}
&1.~
\begin{pmatrix} 1 & 0 & 2 \\ 0 & 1 & -1
\end{pmatrix}\qquad
2.~\begin{pmatrix} 2 & 1 \\ 2 & 1
\end{pmatrix}\qquad
3.~\left(\begin{array}{ccc|c}
2 & 7 & 1 & 4\\
0 & 0 & 2 & 1\\
0 & 0 & 1 & 3
\end{array}\right)\\
&4.~\left(\begin{array}{ccc|c}
2 & 7 & 1 & 4\\
0 & 0 & 2 & 1\\
0 & 0 & 0 & 3
\end{array}\right)\qquad
5.~\begin{pmatrix} 0 & 1 & 8 & 0
\end{pmatrix}\qquad
6.~\begin{pmatrix} 2 & 1 & 3 \\ 0 & 0 & 0
\end{pmatrix}
\end{align*}
$$
```

### Gaussian Elimination for Reduction to Echelon Form

```{admonition} Row Reduction Algorithm (Gaussian Elimination)

**Step 1** If necessary, swap the 1st row with a lower one so a leftmost nonzero entry is in the 1st row.

**Step 2** Multiply the 1st row by a nonzero number so that its first nonzero entry is equal to 1.

**Step 3** Replace all lower rows with multiples of the first row so all entries below this 1 are 0.

**Step 4** Repeat Steps 1-3 for row 2, row 3 and so on.

The matrix is now in row echelon form. To convert it to reduced row echelon form:

**Step 5** Replace all rows above with multiples of the final pivot row to clear all entries above the pivot.

**Step 6** Repeat step 5 for each of the other pivot rows, working from bottom to top.
```

```{admonition} Example: Gaussian Elimination
:name: ex_gaussian_elimination
:class: tip
Use Gaussian elimination to reduce the following matrix to reduced row echelon form:

$$
\begin{pmatrix}
-2 & -4 & -2 & -10 & 0\\
2 & 4 & 1 & 9 & -2\\
3 & 6 & 1 & 13 & -4
\end{pmatrix}
$$

**Solution**

First get a 1 pivot in the first row and zeros below in the same column:

$$
\begin{array}{rc}
\begin{array}{ccr}
 & & (r_1)\\
 & & (r_2)\\
& & (r_3)
\end{array}
&
\begin{pmatrix}
-2 & -4 & -2 & -10 & 0\\
2 & 4 & 1 & 9 & -2\\
3 & 6 & 1 & 13 & -4
\end{pmatrix}\\
\begin{array}{ccr}
 -\frac{1}{2}r_1 & \longrightarrow & (r_1)\\
 & & (r_2)\\
& & (r_3)
\end{array}
&
\begin{pmatrix}
1 & 2 & 1 & 5 & 0\\
2 & 4 & 1 & 9 & -2\\
3 & 6 & 1 & 13 & -4
\end{pmatrix}\\
\begin{array}{ccr}
 & & (r_1)\\
 r_2 - 2r_1 & \longrightarrow & (r_2)\\
 r_3 - 3r_1& \longrightarrow & (r_3)
\end{array}
&
\begin{pmatrix}
\boxed{1} & 2 & 1 & 5 & 0\\
0 & 0 & -1 & -1 & -2\\
0 & 0 & -2 & -2 & -4
\end{pmatrix}
\end{array}
$$

We have zeros in the second column so the next pivot will be in column 3:

$$
\begin{array}{rc}
\begin{array}{ccr}
 & & (r_1)\\
 -r_2 & \longrightarrow & (r_2)\\
 & & (r_3)
\end{array}
&
\begin{pmatrix}
\boxed{1} & 2 & 1 & 5 & 0\\
0 & 0 & 1 & 1 & 2\\
0 & 0 & -2 & -2 & -4
\end{pmatrix}\\
\begin{array}{ccr}
 & & (r_1)\\
 & & (r_2)\\
 r_3 + 2r_2 & \longrightarrow & (r_3)
\end{array}
&
\begin{pmatrix}
\boxed{1} & 2 & 1 & 5 & 0\\
0 & 0 & \boxed{1} & 1 & 2\\
0 & 0 & 0 & 0 & 0
\end{pmatrix}
\end{array}
$$

The matrix is now in echelon form. To achieve reduced row echelon form, we eliminate the values above the pivots:

$$
\begin{array}{rc}
\begin{array}{ccr}
 r_1 - r_2 & \longrightarrow & (r_1)\\
 & & (r_2)\\
 & & (r_3)
\end{array}
&
\begin{pmatrix}
\boxed{1} & 2 & 0 & 4 & -2\\
0 & 0 & \boxed{1} & 1 & 2\\
0 & 0 & 0 & 0 & 0
\end{pmatrix}\\
\end{array}
$$
```

```{exercise}
:label: q_echelon_form_2

<!-- https://www.math.uh.edu/~jiwenhe/math2331/lectures/sec1_2.pdf -->

Use Gaussian elimination to reduce the following matrix to row echelon form and reduced row echelon form:

$$
\begin{pmatrix}
0 & 3 & -6 & 6 & 4 & -5\\
3 & -7 & 8 & -5 & 8 & 9\\
3 & -9 & 12 & -9 & 6 & 15
\end{pmatrix}$$

```

## Parametric Solutions to a Linear System

The reduced row echelon form of the augmented matrix allows us to determine the solutions to the system. There are three cases:

1\. **Every column except the last column is a pivot column**. In this case, the system of equations is consistent and there is a single unique solution. For example,

$$
\left(\begin{array}{ccc|c}
\boxed{1} & 0 & 0 & 5\\
0 & \boxed{1} & 0 & 2\\
0 & 0 & \boxed{1} & -1
\end{array}\right)$$

has the solution $\pmatrix{x_1\\x_2\\x_3} = \pmatrix{5\\2\\-1}$.

2\. **The last column is a pivot column**. In this case the system is inconsistent and there are no solutions. For example,

$$
\left(\begin{array}{cc|c}
\boxed{1} & 0 & 0\\
0 & \boxed{1} & 0\\
0 & 0 & \boxed{1}
\end{array}\right)$$

is equivalent to $\pmatrix{x_1\\x_2\\0} = \pmatrix{0\\0\\1}$ which is inconsistent. There are no values of $x_1, x_2$ and $x_3$ which solve this system.

3\. **The last column is not a pivot column, and some other column is also not a pivot column**. In this case, there are infinitely many solutions. For example,

$$
\left(\begin{array}{cccc|c}
\boxed{1} & 2 & 0 & 3 & 1\\
0 & 0 & \boxed{1} & -2 & -2
\end{array}\right)$$

has infinitely many solutions since columns 2 and 4 are non-pivot columns. The variables corresponding to a non-pivot column of the matrix are termed **free variables**. In the next section will explore how these solutions can be determined.

### General Solution Set

The following system of equations,

$$
\begin{alignat*}{4}
x_1 & {}+{} & 2x_2 & {}+{} & 9x_3 & {}={} & -1\\
2x_1 & {}+{} & x_2 & {}+{} & 12x_3 &  {}={} & 1
\end{alignat*}$$

is represented by the following augmented matrix,

$$
\left(\begin{array}{ccc|c}
1 & 2 & 9 & -1\\
2 & 1 & 12 & 1
\end{array}
\right)
$$

which through Gaussian elimination may be reduced to the following echelon form,

$$
\left(\begin{array}{ccc|c}
1 & 0 & 5 & 1\\
0 & 1 & 2 & -1
\end{array}
\right)
$$

corresponding to the following pair of equations:

$$
\begin{alignat*}{3}
x_1 & {}+{} & 5x_3 & {}={} & 1\\
x_2 & {}+{} & 2x_3 &  {}={} & -1&.
\end{alignat*}$$

Rearranging slightly,

$$
\begin{alignat*}{3}
x_1 & {}={} & 1 & {}-{} & 5x_3\\
x_2 & {}={} & -1 & {}-{} & 2x_3 &.
\end{alignat*}$$

For any value of $x_3$, there is exactly one value of $x_1$ and $x_2$ that satisfy the equations. But we are free to choose *any* value of $x_3$, and so we have found all the solutions: the set of all values $x_1, x_2, x_3$ where

$$
\begin{alignat*}{3}
x_1 & {}={} & 1 & {}-{} & 5t\\
x_2 & {}={} & -1 & {}-{} & 2t\\
x_3 & {}={} &  &  & t
\end{alignat*}$$

for any $t \in \mathbb{R}$.

This is the **general solution in parametric form** of the system of equations, and $x_3$ is a **free variable**.

In a later section we will see how to write this in vector form as follows:

$$
\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} = t\begin{pmatrix}-5\\-2\\1\end{pmatrix} + \begin{pmatrix}1\\-1\\0\end{pmatrix}.
$$

**The solution set is a straight line**.

```{admonition} Parametric solution to system of linear equations

Suppose we have a linear system of $m$ equations in $n$ unknowns. Determine the **parameteric form** of the solution set as follows:

1. Write the system of as an augmented matrix.
2. Use Gaussian elimination to reduce to reduced row echelon form.
3. Write the corresponding system of linear equations.
4. Move all free variables to the right hand side.

```

```{admonition} Example

Write the solution to the system represented by the following augmented matrix in parametric form.

$$\left(\begin{array}{cccc|c}
\boxed{1} & 2 & 0 & 3 & 1\\
0 & 0 & \boxed{1} & -2 & -2
\end{array}\right)$$

**Solution**

The matrix is already in reduced row echelon form. The pivot variables are $x_1$ and $x_3$; the free variables are $x_2$ and $x_4$. It corresponds to the following equations:

$$\begin{alignat*}{4}
x_1 & {}+{} & 2x_2 & \quad &      & {}+{} & 3x_4 & {}={} & 1\\
    &       &      & \quad & x_3 & {}-{} & 2x_4 & {}={} & -2.
\end{alignat*}
$$

Move the free variables to the right hand side to give the parametric solution:

$$\begin{alignat*}{5}
x_1 & {}={} & -2x_2 & {}-{} & 3x_4 & {}+{} & 1\\
x_3 & {}={} &       & {}-{} & 2x_4 & {}-{} & 2
\end{alignat*}
$$

for any $x_2, x_4 \in \mathbb{R}$.

This is the equation of a (2d) plane.

```



```{exercise}
:label: q_parametric_form

The reduced row echelon form of the matrix for a linear system in four variables $x_1, x_2, x_3, x_4$ is

$$\left(\begin{array}{cccc|c}1 & 0 & 0 & 3 & 2\\
0 & 0 & 1 & 4 & -1\end{array}\right).$$

1. Identify the pivot variables and free variables.
2. Write the solution to the system in parametric form.
```


## Solutions

```{solution} q_elimination

**Gaussian elimination**

$$
\begin{array}{rc}
\begin{array}{r}
 (r_1)\\
 (r_2)\\
 (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
1 & -2 & 1 & 0 \\
2 & 1 & -3 & 5 \\
4 & -7 & 1 & -1
\end{array}
\right)\\ \\
\begin{array}{ccr}
 & & (r_1)\\
r_2-2r_1 & \longrightarrow & (r_2) \\
r_3-4r_1 & \longrightarrow & (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
1 & -2 & 1 & 0 \\
0 & 5 & -5 & 5 \\
0 & 1 & -3 & -1
\end{array}
\right) \\ \\
\begin{array}{ccr}
 & & (r_1)\\
& & (r_2) \\
r_3-\frac{1}{5}r_2 & \longrightarrow & (r_3)
\end{array}
&
\left(
\begin{array}{ccc|c}
1 & -2 & 1 & 0 \\
0 & 5 & -5 & 5 \\
0 & 0 & -2 & -2
\end{array}
\right)
\end{array}
$$

**Back-substitution**

\begin{align*}
-2z = -2 &\Rightarrow z = 1.\\
5y - 5z = 5 &\Rightarrow y = 1 + z = 2.\\
x - 2y + z = 0 &\Rightarrow x = 2y-z = 3.
\end{align*}

The solution is $\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}3\\2\\1\end{pmatrix}$.
```

```{solution} q_row_echelon_form

1, 4, 5, 6 are in row echelon form.

1, 5 are in reduced row echelon form.
```

```{solution} q_echelon_form_2

Row echelon form:

$$
\begin{pmatrix}
3 & -9 & 12  & -9 & 6 & 15\\
0 & 1 & -2 & 2 & 1 & -3\\
0 & 0 & 0 & 0 & 1 & 4
\end{pmatrix}
$$

Reduced row echelon form:

$$
\begin{pmatrix}
1 & 0 & -2  & 3 & 0 & -24\\
0 & 1 & -2 & 2 & 0 & -7\\
0 & 0 & 0 & 0 & 1 & 4
\end{pmatrix}
$$


```

```{solution} q_parametric_form

1\. The pivots are $x_1, x_3$; the free variables are $x_2, x_4$.

2\. Write the system of equations:

$$
\begin{alignat*}{4}
x_1 & \quad &     & {}+{} & 3x_4 & {}={} & 2\\
    &       & x_3 & {}+{} & 4x_4 & {}={} & -1
\end{alignat*}.
$$

In parametric form:

$$
\begin{alignat*}{3}
x_1 & {}={} & 2 & {}-{} & 3x_4\\
x_3 & {}={} & -1 & {}-{} & 4x_4
\end{alignat*}.
$$

What happened to $x_2$? It is a free variable, but no other variable depends on it. The general solution is:

$$
\begin{pmatrix}
x_1\\x_2\\x_3\\x_4
\end{pmatrix}
=
\begin{pmatrix}
2-3x_4\\x_2\\-1-4x_4\\x_4
\end{pmatrix}
$$

for any values of $x_2$ and $x_4$.

```
