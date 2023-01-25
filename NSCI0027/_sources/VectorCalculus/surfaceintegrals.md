# Surface Integrals

We can look at surface integrals next, these are the natural extension to line integrals, now we require a two variable parameterisation, here we
will use $(u,\, v)$ as variables which can parameterise the surface $S$ we are interested in.  

Lets start by thinking about some surface, as depicted in {numref}`parametrized_surface`, which we will break up 
into infinitesimal area elements $\mathrm{d}S$.  Just like we can write infinitesimal area elements $\mathrm{d}A = \mathrm{d}x\,\mathrm{d}y$ in 
Cartesian coordinates (and in polar coordinates $\mathrm{d}A = r\,\mathrm{d}r\,\mathrm{d}\theta$), we can 
break up this surface using the parameterisation $(u,\,v)$.  

```{figure} ../figures/parametrized_surface.png
---
name: parametrized_surface
---
Some general surface $S$ broken up into infinitesimal area elements $\mathrm{d}S$.  
```

We can think about the effect of some vector field crossing this surface, as depicted in {numref}`vector_field_thru_a_surface`.  


```{figure} ../figures/vector_field_thru_a_surface.png
---
name: vector_field_thru_a_surface
---
A vector field ${\bf F}$ crossing a surface $S$.  
```
To find the total contribution of the vector field actually going through a surface area element, we need to think about the 
components of the vector field. 


We can decompose ${\bf F} = {\bf F}_\bot + {\bf F}_{\parallel}$ components, as depicted in {numref}`normal_component_of_field`

```{figure} ../figures/normal_component_of_field.png
---
name: normal_component_of_field
---
Decomposition of vector field ${\bf F}$ into perpendicular components with respect to a surface area element $\mathrm{d}S$.
```

In order to find the components that cross through the surface, ${\bf F}_{\bot}$, we need a surface normal vector.  We know 
that in order to find a surface normal, we can do the cross product of two vectors that live on the surface.  

We also that the effect of differentiating vector ${\bf r}$ with respect to some parameter produces a vector which points in
the direction where ${\bf r}$ is maximised with respect to that parameter *and* crucially lives on the surface $S({\bf r})$, so
we use the derivatives with respect to the two parameters $(u,\,v)$:
```{math}
{\bf n} = \left( \frac{\partial {\bf r}}{\partial u}\right)\times \left(\frac{\partial {\bf r}}{\partial v} \right)
```

This means that combination of the vector field with the area element $|\mathrm{d}{\bf S}| = \mathrm{d}u\,\mathrm{d}v$ will be:
```{math}
\iint_S {\bf F} \cdot \mathrm{d}{\bf S} = \iint_S {\bf F}\cdot \left( \frac{\partial {\bf r}}{\partial u}\times \frac{\partial {\bf r}}{\partial v} \right)\,\mathrm{d}u\,\mathrm{d}v
```

We call this the **flux** of the vector field ${\bf F}$ crossing the surface $S$.

````{admonition} Definition

We can define:
```{math}
\iint_S {\bf F}({\bf r}) \cdot \mathrm{d}{\bf S} = \iint_S {\bf F}({\bf r}(u,\,v)) \cdot \left( \frac{\partial {\bf r}}{\partial u}\times \frac{\partial {\bf r}}{\partial v} \right)\,\mathrm{d}u\,\mathrm{d}v
```
as a *vector surface integral* along some surface $S$.

We can also define a *scalar surface integral*:
```{math}
\iint_S f({\bf r}(u,\,v))\left|\frac{\partial {\bf r}}{\partial u}\times \frac{\partial {\bf r}}{\partial v} \right|\,\mathrm{d}u\,\mathrm{d}v
```
````

## Calculating Surface Integrals

Similar to line integrals, we must parameterise the surface $S$ in order for this integral to be possible, so we will pick 
$S = S({\bf r})$ with ${\bf r} = {\bf r}(s,\, t)$ with $s \in[s_{min},\, s_{max}],\, t \in [t_{min},\, t_{max}]$.  
This means that if we move from 2D parametrisation to a surface parameterisation, we can find infinitesimal changes 
$\mathrm{d}s,\, \mathrm{d}t$ that make up the $\mathrm{d}S$ on the surface.  We can then 
define vectors $\bf u,\, v$ which live on the surface:
```{math}
\mathrm{d}{\bf u} &= \frac{\partial {\bf r}}{\partial s}\,\mathrm{d}s \\
\mathrm{d}{\bf v} &= \frac{\partial {\bf r}}{\partial t}\,\mathrm{d}t
```

