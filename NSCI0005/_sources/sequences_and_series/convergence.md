# Convergence of Series

Whilst we have tools to figure out what to do with a finite series, infinite series also require some thought.  In the case of some infinite series, we see that 
although there will be an infinite number of terms, they **converge** towards a specific value.  We can see this in the case of geometric series, 

* if $\lvert r \rvert < 1$ then $S_n$ converges and approaches $\displaystyle \frac{a}{1-r}$ as $n\to \infty$,
* if $\lvert r \rvert > 1$ then $S_n$ diverges and approaches $\infty$ as $n\to \infty$.


````{admonition} Definition
:class: note
The value of a infinite series can be defined as the value of the limit (if exists) of the sequence defined by it partial
sums, that is:
```{math}
\sum_{k=1}^\infty u_k = \lim_{n \to \infty} \sum_{k=1}^n u_k \ .
```
Alternatively we could write that:
```{math}
S_n = \sum_{k=1}^n u_k
```
and therefore:
```{math}
\lim_{n \to \infty} S_n = S_\infty 
```
````

## Fundamental concept

We have already seen in the sections on geometric progression and method of differences that some series can approach
a finite value as the number of terms grows infinitely large, series of this type are called **convergent**.

For instance, the value of the series:
```{math}
\sum_{n=1}^N \left(\frac{1}{4}\right)^n
```
approaches, or converges, to a fixed value of $\frac{1}{3}$ as $N \to \infty$.

On the other hand, the series:
```{math}
\sum_{n=1}^N n
```
can be made as big as we like by adding additional terms.  We say that this series **diverges**.

We can draw up some criterion that series need to follow in order to be convergent:

````{admonition} Criterion for convergence
:class: note
1\. *Terms in a convergent series need to decrease in size* - in order to converge to a fixed value, the limit of the partial sums of a series must be 
slowing down towards a fixed value, if they do not then there is no chance that the series will converge.  

2\. *Terms in a convergent series need to get "small enough quick enough"* - it turns out that strictly decreasing series are not sufficient for 
convergence, the "rate of decline" is also important.  If the 

3 \. *For any convergent series, there is a corresponding geometric series that converges to the same or a larger value* - since the expression for 
$S_\infty = a/(1-r)$, there are actually an infinite number of corresponding geometric series given a free choice of $a$ and $r$.
````

We may start to understand this behaviour by looking at what happens to the size of the terms in a series in the long run (i.e. for large $n$).

In the series $\displaystyle \sum_{n=1}^N n$, the terms in the series are themselves growing and therefore this series will diverge.  But in order to make a series diverge,
the terms themselves do not necessarily need this growing behaviour. For instance, in the series $\displaystyle \sum_{n=1}^N \frac{1}{4}$ the terms remain finite, 
but we can make the sum as big as we like by adding more terms - so this series also diverges.

Less obviously, if we look at the series $\displaystyle \sum_{n=1}^N \frac{n^2}{4n^2 + 3 n + 1}$ then it may be shown that in the limit of $n \to \infty$,
```{math}
\frac{n^2}{4n^2 + 3 n + 1} &= \frac{1}{4 + \frac{3}{n} + \frac{1}{n^2}} \\
\lim_{n \to \infty} \frac{n^2}{4n^2 + 3 n + 1} &= \frac{1}{4}

``` 
This means that in the long run the series starts to resemble $\displaystyle\sum_{n=1}^N \frac{1}{4}$ and therefore also diverges.

## Preliminary test for divergence

The first criterion here can be written into a "preliminary test" for convergence/divergence.

````{admonition} Definition
:class: note
A convergent series *must* satisfy the following result:
```{math}
\lim_{n \to \infty}\Big| u_n\Big | = 0
```
````

Note that the preliminary test cannot conclusively identify a series as convergent, we require further tests in order to do this, but if a series fails this test, 
it is definitely divergent (i.e. a necessary but not sufficient condition on convergence).


## D'Alembert's ratio test

D'Alembert's ratio test, also called the Cauchy ratio test or just the ratio test, looks at the **ratio** of subsequent terms in a series to determine if it 
converges or diverges, this is based on our second criterion.

