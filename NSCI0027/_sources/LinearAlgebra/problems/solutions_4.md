# Linear Algebra Answers 4

## Question 1

1\.

The eigenvalues of $H$ are the values of $\lambda$ for which $H-\lambda I$ has nonzero null space, which is exactly when the determinant of $H-\lambda I$ is zero.

$$\begin{align*}\det\left({H-\lambda I}\right) &= \begin{vmatrix}7/8-\lambda&-3\sqrt{3}/8\\-3\sqrt{3}/8&13/8-\lambda\end{vmatrix}\\
&= (7/8-\lambda)(13/8-\lambda) - 27/64\\
&= (\lambda-1/2)(\lambda-2)
\end{align*}$$

Therefore the eigenvalues of $H$ are $\lambda_1-1/2$ and $\lambda_2=2$).

To find the eigenvector $v_1$, determine the null space of $H-\lambda_1$:

$$
\begin{align*}H - \lambda_1I &= \begin{pmatrix}7/8-1/2&-3\sqrt{3}/8\\-3\sqrt{3}/8&13/8-1/2\end{pmatrix}\\
&= \begin{pmatrix}3/8 & -3\sqrt{3}/8\\-3\sqrt{3}/8&9/8\end{pmatrix} \xrightarrow[]{\mathrm{RREF}}
\begin{pmatrix}1&-\sqrt{3}\\0&0\end{pmatrix}  \\
\end{align*}
$$

Therefore there is a single independent eigenvector corresponding to $\lambda_1=1/2$:

$$v_1= \begin{pmatrix}\sqrt{3}\\1\end{pmatrix}.$$

To find the eigenvector $v_2$, determine the null space of $H-\lambda_2$:

$$
\begin{align*}H - \lambda_2I &= \begin{pmatrix}7/8-2&-3\sqrt{3}/8\\-3\sqrt{3}/8&13/8-2\end{pmatrix}\\
&= \begin{pmatrix}-9/8 & -3\sqrt{3}/8\\-3\sqrt{3}/8&-3/8\end{pmatrix} \xrightarrow[]{\mathrm{RREF}}
\begin{pmatrix}\sqrt{3}&1\\0&0\end{pmatrix}  \\
\end{align*}
$$

Therefore there is a single independent eigenvector corresponding to $\lambda_2=2$:

$$v_2= \begin{pmatrix}1\\-\sqrt{3}\end{pmatrix}.$$

2\. Therefore $H = X\Lambda X^{-1}$ where

$$X = \begin{pmatrix}\sqrt{3}&1\\1&-\sqrt{3}\end{pmatrix}$$

and

$$\Lambda = \begin{pmatrix}1/2&0\\0&2\end{pmatrix}.$$

3\.

$$X^{-1} = \frac{1}{4}\begin{pmatrix}\sqrt{3}&1\\1&-\sqrt{3}\end{pmatrix}.$$

$X$ represents a rotation $\pi/6$ anticlockwise followed by a $\times 2$ dilation. $\Lambda$ represents a stretch $\times 1/2$ along the $x$-axis and $\times 2$ along the $y$-axis. $X^{-1}$ represents a rotation $\pi/6$ anticlockwise followed by a $\times 2$ dilation.

The transformations can be worked out sketching the images of the unit vectors. Note that if you chose different eigenvectors during part 1, you would get different eigenvectors. For example, if you chose $v_1 =\begin{pmatrix}-\sqrt{3}\\-1\end{pmatrix}$ instead of $\begin{pmatrix}\sqrt{3}\\1\end{pmatrix}$ then $X$ would represent a rotation followed by a reflection - and this is harder to interpret.

## Question 2

1\. To show that $1$ is eigenvalue of $A$, calculate the null space of $A -I$:

$$A - I = \begin{pmatrix}0&3&3\\-3&-6&-3\\3&3&0\end{pmatrix} \xrightarrow[]{\mathrm{RREF}} \begin{pmatrix}1&0&-1\\0&1&1\\0&0&0\end{pmatrix}$$

The echelon form has only two pivots therefore the null space of $A - I$ is nonzero and $1$ is an eigenvalue. The eigenvector is

$$v_1 = \begin{pmatrix}1\\-1\\1\end{pmatrix}.$$

To show that $-2$ is eigenvalue of $A$, calculate the null space of $A +2I$:

$$A  +2I = \begin{pmatrix}3&3&3\\-3&-3&-3\\3&3&3\end{pmatrix} \xrightarrow[]{\mathrm{RREF}} \begin{pmatrix}1&1&1\\0&0&0\\0&0&0\end{pmatrix}$$

The echelon form has only one pivot therefore the null space of $A +2I$ is nonzero and $-2$ is an eigenvalue. In fact, because there is only one pivot and two free variables there are two independent eigenvectors:

$$v_2=\begin{pmatrix}-1\\0\\1\end{pmatrix}$$

$$v_3=\begin{pmatrix}-1\\1\\0\end{pmatrix}.$$

To show that $1$ is eigenvalue of $B$, calculate the null space of $B -I$:

$$B - I = \begin{pmatrix}1&4&3\\-4&-7&-3\\3&3&0\end{pmatrix} \xrightarrow[]{\mathrm{RREF}} \begin{pmatrix}1&0&-1\\0&1&1\\0&0&0\end{pmatrix}$$

The echelon form has only two pivots therefore the null space of $B - I$ is nonzero and $1$ is an eigenvalue. The eigenvector is

$$v_1 = \begin{pmatrix}1\\-1\\1\end{pmatrix}.$$

To show that $-2$ is eigenvalue of $B$, calculate the null space of $B +2I$:

$$B +2I = \begin{pmatrix}4&4&3\\-4&-4&-3\\3&3&3\end{pmatrix} \xrightarrow[]{\mathrm{RREF}} \begin{pmatrix}1&1&0\\0&0&1\\0&0&0\end{pmatrix}$$

The echelon form has only two pivots therefore the null space of $B+2I$ is nonzero and $-2$ is an eigenvalue. The eigenvector is

$$v_2 = \begin{pmatrix}-1\\1\\0\end{pmatrix}.$$

2\. Because they are $3\times 3$ matrices know that both $A$ and $B$ will have a cubic characteristic polynomial of the form:

$$(\lambda - \lambda_1)(\lambda-\lambda_2)(\lambda-\lambda_3).$$

Recall that **the algebraic multiplicity of an eigenvalue is greater or equal to the geometric multiplicity**. For $A$, the geometrical multiplicity of $\lambda_2=-2$ is two since there are two independent eigenvectors in its eigenspace. Therefore its algebraic multiplicity must be two and the characteristic polynomial is

$$(\lambda-1)(\lambda+2)^2.$$

For $B$, use the fact that $\mathrm{tr}(B)=\lambda_1+\lambda_2+\lambda_3$ to determine that the third eigenvalue is $-2$ and the characteristic polynomial is the same as $A$:

$$(\lambda - 1)(\lambda+2)^2.$$

3\. and 4\. Already calculated above.

5\. $A$ is diagonalisable since it has three independent eigenvectors. $B$ is not diagonalisable since it only has two independent eigenvectors.

6\.

$$A = X\Lambda X^{-1}$$

where

$$X = \begin{pmatrix}1&-1&-1\\-1&0&1\\1&1&0\end{pmatrix}$$

and

$$\Lambda = \begin{pmatrix}1&0&0\\0&-2&0\\0&0&-2\end{pmatrix}.$$

## Question 3

1\. Eigenvalues of a triangular matrix are the diagonal entries therefore eigenvalues are $\lambda_1=a$ and $\lambda_2=b$.

2\.

$$A-aI = \begin{pmatrix}0&b-a\\0&b-a\end{pmatrix}\xrightarrow[]{\mathrm{RREF}}\begin{pmatrix}0&b-a\\0&0\end{pmatrix}$$

therefore

$$v_1 = \begin{pmatrix}1\\0\end{pmatrix}.$$

$$A-bI = \begin{pmatrix}a-b&b-a\\0&0\end{pmatrix}\xrightarrow[]{\mathrm{RREF}}\begin{pmatrix}1&-1\\0&0\end{pmatrix}$$

therefore

$$v_2 = \begin{pmatrix}1\\1\end{pmatrix}.$$

3\.

$$A = X\Lambda X^{-1} = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a&0\\0&b\end{pmatrix}\begin{pmatrix}1&-1\\0&1\end{pmatrix}.$$

4\.

$$
\begin{align*}A^k &= \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a^k&0\\0&b^k\end{pmatrix}\begin{pmatrix}1&-1\\0&1\end{pmatrix}\\
&= \begin{pmatrix}a^k&b^k-a^k\\0&b^k\end{pmatrix}.
\end{align*}$$

## Question 4

1\.

$$\begin{align*}
\det(M-\lambda I) &= (a-\lambda)(d-\lambda) - bc\\
&=\lambda^2-(a+d)\lambda+ad-bc\\
&=\lambda^2-\mathrm{tr}(M)\lambda + \det(M).
\end{align*}$$

Therefore the eigenvalues are

$$\frac{\mathrm{tr}(M) \pm \sqrt{\mathrm{tr}(M)^2 - 4\det(M)}}{2}$$

2\. Let

$$D = \mathrm{tr}(M)^2 - 4\det(M).$$

Then $D>0 \implies$ two distinct real eigenvalues, $D=0 \implies$ exactly one eigenvalue, $D<0 \implies$ no real eigenvalues.

## Question 5

