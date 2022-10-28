# temp

A drawing of the state space showing equilibrium points, and a few representative change vectors and key trajectories

Unwrap the phase portrait to obtain the time series

Recall (shark-tuna): A small amount of shark fishing actually results in a higher peak shark population!

**Nullclines**

Lines along which one of the variables is not changing. For example
* $x$-nullcline satisfies $x^{\prime}=0$
* $y$-nullcline satisfies $y^{\prime}=0$

By studying the nullclines, we can determine the stability of the equilibrium points. The nullclines divide state space into sectors where the change vectors point in consistent directions.

Why bother with nullclines?
When we have a vector field, plotting the nullclines may seem redundant. However, a computer can plot a vector field only when numeric values are available for all parameters. On the other hand it is often possible to work with nullclines without specifying exact parameter values.


**State space:**

All possible states $\underline{X}$. With $n$ variables the state space is $\mathbb{R}^n$.

Change is movement through state space.

Start at an initial condition in state space and follow a trajectory tangent to the change vectors (for an autonomous system).

Note that change is continuous (not discrete). Can use Euler's method to discretise if this is desirable!


Next week we will linearize nonlinear problems. For now we won't do the maths, but just plot the phase portrait numerically:
