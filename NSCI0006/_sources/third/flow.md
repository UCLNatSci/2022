# Flow diagrams


### Flow diagrams

```{figure} imgs/flow1.png
---
name: flow1
---
A flow
```

Clouds are used to represent a source or a sink. Normally "the environment". Stocks are shown with trapezia. The other shape used is to indicate a process. Here an unspecified inflow that increases the stock (as indicated by +). Think if a bathtub filling up! The feedback arrow marked with ? is used to indicate +/- the dependence of the process on stock levels. Positive feedback would indicate that the process is faster for higher stock levels (e.g. think of reproduction). Negative feedback would indicate that the process is slower for higher stock levels (e.g. think of ...?)

### Logistic growth model

Net flow into the stock is proportional to the product of
(a) the level of the stock
(b) the amount by which the stock is below the carrying capacity

i.e. NET INFLOW = $kS(C-S)$, where $C$ is the carrying capacity, $K$ is the constant of proportionality.

Rewrite:

```{math}
\text{NET INFOW} = rS(1-S/C)
```
where $r=KC$ is the rate constant.

For $S<C/2$ the feedback loop is positive (upward sloping solution : amplifying).
For $S>C/2$ the feedback loop is negative (downward sloping solution : stabilizing)

**Plot the logistic curve on the computer with its stock and flow rate**

Note:
```{math}
rS\left(1-\frac{S}{C}\right)=\frac{r}{C}\left(CS-S^2\right)=\frac{r}{C}\left[-\left(S-\frac{C}{2}\right)^2+\frac{C^2}{4}\right]
```
The max flow rate occurs when $S=C/2$.

E.g for resource extraction:

$S$ is the amount of resource extracted
$C-S$ is the amount remaining

```{figure} imgs/flow2.png
---
name: flow2
---
A flow
```

"Stocks" are shown as trapezia. Think of two containers, and a flow from one to the other. The "process" controlling the extraction is extraction. Extraction causes a decrease in unextracted resource (indicated by minus) and an increase in extracted resource (indicated by +). There is a positive feedback loop for each for the following reasons:

* higher levels of unextracted resource makes extraction easier
* higher levels of extracted resource creates capital to spend on extraction!
(big oil grows faster than little oil)

Rate of extraction: $\frac{\mathrm{d}S}{\mathrm{d}t}\propto S$, i.e. $\frac{\mathrm{d}S}{\mathrm{d}t}=kS$

[$\frac{\dot{S}}{S}=k$ is the "per capita" rate of change]

But $K\propto(C-S)$, i.e. $K=r(C-S)$

Therefore $\frac{\mathrm{d}S}{\mathrm{d}t}=rS(C-S)$

### Growth rates in logistic model

```{math}
\frac{1}{S}\frac{\mathrm{d}S}{\mathrm{d}t}=\frac{rS(1-S/C)}{S}=r-\frac{r}{C}S
```

```{figure} imgs/grlogistic.png
---
name: growth rate logistic
---
Growth rate in logistic model
```

This provides a way to estimate the carrying capacity. We can calculate $\frac{1}{S}\frac{\Delta S}{\Delta t}$ for a few initial points and then extrapolate to the axis. However, this can be dangerous. The pattern may not continue (or errors may be magnified).

The exponential model is a special case of the logistic model with infinite carrying capacity.

Time to peak:

```{math}
\frac{\mathrm{d}S}{\mathrm{d}t}=0 \quad \Rightarrow S=C
```

```{math}
\begin{align}
\frac{1}{S(C-rS)}\frac{\mathrm{d}S}{\mathrm{d}t}&=\frac{r}{C}\\
\Rightarrow \quad \frac{1}{C}\left[\frac{1}{S}+\frac{r}{C-rS}\right]\mathrm{d}S&=\frac{r}{C}\mathrm{d}t\\
\Rightarrow \quad \ln(S)-\ln(C-rS)-rt+K
\end{align}
```

here we used partial fractions: $\frac{1}{S(C-rS)}=\frac{A}{S}+\frac{B}{C-rS}$ gives $A=1/c$ and $B=r/C$.

When $t=0$, $S=M$ (amount of stock extracted to date)
This gives $K=\ln(M)-\ln(C-rM)$

Combining
```{math}
rt =\ln\left(\frac{S}{M}\right)-\ln\left(\frac{C-rS}{C-rM}\right)
```

When $S=C$, $rt=\ln\left(\frac{C}{M}\frac{C-rM}{C(1-r)}\right)=\ln\left(\frac{C/M-r}{1-r}\right)$

Or write
```{math}
\frac{S}{C-S}=\frac{M}{C-M}e^{rt}
```


pp218. The results of mathematical models tell us what will happen if present trends continue. Logistic model of US oil production pre-fracking indicated that oil would have run out by now, but fracking technology led to explosive growth in oil extraction.

**There is a plot showing us oil production against time, fitted to a logistic model. Can we do this in class?**

Global oil peak is the year in which the world's oil production is greater than that of any year before or after. All studies cited by the US Energy Information Administration place this peak within the next 50 years.

Note: carbon budgets (output end) rather than resource depletion (input end) might be the more urgent limit to growth currently! (see pp220)

pp225: stable and unstable equilibria.
