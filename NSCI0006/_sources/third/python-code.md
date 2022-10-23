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

# Python code

## numpy

### What it's for

The `numpy` function library is required for numeric calculations. It allows us to do mathematics using transcendental quantities such as $\pi$ and $e$, and it introduces mathematical functions such as $\sin$ and $\cos$.

In the preamble below we import the library using a convenient short name `np`. Therefore to use the definitions from this library we have to type `np.def` where `def` is the definition or function that we want to use.

```{code-cell}
import numpy as np
```

### First example here

Some example use of the numpy library, relevant to the materials covered in this book.

### Linspace

The function `linspace(start,end,n)` is used to generate a list of `n` equally spaced values between the specified start and end values. For example, the following code produces five equally spaced points in the range $[0,2\pi]$

```{code-cell}
start=0; end=2*np.pi
x=np.linspace(start,end,5)
```

## matplotlib

### What it's for

The `matplotlib.pyplot` library is used to make plots of our results. In the preamble below we import the library using a convenient short name `plt`. It allows us to create a variety of figures, including `plot` type.

```{code-cell}
import matplotlib.pyplot as plt
```

### Line or scatter plots

To make a line series plot or scatter plot we need to define a set of $x$ values and corresponding $y$ values. The example below produces a plot of $\sin(x)$ between $x=0$ and $x=\pi/2$.

```{code-cell}
# Make the data
x=np.linspace(0,np.pi/2,1000)
y=np.sin(x)

# Create the plot
plt.plot(x,y)

# customise the appearance:
plt.xlabel('x')
plt.xlim([0,1.5])

# Show the plot
plt.show()

```

## scipy

The `scipy` library is a very powerful suite of scientific methods. We will only use one function from this vast library, and so we import it with its own name.

```{code-cell}
from scipy.integrate import odeint
```

### odeint

The `odeint` function is used to solve ordinary differential equations of the form

\begin{equation}
\frac{\mathrm{d}x}{\mathrm{d}t}=f(x,t,\dots)
\end{equation}

where $\dots$ is a list of parameters.

For example, in REF we looked at the following equation involving parameters DEFINE

In this example there is no explicit time-dependence in function $f$, but we have to include `t` in our list of input arguments for the function definition, because `odeint` expects this.

We can write our function definition as follows. Here, we have named the function NAME, but you can choose any name for your function.

```{code-cell}
def NAME(x,t,p):
  dxdt = x
  return dxdt
```

To solve the ode we have to provide initial conditions and parameter values. We also have to define the list of time points that we want to find the solution for.

```{code-cell}
# Initial condition and parameter values
t0=0; x0=1; p=1

# Time points
tmax=20
t = np.linspace(0,20,100)

# Solve ODE
x = odeint(NAME,x0,t,args=(p,))

# Plot the result
plt.plot(t,x)
plt.show()
```

(import-plot)=
## Import data

Here goes the example of plotting the Hertzsprung-Russell diagram for the 100 nearest and 100 brightest stars.
