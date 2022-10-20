# Homework

## BZ Reaction

<!-- https://www3.nd.edu/~powers/mcdowell.pdf -->

The [Belousov–Zhabotinsky reaction](https://en.wikipedia.org/wiki/Belousov%E2%80%93Zhabotinsky_reaction), or BZ reaction, is a chemical reaction which exhibits non-equilbrium dynamics. Under certain conditions, the BZ reaction results in oscillatory behaviour, as demonstrated in [this video](https://www.youtube.com/watch?v=dMF4RjiITGM).

The BZ reaction can be modelled by the following equations, where $X_i$ and $Y_i$ are the concentrations of the two reactants X (red) and Y (colourless) at timestep $i$. At each timestep, the concentrations of the two reactants change according to the difference equations below. Each timestep has a duration of one second.

$$\begin{align}
X_{i+1} &= X_i + k_1-k_2X_i + k_3X_i^2Y_i\\
Y_{i+1} &= Y_i + k_4X_i - k_3X_i^2Y_i
\end{align}$$

1. Model the evolution of the chemical reaction for $300$ seconds, assuming the initial concentrations are zero, and using the parameter values $k_1=0.2,k_2 = 0.4, k_3 = 0.1\mathrm{~and~}k_4 = 0.3$.
2. Experiment with different values of $k_1$. For what range of values of $k_1$ does the reaction exhibit oscillations?
