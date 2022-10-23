# Intro to ODEs


### Population growth

Let $x(t)$ be the population of a given area at time $t$.

Write down an expression for the per-capita rate of change of population change.
Derive an equation for $x(t)$ by assuming that the per-capita rate of population change is equal to a constant $\alpha$.

Requires direct integration

### Population growth (modified)

Let $x(t)$ be the population of a given area at time $t$. The area has sufficient resource to support a maximum population size $k$, called the carrying capacity.

Write down an expression for the fraction of remaining resource when the population size is $x$.
Assume that the per-capita rate of change of population is proportional to the fraction of available resources, with constant of proportionality $r$. Write down an ordinary differential equation for $x(t)$.


Solution

Resource-limited growth
```{math}
\frac{\dot{x}}{x}=r\left(1-\frac{x}{k}\right)
```

Separate the variables:

```{math}
\int_{x_0}^x \frac{1}{x(k-x)}\mathrm{d}x=\int_{t_0}^t\frac{r}{k}\mathrm{d}t
```

Use partial fractions to integrate the LHS:

```{math}
\int_{x_0}^x \left(\frac{1}{x}+\frac{1}{k-x}\right)\mathrm{d}x=\int_{t_0}^t r\mathrm{d}t
```

```{math}
\ln\left(\frac{x}{k-x}\right)=r(t-t_0)+C, \qquad C=\ln\left(\frac{x_0}{k-x_0}\right)
```

```{math}
\frac{x}{x-k}=Ae^{r(t-t_0)}, \qquad A=e^c=\frac{x_0}{k-x_0}
```

```{math}
x=\frac{k}{1+\left(\frac{k-x_0}{x_0}\right)e^{-r(t-t_0)}}
```

(the logistic function)

SEE ALSO THE VIDEO IN THE SECTION ON DIFFERENTIATION (MODELLING: VIRAL GROWTH)


### Examples

Mitochondria are organelles that provide energy for human and other eukaryotic cells. Mitochondria can divide like bacteria and fuse with each other. Use the following assumptions to write a differential equation for $M$, the number of mitochondria in a cell:

There is an optimal mitochondrial population, $m$. The rate at which mitochondria reproduce is proportional to the difference between the current population and the optimal population, with proportionality constant $r>0$.
When two mitochondria are close to each other, they may fuse together. This occurs with probability $f$
Mitochondria die at a per capita rate $d$


Solution:
```{math}
\frac{\mathrm{d}M}{\mathrm{d}t}=r(m-M)-Md -2fM^2
```

QUESTION!!
Should the first term on the right be $r(M-m)$ or $r(m-M)$ ?

Consider

```{math}
\frac{\mathrm{d}M}{\mathrm{d}t}=r(M-m)
```

In this case, the growth rates will tend to move the system *away* from equilibrium. For $M>m$, the growth rate is positive and for $M<m$ the growth rate is negative.

Now consider
```{math}
\frac{\mathrm{d}M}{\mathrm{d}t}=r(m-M)
```

In this case, the growth rates will tend to move the system *towards*  equilibrium. For $M>m$, the growth rate is negative and for $M<m$ the growth rate is positive.




### Noyes-Whitney equation

The dissolution rate of a solid in solvent:

```{math}
\frac{\mathrm{d}C}{\mathrm{d}t}=\frac{D S_w}{Vh}(C_s-C)
```

* $C(t)$ : Concentration of dissolved substance at time 𝑡
* $C_s$ : Solubility concentration
* $D$ : Diffusion coefficient of substance
* $S_w$ : Surface area of exposed solid
* $V$ : Volume of solution
* $h$ : Thickness of diffusion layer

Used to find drug dissolution profiles of solid dosages. Under constant conditions of temperature, the parameters $D,V,h,C_s$ remain constant. However, $S_w$ varies and should be treated as a function of time.

Solve by hand for the case where $S_w$ is constant. Computer exercise for non-constant $S_w$?

(this is a separation problem)

### The Streeter-Phelps model of water quality

Used in water pollution studies

```{math}
\frac{\mathrm{d}D}{\mathrm{d}t}=k_1L-k_2D
```

* $D(t)$ : Oxygen deficit at time 𝑡
* $L(t)$ : Oxygen demand at time 𝑡
* $k_1$ : Deoxygenation rate
* $k_2$ : reaeration rate

Assuming that $L=L_0e^{-k_1 t}$ where $L_0$ is the initial oxygen demand, solve the problem to obtain D explicitly as a function of time.

(requires the integration factor technique)


### A coupled problem that can be reduced

A basic model of flu transmission is given below, in which $S$ denotes susceptible individuals and $I$ denotes infected individuals. The constants $k$ and $m$ in these equations are taken to be positive:

\begin{equation*}
\begin{aligned}
\frac{\mathrm{d}S}{\mathrm{d}t} &=-k SI+m I&& \text{[Equation I]} \\[10pt]
\frac{\mathrm{d}I}{\mathrm{d}t} &=\phantom{-}k SI-mI && \text{[Equation II]}
\end{aligned}
\end{equation*}

