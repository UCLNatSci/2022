# Multidimensional Integrals

Although we are used to find the area under a curve from the integral of a function $f(x)$ over some limits $x \in [a,\, b]$:

```{math}
A = \int_a^b f(x)\,\mathrm{d}x
```

if we had some area described by a function $f(x,\,y)$ we could try to find the area contained within this 2D shape.  Likewise if we have some 
function $f(x,\,y,\,z)$ describing some shape in 3D space, we could aim to find the total volume contained in this shape.  We think of these 
as multidimensional integals as extending integral calculus to multivariables, akin to partial differentiation extending differential calculus 
to multivaribles.

## Area Integrals
Formally we can think of some scalar field $\phi({\bf r})$ which has as inputs $\bf r$ which is some 2D position vector, which allows us to define:

```{math}
A = \int_A \phi({\bf r})\,\mathrm{d}A 
```
Conceptually we can think of $\mathrm{d}A$ just like we do for the one variable case of integration, breaking up a shape into infintesimal blocks 
which we then sum up over the integral, as depicted in {numref}`infinitesimalarea`:

```{figure} ../figures/infinitesimalarea.png
---
name: infinitesimalarea
---
Division of a 2-dimensional area A into infinitesimal area elements $\mathrm{d}A$.
```

An area integral is a <b>double integral</b>, because we have to perform integrals over both the $x$ and $y$ variables. When integrating over 
one variable, the other is held constant - akin to how we do partial differentiation too.  

```{math}
I = \int_A \phi({\bf r})\,\mathrm{d}A = \iint_A\phi({\bf r})\,\mathrm{d}x\,\mathrm{d}y
```

Note that an important special case is $\phi = 1$, where the area integral is equal to the total area, $A = \int_A \,\mathrm{d}A$.  
Otherwise what we are finding is an area weighed by the function $\phi$ - if $\phi(x,\,y)$ describes a function plotted on the $z$ axis, 
then the value of $\phi$ in each infinitesimal box will be what is summedup by this area integral.

The order of the integration can however sometimes matter - this becomes important if the limits of each of the integals depends on one of the other 
variables (this can happen as when the integration is done, all the other variables are considered constant).

### Area Integral Examples 

Lets think about a flat 2D sheet with some density $\sigma(x,\,y)$ (mass per unit area), as depcited in {numref}`areaintegral`,

```{figure} ../figures/areaintegral.png
---
name: areaintegral
---
Rectangular plate with some density $\sigma(x,\,y)$.
```
The total mass of the plate will be given by:

```{math}
M = \iint_A\sigma(\bf{r})\,\mathrm{d}A = \int_0^a\,\int_0^b\,\sigma(x,\,y)\,\mathrm{d}x\,\mathrm{d}y = \int_0^a\,\mathrm{d}x\,\int_0^b\,\mathrm{d}y\,\sigma(x,\,y)
```
where we use the final notation for brevity and ease of expression - it does not mean not to include the $\sigma$ term in the evaluation of the integrals. 

- If the rectangular plate has a uniform density, then $\sigma$ is just a constant and we find:

```{math}
M = \sigma\,\int0^a\,\mathrm{d}x\,\int_0^b\,\mathrm{d}y = \sigma\,a\,b = \sigma \,A
```

- If the rectangular plate has a uniform density, then we need to evaluate the integrals in turn, e.g. for $\sigma(x,\, y) = y^2 + xy$, we can 
calculate the $y$ integral first:

```{math}
M = \int_0^a\,\mathrm{d}x\,\int_0^b\,\mathrm{d}y\,(y^2 + xy) = \int_0^a\,\Bigg[\frac{1}{2}xy^2 + \frac{1}{3}y^3\Bigg]_0^b\,\mathrm{d}x = 
\int_0^a\,\left(\frac{1}{2}x b^2 + \frac{1}{3}b^3\right)\,\mathrm{d}x
```
This is now reduced the 2D integral to a 1D integral, which we can evaluate:
```{math}
M = \left[\frac{1}{4}x^2 b^2 + \frac{1}{3}b^3x\right]_0^a = \frac{1}{4}a^2b^2 + \frac{1}{3}ab^3
```

