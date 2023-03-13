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

# Solutions

```{code-cell}
import numpy as np
import matplotlib.pyplot as plt
import matplotlib.cm as cm
```

## {ref}`pot-fun` 26

The velocity field is given by 

\begin{equation*}
(u,v)=(\phi_x,\phi_y) = (1-2x^2,-2xy)e^{-x^2-y^2}
\end{equation*}

A plot of the vector field and contours of the potential function is shown below. The contours of the scalar potential are perpendicular to the vector field.

```{code-cell} 

x=np.linspace(-2, 2, 30)
y=np.linspace(-2, 2, 30)

X,Y = np.meshgrid(x, y)  
(U,V)=(1-2*X**2,-2*X*Y)*np.exp(-X**2-Y**2)

# options to prettify the plot
fig,ax=plt.subplots(figsize=(5,5))
ax.axis([-2,2,-2,2])
ax.xaxis.set_ticks([]), ax.yaxis.set_ticks([])

ax.quiver(X,Y,U,V)

ax.contour(X,Y,X*np.exp(-X**2-Y**2),levels=10)

plt.show()
```

## {ref}`visuq` 27

**Question 1**<br>

The streamline for this problem that passes through satisfy $(x_0,y_0)$ at time $t$ is given as follows:
\begin{equation*}\frac{\mathrm{d}x}{\mathrm{d}s}=2x, \quad \frac{\mathrm{d}y}{\mathrm{d}s}=2ts \quad \rightarrow \quad (x,y)=(x_0 e^{2s},y_0 e^{2ts}).\end{equation*}

Note that the streamlines satisfy $y=kx e^{t}$, where $k=y_0/x_0$.

**Question 2**<br>


$\underline{u}=(x^2y,-xy^2)=\left(\frac{\partial\psi}{\partial y},-\frac{\partial\psi}{\partial x}\right) \quad \rightarrow \psi = \frac{x^2 y^2}{2}$

```{code-cell}
x=np.linspace(-2, 2, 100)
y=np.linspace(-2, 2, 100)

X,Y = np.meshgrid(x, y)
F=(X**2)*(Y**2)/2

# options to prettify the plot
fig,ax=plt.subplots(figsize=(5,5))
ax.axis([-2,2,-2,2])
ax.xaxis.set_ticks([]), ax.yaxis.set_ticks([])

ax.contour(X,Y,F,levels=[0.005,0.1,0.4,1,2,4])

plt.show()
```

**Question 3**<br>

**Streamlines :**

$\frac{\mathrm{d}x}{\mathrm{d}s}=\alpha \quad \rightarrow \quad x=\alpha s + x_0$

$\frac{\mathrm{d}y}{\mathrm{d}s}=\beta t \quad \rightarrow \quad y=\beta t s + y_0$

Combining the two expressions gives $y=\frac{\beta t}{\alpha}(x-x_0)+y_0$. This is the equation of the streamline at time $t$ that passes through $(x_0,y_0)$.   

**Particle paths :**

$\frac{\mathrm{d}x}{\mathrm{d}t}=\alpha \quad \rightarrow \quad x=\alpha t +x_0$  

$\frac{\mathrm{d}y}{\mathrm{d}t}=\beta t \quad \rightarrow \quad y=\beta \frac{t^2}{2}+y_0$

Combining the two expressions gives $y=\frac{\beta}{2 \alpha^2}(x-x_0)^2+y_0$. This is the path of a particle released from $(x_0,y_0)$ at time $t=0$.  

For this example, the streamlines are straight lines, and the particle paths are parabolas.

```{admonition} Note
:class: warning
In the case of the streamlines, we may obtain the following result using the chain rule

$\frac{\mathrm{d}y}{\mathrm{d}x}=\frac{\beta t}{\alpha} \quad \Rightarrow \quad y=\frac{\beta t}{\alpha}x+c$

However, we cannot use this treatment to solve for the particle paths since in that case $x=x(t)$, $y=y(t)$ and so $t$ must not be treated as constant.
```

## {ref}`chapex3` 28

**Question 1**<br>

$\nabla.\underline{u}=\nabla^2\phi=\frac{\partial^2\phi}{\partial x^2}+\frac{\partial^2\phi}{\partial y^2}=4x(x^2+y^2-2)e^{-x^2-y^2}$