Question (a):
Give a physical interpretation of each term on the right hand side of the equation for $\frac{\mathrm{d}I}{\mathrm{d}t}$.

Question (b):
Taking $N=(S+I)$,

Part (i):
Find $\frac{\mathrm{d}N}{\mathrm{d}t}$ and explain the result in terms of the population dynamics.

Part (ii):
Use the substitution $I=y^{-1}$ in [Equation II] to show that:
\begin{equation*}
\frac{\mathrm{d}y}{\mathrm{d}t}=(m-kN)y+k.
\end{equation*}

Question (c):
Solve the ODE given in (bii)) assuming that $N$ is constant, and verify that the result may be written in the form:
\begin{equation*}
I=\frac{\beta}{k+\gamma e^{-\beta t}}.
\end{equation*}
where $\beta=(kN-m)$ and $\gamma$ is an arbitrary constant.


MEDIUM
Collagen is a key protein in connective tissues. One of the steps in collagen formation involves the combination of three molecules of a collagen precuror called propeptide, which occurs with rate constant $k$. The rate of formation of propeptide is a constant, $f$. The propeptide also degrades with per molecule degradation rate $d$. Write a differential eq for the propeptide concentration, $P$.

HARD
Solow's fundamental differential equation for economic productivity states that the rate of change of capital stock is given by the rate of investment minus the rate of depreciation. Assuming a constant annual depreciation rate $\delta$, and a production function $sAk^\alpha$ (Cobb-Douglas model), we obtain:
\begin{equation*}\frac{\mathrm{d}k}{\mathrm{d}t}=sAk^{\alpha}-\delta k\end{equation*}
This equation is of Bernoulli type. Use a change of variables $y=Ak^{1-\alpha}$ to rewrite the problem as a first order ODE for $y(t)$ and hence solve the problem.






BORING
Solve the following problems, subject to any given constraints:

$(1+x^2)\frac{\mathrm{d}y}{\mathrm{d}x}-y=0$

$\frac{\mathrm{d}y}{\mathrm{d}x}+y=e^{-x},\quad y(0)=1$

$\frac{\mathrm{d}y}{\mathrm{d}x}=y\tan(x)-\sec(x)$

$\frac{\mathrm{d}y}{\mathrm{d}x}+2\frac{y}{x}=\frac{e^{3x}}{x^2},\quad y(2)=0$

$(1+x)\frac{\mathrm{d}y}{\mathrm{d}x}+2y=e^x,\quad y(0)=1$

$\frac{\mathrm{d}y}{\mathrm{d}x}+2y\tan(x)=\tan^3(x)$

$(yx-x+y-1)\frac{\mathrm{d}y}{\mathrm{d}x}=1,\quad y(0)=4$

### Solutions 1

Exponential growth of a quantity $y$ is described by the relationship \begin{equation*}y=y_0 e^{\frac{r}{100} t},\end{equation*} where $y_0=y(0)$ and $r$ is the compounded growth rate per unit of time $t$, given as a percentage. This relationship may be derived from the differential equation
\begin{equation*}\frac{\mathrm{d}y}{\mathrm{d}t}=\frac{r}{100}y.\end{equation*}
To find the doubling time, we must solve the problem $y(t)=2y_0$, which gives
\begin{equation*}t=\frac{100\ln(2)}{r}\simeq \frac{70}{r}\end{equation*}

The differential equation that was described here in words is
\begin{equation*}\frac{\mathrm{d}P}{\mathrm{d}t}=f-dP-3kP^3\end{equation*}

*Note: If conditions are not given to determine the constants, then your solutions may possibly differ from those given by a constant. It is good practice to always check your solutions by differentiating and substituting into the given equation. If it doesn't satisfy the equation then you've made a mistake!*


This problem can be solved either by separation or by integrating factor, with the former being the easier (and therefore recommended!) approach. We obtain
\begin{equation*}\int\frac{1}{y}\mathrm{d}y = \int\frac{1}{1+x^2}\mathrm{d}x \quad \Rightarrow \quad \ln(|y|) = \arctan(x) + \mathrm{const}\end{equation*}
The solution is $y=Ae^{\arctan(x)}$, where $A$ is a constant.


This equation can't be separated, but can be tackled using integrating factor $\mu=e^x$. Multiplying through by the integrating factor gives
\begin{equation*}e^x\frac{\mathrm{d}y}{\mathrm{d}x}+e^x y = 1 \quad \Rightarrow \quad \frac{\mathrm{d}}{\mathrm{d}x}\left(ye^x\right)=1 \quad \Rightarrow ye^x=x+k\end{equation*}
Applying the given initial condition gives $k=1$ and hence, the solution is $y=(x+1)e^{-x}$


Rewrite the equation in integrating factor form
\begin{equation*}\frac{\mathrm{d}y}{\mathrm{d}x}-\tan(x)y=-\sec(x)\end{equation*}
Integrating factor: $\mu=\exp\left(-\int\tan(x)\mathrm{d}x\right)=\exp(\ln(\cos(x)))=\cos(x)$
\begin{equation*}\cos(x)\frac{\mathrm{d}y}{\mathrm{d}x}-\sin(x)y = -1 \quad \Rightarrow \quad \frac{\mathrm{d}}{\mathrm{d}}\left(\cos(x)y\right)=1 \quad \Rightarrow y=(x+K)\sec(x),\end{equation*}
where $K$ is an arbitrary constant.