If we reverse the order integration however, starting from the $x$ integral, we find:
```{math}
M &=  \int_0^a\,\mathrm{d}x\,\int_0^b\,\mathrm{d}y\,(y^2 + xy) = \int_0^b\,\Bigg[\frac{1}{2}x^2y + xy^2\Bigg]_0^a\,\mathrm{d}y = 
\int_0^a\,\left(\frac{1}{2}y a^2 + ay^2\right)\,\mathrm{d}y \\
&= \left[\frac{1}{4}y^2 a^2 + \frac{1}{3}ay^3\right]_0^a = \frac{1}{4}a^2b^2 + \frac{1}{3}ab^3
```
So we see in this case, the order of integration does not matter.

Lets look a more involved example, $f(x,\,y) = x^2 + 2xy$ and we are interested in an area over a triangle, as depicted in {numref}`areaintegraltriangle`:

```{figure} ../figures/areaintegraltriangle.png
---
name: areaintegraltriangle
---
Triangular area with some function $f(x,\,y) = x^2 + 2xy$ defined over it.
```

We see here that the limits of the two integrals cannot both be constant - upper limit of the $y$ integral will change depending on the value of $x$ 
(or vice-versa), hence $x \in[0,\, 1]$ and $y \in [0,\, 1-x]$ is one way to think about this area:

```{math}
I = \iint f(x,\,y)\,\mathrm{d}A = \int_0^1\,\mathrm{d}x\,\int_0^{1-x}\,\mathrm{d}y\,(x^2 + 2xy)
```

Now that there is some function of $x$ in the limit, this says evaluate the $y$ integral first and the $x$ integral last:

```{math}
I &=  \int_0^1\,\mathrm{d}x\,\Bigg[x^2y + xy^2\Bigg]_0^{1-x}  = \int_0^1\,\mathrm{d}x\,\Bigg[x^2(1-x) + x(1-x)^2\Bigg] \\
&=  \int_0^1\,\mathrm{d}x\,(x-x^2) = \Bigg[\frac{1}{2}x^2 - \frac{1}{3}x^3 \Bigg]_0^1 = \frac{1}{6}
```
We can also switch round the integration, but choosing to have $y \in [0,\, 1],\, x \in [0,\, 1-y]$, which means that:
```{math}
I &=  \int_0^{1-y}\,\mathrm{d}x\,\int_0^{1}\,\mathrm{d}y\,(x^2 + 2xy) = \int_0^1\,\mathrm{d}y\,\Bigg[\frac{1}{3}x^3 + x^2y\Bigg]_0^{1-y}  \\
&=  \int_0^1\,\mathrm{d}y\,\Bigg[\frac{1}{3}(1-y)^3 + y(1-y)^2\Bigg] = \int_0^1\,\mathrm{d}y\,\left(\frac{2}{3}y^3 - y^2 + \frac{1}{3}\right) 
= \Bigg[\frac{1}{6}y^4 - \frac{1}{3}y^3 +\frac{1}{3}y\Bigg]_0^1 = \frac{1}{6}
```

A final example looks at a trickier set of limits, lets try and calculate the integral $I = \iint_A x^2y\,\mathrm{d}A$ for an area composed of 
a rectangle and a semi-circle, as depicted in {numref}`areaintegralsemicircle`:


```{figure} ../figures/areaintegralsemicircle.png
---
name: areaintegralsemicircle
---
Area shown as a shaded region composed of a rectangle and a half circle.
```
If we pick $x \in [-1,\,1]$, then the $y$ limits should be between the lower limit $y = -1$ and the upper limit at the semi-circle edge.  
Given that $x^2 + y^2 = 1$ is the equation of this line, then $y = \sqrt{1-x^2}$, hence $y \in [-1,\, \sqrt{1-x^2}]$, so the area is found by:

```{math}
I &=  \int_{-1}^1 \,\mathrm{d}x\,\int_{-1}^{\sqrt{1-x^2}}x^2y\,\mathrm{d}y = 
\int_{-1}^1\Bigg[\frac{1}{2}x^2y^2\Bigg]_{-1}^{\sqrt{1-x^2}} \,\mathrm{d}x\\
&=  \frac{1}{2}\int_{-1}^1\left(x^2(1-x^2) - x^2\right) \,\mathrm{d}x = -\frac{1}{2}\int_{-1}^1 x^4\,\mathrm{d}x = -\frac{1}{5}
```

We could do this integral the other way round, but this is quite a bit tricker!