````{admonition} Definition
:class: note
To determine if an infinite series $\displaystyle \sum_{n=1}^\infty u_n$ converges or diverges, we can look at the behaviour of the ratio of consecutive terms in the limit
$n \to \infty$:

```{math}
 \rho = \lim_{n \to \infty}\Bigg\lvert \frac{u_{n+1}}{u_n} \Bigg\rvert \ ,
```

This gives us three cases:

* $\rho < 1$ then the series converges absolutely,

* $\rho=1$ then the test is inconclusive.

* $\rho>1$ then the series diverges absolutely,

````

The ratio test is more powerful than the preliminary test, it will tell us definitively if a series converges, but is often a bit harder to apply 
and so we should use the preliminary test first (the clue is in the name!), if a series fail this then no point to apply the ratio test.

Intuitively, D'Alembert's ratio test tells us that if the ratio of sequential terms is less than 1 then the terms are **shrinking** and hence the 
series converges.  If the converse is true the terms are **growing** and hence the series diverges.

Cases where the ratio test is inconclusive will require further tests.  

````{admonition} Worked example
:class: seealso
We will use D'Alembert's ratio test to determine whether $\displaystyle \sum_{k=1}^n \frac{k^2}{k!}$ converges.

Letting $\displaystyle u_k = \frac{k^2}{k!}$, the ratio $\displaystyle\frac{u_{k+1}}{u_k}$ simplifies to:
```{math}
\frac{u_{k+1}}{u_k} &= \frac{(k+1)^2}{k^2} \frac{k!}{(k+1)!} \\
&= \frac{(k+1)^2 k!}{k^2 (k+1) k!} \\
& = \frac{k+1}{k^2} \ .
```
Where we have used the definition of the factorial to write $(k+1)! = (k+1) k!$, such that we have:
```{math}
\rho = \lim_{k\to\infty} \Bigg\lvert \frac{u_{n+1}}{u_n} \Bigg\rvert = \lim_{k \to \infty} \Big|\frac{k+1}{k^2}\Big| 
= \lim_{k \to \infty} \Big| \frac{1}{k} + \frac{1}{k^2} \Big|= 0 < 1 \ ,
```
and thus the series converges.
````

````{admonition} Tips
:class: tip
1. It is very important to get the algebra correct in the division step. This is often done carelessly and can 
cost a lot of marks.
2. The limit step is important! We are interested to know what happens to the terms in the series in the long 
run - i.e. as $n \to \infty$. The limit must be explicitly taken!
3. Do not drop the modulus signs unexpectedly, otherwise you might get an answer $< -1$ and then conclude that $\rho < 1$, when it should have actually been $\rho > 1$.
````

````{admonition} Practice questions
:class: seealso, dropdown

Use the ratio test to determine if the following series converges:

1\. $\displaystyle \sum_{k=1}^n \frac{k!}{2^k}$,

2\. $\displaystyle \sum_{k=1}^n \frac{(2 k)!}{2^k k!}$,

3\. $\displaystyle \sum_{k=1}^n \frac{(-1)^k}{k} = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots$.
````

````{admonition} Solutions
:class: seealso, dropdown

1\. Let $\displaystyle u_k = \frac{2^k}{k!}$.
```{math}
\frac{u_{k+1}}{u_k} = \frac{2^{k+1}}{(k+1)!}\frac{k!}{2^k} = \frac{k!}{(k+1)!}\frac{2^{k+1}}{2^k} = \frac{2}{k+1}
```
so $\displaystyle \lim_{k \to \infty} \Big| \frac{u_{k+1}}{u_k} \Big| =  \lim_{k \to \infty} \Big|\frac{2}{k+1}\Big| = 0 < 1$.

Thus we conclude that the series converges.

2\. Let $\displaystyle u_k = \frac{(2k)!}{2^k k!}$.

```{math}
\frac{u_{k+1}}{u_k} &= \frac{(2k+2)! (2^k k!)}{\big( 2^{k+1} (k+1)! \big) (2k)!} \\
&= \frac{(2k+2) (2k+1) (2k)! (2^k k!)}{\big( 2 2^{k} (k+1) k! \big) (2k)!} = \frac{(2k+2)(2k+1)}{2 (k+1)} = 2k+1
```
So, $\displaystyle\lim_{k \to \infty} \Big| \frac{u_{k+1}}{u_k} \Big| =  \lim_{k \to \infty} \Big|2k+1\Big| > 1$.