and the final step is to find a cross product, this will produce the normal area vector, hence:
```{math}
\mathrm{d}{\bf S} = \mathrm{d}{\bf u} \times \mathrm{d}{\bf v} = \left(\frac{\partial {\bf r}}{\partial s} \times \frac{\partial {\bf r}}{\partial t} \right)\,\mathrm{d}s\,\mathrm{d}t
```

This means that in order to actually calculate the surface integrals we will need:
```{math}
I_f &=  \int_{s_{min}}^{s_{max}} \,\mathrm{d}s\,\int_{t_{min}}^{t_{max}} \, \mathrm{d}t\,f({\bf r}(s,\,t)\,\left| \frac{\partial {\bf r}}{\partial s} \times \frac{\partial {\bf r}}{\partial t} \right|\\
I_{\bf G} &=  \int_{s_{min}}^{s_{max}} \,\mathrm{d}s\,\int_{t_{min}}^{t_{max}} \, \mathrm{d}t\,{\bf G}({\bf r}(s,\,t))\cdot\left(\frac{\partial {\bf r}}{\partial s} \times \frac{\partial {\bf r}}{\partial t} \right)
```

## Surfaces of the form $z = f(x,\, y)$

A different sort of example is where we have a 2D scalar field $f(x,\,y)$ and we plot this as a surface $z = f(x,\,y)$.  
Here the parameterisation of the surface is given for free in terms of $x,\,y$.

The surface has a coordinate vector of the form:
```{math}
{\bf r}(x,\,y) = \begin{pmatrix} x \\ y \\ f(x,\, y) \end{pmatrix}
```
and the infinitesimal area element is given by:
```{math}
\mathrm{d}{\bf S} &=  \left(\frac{\partial {\bf r}}{\partial x} \times \frac{\partial {\bf r}}{\partial y}\right)\,\mathrm{d}x\,\mathrm{d}y =  \begin{pmatrix} 1 \\ 0 \\ \partial z/\partial x \end{pmatrix} \times \begin{pmatrix} 0 \\ 1 \\ \partial z/\partial y  \end{pmatrix}\,\mathrm{d}x\,\mathrm{d}y \\
&= \begin{vmatrix} \hat{\bf x} & \hat{\bf y} & \hat{\bf z} \\ 1 & 0 & f_x \\ 0& 1& f_y\end{vmatrix}\,\mathrm{d}x\,\mathrm{d}y =  \begin{pmatrix} -f_x \\ -f_y \\ 1  \end{pmatrix}\,\mathrm{d}x\,\mathrm{d}y
```
If we have a scalar surface integral, then area element will involve the magnitude of this vector:
```{math}
\mathrm{d}{S} = \left(\sqrt{\left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2 + 1}\right)\,\mathrm{d}x\,\mathrm{d}y
```

````{admonition} Worked example
:class: seealso
1\.
Lets find the surface area of a sphere with radius $R$.  The most natural choice of parameters here would be the angles $(\theta,\, \phi)$:


```{math}
{\bf r}(\theta,\,\phi) = \begin{pmatrix} R\sin(\theta)\cos(\phi) \\ R \sin(\theta)\sin(\phi)\\ R \cos(\theta)\end{pmatrix}
```

hence we can calculate $\mathrm{d}{\bf S}$ here:

```{math}
\mathrm{d}{\bf S} &=  \left(\frac{\partial {\bf r}}{\partial \theta} \times \frac{\partial {\bf r}}{\partial \phi}\right)\,\mathrm{d}\theta\,\mathrm{d}\phi\\
&=  R^2\begin{pmatrix} \cos(\theta)\cos(\phi) \\ \cos(\theta)\sin(\phi)\\ -\sin(\theta)\end{pmatrix} \times \begin{pmatrix} -\sin(\theta)\sin(\phi) \\ \sin(\theta)\cos(\phi)\\ 0 \end{pmatrix} \,\mathrm{d}\theta\,\mathrm{d}\phi\\
&=  R^2 \begin{pmatrix} \sin^2(\theta) \cos(\phi) \\ \sin^2(\theta)\sin(\phi)\\ \sin(\theta) \cos(\theta)\end{pmatrix} \,\mathrm{d}\theta\,\mathrm{d}\phi \\
&=  R^2 \begin{pmatrix} \sin(\theta) \cos(\phi) \\ \sin(\theta)\sin(\phi)\\ \cos(\theta)\end{pmatrix} \,\sin(\theta)\mathrm{d}\theta\,\mathrm{d}\phi \\
```
We can then recall that the radial vector for spherical polar coordinates has the form:
```{math}
\hat{\bf r} = \begin{pmatrix} \sin(\theta) \cos(\phi) \\ \sin(\theta)\sin(\phi)\\ \cos(\theta)\end{pmatrix}
```
and therefore :
```{math}
\mathrm{d}{\bf S} =  R^2\,\sin(\theta)\,\mathrm{d}\theta\,\mathrm{d}\phi\,\hat{\bf r} 
```