Integrating factor $\mu=\exp\left(\int\frac{2}{x}\right)=x^2$
\begin{equation*}x^2 \frac{\mathrm{d}y}{\mathrm{d}x} +2xy=e^{3x} \quad \Rightarrow \quad \frac{\mathrm{d}}{\mathrm{d}x}\left(x^2 y \right)=e^{3x} \quad \Rightarrow \quad x^2y=\frac{1}{3}e^{3x}+K\end{equation*}
Applying the given condition gives $K=-\frac{1}{3}e^6$ and hence the particular solution that satisfies the condition is
\begin{equation*}y=\frac{1}{3x^2}\left(e^{3x}-e^6\right)\end{equation*}


Rewrite the equation in integrating factor form
\begin{equation*}\frac{\mathrm{d}y}{\mathrm{d}x}+\frac{2}{1+x}y=\frac{e^x}{1+x}, \quad y(0)=1\end{equation*}
Integrating factor $\mu=\exp\left(\int \frac{2}{1+x}\mathrm{d}x\right)=(1+x)^2$
\begin{equation*}(1+x)^2\frac{\mathrm{d}y}{\mathrm{d}x}+2(1+x)y=e^x(1+x) \quad \Rightarrow \quad y(1+x)^2 = \int e^x(1+x)\mathrm{d}x\end{equation*}
The solution which satisfies the given condition is $\frac{1+xe^x}{(1+x)^2}$


Integrating factor $\mu=\exp\left(2\int\frac{\sin(x)}{\cos(x)}\mathrm{d}x\right)=\exp(-2\ln(\cos(x)))=\sec^2(x)$
\begin{equation*}\sec^2(x)\frac{\mathrm{d}y}{\mathrm{d}x}+2\sec^2(x)\tan(x)y=\sec^2(x)\tan^3(x) \quad \Rightarrow \quad \sec^2(x)y=\frac{1}{4}\tan^4(x)+K,\end{equation*}
where $K$ is a constant. The solution can be written in explicit form as
$y= \frac{1}{4}\sin^2(x)\tan^2(x) + K\cos^2(x)$


It may not be obvious, but this equation can be separated:
\begin{equation*}\biggr[y(x+1)-(x+1)\biggr]\frac{\mathrm{d}y}{\mathrm{d}x}=1 \quad \Rightarrow \quad \int(y-1)\mathrm{d}y = \int\frac{1}{1+x} \quad \Rightarrow \quad \frac{y^2}{2}-y=\ln(x+1)+K\end{equation*}
When performing the integration,  we used $|x+1|=(x+1)$ for $x>-1$. Applying the initial condition gives $K=4$. To write the solution in explicit form requires solving the quadratic in $y$ and therefore deciding which is the correct branch of the square root. It is ok to leave the solution implicitly if you want to:
\begin{equation*}y^2-2y-2\ln(x+1)-8=0 \quad \Rightarrow \quad y= 1+ \sqrt{9+2\ln(x+1)}\end{equation*}


Using the given transformation,
\begin{equation*}\frac{\mathrm{d}y}{\mathrm{d}t}=\frac{\mathrm{d}y}{\mathrm{d}k}\frac{\mathrm{d}k}{\mathrm{d}t}=A(1-\alpha)k^{-\alpha}\biggr[aA k^\alpha-\delta k \biggr]\quad \Rightarrow \quad \frac{\mathrm{d}y}{\mathrm{d}t}+\delta (1-\alpha)y=A^2(1-\alpha s)\end{equation*}
This equation is integrating factor type: $\mu=e^{\delta(1-\alpha)t}$
\begin{equation*}y=  e^{-\delta(1-\alpha)t}\int A^2(1-\alpha)s e^{\delta (1-\alpha)t}\mathrm{d}t=\frac{A^2 s +C e^{-\delta(1-\alpha)t}}{\delta}, \end{equation*}
where $C$ is an arbitrary constant of integration.\\
The solution for $k$ is given by the substitution relationship $y=ke^{1-\alpha}$. Given in explicit form:
\begin{equation*}k=\left(\frac{A^2 s +C e^{-\delta(1-\alpha)t}}{\delta}\right)^{\frac{1}{1-\alpha}}.\end{equation*}
Care should be taken over choosing the correct root.

### More Problems
Solve the logistic differential equation, which is given by

$\frac{\mathrm{d}S}{\mathrm{d}t}=k S\left(1-\frac{S}{L}\right),$ taking $k=1$, $L=100$, and the initial value $S(0)=1$. You should find the familiar S shaped logistic curve. Investigate what happens to the shape of the curve if you change the value of $k$, and see if you can show the results for more than one value of $k$ on the same axis, with a legend.

### USEFUL!

https://en.wikipedia.org/wiki/Area_under_the_curve_(pharmacokinetics)