In fact the choice of coordinates we choose will not change the value of the integral either, lets look at doing these sorts of integral in polar 
coordinates, given $y^2 + x^2 = R^2$ for $y \geq 0$, as depicted in {numref}`semicircle`:

```{figure} ../figures/semicircle.png
---
name: semicircle
---
Area shown as a shaded region composed of a half circle.
```

In Cartesian coordinates to find this area we would need to do:
```{math}
A = \iint \,\mathrm{d}x\,\mathrm{d}y = \int_{-R}^R\,\mathrm{d}x\,\int_0^{\sqrt{R^2 -x^2}}\,\mathrm{d}y = \int_{-R}^R\sqrt{R^2 - x^2}\,\mathrm{d}x
```

which will then require an integral substitution to solve, quite a pain!

In polar coodinates this becomes:

```{math}
A = \iint\,r\mathrm{d}r\,\mathrm{d}\theta = \int_0^R\,r\mathrm{d}r\,\int_0^{\pi}\,\mathrm{d}\theta = 
\pi\Bigg[\frac{1}{2}r^2\Bigg]_0^\pi = \frac{1}{2}\pi R^2
```
which makes the result we expect!


## Volume Integrals

The concept of an area integral can be extended to volume integrals. The integration region is now a volume having some shape. The integration 
egion is divided up into volume elements $\mathrm{d}V$, and the function to be integrated $\phi({\bf r})$ has a value in each element. Conceptually, 
the integral is the sum of all the contributions $\phi({\bf r})\,\mathrm{d}V$ over all the elements, in the limit where the volume elements become 
infinitesimally small.  In Cartesian coordinates, the volume element is simply $\mathrm{d}V = \mathrm{d}x\,\mathrm{d}y\,\mathrm{d}z$, and the volume
integral can be expressed as a <b>triple integral</b> over $x, \,y,\, z$:

```{math}
I = \int_V \phi({\bf r})\,\mathrm{d}V = \iiint_V \phi(x,\,y,\,z)\,\mathrm{d}x\,\mathrm{d}y\,\mathrm{d}z
```

### Volume Integral Examples

Lets think about volume integrals in Cartesian coordinates first, to calculate the volume integral of the function 
$f(x,\, y,\, z) = \frac{1}{2} \left(x^2 + y^2 + z^2\right)$ over a cube whose 8 corners are at the points $(\pm 1,\, \pm 1,\, \pm 1)$:

```{math}
V &=  \iiint\,\mathrm{d}V = \int_{-1}^1\,\mathrm{d}x\,\int_{-1}^1\,\mathrm{d}y\,\int_{-1}^1\,\mathrm{d}z\,
\left[\frac{1}{2} \left(x^2 + y^2 + z^2\right)\right]\\
&=  \frac{1}{2}\int_{-1}^1\,\mathrm{d}x\,\int_{-1}^1\,\mathrm{d}y\,\Bigg[x^2z + y^2z +\frac{1}{3}z^3\Bigg]_{-1}^1\\
&=  \int_{-1}^1\,\mathrm{d}x\,\int_{-1}^1\,\mathrm{d}y\,\Bigg(x^2 + y^2 +\frac{1}{3}\Bigg)\\
&=  \int_{-1}^1\,\mathrm{d}x\,\Bigg[x^2y + \frac{1}{3}y^3 +\frac{1}{3}y\Bigg]_{-1}^1\\
&=  2\int_{-1}^1\,\mathrm{d}x\,\Bigg(x^2 + \frac{2}{3} \Bigg)\\
&=  2\Bigg[\frac{1}{3}x^3 +\frac{2}{3}x\Bigg]_{-1}^1 = 4
```

If we wanted to find the volume of a sphere of radius $R$, we could calculate this using cartesian coordinates, where 
$x \in [-R,\, R]$ and then akin to the circle area in 2D $y \in[-\sqrt{R^2 - x^2},\,-\sqrt{R^2 - x^2}]$ and finally to elevate this 
to a volume in 3D $z \in[-\sqrt{R^2 - x^2 - y^2},\,-\sqrt{R^2 - x^2 - y^2}]$

```{math}
V = \iiint\,\mathrm{d}V = \int_{-R}^R \,\mathrm{d}y\,\int_{-\sqrt{R^2 - x^2}}^{\sqrt{R^2 - x^2}}\,
\mathrm{d}y\,\int_{-\sqrt{R^2 - x^2-y^2}}^{\sqrt{R^2 - x^2-y^2}} \,\mathrm{d}z
```
truely a nightmare to solve!  