Thus we conclude that the series diverges.

3\. Let $\displaystyle u_k \frac{(-1)^{k-1}}{k}$.

```{math}
\big\lvert \frac{u_{k+1}}{u_k} \big\rvert =  \big\lvert \frac{(-1)^k}{(k+1) (-1)^{k-1} / k} \big\rvert= \big\lvert \frac{k}{k+1} \big\rvert  = \frac{1}{1+1/k}
```
So, $\displaystyle\lim_{k \to \infty} \Big| \frac{u_{k+1}}{u_k} \Big| =  \Big|\frac{1}{1+1/k}\Big| = 1$.

Thus we conclude that the test is inconclusive! Further tests are required to determine convergence/divergence.
````

## Interval of convergence

Some series can be parameterised $S[x,\, p,\, \dots]$ so that it is not clear if they converge or not, in which case there can be an **interval** of $x$ values 
in which the series can be shown to converge and outside of which it is divergent.  The ratio test results can help us to find this interval.  



````{admonition} Worked Example
:class: seealso
Argue if the following series converges and find the interval of convergence:
```{math}
S_1 = \sum_n^\infty \Big(\frac{x}{2}\Big)^n  
```
Using the ratio test we find :
```{math}
\rho = \lim_{n \to \infty}\Bigg| \frac{x^{n+1}}{2^{n+1}}\frac{2^n}{x^n}\Bigg| = \Bigg|\frac{x}{2}\Bigg|
```
If we want to have a convergent series, then we require $\rho < 1$, 

hence $\displaystyle \Big|\frac{x}{2}\Big| < 1 \Rightarrow \Big|x\Big| < 2$, which we can convert into
an interval:

```{math}
-2 < x < 2
```

````

````{admonition} Practice questions
:class: seealso, dropdown

1\. Find the Maclaurin series for $\displaystyle \ln\Big(\frac{1+x}{1-x}\Big)$, and determine the interval of convergence for this expansion.

2\. Given the series:
```{math}
S[x;\,p] = \sum_{n=1}^\infty\frac{(2x)^{2n}}{n^p}
```
find the interval of convergence.
````

````{admonition} Solution
:class: seealso, dropdown

1\. The series expansion of $\ln(1+x)$ can be found by taking $f(x)=\ln(1+x)$ and using the formula for a Maclaurin series
as we are about the point $x=0$.

```{math}
f(x) &= \ln(1+x) \Rightarrow f(0) = \ln(1) = 0\\
f'(x) &= \frac{1}{1+x} \Rightarrow f'(0) = \frac{1}{1+0} = 1\\
f''(x) &= -\frac{1}{(1+x)^2} \Rightarrow f''(0) = -\frac{1}{(1+0)^2} = 2\\
f''(x) &= \frac{2}{(1+x)^3} \Rightarrow f'''(0) = \frac{2}{(1+0)^3} = 2\\
\Rightarrow f(x) &= x-\frac{x^2}{2}+\frac{x^3}{3}-\frac{x^4}{4}+\frac{x^5}{5}-\dots
```

We can use the result to obtain:

```{math}
\ln\left(\frac{1+x}{1-x}\right) &= \ln(1+x)-\ln(1-x) \\
&= \left(x-\frac{x^2}{2}+\frac{x^3}{3}-\frac{x^4}{4}+\frac{x^5}{5}-\dots\right) 
- \left(-x-\frac{x^2}{2}-\frac{x^3}{3}-\frac{x^4}{4}-\dots\right)\\
&= 2x+\frac{2x^3}{3}+\frac{2x^5}{5}+\dots = 2\Big(x + \frac{x^3}{3} + \frac{x^5}{5} + \dots\Big)\\
&= \sum_{n=1}^{\infty}\frac{2x^{2n-1}}{2n-1}
```

To find the radius of convergence, we have:


```{math}
\frac{u_{n+1}}{u_n} &= \frac{2x^{2n+1}}{2n+1}\frac{2n-1}{2x^{2n-1}} = x^2\frac{2n-1}{2n+1} = x^2\frac{2-\frac{1}{n}}{2+\frac{1}{n}} \\
\rho &= \lim_{n\rightarrow\infty}\Big|\frac{u_{n+1}}{u_n}\Big| = \lim_{n\rightarrow\infty}\Big|x^2\frac{2-\frac{1}{n}}{2+\frac{1}{n}}\Big|=\Big|x^2\Big|
```

Thus for $\rho <1$, the series converges for $|x^2|<1 \Rightarrow -1<x<1$.

When $x=\pm 1$, the series expansion is equal to 
```{math}
\pm 2\Big(1+\frac{1}{3}+\frac{1}{5}+\frac{1}{7}+\dots\Big)
```
which does not converge - it is actually the harmonic series in disguise!

For these values of $x$, the function $f(x)$ is also not finite.

2\. Applying the ratio test:
```{math}
\frac{u_{n+1}}{u_n} &= \frac{(2x)^{2n+2}}{(n+1)^p} \Big/ \frac{(2x)^{2n}}{n^p} = \frac{(2x)^{2n+2}}{(2x)^{2n}}\frac{n^p}{(n+1)^p}\\
&= x^2\Big(\frac{n}{n+1}\Big)^p = (2x)^2\Big(\frac{1}{1+\frac{1}{n}}\Big)^p \\
\lim_{n \rightarrow \infty}\Big| \frac{u_{n+1}}{u_n}\Big|&= \lim_{n \rightarrow \infty}\Big| (2x)^2\Big(\frac{1}{1+\frac{1}{n}}\Big)^p \Big|
```
this means that $|4x^2|<1$, i.e. $\displaystyle |x|^2 < \frac{1}{4} \Rightarrow -\frac{1}{4} < x < \frac{1}{4}$.  

````


## Comparison Test

Often called the sandwich or squeeze theorem, this test is based on our third criterion, we will look to find a convergent series, 
which when compared term by the term our series of interest will be same size or larger.  This means that our smaller series will *also* be convergent.
Typically we will compare to geometric series involving powers of two - by the same principles to a geometric series with a different base of powers.

````{admonition} Definition
:class: note

A series $\displaystyle S_1 = \sum_n a_n$ can be shown to converge if there exists a series $\displaystyle S_1' = \sum_n b_n$ such that $\forall n$, $|b_n| \geq |a_n|$.

If series $S_1'$ is known to converge (e.g. an infinite geometric series), then series $S_1$ **must** also converge.

````


````{admonition} Worked Example
:class: seealso
Show that the following series converges
```{math}
S_1 = \sum_n^\infty \frac{1}{(2n)^2}= \frac{1}{2^2} + \frac{1}{4^2} + \frac{1}{6^2} + \frac{1}{8^2} + \frac{1}{10^2} + \frac{1}{12^2} + \frac{1}{14^2} + \frac{1}{16^2} +\dots 

```
Lets think how we can make a series which has terms that are greater than or equal to the terms in $S_1$.  If we round down every terms denominator to the nearest power 
of two (before applying the squared), we will get:

```{math}
S_1' = \frac{1}{2^2} + \frac{1}{4^2} + \frac{1}{4^2} + \frac{1}{8^2} + \frac{1}{8^2} + \frac{1}{8^2} + \frac{1}{8^2} + \frac{1}{16^2} +\dots
```

We can rewrite $S_1'$ by collecting together like terms:

```{math}
S_1' &= \frac{1}{2^2} + \frac{2}{4^2} + \frac{4}{8^2} + \dots \\
&= 1 + \frac{1}{2^2} + \frac{1}{2^3} + \frac{1}{2^4} + \dots
```
which we can see is a geometric series, with $a = \frac{1}{2^2}$ and $r = \frac{1}{2}$, which means that

```{math}
S_1' = \frac{1/2^2}{1 - 1/2} = \frac{1}{2}
```
So we have shown that $S_1'$ converges.  But since $S_1 \leq S_1'$,, then by the comparison test this means that $S_1$ also converges.


