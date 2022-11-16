# Linear Algebra Answers 1

## Question 1

Write as augmented matrix then reduce to echelon form (NB I have omitted the vertical line):

$$
\begin{array}{rc}
\begin{array}{ccr}
 & & (r_1)\\
 & & (r_2)\\
& & (r_3)
\end{array}
&
\begin{pmatrix}
1 & 0 & -1 & 0 & -3 & 1\\
3 & 1 & -1 & 1 & -9 & 3\\
1 & 0 & -1 & 1 & -2 & 1
\end{pmatrix}\\
\begin{array}{ccr}
  & & (r_1)\\
r_2 - 3r_1 & \longrightarrow & (r_2)\\
r_3 - r_1 & \longrightarrow & (r_3)
\end{array}
&
\begin{pmatrix}
1 & 0 & -1 & 9 & -3 & 1\\
0 & 1 & 2 & 1 & 0 & 0\\
0 & 0 & 0 & 1 & 1 & 0
\end{pmatrix}\\
\begin{array}{ccr}
 & & (r_1)\\
 r_2 - r_3 & \longrightarrow & (r_2)\\
 & & (r_3)
\end{array}
&
\begin{pmatrix}
1 & 0 & -1 & 0 & -3 & 1\\
0 & 1 & 2 & 0 & -1 & 0\\
0 & 0 & 0 & 1 & 1 & 0
\end{pmatrix}
\end{array}
$$

Write the pivot variables in terms of the free variables to find the general solution:

$$
\begin{align*}
x_1 &= x_3 + 3x_5 + 1\\
x_2 &= -2x_3 + x_5\\
x_4 &= -x_5
\end{align*}
$$

for any $x_3, x_5 \in \mathbb{R}$.

Finally we can write the solution in vector form:

$$
\begin{pmatrix}x_1\\x_2\\x_3\\x_4\\x_5\end{pmatrix} = \begin{pmatrix}x_3 +3x_5 + 1\\-2x_3+x_5\\x_3\\-x_5\\x_5\end{pmatrix} = t_1\begin{pmatrix}1\\-2\\1\\0\\0\end{pmatrix} + t_2\begin{pmatrix}3\\1\\0\\-1\\1\end{pmatrix} + \begin{pmatrix}1\\0\\0\\0\\0\end{pmatrix}
$$

for $t_1, t_2 \in \mathbb{R}$.

[*I have swapped the variables $x_3$ and $x_5$ for $t_1$ and $t_2$. In practice these are just dummy variables and we could use any symbols we like to represent a pair of real numbers.*]

This is the equation of a plane in $\mathbb{R}^5$ parallel to $\begin{pmatrix}1\\-2\\1\\0\\0\end{pmatrix}$ and $\begin{pmatrix}3\\1\\0\\-1\\1\end{pmatrix}$ and passing through the point $\begin{pmatrix}1\\0\\0\\0\\0\end{pmatrix}$.

## Question 2

1\.

 $A$: $\begin{pmatrix}1 & 2 & 0 & 0 & 0\\0 & 0 & 1 & 2 & 3\\0 & 0 & 0 & 0 &0\end{pmatrix}$. $x_2, x_4$ and $x_5$ are free variables.

 $B$: $\begin{pmatrix}1 & 0 & -1 \\0 & 1 & 1\\0 & 0 & 0 &\end{pmatrix}$. $x_3$ is a free variable.

2\.

$A$: $\begin{pmatrix}x_1\\x_2\\x_3\\x_4\\x_5\end{pmatrix}=\begin{pmatrix}-2x_2\\x_2\\-2x_4-3x_5\\x_4\\x_5\end{pmatrix}$.

The special solution for $x_2$ is found by setting $x_2=1$ and $x_4=x_5=0$:

$$\begin{pmatrix}-2\\1\\0\\0\\0\end{pmatrix}.$$

Likewise for $x_4$:

$$\begin{pmatrix}0\\0\\-2\\1\\0\end{pmatrix}$$

and $x_5$:

$$\begin{pmatrix}0\\0\\-3\\0\\1\end{pmatrix}.$$

$B$: There is only one free variable so only one special solution $\begin{pmatrix}1\\-1\\1\end{pmatrix}.$

3\. The null space is all linear combinations of the special solutions.

$A$: $t_1\begin{pmatrix}-2\\1\\0\\0\\0\end{pmatrix}+t_2\begin{pmatrix}0\\0\\-2\\1\\0\end{pmatrix}+t_3\begin{pmatrix}0\\0\\-3\\0\\1\end{pmatrix}, t_1, t_2, t_3 \in \mathbb{R}$.

