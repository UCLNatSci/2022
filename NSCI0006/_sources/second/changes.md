---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---


# Rates of change

This section will introduce the concept of a derivative and standard results
Calculate derivatives of functions (e.g. using mathematical software)
We will start to solve some differential equations and consider their meaning
We will begin to construct models


### Note

The derivative of the sigmoid function is similar to the normal distribution, but having higher kurtosis. It can also be motivated by a differential equation for capacity-limited growth.


### Differentiation principle


Curves can be approximated by line segments. The more segments the better.
Calculating $\frac{\Delta x}{\Delta t}$   for each line segment gives an estimate of the slope at each point.
We can see how the slope changes. Here, it gets steeper as we move away from the origin.

(plot graph showing connecting points by secant lines)

"In the limit"

```{math}
\frac{\Delta y}{\Delta x} \rightarrow \frac{\mathrm{d}y}{\mathrm{d}x}
```

... we call this the derivative. We can think of $\frac{\mathrm{d}x}{\mathrm{d}t}$ as a measure of the "rate of change" of $x$.

Most things change, and we are already quite familiar with discussing how quickly they do so in our day-to-day lives. The formal study of time-dependent systems is called “mathematical dynamics”.


### Problems 0.0 (ON SLOPE)

Blood pressure
You are studying a new blood pressure drug. At a dose of 5mg the slope of the
dose-response curve is -2 mmHg/mg. Approximately how much would a patient’s
blood pressure change of the drug dose was increased to 5.1mg?

### Solution
Let $R$ be the response and $D$ be the dose. According to the information given in the question $\frac{\Delta R}{\Delta D}=-2\frac{mmHg}{mg}$

Taking $\Delta D=0.1mg$ gives

```{math}
\Delta R = -2 \frac{mmHg}{mg}(0.1mg)=-0.2mmHg
```
The blood pressure would decrease by 0.2mmHg. Here, we treated the slope of
the dose-response curve as constant, which is usually a reasonable approximation
when looking at small changes.


### Problems 0.1 (ON SLOPE)

The number of species $S$ living on an island or habitat fragment of area $A$ can be modelled as $S = cA^z$, where $z > 0$. We can measure area in units that make $c = 1$, simplifying this equation into $S = A^z$. A common value for z is approximately 0.45 (found by data fitting).

Find $\frac{\mathrm{d}S}{\mathrm{d}A}$ and explain the meaning of this function and its significance for biodiversity conservation.

### Solution

```{math}
\frac{\mathrm{d}S}{\mathrm{d}A}=0.45 A^{-0.55}.
```
We can find when $\frac{\mathrm{d}S}{\mathrm{d}A}=1:$

```{math}
0.45A_c^{-0.55}=1 \quad \Rightarrow \quad A_c=\left(\frac{9}{20}\right)^{20/11}\simeq 0.234
```
For areas that are below this critical value, any loss of habitat results in a proportionally greater loss of species. This result can also be understood by looking at the graph of $S = A^{0.45}$. PLOT IT

```{figure} imgs/temp.png
---
name: will replace
---
Will be replaced with a Python plot
```


### Recommended reading
Strogatz Ch 7: The Secret Fountain.


### Good exercises

Un-natural disasters: two calculus projects, **with handouts** [PRIMUS]





Heated rod:

Here $T(x)$ represents temperature in a bar that is heated at one end.

The slope of the curve, approximated by $\frac{\mathrm{d}T}{\mathrm{d}x}$ tells us how the temperature changes as we move along the bar, at a fixed time.


We can think of $\frac{\mathrm{d}T}{\mathrm{d}x}$ as the rate of change of $T$ with respect to $x$, though the language of "rates" my seem peculiar when applied to something that is not changing in time.
To make things even more confusing, the heated rod problem involves change in both the spatial $x$ direction and in time! Eventually the temperature would arrive at an equilibrium linear profile.
All of the problems we will look at in this course involve only things that change in time.

### Simple ones from the powerpoint

Q1:
Water flows out of a bucket at a constant rate of 0.1L/sec. Write down an equation for the amount of water $V$ left in the bucket at time $t$.

```{math}
\frac{\mathrm{d}V}{\mathrm{d}t}=-0.1 \quad \Rightarrow V(t)=V_0 - 0.1t
```

It works until the bucket is empty! Is it realistic? Rate of outflow may depend on water level in the bucket (e.g. due to pressure)

Q2: Newton's second law says that Force=mass $\times$ acceleration. Can you write this down as a problem involving velocity $v$?

```{math}
m\frac{\mathrm{d}v}{\mathrm{d}t}=F \quad \Rightarrow \quad m \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\mathrm{d}x}{\mathrm{d}t}\right)=F
```

Q3: A loan company charges interest of 1% per month. Write down an equation for the amount of money $M$ that is owed

Possible:

$M_{n+1}=M_n(1.01)$

OR

$\frac{\Delta M}{\Delta t}=0.01M$