1\.

$$\begin{align*}u_{i+1} &= \begin{pmatrix}F_{i+2}\\F_{i+1}\end{pmatrix}\\
&= \begin{pmatrix}F_{i+1} + F_{i}\\F_{i+1}\end{pmatrix}\\
&= \begin{pmatrix}1&1\\1&0\end{pmatrix}\begin{pmatrix}F_{i+1}\\F_i\end{pmatrix}\\
&= Au_i\end{align*}$$

where

$$A = \begin{pmatrix}1&1\\1&0\end{pmatrix}.$$

2\.

$$\begin{align*}
\det(A-\lambda I) &= \begin{vmatrix}1-\lambda&1\\1&-\lambda\end{vmatrix}\\
&=\lambda(\lambda-1-1)\\
&=\lambda^2-\lambda-1
\end{align*}$$

Therefore the two eigenvalues are

$$\lambda_1 = \frac{1+\sqrt{5}}{2}$$

and

$$\lambda_2 = \frac{1-\sqrt{5}}{2}.$$

$$Av_1 = \begin{pmatrix}1&1\\1&0\end{pmatrix}\begin{pmatrix}\frac{1+\sqrt{5}}{2}\\1\end{pmatrix}=\begin{pmatrix}\frac{1+\sqrt{5}}{2}+1\\\frac{1+\sqrt{5}}{2}\end{pmatrix}$$

$$\lambda_1v_1 = \frac{1+\sqrt{5}}{2}\begin{pmatrix}\frac{1+\sqrt{5}}{2}\\1\end{pmatrix}=\begin{pmatrix}\frac{1+\sqrt{5}}{2} + 1\\\frac{1+\sqrt{5}}{2} \end{pmatrix},$$

therefore $Av_1 = \lambda_1 v_1$ and $v_1$ is an eigenvector. Similar calculation for $v_2$.

3\.

$$A = X\Lambda X^{-1}$$

where

$$X = \begin{pmatrix}\lambda_1&\lambda_2\\1&1\end{pmatrix}$$

and

$$\Lambda = \begin{pmatrix}\lambda_1&0\\0&\lambda_2\end{pmatrix}.$$

4\.

$$X^{-1} = \frac{1}{\lambda_1-\lambda_2}\begin{pmatrix}1&-\lambda_2\\-1&\lambda_1\end{pmatrix}.$$

$$\begin{align*}
u_{100} &= X\Lambda^{100}X^{-1}u_0\\
&=\frac{1}{\lambda_1-\lambda_2}\begin{pmatrix}\lambda_1&\lambda_2\\1&1\end{pmatrix}\begin{pmatrix}\lambda_1^{100}&0\\0&\lambda_2^{100}\end{pmatrix}\begin{pmatrix}1&-\lambda_2\\-1&\lambda_1\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix}\\
&=\frac{1}{\lambda_1-\lambda_2}\begin{pmatrix}\lambda_1&\lambda_2\\1&1\end{pmatrix}\begin{pmatrix}\lambda_1^{100}&0\\0&\lambda_2^{100}\end{pmatrix}\begin{pmatrix}1\\-1\end{pmatrix}\\
&=\frac{1}{\lambda_1-\lambda_2}\begin{pmatrix}\lambda_1&\lambda_2\\1&1\end{pmatrix}\begin{pmatrix}\lambda_1^{100}\\-\lambda_2^{100}\end{pmatrix}\\
&= \frac{\lambda_1^{100}v_1-\lambda_2^{100}v_2}{\lambda_1-\lambda_2}
&=\end{align*}.$$

5\. Now $|\lambda_2|<1$ so $\lambda_2^{100}$ is *very* small (try it in your calculator). Therefore we can assume $\lambda_2\approx 0$ and so

$$u_{100} \approx \frac{\lambda_1^{100}}{\lambda_1-\lambda_2}v_1.$$

Then

$$F_{100} \approx \frac{\lambda_1^{100}}{\lambda_1-\lambda_2} = \frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{100}.$$

6\.

$$F_i = \frac{\lambda_1^{100} - \lambda_2^{100}}{\lambda_1-\lambda_2}$$

so

$$F_{i+1}/F_i = \frac{\lambda_1^{i+1}-\lambda_2^{i+1}}{\lambda_1^i-\lambda_2^{i}} = \frac{\lambda_1-\lambda_2\left(\frac{\lambda_2}{\lambda_1}\right)^i}{1 - \left(\frac{\lambda_2}{\lambda_1}\right)^i}.$$

$|\lambda_2/\lambda_1| < 1$ therefore $\lim_{i\to\infty}\lambda_2/\lambda_1 = 0$ and

$$\lim_{i\to\infty}F_{i+1}/F_{i} = \lambda_1 = \frac{1+\sqrt{5}}{2}.$$