The comparison test can also be used to put bounds on the values of some series, since the rounding down 
procedure could be exchanged for a rounding up procecure, which will give us upper and lower bounds for a 
series.  For the sum $S_1$, we can have:
```{math}
S_1'' = \frac{1}{2^2} + \frac{1}{4^2} + \frac{1}{8^2} + \frac{1}{8^2} + \frac{1}{16^2} + \frac{1}{16^2} + \frac{1}{16^2} + \frac{1}{16^2} +\dots
```
which we can see gives every term less than or equal to every term in $S_1$.  By a similar process to finding the value of $S_1'$ we find:
```{math}
S_1'' = \frac{1}{2^2} + \frac{1}{4^2} + \frac{2}{8^2} + \frac{4}{16^2} + \dots = \frac{1}{2^2} + \frac{1}{2^4} + \frac{1}{2^5} + \frac{1}{2^6} + \dots
```
and if we skip the first term here, this is also a geometric series, with $a = \frac{1}{2^4}$ and $r = \frac{1}{2}$, therfore:
```{math}
S_1'' = \frac{1}{2^2} + \frac{1/2^4}{1 - 1/2} = \frac{3}{8}
```
and since $S_1' > S_1 > S_1''$ we have $\frac{4}{8} > S_1 > \frac{3}{8}$ or $0.5 > S_1 > 0.375$.

It turns out that $\displaystyle S_1 = \sum_n^\infty \frac{1}{(2n)^2} = \frac{\pi^2}{24} \simeq 0.41123$, which is indeed between these limits.

````


## Absolute and Conditional Convergence

The preliminary and ratio tests look at the absolute value of the terms in the series to determine whether they are growing or decaying in absolute size terms, 
but with without recourse to their sign.  

```{math}
S_c &= \sum_{n=1}^\infty a_n\\
S_{ac} &= \sum_{n=1}^\infty |a_n|
```

This allows us to make a statement about the **absolute convergence** of the series. That is, series that converge to a single, finite number.  Any series which 
converges absolutely must also converge - the value of $S_{c} \leq S_{ac}$.  

There are however there are series that do not absolutely converge, but still do converge, these series are said to be **conditionally convergent**.  

It further turns out that such series can be "rearranged" to converge to any value at all.  This statement although quite unintuitive is true, thanks to something 
called the Riemann series theorem. 
 
Thankfully in this course we will only look at absolute convergence.



## Harmonic Series

The elephant in the room when it comes to series is the harmonic series:

````{admonition} Definition of the harmonic series
:class: note

```{math}
S_h = \sum_{n=1}^\infty \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \dots
```

We can also make an alternating harmonic series:

```{math}
S_{ah} = \sum_{n=1}^\infty \frac{(-1)^{n+1}}{n} = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots
```

````

The harmonic series is divergent, although the alternating harmonic series is convergent.  In order to show these facts, lets look at the convergence tests in turn:

1\. *Preliminary Test (PT)*:
```{math}
\lim_{n \to \infty} \Big| \frac{1}{n}\Big| = 0
```
hence both the harmonic and alternating harmonic series pass the PT.

2\. *Ratio Test (RT)*:
```{math}
\rho = \lim_{n \to \infty} \Big| \frac{n}{n+1}\Big| = \lim_{n \to \infty} \Big| \frac{1}{1+\frac{1}{n}}\Big| = 1
```
so the RT is inconclusive for both the harmonic and alternating harmonic series.

3\. *Comparison Test (CT)*:
If we apply the rounding the denominator down to the nearest power of two procedure, 
```{math}
S_h &= \sum_{n=1}^\infty \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} + \dots\\
S_h'&= 1 + \frac{1}{2} + \frac{1}{2} + \frac{1}{4} + \frac{1}{4} + \dots\\
&= 1 + \frac{2}{2} + \frac{4}{4} + \dots \\
&= 1 + 1 + 1 + \dots = \sum_{n=1}^\infty n
```
This means that there is an infinite series that is larger than $S_1$ - this does not rule out $S_1$ converging though, since $S_h < S_h'$.  Let's try the related 
procedure of rounding the denominator up to the nearest power of two, this will give us a lower bound on the size of $S_h$:

```{math}
S_h'' &= 1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{4} + \frac{1}{8} + \dots\\
&= 1 + \frac{1}{2} + \frac{2}{4} + \frac{4}{8} + \dots \\
&= 1 + \frac{1}{2} + \frac{1}{2} + \frac{1}{2} + \dots = 1 + \sum_{n=1}^\infty \frac{n}{2}
```
This is also infinite - hence we can see that the harmonic series is bounded from above and below by two divergent series, hence it is also divergent!

What about the alternating harmonic series?
```{math}
S_{ah} &= \sum_{n=1}^\infty \frac{(-1)^{n+1}}{n} = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - \dots\\
S_{ah}'&= 1 - \frac{1}{2} + \frac{1}{2} - \frac{1}{4} + \frac{1}{4} - \dots\\
&= 1 + 0 + 0 + \dots =1 \\
S_{ah}'' &= 1 - \frac{1}{2} + \frac{1}{4} - \frac{1}{4} + \frac{1}{8} - \dots\\
& = 1 - \frac{1}{2} + 0 + 0 + \dots = \frac{1}{2}
```

So the alternative harmonic series is bounded from above and below by two finite values:
```{math}
\frac{1}{2} < S_{ah} < 1
```
and therefore it *is* a convergent series - it is however a conditionally convergent series and not an absolutely convergent one.

However, if we do a regrouping of the terms:
```{math}
S_{ah} = \sum_{n=1}^\infty \frac{(-1)^{n+1}}{n} &= \Big( 1 - \frac{1}{2} \Big)  - \frac{1}{4} + \Big(\frac{1}{3} - \frac{1}{6}\Big) - \frac{1}{8} +
\Big( \frac{1}{5} - \frac{1}{10} \Big) - \frac{1}{12} + \dots \\
&= \frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + \frac{1}{10} - \frac{1}{12} \\
&= \frac{1}{2} \Big( 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - \frac{1}{6} + \dots \Big) \ ,
```
we can find a result which appears to suggest that the series can be written as half of the original series - in fact, it can be shown that this series can be 
made equal to **any** value by a suitable rearrangement of the terms!  This is known as Riemann's paradox and explains why we need to be very careful when handling 
infinite series.  These sorts of issues lead to statements like $\displaystyle 1 + 2 + 3 + 4 + \dots = -\frac{1}{12}$!

We do not have any such issues with series that converge absolutely - any rearrangement does not change the value they converge to.


Another way to see the behaviour of the harmonic series is through a re-grouping of the terms, this trick, which was proved in 1350 by the French mathematician 
Nicole Oresme, relies on grouping the terms in the following way:
```{math}
S_h = \sum_{n=1}^N \frac{1}{n} = \frac{1}{2} + \Big( \frac{1}{3} + \frac{1}{4} \Big) +
 \Big( \frac{1}{5}  + \frac{1}{6} + \frac{1}{7}  + \frac{1}{8} \Big) + \dots
```
so that each new group has twice as many terms as the previous one.

It can be shown that each group of terms is then bigger than $\displaystyle \frac{1}{2}$, and so the sum must be larger than
```{math}
S_{1/2} = \sum_{n=1}^\infty \frac{1}{2} = \frac{1}{2} + \frac{1}{2} + \frac{1}{2} + \dots
```
The issue is that $S_{1/2}$ diverges and $S_h \geq S_{1/2}$ - hence $S_h$ must also diverge.


## Binomial Series
A well known example of a finite series is the binomial series:

```{math}
(a + b)^n &= a^n + n\,a^{n-1}\,b^1 + \frac{n(n-1)}{2!}\,a^{n-2}\,b^2 + \dots + n\,a^1\,b^{n-1} + b^n \\
&= \sum_{r=0}^{n}\frac{n!}{r!(n-r)!}a^{n-r}\,b^r,\, n \in \mathbb{N}
```

We can extend this to a series with $n \in \mathbb{Q}$ which by the first definition means that the series is now infinite:

```{math}
(a + b)^n = \sum_{r=0}^\infty\frac{n(n-1)(n-2)\dots(n-r+1)}{r!}a^{n-r}\,b^r
```

But will this series converge?

To begin with lets start with a simpler series:

```{math}
\frac{1}{1-x} = \Big( 1 - x \Big)^{-1}
```

which using a binomial series (or expansion) will be:

```{math}
\Big( 1 - x \Big)^{-1} &= 1 + (-1)(-x) + \frac{(-1)(-2)}{2!}(-x)^2 + \frac{(-1)(-2)(-3)}{3!}(-x)^3 + \dots\\
&= 1 + x + x^2 + x^3 + \dots
```

which is also a geometric series, with $a=1$, $r=x$, which we know will converge, provided that $|r|=|x|<1$.  

But does this mean that we can't represent $|x|>1$ with $\displaystyle \frac{1}{1-x}$ using a binomial series? No, we just have to be careful which way 
round we look at the function, say $x = 3/2$:

```{math}
\frac{1}{1-\frac{3}{2}} &= -\frac{1}{1/2} = -2 \\
&= \frac{1}{-\frac{3}{2}\Big(1-\frac{2}{3}\Big)} = -\frac{2}{3} \frac{1}{1-\frac{2}{3}}
```
which clearly we can represent using a geometric series now as $|r|<1$.  

If we go back to the full binomial series:

```{math}
(a+b)^n = a^n \Big(1 + \frac{b}{a}\Big)^n
```
where we have picked $a$ here out of the two terms such that $\displaystyle \Big|\frac{b}{a}\Big| < 1$.  Expanding out we find:

```{math}
S_b = \Big(1 + \frac{b}{a}\Big)^n = 1 + n\frac{b}{a} + \frac{n(n-1)}{2!}\Big(\frac{b}{a}\Big)^2 + \dots 
```

and if we think about a related geometric series, where $a=1, \, r = nb/a$ and $|r|<1$:

```{math}
S_b' = 1 + n\frac{b}{a} + n^2\Big(\frac{b}{a}\Big)^2 + \dots = \frac{1}{1-\frac{nb}{a}} = \Big( 1 - \frac{nb}{a}\Big)^{-1}
```

we can see that term by term that $S_b \leq S_b'$ and since $S_b'$ is a convergent geometric series, then $S_b$ must also a convergent series.  

From the ratio test we can see that: 

```{math}
\rho &=\lim_{r \to \infty} \Big| \frac{n(n-1)(n-2)\dots(n-r+1)(n-r)}{(r+1)!}\frac{r!}{n(n-1)(n-2)\dots(n-r+1)}\frac{a^{n-r-1}\,b^{r+1}}{a^{n-r}\,b^r} \Big|\\
&=\lim_{r \to \infty} \Big| \frac{n-r}{r+1} \frac{b}{a} \Big| = \Big|\frac{b}{a}\Big|\lim_{r \to \infty} \Big| \frac{\frac{n}{r}-1}{1 + \frac{1}{r}}\Big| = \Big|\frac{b}{a}\Big|
```

hence for a convergent infinite binomial expansion we just need $\displaystyle \Big|\frac{b}{a}\Big|<1$.  This is good for two reasons:

1\. It produces a convergent series expansion for the binomial term

2\. It allows us to do an expansion where the order parameter (the variable we expand out in) is getting smaller and smaller - it provides a 
great way to approximate the complicated binomial functions with a one or two parameter expansion - this is VERY useful.

````{admonition} Practice questions
:class: seealso, dropdown

1\. The energy mass relation of a massive particle in special relativity is given by:
```{math}
E = \frac{m_0\,c^2}{\sqrt{1 - \frac{v^2}{c^2}}}
```
where $c \gg v$.  Find the leading order and next to leading order term in the energy of the particle.

2\. A conical pendulum consists of a bob suspended on a string which oscillates round in a circular path. with a frequency of:
```{math}
f = \frac{\sqrt{g}}{2\pi(L^2 - R^2)^{1/4}}
```
wher $L$ is the string length and $R$ is the radius of the circular path at the base of the cone.  For $R$ this pendulum mimics a simple 
pendulum with $f = \frac{1}{2\pi}\sqrt{\frac{g}{L}}$, find the size of the correction term.
````

````{admonition} Solutions
:class: seealso, dropdown

1\. Using $c \gg v \Rightarrow v/c \ll 1$
```{math}
E = \frac{m_0\,c^2}{\sqrt{1 - \frac{v^2}{c^2}}} &= m_0\,c^2\,\Big(1 - \frac{v^2}{c^2}\Big)^{-1/2}\\
&= m_0\,c^2\,\Big(1 - \Big(-\frac{1}{2}\Big)\frac{v^2}{c^2} + \dots\Big) = m_0\,c^2 + \frac{1}{2}m_0\,v^2 + \dots
```
which we should recognise as rest mass energy and kinetic energy!