Thus the surface area integral takes the form:

```{math}
A = \iint_A \mathrm{d}S = R^2 \int_0^{2\pi}\,\mathrm{d}\phi\,\int_0^\pi\,\sin(\theta)\,\mathrm{d}\theta = 2\pi R^2\Big[-\cos(\theta)\Big]_0^{\pi} = 4\pi R^2
``` 
````

````{admonition} Further worked examples:
:class: seealso, dropdown
1\.
Find the surface area for $0 \leq x \leq 3$, $0 \leq y \leq 3$ for a sphere:
```{math}
x^2 + y^2 + z^2 = 9
```
This means that $z = f(x,\,y) = \sqrt{9 - x^2 - y^2}$, 
```{math}
\iint_A \mathrm{d}S &=  \int_{-R}^R\,\mathrm{d}x\,\int_{-R}^R\,\mathrm{d}y\,\sqrt{\left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2 + 1} \\
&=  \int_0^3\,\mathrm{d}x\,\int_0^3\,\mathrm{d}y\,\sqrt{ \frac{x}{\sqrt{9 - x^2 - y^2}} + \frac{y}{\sqrt{9 - x^2 - y^2}}  + 1} \\
&=  \int_0^3\,\mathrm{d}x\,\int_0^3\,\mathrm{d}y\,\frac{3}{\sqrt{9 - x^2 - y^2}}
```
If we use a change of variable, $x = \sqrt{9-y^2}\sin(\varphi) \Rightarrow \mathrm{d}x = \sqrt{9-y^2}\cos(\varphi)\,\mathrm{d}\varphi$ and therefore we have:
```{math}
\iint_A \mathrm{d}S =  3\int_0^{\pi/2}\,\mathrm{d}\varphi \int_0^3 \,\mathrm{d}y =  \frac{9\pi}{2}
```
which corresponds to $\frac{1}{8}$ of the full sphere's surface area $36\pi$, as expected.


2\. Find the surface area of a cone with height $h$ and base radius $R$.

Here we can use the parameterisation $z,\, \theta$ to describe any point on this surface.  This means we 
describe any point in cylindrical polar coordinates:
```{math}
{\bf r} = \begin{pmatrix} \frac{R}{h}z\,\cos(\theta) \\ \frac{R}{h}z\,\sin(\theta) \\ z \end{pmatrix}
```
with ranges $0 \leq z \leq h$ and $0 \leq \theta \leq 2\pi$.  Then to find the vectors in terms of this parameterisation:
```{math}
\frac{\partial {\bf r}}{\partial z} = \begin{pmatrix} \frac{R}{h}\,\cos(\theta) \\ \frac{R}{h}\,\sin(\theta) \\ 1 \end{pmatrix}\\
\frac{\partial {\bf r}}{\partial \theta} = \begin{pmatrix} -\frac{R}{h}z\,\sin(\theta) \\ \frac{R}{h}z\,\cos(\theta) \\ 0 \end{pmatrix}
```
which means the integrand takes the form:
```{math}
\frac{\partial {\bf r}}{\partial z} \times \frac{\partial {\bf r}}{\partial \theta} &= 
\begin{vmatrix} \hat{\bf x} & \hat{\bf y} & \hat{\bf z} \\ \frac{R}{h}\,\cos(\theta) & \frac{R}{h}\,\sin(\theta) & 1  \\ -\frac{R}{h}z\,\sin(\theta) & \frac{R}{h}z\,\cos(\theta) & 0  \end{vmatrix}\\
&= \begin{pmatrix} -\frac{R}{h}z\,\cos(\theta) \\ -\frac{R}{h}z\,\sin(\theta)\\ \frac{R^2}{h^2}z\end{pmatrix}\\
\Rightarrow \left|\frac{\partial {\bf r}}{\partial z} \times \frac{\partial {\bf r}}{\partial \theta}\right| &= \sqrt{\frac{R
^2}{h^2}z^2 + \frac{R^4}{h^4}z^2} = \frac{R}{h}z\sqrt{1 + \frac{R^2}{h^2}}
```
and so integrating we find:
```{math}
\iint_S\,\mathrm{d}S &= \int_0^{2\pi}\mathrm{d}\theta\,\int_0^h \frac{R}{h}z\sqrt{1 + \frac{R^2}{h^2}} \,\mathrm{d}z\\
&= 2\pi\frac{R}{h}\sqrt{1 + \frac{R^2}{h^2}}\Big[\frac{1}{2}z^2 \Big]_0^h = 2\pi\frac{R}{h}\frac{h^2}{2}\sqrt{1 + \frac{R^2}{h^2}} 
= \pi R\sqrt{h^2 + R^2}
```


````