$B$: $t\begin{pmatrix}1\\-1\\1\end{pmatrix}, t \in \mathbb{R}$.

4\. True. The null space of A matrix and its reduced echelon form is the same since the right hand side of the equation $Ax=0$ is not altered by the row operations.

## Question 3

1\. For the system of 4 nodes, this gives us four equations:

$$\begin{align*}
y_3&=y_1+y_4\\y_1&=y_2+y_5\\y_2&=y_3+y_6\\y_4+y_5+y_6&=0\end{align*}.$$

2\. Written in augmented matrix form, the system is:

$$\left(\begin{array}{cccccc|c}1 & 0 & -1 & 1 & 0 & 0 &0\\-1 & 1 & 0 & 0 & 1 & 0&0 \\0 & -1 & 1 & 0 & 0 & 1&0 \\0 & 0 & 0 & -1 & -1 & -1 &0\\\end{array}\right).$$

The first 6 columns are for the coefficients of $y_1,\ldots,y_6$ and the last column is the constant term that appears on the right hand side of the equation.

After applying Gaussian elimination to the pivot elements in the first and second column, we can't do anything with the third column without spoiling the progress we've made in the first two columns, so we leave that one and move on to use the fourth column as a pivot. After that, we can't make any more progress so we stop. We obtain:

$$\left(\begin{array}{cccccc|c}1 & 0 & -1 & 0 & -1 & -1 & 0 \\0 & 1 & -1 & 0 & 0 & -1 & 0 \\0 & 0 & 0 & 1 & 1 & 1 & 0 \\0 & 0 & 0 & 0 & 0 & 0 & 0 \\\end{array}\right)$$

3\.
The first, second, and fourth columns are the pivot columns, and the other columns are all "free" since they can be obtained from a combination of the other columns.

Choosing $(y_3,y_5,y_6)=(1,0,0)$ gives the special solution $s_1=(1,1,1,0,0,0)$  
Choosing $(y_3,y_5,y_6)=(0,1,0)$ gives the special solution $s_2=(1,0,0,-1,1,0)$  
Choosing $(y_3,y_5,y_6)=(0,0,1)$ gives the special solution $s_3=(1,1,0,-1,0,1)$

4\. The full solution space consists of all possible linear combinations $a s_1 + b s_2 +c s_3$ for $a, b, c \in \mathbb{R}$.

## Question 4

By differentiating $p(x)$ we obtain

$$p'(x) = b + 2cx + 3dx^2.$$

Thus the given conditions are

$$\begin{align*}
p(1) &= a + b + c + d = 1\\
p'(1) &= b + 2c + 3d = 5\\
p(-1) &= a - b + c - d = 3\\
p'(-1) &= b - 2c + 3d = 1
\end{align*}$$

which is a linear system of four equations in the four unknowns $a, b, c, d$.

The augmented matrix for this system is

$$
\left(
\begin{array}{cccc|c}
1 & 1 & 1 & 1 & 1\\
0 & 1 & 2 & 3 & 5\\
1 & -1 & 1 & -1 & 3\\
0 & 1 & -2 & 3 & 1
\end{array}
\right).
$$

Apply elementary row operations to reduce to reduced row echelon form as follows (vertical line omitted):



$$
\begin{array}{rc}
\begin{array}{ccr}
 & & (r_1)\\
 & & (r_2)\\
& & (r_3)\\
& & (r_4)
\end{array}
&
\begin{pmatrix}
1 & 1 & 1 & 1 & 1\\
0 & 1 & 2 & 3 & 5\\
1 & -1 & 1 & -1 & 3\\
0 & 1 & -2 & 3 & 1
\end{pmatrix}\\
\begin{array}{ccr}
  & & (r_1)\\
& & (r_2)\\
r_3 - r_1 & \longrightarrow & (r_3)\\
& & (r_4)
\end{array}
&
\begin{pmatrix}
1 & 1 & 1 & 1 & 1\\
0 & 1 & 2 & 3 & 5\\
0 & -2 & 0 & -2 & 2\\
0 & 1 & -2 & 3 & 1
\end{pmatrix}\\
\begin{array}{ccr}
 r_1 - r_2 & \longrightarrow & (r_1)\\
 & & (r_2)\\
