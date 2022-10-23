# Faustmann  model

See pp261 Growth and aging [Clark, Mathematical Bioeconomics]

Commercial value of a tree $V(t)$.

Trees of age $t<t^*$ have no commercial value. The value increases with age as volume of useable timber increases until approaching biological maturity the value plateaus.

Ultimately, decay sets in and the value of the trees begin to decline to zero. However, many commercial trees continue to grow and increase in value for several hundred years.

Let $\hat{V}$ denote the present value of a future payment

\begin{equation}
\hat{V}=e^{-\delta t}(V(t)-c)
\end{equation}
where $c$ is the cost of felling, and $\delta$ is the annual rate of interest.

Then,

\begin{equation*}
\hat{V}^{\prime}=e^{-\delta t}(V^{\prime}-\delta(V-c))
\end{equation*}

To maximise $\hat{V}$ we must set $\delta=\frac{V^{\prime}}{V-c}$.

However, this neglects the opportunity to replant. When replanting is taken into account we have

\begin{equation}
\hat{V}=e^{-\delta T_1}[V(T_1)-c]+e^{-\delta T_2}[V(T_2-T_1)-c]+e^{-\delta T_3}[V(T_3-T_2)-c]+\dots
\end{equation}

Since the second rotation problem is identical to the first (and so on) we an assume that all rotation periods are equal and so $T_k=kT$, $k=1,2,\dots$

Thus,
\begin{equation}
\hat{V}=\sum_{k=1}^{\infty}e^{-k\delta T}[V(T)-c]=[V(t)-c]\sum_{k=1}^{\infty}e^{-k\delta T}
\end{equation}
The sum is a geometric progression. With first term and common difference both equal to $e^{-\delta T}$.

We obtain
\begin{equation}
\hat{V}=\frac{V(T)-c}{e^{\delta T}-1}
\end{equation}

To maximise,

\begin{equation}
\hat{V}^{\prime}=\frac{(e^{\delta T}-1)V^{\prime}-(V-c)\delta e^{\delta T}}{(e^{\delta T}-1)^2}
\end{equation}

$\hat{V}^{\prime}=0$ gives

\begin{equation}
\frac{V^{\prime}}{V-c}=\frac{\delta}{1-e^{-\delta T}}
\end{equation}

This is the Faustmann formula.

$(V-c)$ is the net stumpage value, which can be determined from data tables.

We can plot $\frac{V^{\prime}}{V-c}$ against $\frac{\delta}{1-e^{-\delta T}}$ and calculate their intersection.

```{table} Yield tables for Douglas fir, multiplied by cost (in cents per cubic foot!)
| Year  | 30  | 40  | 50  | 60  | 70  | 80  | 90  | 100 | 110 | 120  |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ---- |
| $V-c$ | 0   | 43  | 143 | 303 | 497 | 650 | 805 | 913 | 1002| 1076 |
```

$V-c$ is the net stump value.

```{exercise}
Determine the relative growth rate $V^{\prime}/(V-c)$ and the average yield $(V-c)/T$

Note: to estimate $V^{\prime}$ use the central differences formula
```

Soln:

```{table} Solution
| Year          | 30  | 40   | 50   | 60   | 70   | 80   | 90   | 100  | 110  | 120  |
| ------------- | --- | ---  | ---  | ---  | ---  | ---  | ---  | ---  | ---  | ---- |
| net stump val | 0   | 43   | 143  | 303  | 497  | 650  | 805  | 913  | 1002 | 1076 |
| Rel gr rate % | -   | 16.6 | 9.1  | 5.8  | 3.5  | 2.4  | 1.6  | 1.1  | 0.8  | 0    |
| Avg yield     | 0   | 1.08 | 2.86 | 5.05 | 7.10 | 8.12 | 8.94 | 9.13 | 9.11 | 8.97 |
```

Fit a Weibull function to the net stumpage value. The Weibull function is given by

\begin{equation}
w(t) = 1-e^{-(t/\mu)^L}
\end{equation}

Note: this is hard. The data need to be transformed to the range [0,1] on both axes to perform the fit, and then the inverse transform needs to be performed. It's worth it though, as the data fit very nicely!

Plot the following function for different values of the discount $\delta$. Use the following values:
$\delta = [0,0.05,0.1,0.15]$

\begin{equation}
\frac{\delta}{1-e^{-\delta t}}
\end{equation}

```{figure} imgs/wbll-temp.png
---
name: will replace
---
Will be replaced with a Python plot
```

The intersections give the optimal rotation age (years) for different values of the discount

| Annual discount $\delta$    | 0.00 | 0.03 | 0.05 | 0.07 | 0.10 | 0.15 | 0.20 |
| Optimal rotation age T (yr) | 99   | 73   | 63   | 56   | 50   | 44   | 40   |
| Avg annual yield            | 9.23 | 7.41 | 5.63 | 4.13 | 2.80 | 1.56 | 0.86 |


Note: because $1-e^{-\delta T}<1$, taking rotation into account leads to a decrease in the age of cutting.

Note 2: The Faustmann formula can be understood by rearrangement to:

\begin{equation}
V^{\prime}=\delta(V-c)+\delta\left(\frac{V-c}{e^{\delta T}-1}\right)
\end{equation}

The first term represents the interest earned if revenue from cutting is invested at interest rate $\delta$

The second term represents the rotation aspect of the problem.