```{code-cell}
x=np.linspace(-2, 2, 100)
y=np.linspace(-2, 2, 100)

X,Y = np.meshgrid(x, y)
Z=4*X*(X**2+Y**2-2)*np.exp(-X**2-Y**2)

# options to prettify the plot
fig,ax=plt.subplots(figsize=(5,5))
ax.axis([-2,2,-2,2])
ax.xaxis.set_ticks([]), ax.yaxis.set_ticks([])

# The "pcolormesh" function can be used to make a density plot.
ax.pcolormesh(X,Y,Z,shading='auto',cmap=cm.gray)
plt.show()
```

Note: This picture matches with what we found in {ref}`pot-fun` 26. From the plot of the vector field we could imply that there is a source in the left half plane and a sink in the right half plane.

**Question 2**<br>

**Particle paths:**

$\frac{\mathrm{d}x}{\mathrm{d}t}=2x, \quad \frac{\mathrm{d}y}{\mathrm{d}t}=3y, \quad \frac{\mathrm{d}z}{\mathrm{d}t}=-5z$

Solution: $x=x_0e^{2t}, \quad y=y_0e^{3t}, \quad z=z_0e^{-5t}$.

Fluid particles that initially lie on the ring $x_0=\cos(\theta)$, $y_0=\sin(\theta)$, $z_0=1$ are described in parametric form by

$x=\cos(\theta)e^{2t}, \quad y=\sin(\theta)e^{3t}, \quad z=e^{-5t}$

The equations can also be written as

$\left(\frac{x}{e^{2t}}\right)^2+\left(\frac{y}{e^{3t}}\right)^2=1, \quad z=e^{-5t}.$

The equations describe an ellipse parallel to the $(x,y)$ plane at height $z=e^{-5t}$. The ellipse has major axis $e^{3t}$ parallel to $x$ and minor axis $e^{2t}$ parallel to $y$.

Particles that initially lie on the ring are therefore swept towards the $(x,y)$ plane and away from the $z$ axis. This type of motion is called a straining motion.

<br>

```{image} navstok_img/straining.png
---
name: uniform flow
alt: alternative description
align: center
scale: 80%
---
```
<br>

Irrotational: $\nabla\times\underline{u}=\begin{vmatrix}\underline{e}_x & \underline{e}_y & \underline{e}_z\\\frac{\partial}{\partial x} & \frac{\partial}{\partial y}& \frac{\partial}{\partial z}\\ 2x & 3y & -5z\end{vmatrix}=0\underline{e}_x+0\underline{e}_y+0\underline{e}_z$

Solenoidal: $\nabla.\underline{u} = \frac{\partial}{\partial x}\left(2x\right)+\frac{\partial}{\partial y}\left(3y\right)+\frac{\partial}{\partial z}\left(-5z\right)=0$

## {ref}`consvq` 29

**Question 1**<br>

a). $\frac{\partial \rho }{\partial t}+u\frac{\partial \rho}{\partial x}+v\frac{\partial \rho}{\partial y}+w\frac{\partial \rho}{\partial z}+\rho \left(\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}+\frac{\partial w}{\partial z}\right)=0$

b). Laplace's equation, $\nabla^2\phi=0$, where $\underline{u}=\nabla\phi$

c). The condition for both types of flow is the same. Since incompressible flows must satisfy $\nabla.\underline{u}$, they are solenoidal. However, it may be possible for a compressible fluid to exhibit solenoidal flow.

**Question 2**<br>
\begin{align}
\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}+w\frac{\partial u}{\partial z}&=-\frac{1}{\rho}\frac{\partial p}{\partial x}\\
\frac{\partial v}{\partial t}+u\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}+w\frac{\partial v}{\partial z}&=-\frac{1}{\rho}\frac{\partial p}{\partial y}\\
\frac{\partial w}{\partial t}+u\frac{\partial w}{\partial x}+v\frac{\partial w}{\partial y}+w\frac{\partial w}{\partial z}&=-\frac{1}{\rho}\frac{\partial p}{\partial z}-g\end{align}

## {ref}`navstoq` 30