r_3 + 2r_2 & \longrightarrow & (r_3)\\
r_4 - r_2 & \longrightarrow& (r_4)
\end{array}
&
\begin{pmatrix}
1 & 0 & -1 & -2 & -4\\
0 & 1 & 2 & 3 & 5\\
0 & 0 & 4 & 4 & 12\\
0 & 0 & -4 & 0 & -4
\end{pmatrix}\\
\begin{array}{ccr}
  & & (r_1)\\
 & & (r_2)\\
\frac{1}{4}r_3 & \longrightarrow & (r_3)\\
-\frac{1}{4}r_4 & \longrightarrow& (r_4)
\end{array}
&
\begin{pmatrix}
1 & 0 & -1 & -2 & -4\\
0 & 1 & 2 & 3 & 5\\
0 & 0 & 1 & 1 & 3\\
0 & 0 & 1 & 0 & 1
\end{pmatrix}\\
\begin{array}{ccr}
 r_1 + r_4 & \longrightarrow & (r_1)\\
 r_2 - 2r_4 & \longrightarrow & (r_2)\\
r_3 - r_4 & \longrightarrow & (r_3)\\
 & & (r_4)
\end{array}
&
\begin{pmatrix}
1 & 0 & 0 & -2 & -3\\
0 & 1 & 0 & 3 & 3\\
0 & 0 & 0 & 1 & 2\\
0 & 0 & 1 & 0 & 1
\end{pmatrix}\\
\begin{array}{ccr}
 & & (r_1)\\
 & & (r_2)\\
r_3 \leftrightarrow  r_4 & & (r_3)\\
 & & (r_4)
\end{array}
&
\begin{pmatrix}
1 & 0 & 0 & -2 & -3\\
0 & 1 & 0 & 3 & 3\\
0 & 0 & 1 & 0 & 1\\
0 & 0 & 0 & 1 & 2
\end{pmatrix}\\
\begin{array}{ccr}
 r_1 + 2r_4 & \longrightarrow & (r_1)\\
 r_2 - 3r_4 & \longrightarrow & (r_2)\\
& & (r_3)\\
 & & (r_4)
\end{array}
&
\begin{pmatrix}
1 & 0 & 0 & 0 & 1\\
0 & 1 & 0 & 0 & -3\\
0 & 0 & 1 & 0 & 1\\
0 & 0 & 0 & 1 & 2
\end{pmatrix}
\end{array}.
$$

The matrix is now in reduced row echelon form and the solution to the system is

$$a=1, b=-3, c=1, d=2.$$

The polynomial is

$$p(x) = 1 - 3x + x^2 + 2x^3.$$

## Question 5

1\. We need to find $a, b, c, d$ satisfying

$$
\begin{pmatrix}1 & 3\\2 & 4\end{pmatrix}\begin{pmatrix}a & b\\c & d\end{pmatrix} = \begin{pmatrix}a & b\\c & d\end{pmatrix}\begin{pmatrix}1 & 3\\2 & 4\end{pmatrix}.
$$

Multiply out the matrices:

$$
\begin{pmatrix}a + 3c & b + 3d\\2a+4c & 2b+4d\end{pmatrix}=\begin{pmatrix}a + 2b & 3a+4b\\c+2d & 3c+4d\end{pmatrix}.
$$

Equate entries:

$$
\begin{align*}
a + 3c &= a + 2b\\
b + 3d &= 3a + 4b\\
2a + 4c &= c + 2d\\
2b + 4d &= 3c + 4d
\end{align*}
$$

which simplifies to:

$$
\begin{align*}
2b - 3c &= 0\\
3a + 3b - 3d &= 0\\
2a + 3c - 2d &= 0\\
2b - 3c &= 0.
\end{align*}
$$

The first and last equations are identical, so we omit the first one.

*[NB If you include both equations you will get the same result, but you will need to do a row swap during the Gaussian elimination. Try it!]*

