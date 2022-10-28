# Surface Integrals

Now that we are happy with flat area and volume integrals, we can turn our attention to surfaces that are not flat, if we can break up the surface into area elements $\mathrm{d}A$ and then 
integrate over the whole surface, we can use all the same techniques described so far to think about this.  It is typical to define here an area vector ${\bf A}$ which points outwards from a 
surface and is in the normal direction to it:

```{math}
{\bf A} = A\,\hat{\bf n}
```

although sometimes for a curves surface we will use the letter $S$ for the surface normal.  We can write the inifinitesimal area element as:

```{math}
\mathrm{d}{\bf S} = \hat{\bf n} \,\mathrm{d}S
```
and this is depicted in {numref}`surfacenormal`.

```{figure} ../figures/surfacenormal.png
---
name: surfacenormal
---
Some general surfece surface $S$ with an infinitesimal surface element $\mathrm{d}{\bf S}$.  
```

For any scalar field $f(r) = f(x,\, y,\, z)$ that is defined on all the points of
the surface $S$ we can define the <b>Surface Integral</b> as:
```{math}
I_f = \int_Sf({\bf r})\,\mathrm{d}S
```

However this will only tell us the total amount of $f$ on the surface $S$, what is we instead had a vector field ${\bf G(r)}$ which crossed the surface $S$?  Then in this case, the surface integral is
given by:
```{math}
I_{\bf G} = \int_S {\bf G}\cdot \mathrm{d}{\bf S} = \int_S \left({\bf G}\cdot \hat{\bf n}\right)\,\mathrm{d}{ S} 
```

We define this quantity as the <b>flux</b> of the vector field $\bf G$ crossing the surface $S$.  Clearly as this has a scalar product, only the components parallel to $\hat{\bf n}$ (perpendicular 
to $S$) will be summed over in the integral.  

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

### Example - Sphere
An example, finding the surface area of a sphere with radius $R$, the most natural choice of $s,\,t$ here would be angles $\theta,\, \phi$:
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


Another way to see this is that $\frac{\partial {\bf r}}{\partial \theta} \propto \hat{\theta}$ from the definition of the spherical coordinate system, likeise$\frac{\partial {\bf r}}{\partial \phi}\ \propto \hat{\phi}$ therefore, 
we have $\hat{\theta} \times \hat{\phi} = \hat{\bf r}$ from the definition of the cross products.  

Thus the surface area integral takes the form:

```{math}
A = \int_A \mathrm{d}S = \int_A |\mathrm{d}{\bf S}| = R^2 \int_0^{2\pi}\,\mathrm{d}\phi\,\int_0^\pi\,\sin(\theta)\,\mathrm{d}\theta = 2\pi R^2\Big[-\cos(\theta)\Big]_0^{\pi} = 4\pi R^2
``` 

### Example of the form $z = (x,\, y)$
A different sort of example is where the coordinates $x,\, y$ are defined as terms of $z$, say $x^2 + y^2 + z^2 = R^2$, which would describe the upper half of a sphere (recall the lower half would be
with the negative root).  Here we have $z = z(x,\,y)$, thus the parametirisation of thesurface is just in terms of $x,\,y$ (a little like doing a line integral only in terms of $x$).  
Thus the surface has a coordinate vector of the form:
```{math}
{\bf r}(x,\,y) = \begin{pmatrix} x \\ y \\ z(x,\, y) \end{pmatrix}
```
meaning that the infinitemsimal surface vector element is given by:
```{math}
\mathrm{d}{\bf S} &=  \left(\frac{\partial {\bf r}}{\partial x} \times \frac{\partial {\bf r}}{\partial y}\right)\,\mathrm{d}x\,\mathrm{d}y \\
&=  \begin{pmatrix} 1 \\ 0 \\ \partial z/\partial x \end{pmatrix} \times \begin{pmatrix} 0 \\ 1 \\ \partial z/\partial y  \end{pmatrix}\,\mathrm{d}x\,\mathrm{d}y \\
&=  \begin{pmatrix} -\partial z/\partial x \\ -\partial z/\partial y \\ 1  \end{pmatrix}\,\mathrm{d}x\,\mathrm{d}y
```
Which means to solve this problem either we use this result with the scalar product of a vectof field $\bf G$, $I = \int {\bf G(r)}\cdot \mathrm{d}{\bf S}$.  For a scalar field we have 
$I = \int f\,\mathrm{d}S$, with:
```{math}
\mathrm{d}{S} = \left(\sqrt{\left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2 + 1}\right)\,\mathrm{d}x\,\mathrm{d}y
```

Lets see this for $x^2 + y^2 + z^2 = 9$, thus $z = \sqrt{9 - x^2 - y^2}$, lets consider the surface area over the range $x \in [0,\,3],\, y \in [0,\, 3]$:
```{math}
\iint \mathrm{d}S &=  \int_0^3\,\mathrm{d}x\,\int_0^3\,\mathrm{d}y\,\left(\sqrt{\left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2 + 1}\right) \\
&=  \int_0^3\,\mathrm{d}x\,\int_0^3\,\mathrm{d}y\,\left(\sqrt{ 1 + \frac{x}{\sqrt{9 - x^2 - y^2}} + \frac{y}{\sqrt{9 - x^2 - y^2}} }\right) \\
&=  \int_0^3\,\mathrm{d}x\,\int_0^3\,\mathrm{d}y\,\frac{3}{\sqrt{9 - x^2 - y^2}}
```
If we use a change of variable, $x = \sqrt{9-y^2}\sin(\varphi) \Rightarrow \mathrm{d}x = \sqrt{9-y^2}\cos(\varphi)\,\mathrm{d}\varphi$ and therefore we have:
```{math}
\iint \mathrm{d}S &=  3\int_0^{\pi/2}\,\mathrm{d}\varphi \int_0^3 \,\mathrm{d}y \\
&=  \frac{9\pi}{2}
```
which corresponds to $\frac{1}{8}$ of the full sphere's surface area $36\pi$, as expected.