**Question 2**<br>
\begin{align}
\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}+w\frac{\partial u}{\partial z}&=-\frac{1}{\rho}\frac{\partial p}{\partial x}+\nu\left(\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}+\frac{\partial^2 u}{\partial z^2}\right)\\
\frac{\partial v}{\partial t}+u\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}+w\frac{\partial v}{\partial z}&=-\frac{1}{\rho}\frac{\partial p}{\partial y}+\nu\left(\frac{\partial^2 v}{\partial x^2}+\frac{\partial^2 v}{\partial y^2}+\frac{\partial^2 v}{\partial z^2}\right)\\
\frac{\partial w}{\partial t}+u\frac{\partial w}{\partial x}+v\frac{\partial w}{\partial y}+w\frac{\partial w}{\partial z}&=-\frac{1}{\rho}\frac{\partial p}{\partial z}+\nu\left(\frac{\partial^2 w}{\partial x^2}+\frac{\partial^2 w}{\partial y^2}+\frac{\partial^2 w}{\partial z^2}\right)\\
\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}+\frac{\partial w}{\partial z}&=0\end{align}

## {ref}`scalq` 31

\begin{equation*}\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}=0\end{equation*}

**Conservation of momentum** :

\begin{align*}
u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}&=-\frac{1}{\rho}\frac{\partial p}{\partial x}+\nu\left(\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}\right)\\
u\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}&=-\frac{1}{\rho}\frac{\partial p}{\partial y}+\nu\left(\frac{\partial^2 v}{\partial x^2}+\frac{\partial^2 v}{\partial y^2}\right)\\
\end{align*}

In terms of the non-dimensional variables (and with the pressure term dropped):

\begin{align*}&\frac{U_0^2}{L}\frac{\partial \hat{u}}{\partial\hat{x}}+\frac{V_0}{\delta}U_0\frac{\partial \hat{u}}{\partial\hat{y}}=\nu\left(\frac{U_0}{L^2}\frac{\partial^2 \hat{u}}{\partial\hat{x}^2}+\frac{U_0}{\delta^2}\frac{\partial^2 \hat{u}}{\partial\hat{y}^2}\right)\\
&\Rightarrow \quad \frac{U_0^2}{L}\left[\frac{\partial\hat{u}}{\partial\hat{x}}+\frac{\partial\hat{u}}{\partial\hat{y}}-\frac{\nu}{U_0 L}\left(\frac{\partial^2\hat{u}}{\partial\hat{x}^2}+\left(\frac{L}{\delta}\right)^2\frac{\partial^2\hat{u}}{\partial\hat{y}^2}\right)\right]=0
\end{align*}

That is,
\begin{equation*}
\frac{\partial \hat{u}}{\partial \hat{x}}+\frac{\partial \hat{u}}{\partial \hat{y}}-\frac{1}{R}\left[\frac{\partial^2 \hat{u}}{\partial \hat{x}^2}+\left(\frac{L}{\delta}\right)^2\frac{\partial^2\hat{u}}{\partial \hat{y}^2}\right], \quad R=\frac{U_{\infty} L}{\nu}.
\end{equation*}

The inertial terms are $\displaystyle \frac{\partial\hat{u}}{\partial\hat{x}}+\frac{\partial\hat{u}}{\partial\hat{y}}$

The convective terms are $\displaystyle \frac{1}{R}\left[\frac{\partial^2\hat{u}}{\partial\hat{x}^2}+\left(\frac{L}{\delta}\right)^2\frac{\partial^2\hat{u}}{\partial\hat{y}^2}\right]$

As $R\rightarrow\infty$, $\displaystyle\frac{1}{R}\frac{\partial^2\hat{u}}{\partial\hat{x}^2}\rightarrow 0$.

However, close to the boundary, $\displaystyle \frac{1}{R}\left(\frac{L}{\delta}\right)^2$ may be $\mathcal{O}(1)$, so the term involving $\displaystyle \frac{\partial^2\hat{u}}{\partial\hat{y}^2}$ should not be neglected.

Note: the equations of motion should be supplemented by boundary conditions. The appropriate conditions for this problem are "no slip" and no through-flow at the plate (see chapter {numref}`steady-soln`), and a requirement that the velocity must approach the free stream away from the boundary:

\begin{equation*}u(y=0)=0, \quad v(y=0)=0, \quad \lim_{y \rightarrow \infty}\underline{u}=(U_{\infty},0)\end{equation*}
