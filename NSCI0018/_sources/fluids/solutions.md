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