### Stepping forward

Demonstrate the Euler method (forward stepping) to construct the derivative curve. The approximation gets better for smaller step sizes. A good equation to demonstrate for is the equation for exponential growth:

```{math}
\frac{\mathrm{d}N}{\mathrm{t}}=\alpha N
```

(where $\alpha$ is a constant.)



### Microbial growth (textbook)

Exponential growth:
```{math}
\frac{\mathrm{d}x}{\mathrm{d}t}=\mu x \quad \Rightarrow x=x_0 e^{\mu t}
```

For $x$ to be doubled, $x/x_0=2$ which gives $\mu=\frac{1}{t}\ln(2)$, where $t$ is the generation time.

E.g. if the generation time is 2h, $\mu=\frac{1}{2}\ln(2)$

And $x=x_0 e^{1/2\ln(2)t}=x_0\left[e^{\ln(2)}\right]^{t/2}=x_0 2^{t/2}$

After 24hrs, $x=x_0 2^{12}$, after 48hrs $x=x_0 2^{24}$

microbial growth has a "lag" phase (flat) followed by exponential growth, followed by a "stationary" (flat) phase (and possibly followed by death). S-shaped curve!

Example 3.2: finding slope of exponential phase (useful!)


Effect of substrate concentration on growth:
Monod equation has $\mu=\frac{\mu_{max}S}{K_s+S}$ where $\mu$ is the specific growth rate, $\mu_{max}$ is the maximum growth rate, $S$ is the substrate concentration, $K_s$ is half-saturation constant.

At high substrate concentrations (e.g initially) $S\gg K_s$, so $\mu\sim \mu_{max}$. The growth rate is approximately independent of the substrate concentration.

At low substrate concentrations (late in evolution), $S\ll K_s$, so $\mu\sim\frac{\mu_{max}S}{K_s}$. The growth rate is proportional to the substrate concentration.

The describing equation is

```{math}
\frac{\mathrm{d}X}{\mathrm{d}t}=\mu X = \mu_{max S X}{K_s+S}
```

