# Simple models

We will begin to explore some differential equations, their meaning, and their solutions.


```{exercise}
Water flows out of a bucket at a constant rate of 0.1L/sec. Write down an equation for the amount of water $V$ left in the bucket at time $t$. Is it realistic?
```

```{toggle}

Let $V(t)$ be the amount of water (in litres) left in the bucket at time $t$ (in seconds). According to the given information,

\begin{equation*}
\frac{\mathrm{d}V}{\mathrm{d}t}=-0.1 \quad \Rightarrow V(t)=V_0 - 0.1t
\end{equation*}

It works until the bucket is empty!

However, the rate of outflow may depend on water level in the bucket (e.g. due to pressure)
_________
```

```{exercise}
Newton's second law says that Force=mass $\times$ acceleration.

Can you write this down as a problem involving velocity $v$?
```

```{toggle}
We use the fact that acceleration is the rate of change of velocity to write result in mathematical form as:

\begin{equation*}
F=m\frac{\mathrm{d}v}{\mathrm{d}t}
\end{equation*}

We may also write the equation in terms of the displacement, using the fact that the velocity is the rate of change of displacement:

\begin{equation*}
F= m \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\mathrm{d}x}{\mathrm{d}t}\right)=m\frac{\mathrm{d}^2 x}{\mathrm{d}t^2}
\end{equation*}
_________
```

## Exponential model

```{exercise}
A loan company charges interest of $r\%$ per month. Write this down in the form of a difference equation. Also write down the general solution given an initial investment of $M_0$
```

```{toggle}
In each time step $\Delta t=1$

\begin{equation*}
\frac{\Delta M}{\Delta t} = \frac{\left(1+\frac{r}{100}\right)M-M}{1}=\frac{r}{100}M.
\end{equation*}

The equation may be rearranged as
\begin{equation*}
\frac{1}{M}\frac{\Delta M}{\Delta t} = \frac{r}{100}.
\end{equation*}

The relative growth rate is constant, as we have seen previously for this model.
_________
```

```{exercise}
Write down a differential equation corresponding to the previous exercise, supposing that interest is compounded continuously, rather than monthly.
```

```{toggle}
If interest is compounded continuously then it is convenient to write
\begin{equation*}
M=M_0 e^{\lambda t},
\end{equation*}
which we can do by taking $\lambda =\ln\left(1+\frac{r}{100}\right)$.

Differentiating then gives

\begin{equation*}
\frac{1}{M}\frac{\mathrm{d}M}{\mathrm{d}t}=\lambda
\end{equation*}
```

```{exercise}
Given a module of discrete compound growth of a quantity $M$ with growth factor $r$ and initial value $M_0$, find the time to reach a given value.
```

```{toggle}
\begin{align*}
\frac{M}{M_0}=(1+r)^t \quad &\implies \quad \ln(M/M_0)=t\ln(1+r)\\
& \implies t=\frac{\ln(M/M_0)}{\ln(1+r)}
\end{align*}
_________
```

```{exercise}
Let $x(t)$ be the population of a given area at time $t$. Write down an expression for the per-capita rate of change of population change.

Convert this to an equation for $x(t)$ by assuming that the per-capita rate of population change is equal to a constant $\mu$.
```

```{toggle}
\begin{equation*}
\frac{1}{x}\frac{\mathrm{d}x}{\mathrm{d}t} = \mu \quad \implies \quad x = x_0 e^{\mu t}
\end{equation*}

We could also express the equation in relation to the doubling time $\tau$. For $x$ to be doubled, $x/x_0=2$ which gives

\begin{equation*}
e^{\mu\tau}=2 \quad \Rightarrow \quad x=x_0 2^{t/\tau}\ .
\end{equation*}
_________
```

```{exercise}
[Cocaine](https://www.emcdda.europa.eu/publications/drug-profiles/cocaine_en) has a half-life of around 0.7-1.5 hour in human blood. Determine what percentage will remain after six hours.
```

```{toggle}
Let $\tau$ be the half-life. Then, when $t=6$hrs,

\begin{equation*}
\frac{x}{x_0}=2^{-t/\tau} = \frac{1}{2^{6/\tau}} = [0.26 - 6.25]\%.
\end{equation*}

You may wish to compare this to the results for caffeine and alcohol, which each have a mean half-life of about 5 hours.
_________
```