Instead lets switch to spherical polar coordinates, with $r \in[0, \,R],\, \theta \in [0,\,\pi],\, \phi \in [0,\, 2\pi]$:

```{math}
V &=  \iiint\,\mathrm{d}V = \int_0^R r^2\,\mathrm{d}r\,\int_0^\pi\sin(\theta)\,\mathrm{d}\theta\,\int_0^{2\pi}\,\mathrm{d}\phi \\
&=  4\pi\Bigg[\frac{1}{3}r^3\Bigg]_0^R = \frac{4}{3}\pi R^3
```
as expected.

Likewise we could find the volume of a cylinder with radius $R$ and height $H$ (recall this could be done through a solid of revolution type 
calculation, but here we aim to think about 3D axes), in Cartesian coordinates this would take the form of $x \in [-R,\, R]$ then in 2D 
the circular cross section would be found through $y \in [-\sqrt{R^2 - x^2},\,\sqrt{R^2 - x^2}]$ and then the height $z \in [0,\, H]$, giving:

```{math}
V = \iiint\,\mathrm{d}V = \int_{-R}^R \,\mathrm{d}y\,\int_{-\sqrt{R^2 - x^2}}^{\sqrt{R^2 - x^2}}\,
\mathrm{d}y\,\int_{0}^{H} \,\mathrm{d}z
```
still not a great integral to compute, an integration variable chagne would be required.  

In cylindrical polar coordinates however, $r \in[0, R], \theta \in [0,\, 2\pi],\, z \in [0,\, H]$:

```{math}
V &=  \iiint\,\mathrm{d}V = \int_0^R r\,\mathrm{d}r\,\int_0^{2\pi}\,\mathrm{d}\theta\,\int_0^{H}\,\mathrm{d}z \\
&=  2\pi H \Bigg[\frac{1}{2}r^2\Bigg]_0^R = \pi R^2 H
```
as expected.

A more complicated example would be to find the volume integral of $f(x,\,y) = x^2y$ over a tetrahedral volume, bounded by the $x-y$, $y-z$ and $x-z$ axes 
as well as $x + y+ z = 1$, since all the bounding surfaces are symmetric in $x,\, y,\, z$, there is no initial preference in integration order, 
however the integrand does not contain $z$ so this is likely to be the easiest initial integral to compute, therefore:

```{math}
I = \iiint\,\mathrm{d}V\,x^2y 
```

with $x = 0, \,y = 0,\, z = 0$ up to the plane $x + y + z = 1$.  Therefore in the $z$ plane the limits are $z \in[0,\, 1 - x - y]$ and likewise in the 
$y$ plane the limits would be $y \in [0,\, 1-x]$ (since $z=0$ along this plane), hence along with $x \in[0,\, 1]$:

```{math}
I &=  \int_0^1\,\mathrm{d}x\,\int_0^{1-x}\,\mathrm{d}y\,\int_0^{1-x-y}x^2y\,\mathrm{d}z \\
&=  \int_0^1\,\mathrm{d}x\,\int_0^{1-x}\,\mathrm{d}y\Bigg[x^2yz \Bigg]_0^{1-x-y}\\
&=  \int_0^1\,\mathrm{d}x\,\int_0^{1-x}\,\mathrm{d}y\left(x^2y(1-x-y)\right)\\
&=  \int_0^1\,\mathrm{d}x\,\int_0^{1-x}\left(x^2y-x^3y-x^2y^2\right)\,\mathrm{d}y\\
&=  \int_0^1\,\mathrm{d}x\,\int_0^{1-x}\Bigg[\frac{1}{2}x^2y^2-\frac{1}{2}x^3y^2-\frac{1}{3}x^2y^3\Bigg]_0^{1-x}\\
&=  \frac{1}{6}\int_0^1\left(x^2 - 3x^3 + 3x^4 - x^5\right)\,\mathrm{d}x \\
&=  \frac{1}{6}\Bigg[\frac{1}{3}x^3 - \frac{3}{4}x^4 + \frac{3}{5}x^5 - \frac{1}{6}x^6\Bigg]_0^{1}= \frac{1}{360}

```