# Dispersion Relations and Wave Speed

## Dispersion relation

Now that we have our complex wave solutions to the equation, we can see that plugging in the solutions 
to the wave equation produce their own equations.  Lets start with the simplest wave solution, a 1D right hand moving wave:
```{math}
:label: waveform
u = u_0\,\exp(i(kx-\omega t))
```
Plugging this into the wave equation:
```{math}
u_{xx} &=& \,-k^2 \,u\\ 
u_{tt} &=& \, -\omega^2 \,u \\
u_{tt} &=& \, c^2\,u_{xx} \\
-\omega^2 \,u &=& \, -c^2\,k^2\,u \Rightarrow \omega^2 &=& \,c^2 k^2 \Rightarrow \omega = \,\pm\, c k
```
Since we have two roots for $\omega$ here, we can see that these correspond to either left or right hand moving waves.  
Therefore if we use {eq}`waveform` with the proviso that $\omega = \omega(k) = \pm c\, k$, this describes the d'Alembert wave solutions.

The function $\omega = \omega(k)$ is known as a <b>dispersion relation</b>.  In this case, $\omega(k)$ is a linear function of $k$, but in 
general it could be <em>any</em> function of $k$.  We can also rewrite this linear expression in terms of frequency and wavelegnth 
$f = \omega/2\pi, \,\lambda = 2\pi/k$:
```{math}
c = f \,\lambda
```
which is of course a familiar result! 

We do not in general need to stick to $\omega = c\,k$ however, as we will see later, non-linear dispersion relations are not 
uncommon and result from have a different form of wave equation.

Looking at the combination of $\omega/k$, notice it has units of:
```{math}
\frac{[\omega]}{[k]} = \frac{s^{-1}}{m^{-1}} = m\,s^{-1} = [\textrm{speed}]
```
and so we see this is a wave speed of some sort! 

## Group and Phase Velocity

We can start by considering again the movement of waves in time and space:

```{figure} ../figures/wavemove.png
---
name: Wavemove2
---
Visulisation of a wave moving in time and space.
```

A solution for these waves, $u(x,\,t) = u_0\,\cos(kx-\omega t)$, shows that although $x,\,t$ vary, each part of the 
waves remain a fixed distance apart - this is the wave phase $\Phi = kx - \omega t$.  Therefore this wave phase is invariant in 
space and time, hence:
```{math}
\frac{\partial \Phi}{\partial t} = k\frac{\partial(x)}{\partial t} - \omega = 0
```
which we can rearrange to find:
```{math}
v = \frac{\partial(x)}{\partial t} = \frac{\omega}{k}
```
This is known as the <b> phase velocity </b> of the wave $v_p$ and describes the rate at which the phase 
of the wave propagates through space.  

However this measure of wave velocity is only really unambiguous if there is a single wave moving in space and time, what happens 
if we have multiple waves?

Lets consider a sum of two waves, of equal amplitude, but different frequencies and wavelengths:
```{math}
u = u_1 + u_2 = u_0\cos(k_1x-\omega_1t) + u_0\cos(k_2x - \omega_2t)
```
we cna rewrite this using trigonometric identities:
```{math}
\cos(A+B) &= \cos(A)\cos(B) - \sin(A)\sin(B) \\
\cos(A-B) &= \cos(A)\cos(B) + \sin(A)\sin(B) \\
\Rightarrow \cos(A+B) + \cos(A-B) &= 2\cos(A)\cos(B) \\
\Rightarrow \cos(C) + \cos(D) &= 2\cos\left(\frac{C+D}{2}\right)\,\cos\left(\frac{C-D}{2}\right)
```
So we can rewrite our superposition of two waves as:
```{math}
u = 2u_0\,\cos\left(k_{avg}x - \omega_{avg}t\right)\,\cos\left(\frac{\Delta k}{2}x - \frac{\Delta \omega}{2}t\right)
```
where we have defined:
```{math}
k_{avg} = \frac{k_1+k_2}{2} &\qquad \omega_{avg} = \frac{\omega_1+\omega_2}{2} \\
\Delta k = \frac{k_1-k_2}{2} &\qquad \Delta \omega = \frac{\omega_1-\omega_2}{2} \\
```
The result of this can be visualised in {numref}`beats`