2\. If we take $L > R \rightarrow R/L < 1$:
```{math}
f &= \frac{\sqrt{g}}{2\pi(L^2 - R^2)^{1/4}} = \frac{\sqrt{g}}{2\pi}(L^2 - R^2)^{-1/4} = \frac{\sqrt{g}}{2\pi\,L^{1/4}}\Big(1 - \frac{R^2}{L^2}\Big)^{-1/4}\\
&= \frac{\sqrt{g}}{2\pi\,(L^2)^{1/4}}\Big(1 - \Big(-\frac{1}{4}\Big)\frac{R^2}{L^2} + \dots \Big) = \frac{1}{2\pi}\sqrt{\frac{g}{L}}\Big( 1 +  \frac{R^2}{4\,L^2} +\dots \Big)
```

````


## Lagrange remainder theorem

The Lagrange remainder theorem allows us to place precise bounds on the size of the error. 

````{admonition} Lagrange remainder theorem
:class: note
Let $p_n(x;a)$ be the truncated Taylor expansion of $f(x)$ about point $x=a$, up to and including the term in $(x-a)^n$.

The remainder (error) in the truncated expansion is given by
```{math}
R_n(x) = \biggr|f(x)-p_n(x;a)\biggr| = \biggr|\frac{f^{n+1}(\xi)(x-a)^{n+1}}{(n+1)!}\biggr|, \qquad \xi\in(a,x)
```
````

The result shows that the error in the truncated expansion is proportional to the next power of $(x-a)$.We say that the degree $n$ series 
has "order $(x-a)^n$ accuracy", and we may write:
```{math}
f(x)=p_n(x;a)+\mathcal{O}((x-a)^{n+1})
```
where the big-$\mathcal{O}$ notation describes the order of the error terms.

The power-relationship in Lagrange's theorem can be anticipated when $(x-a)$ is small, and for larger differences by noting that the factorial growth of the 
coefficient denominators is much faster than polynomial growth.

```{admonition} Big idea : Local approximation of a function
:class: tip
We can compute a series expansion for a function in powers of $x$ using Taylor series. The resulting truncated polynomial gives a good local approximation to 
a function in a sense made precise by the Lagrange remainder theorem. If the truncated polynomial is used near the expansion point $a$ then its accuracy 
"goes like" the $n^{\text{th}}$ power of the distance from $a$.
```

The proof of the Lagrange remainder theorem, and derivation of the coefficient of $(x-a)^n$ is found by using another result called the *mean value 
theorem*. It won't be of much benefit for our practical purposes to show the proof here. Instead, let us take a look at an illustrative example.


````{admonition} Worked Example
:class: seealso
Use the Lagrange remainder theorem to compute an upper bound for the size of the error in the quadratic expansion of $\sin(x)$ about $\displaystyle x=\frac{\pi}{3}$, at 
a nearby point $\displaystyle x=\frac{\pi}{2}$.

The series expansion is found to be:
```{math}
p_2(x;\pi/3)=\frac{\sqrt{3}}{2}+\frac{1}{2}\biggr(x-\frac{\pi}{3}\biggr)-\frac{\sqrt{3}}{4}\biggr(x-\frac{\pi}{3}\biggr)^2
```
And from Lagrange's formula, the error in the expansion at $\displaystyle x=\frac{\pi}{2}$ is given by:
```{math}
R(\xi)= \biggr|\frac{\cos(\xi)(\frac{\pi}{2}-\frac{\pi}{3})^3}{6}\biggr|
```
Since $|\cos(\xi)|$ is bounded above by $1$ on the given domain, Lagrange's remainder theorem gives an upper bound of $\displaystyle \frac{\pi^3}{6^4}=0.0239246$

The exact error is given by:
```{math}
\biggr|\sin\left(\frac{\pi}{2}\right)-p_2\left(\frac{\pi}{2};\frac{\pi}{3}\right)\biggr| = 0.0091119
```
````