## Numeric solution

Consider a general equation of the following form, where $f(x,t)$ is a known function:

```{math}
:label: std-prob
\frac{\mathrm{d}x}{\mathrm{d}t} = f(x,t).
```

To obtain a numeric estimate of the solution we can use the discrete derivative formula

\begin{equation}
\frac{\Delta x}{\Delta t}  =\frac{x_{i+1}-x_i}{h},
\end{equation}
where $h$ is the step size of $t$. By using this formula to estimate the continuous derivative in {eq}`std-prob` we the may obtain the rearrangement

\begin{equation}
x_{i+1} = x_i + h f(x_i,t_i).
\end{equation}

This allows us to start from a given initial value $x_0$ and "step forward" successively to obtain $x_1$, $x_2$, etc.

### Example

Consider the equation governing exponential growth/decay:

\begin{equation}
\frac{\mathrm{d}x}{\mathrm{d}t} = \alpha x.
\end{equation}

The discrete formula for this problem is given by

\begin{equation}
x_{i+1} = (1+\alpha h)x_i.
\end{equation}

Notice that the solution grows if $\alpha>0$, which matches what we expect to see for exponential growth.

The code below can be used to carry out the forward stepping and plot the solution. By comparing to the known solution we can find the size of the error on a given interval. Here, using a step size $h=0.02$, the maximum error is also around 0.02%.

```{code}
import numpy as np
import matplotlib.pyplot as plt

a=0.1 #alpha

#range of values to plot for
t=np.linspace(0,20,10000)

#initialise solution array
x=np.ones(len(t))

# forward stepping
h=t[1]-t[0] #step size

for i in range(len(t)-1):
  x[i+1] = (1+a*h)*x[i]

plt.plot(t,x)
plt.show()

# Calculate the error using the known solution
x_sol=np.exp(a*t)
err=(x-x_sol)/x_sol

# Maximum error (as %)
print(100*max(abs(err)))
```

## Offset model


```{exercise}
In an offset exponential model, the rate of change of a quantity $Q$ is proportional to the difference from some **equilibrium** value $Q_e$ in the manner
\begin{equation*}
\frac{\mathrm{d}Q}{\mathrm{d}t}=r(Q-Q_e)
\end{equation*}

By defining $D=(Q-Q_e)$, write down an equation for $\dot{D}$ and solve it.

What do we mean when we say that $Q_e$ is the equilibrium value?
```

```{toggle}
Let $D=(Q-Q_e)$, then

\begin{equation*}
\frac{\mathrm{d}D}{\mathrm{d}t}=rD \quad \rightarrow \quad \rightarrow D=D_0 e^{r t}
\end{equation*}

The equilibrium value is the point where $\dot{Q}=0$. If the system reaches its equilibrium then it will remain there unless some external influence acts on the system to move it away from its equilibrium.
```

```{exercise}
Apply the offset equilibrium model to find the time taken for a drink to cool from 80C to 63C given an ambient (room) temperature of 20C, given that $r=-0.11$/min.

```


```{toggle}
\begin{equation*}
\ln(D/D_0)=rt \quad \implies \quad t=\frac{1}{-0.11}\ln\left(\frac{63-20}{80-20}\right)=\frac{1}{0.11}\ln(60/43)
\end{equation*}

The drink will take 3 mins and 2 sec to reach ambient temperature.

Note that according to this model, the drink will never actually _reach_ room temperature, though it will approach it in the limit.
```

## Restricted growth models

The Von Bertalanffy equation is the simplest example of a restricted growth model. It is provided by the equation,
\begin{equation*}
\frac{\mathrm{d}L}{\mathrm{d}t}=k(L_{\infty}-L),\qquad L(t_0)=0
\end{equation*}

It has solution

\begin{equation*}
L=L_{\infty}\left(1-e^{-k(t-t_0)}\right)
\end{equation*}

A plot of this curve is shown below:

```{code}
import numpy as np
import matplotlib.pyplot as plt

# example parameters
k=0.52; Linf=275.2; t0=-0.47;

t=np.linspace(t0,10)

# plot the function
L=Linf*(1-np.exp(-k*(t-t0)))

plt.plot(t,L)
plt.ylim([0,Linf])
plt.show()
```

```{image} imgs/vonbert.png
:alt: von-bertalanffy
:width: 60%
:align: center
```

### To be continued...