```{figure} ../figures/Beating_Frequency.png
---
name: beats
---
Visulisation of a superposition of two waves moving in time and space, the result is known as **beats** where wave 
follows an outer envelope function (dashed line), even though the overall phase (the black line) remains fixed.
```

We can track the phase of the waves now with the first cosine term, which we see follows:
```{math}
\Phi_1 &= k_{avg}x - \omega_{avg}t \\
\Rightarrow v_p = \frac{\omega_{avg}}{k_{avg}}
```
but the wave moves as a group, signified by the second cosine term:
```{math}
\Phi_2 &= \frac{\Delta k}{2}x - \frac{\Delta \omega}{2}t\\
\Rightarrow v &= \frac{\Delta \omega}{\Delta k}
```

If we pick a continuum of waves, then in the limit of $\Delta k \rightarrow 0$, each of the waves is separated by 
an infinitesimal difference $\mathrm{d}k$, meaning:
```{math}
v_g = \frac{\mathrm{d}\omega}{\mathrm{d}k}
```
This is known as the <b> group velocity </b> of the wave and describes the velocity with which the overall 
envelope shape of the wave's amplitudes propagates through space and time.  We also see that this velocity is 
dimensionally equivalent to $v_p$.

We can extend this to two and higher dimensions using partial derivatives and the gradient operator:
```{math}
\bf{v_p} &=& \,\frac{\bf \hat{k} }{|\bf{k}|}\omega \\
\bf{v_g} &=& \,\nabla_k \omega 
```
Usually these vectors point in the same direction, but there are examples in nature, for instance 
the anisotropic structure within a crystal, where the two vectors are not parallel. 

## Non-linear dispersion relation and wave speeds
The first thing to notice about the phase and group velocities is that for a linear dispersion relation, they 
are equal:
```{math}
\omega &= ck\\
v_p &=  \frac{\omega}{k} = c \\
v_g &= \frac{\mathrm{d}\omega}{\mathrm{d}k} = c
```
However once we look at non-linear $\omega(k)$ then the picture changes.  Lets look at a power law type dispersion relation:
```{math}
\omega = A k^{r}
```
where $A$ is a constant that has units of $[A] = s^{-1}\,m^{r}$ and $r$ is some constant exponent to be chosen.

There will be three regimes of $r$ values of interest:

1\. $r < 1$

This is non-linear dispersion relation:
```{math}
v_p &=  \frac{\omega}{k} = Ak^{r-1} \\
v_g &= \frac{\mathrm{d}\omega}{\mathrm{d}k} = Ark^{r-1}
```
and since $r<1$, $v_g < v_p$, which means that the wave envelope is moving slower than the individual parts of the 
wave.

2\. $r=1$

This is linear dispersion relation:
```{math}
v_p &=  \frac{\omega}{k} = A \\
v_g &= \frac{\mathrm{d}\omega}{\mathrm{d}k} = A
```
and so $v_g = v_p$, which means that all parts of the wave are moving at the same speed.

3\. $r > 1$

This is non-linear dispersion relation:
```{math}
v_p &=  \frac{\omega}{k} = Ak^{r-1} \\
v_g &= \frac{\mathrm{d}\omega}{\mathrm{d}k} = Ark^{r-1}
```
and since $r>1$, $v_g > v_p$, which means that the wave envelope is moving faster than the individual parts of the 
wave.

We can see these cases summarised in {numref}`dispersionplots`.
```{figure} ../figures/omegakdispersionplot.png
---
name: dispersionplots
---
Visulisation of a the differences between phase and group velocity in the case of a power law dispersion 
relation.  The left hand figure shows $r < 1$, the middle figure shows $r = 1$ and the right hand figure shows $r > 1$
```
