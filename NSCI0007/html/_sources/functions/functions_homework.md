# Homework

<!-- https://www3.nd.edu/~powers/mcdowell.pdf -->

Last week you used the following equations to model the dynamics of the [Belousov–Zhabotinsky reaction](https://en.wikipedia.org/wiki/Belousov%E2%80%93Zhabotinsky_reaction) where $X_i$ and $Y_i$ are the concentrations of the two reactants X (red) and Y (colourless) at timestep $i$.

$$\begin{align}
X_{i+1} &= X_i + k_1-k_2X_i + k_3X_i^2Y_i\\
Y_{i+1} &= Y_i + k_4X_i - k_3X_i^2Y_i.
\end{align}$$

For the parameter values $k_1=0.1$, $k_2=0.4$, $k_3=0.1$ and $k_4=0.2$, the system results in decaying oscillations of the variables $X$ and $Y$. Over time the system reaches equilibrium and the values of $X$ and $Y$ reach a steady state. Assuming the system is at equilibrium after $1000$ time steps, we can assume that the steady-state value of $X$ is $X_{1000}$.

1. Run the simulation with the parameters above for $1000$ time steps, assuming the initial concentrations are zero, and plot the two arrays `X` and `Y` on the same figure.
2. Determine the steady-state value of $X$. 
3. Write a function `steady_state_X(k4)` which runs the simulation with $k_1=0.1$, $k_2=0.4$, $k_3=0.1$ and the given value of $k_4$, then returns the steady-state value of $X$.
4. Determine the steady-state value of X for a range of values of $k_4$ between $0$ and $0.3$ and plot the results on a graph with $k_4$ on the x-axis and the steady-state value of $X$ on the y-axis.