Form the coefficient matrix and perform Gaussian elimination to reduce to reduced row echelon form. (Because the equation is of the form $Ax=0$ we can omit the right hand side of the equation and we don't need an augmented matrix):

$$
\begin{pmatrix}
3 & 3 & 0 & -3\\
2 & 0 & 3 & -2\\
0 & 2 & -3 & 0\end{pmatrix}
$$

which reduces to...

$$
\begin{pmatrix}
1 & 0 & \frac{3}{2} & -1\\
0 & 1 & -\frac{3}{2} & 0\\
0 & 0 & 0 & 0\end{pmatrix}.
$$

The general solution is:

$$
\begin{align*}
a &= -\frac{3}{2}c + d\\
b &= \frac{3}{2}c,\\
\end{align*}
$$

where $c$ and $d$ are free variables. Therefore the matrix $B$ such that $AB=BA$ must be of the form

$$
\begin{align*}
B &= \begin{pmatrix}-\frac{3}{2}c + d & \frac{3}{2}c\\c & d\end{pmatrix}
 &= c\begin{pmatrix}-\frac{3}{2} & \frac{3}{2}\\1 & 0\end{pmatrix} + d\begin{pmatrix}1 & 0\\0 & 1\end{pmatrix}
\end{align*}
$$

for any $c, d \in \mathbb{R}$.

2\. We need to find a matrix that is not of the form $B = \begin{pmatrix}-\frac{3}{2}c + d & \frac{3}{2}c\\c & d\end{pmatrix}$. Notice that $B_{1,2} = \frac{3}{2}B_{2,1}$ so any matrix which doesn't satisfy this will do e.g.:

$$C = \begin{pmatrix}0 & 0 \\ 1 & 0\end{pmatrix}.$$


## Question 6

1\.

$$\begin{align*}
E_1M &= \begin{pmatrix}1 & 0 & 0\\2 & 1 &0\\0 & 0 & 1\end{pmatrix}\begin{pmatrix}1 & 0 & 2\\-2 & 0 & -3\\
0 & 2 & 0\end{pmatrix}\\
&= \begin{pmatrix}1 & 0 & 2\\0 & 0 & 1\\0 & 2 & 0\end{pmatrix}
\end{align*}$$

2\.

$$\begin{align*}E_2 &= \begin{pmatrix}1 & 0 & 0 \\0 & 0 & 1\\ 0 & 1 & 0\end{pmatrix}.\\
E_2(E_1M) &=\begin{pmatrix}1 & 0 & 0 \\0 & 0 & 1\\ 0 & 1 & 0\end{pmatrix}\begin{pmatrix}1 & 0 & 2\\0 & 0 & 1\\0 & 2 & 0\end{pmatrix}\\
&=\begin{pmatrix}1 & 0 & 2\\0 & 2 & 0\\0 & 0 & 1\end{pmatrix}.
\end{align*}$$

3\.

Next two elementary row operations are $r_2 \rightarrow \frac{1}{2}r_2$:

$$E_3 = \begin{pmatrix}1 & 0 & 0 \\0 & \frac{1}{2} & 0\\ 0 & 0 & 1\end{pmatrix}$$

and $r_1 \rightarrow r_1 - 2r_3$:

$$E_4 = \begin{pmatrix}1 & 0 & -2 \\0 & 1 & 0\\ 0 & 0 & 1\end{pmatrix}.$$

4\.

$$\begin{align*}A &= E_4E_3E_2E_1\\
&= \begin{pmatrix}1 & 0 & -2 \\0 & 1 & 0\\ 0 & 0 & 1\end{pmatrix}\begin{pmatrix}1 & 0 & 0 \\0 & \frac{1}{2} & 0\\ 0 & 0 & 1\end{pmatrix}\begin{pmatrix}1 & 0 & 0 \\0 & 0 & 1\\ 0 & 1 & 0\end{pmatrix}\begin{pmatrix}1 & 0 & 0\\2 & 1 &0\\0 & 0 & 1\end{pmatrix}\\
&=\begin{pmatrix}-3 & -2 & 0 \\0 & 0 & \frac{1}{2}\\ 2 & 1 & 0\end{pmatrix}.
\end{align*}$$

Because of associativity of matrix multiplication, we know that $E_4(E_3(E_2(E_1M))) = (E_4(E_3(E_2(E_1))))M$. In fact we can bracket the multiplication any way we wish, and arrive at the same value of the matrix $A$.

5\. Left multiplication by the matrix $A$ has the effect of performing the four elementary row operations.

$$\begin{align*}
AMx &= Ab\\
\begin{pmatrix}1 & 0 & 0\\ 0 & 1 & 0\\ 0 & 0 & 1\end{pmatrix}x &= \begin{pmatrix}-3 & -2 & 0 \\0 & 0 & \frac{1}{2}\\ 2 & 1 & 0\end{pmatrix}\begin{pmatrix}4\\2\\-1\end{pmatrix}\\
x &= \begin{pmatrix}-16\\-\frac{1}{2}\\10\end{pmatrix} .
\end{align*}$$