We can also write $\frac{\mathrm{d}S}{\mathrm{d}t}=-\frac{1}{Y}\frac{\mathrm{d}X}{\mathrm{d}t$, where $Y$ is the cell yield (i.e. the amount of cell mass produced per unit of substrate consumed). It is a measure of how efficiently the substrate is degraded. It depends on the substrate structure and micro-organism.

Thus
```{math}
\frac{\mathrm{d}S}{\mathrm{d}t}=-\frac{1}{Y}\frac{\mathrm{d}X}{\mathrm{d}t} \quad \Rightarrow \quad S-S_0=-\frac{1}{Y}(X-X_0)
```

FINALLY (PUT IN A BOX!)
```{math}
\frac{\mathrm{d}X}{\mathrm{d}t}=\frac{\mu_{max}SX}{K_s+S}, quad S=S_0-\frac{1}{Y}(X-X_0)
```

For example, take $\mu_{max}=0.29 l/h$. $K_s=10mg/l$, $Y=0.5$, $S_0=500mg/l$, $X_0=1mg/l$.

Plot the substrate S and cell mass X.

### Chemostat (bioreactor)

By controlling the dilution rate, we can control the growth rate $\mu$.

```{math}
\frac{\mathrm{d}X}{\mathrm{d}t}=\mu X-D X = (\mu-D)X
```
where $D$ is the dilution rate. Note that at steady state (equilibrium) $\mu=D$.
This gives
```{math}
D_{crit}=\frac{\mu_{max}S}{K_s+S}
```

If $\mu>D$ the utilisation of the substrate will exceed supply, casuing the growth rate to slow until it is equal to the dilution rate.

If $\mu<D$ the amount of substrate will exceed the amount utilised, so the growth rate will increase until it is equal to the dilution rate.

For $S\gg K_s$, $D_c\simeq \mu_{max}$ (maximum efficiency).

For $D>D_{c}$ washout of cells will occur with a decline in operating efficiency.

For $D<D_c$ the operation efficiency is not optimal

### Frechet function

```{math}
F(t)=e^{-(t/\beta)^{-\alpha}}
```

Note that the function satisfies

```{math}
\frac{\dot{F}}{F}\propto \frac{1}{t^{\alpha+1}}
```
The per-capita growth rate decreases algebraically with t.




### Offset exponential model:
pp165 offset exponential model

```{math}
\begin{align}
\frac{\mathrm{d}Q}{\mathrm{d}t}=r(Q-Q_e)
&\Rightarrow \ln\left(\frac{Q-Q_e}{Q_0-Q_e}\right)=rt\\
&\Rightarrow Q-Q_e = (Q_0-Q_e)e^{rt}\\
&D_t = D_0e^{rt}
\end{align}
```

For example (see pp165 cooling of drink)

```{math}
\frac{\mathrm{d}T}{\mathrm{d}t}=-0.11(T-T_e), \qquad T_e=56, T_0=168
```
Gives $D_0=112$,

```{math}
D_t=112 e^{-0.11t}
```

When $T=119$,

```{math}
63=112 e^{-0.11t} \Rightarrow t=\frac{1}{0.11}\ln\left(112/63\right)
```

Note: for small $r$, $e^r\simeq 1+r$, so may see written

```{math}
\frac{D_t}{D_0}=(1+r)^t \Rightarrow t=\frac{\ln(D_t/D_0)}{\ln(1+r)}
```

This is the result that we would obtain for discrete compound growth rather than continuous

```{math}
S=S_0(1+r)^{t/T} \quad \Rightarrow \quad \ln(S)=\ln(S_0)+\frac{t}{T}\ln(1+r)
```

Note: introduce the result in this section and derive it in the next.


## Weighing fog

Fitting a function to data (melting dry ice). Good to do as classroom exercise.

https://www.tandfonline.com/doi/full/10.1080/10511970.2017.1394945


## Concentration of drug in blood

After a drug is injected intravenously the concentration of the drug in the blood initially decreases by a relatively large factor in each small amount of time as a result of both drug diffusion out of the blood into tissues and delivery of the drug to sites like kidneys and the liver where it is eliminated from the body.

Later, in each small unit of time the concentration decreases by a relatively small factor, because although elimination continues the drug now diffuses out of the tissues back into the body, partly replacing that which is being lost/

After an initial period, plasma concentration decreases exponentially with time.

Plot concentration against time (exponential decrease), and also plot log(conc) against time, which should be linear, apart from initial transient period.


### Logistic solution

\begin{equation}
\frac{\mathrm{d}N}{\mathrm{d}t}=rN\left(1-\frac{N}{k/}\right) \quad \Rightarrow \quad \frac{1}{N}\frac{\mathrm{d}N}{\mathrm{d}t}=r\left(1-N/k\right)
\end{equation}

Partial fractions:

\begin{align*}
&\frac{1}{N(1-N/k)} = \frac{k}{N(k-N)}=\frac{A}{N}+\frac{B}{k-N} \\
&\Rightarrow \quad k=A(k-N)+BN=Ak+N(B-A)\\
&\Rightarrow \quad A=1,\ B=1.
\end{align*}

Therefore,

\begin{equation*}
&\int \left(\frac{1}{N}+\frac{1}{k-N}\right)\mathrm{d}N=\int r\mathrm{d}t\\
& \ln\left(\frac{N}{k-N}\right)=rt+C \quad \frac{N}{k-N}=Ae^{rt}
\end{equation*}

Applying initial condition $N(0)=N_0$ and rearranging to obtain $N$ explicitly gives
\begin{equation}
N=\frac{N_0 k}{N_0+(k-N_0)e^{-r t}}
\end{equation}

The discrete analog is

\begin{equation*}
N_t = \frac{N_0 k}{N_0 +(k-N_0)R_0^{-t}}
\end{equation*}

It is obtained from
\begin{equation*}
N_{t+1}=\frac{R_0 N_t}{1+N_T/M}
\end{equation*}
where $k=(R_0-1)M$ is the carrying capacity and $R_0$ is the proliferation rate per generation.


## Beverton-Holt model

Assumes a density-dependent relative mortality rate of the form

\begin{equation}
\frac{1}{N}\frac{\mathrm{d}N}{\mathrm{d}t}=-(\mu_1+\mu_2 N)
\end{equation}

\begin{align*}
&\frac{1}{N(\mu_1+\mu_2 N)}=\frac{A}{N}+\frac{B}{\mu_1+\mu_2 N}\\
&\Rightarrow A(\mu_1+\mu_2 N)+B N =1\\
&\Rightarrow A\mu_1 +(A\mu_2+B)N=1
\end{align*}

Equating coefficients of $N$ gives $A=\frac{1}{\mu_1}$, $B=-\frac{\mu_2}{\mu_1}$.

Thus, method of separation gives

\begin{align*}
&\left[\frac{1}{N}-\frac{\mu_2}{\mu_1+\mu_2 N}\right]\mathrm{d}N=-\mu_1\mathrm{d}t\\
&\Rightarrow \quad \ln(N)-\ln(\mu_1+\mu_2 N)=-\mu_1 t +k\\
&\Rightarrow \quad \frac{N}{\mu_1+\mu_2 N}=A e^{-\mu_1 t}
\end{align*}

Let $N(0)=N_0$, then

\begin{equation*}
\frac{N_0}{\mu_1+\mu_2 N_0}=A
\end{equation*}

A bit of algebra allows the solution to be rewritten as

\begin{equation}
N=-\frac{N_0 \mu_1}{N_0\mu_2 - (\mu_1+\mu_2N_0)e^{\mu_1 t}}
\end{equation}

Note: for the case when $\mu_1=-r$ and $\mu_2=r/k$ this reduces to the logistic model.
