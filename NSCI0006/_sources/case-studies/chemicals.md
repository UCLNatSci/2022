# Chemical concentrations

This case study provides a demonstration of how technical definitions can be used to obtain measurement results. In some of the problems it can be quite challenging to balance the involved units or to accurately relate the given ratios to the physical scenarios.

```{admonition} [The Sign of Four, Sir Arthur Conan Doyle, (1890)](https://blog.sciencemuseum.org.uk/the-addictive-history-of-medicine-the-curious-case-of-the-7-percent-solution/)
:class: quote
“Which is it to-day,” I asked, “morphine or cocaine?”<br>
He raised his eyes languidly from the old black-letter volume which he had opened.<br>
“It is cocaine,” he said, “a seven-per-cent solution. Would you care to try it?”
```

## Definition

Concentration is a measure of the relative amount of one substance contained within a mixture. In this case study we consider a solute dissolved in a solvent to form a solution, such as glucose dissolved in water. The concentration is the ratio of either:
* solute : solvent
* solute : solution

The concentration of a solution can be expressed in various different ways, referring to either measurements of mass, volume, or number of elementary entities



## Molar concentration (molarity)

Biologists usually refer to concentrations using the non SI unit $\text{M}$, which is referred to as *molarity*. This measurement gives the number of moles of **solute** that are present in a litre of **solution** and so it is given in mol/l.

To convert from a molar concentration (mol/l) to a mass concentration (g/l) we simply multiply the concentration by the molar mass of the solute. For instance, for a 1mM (millimole) solution of glucose we use the molar mass result for glucose, which is 180.16 g/mol:

\begin{equation*}
(1\text{ m mol/l})\times (180.16 \text{ g/mol}) = 180.16 \text{ mg/l}
\end{equation*}

Therefore we can determine (for example) how much glucose is required to prepare 10ml of solution:

\begin{equation*}
(180.16 \text{ mg/l}) \times (10^{-2}\text{l})=1.8016\text{ mg}.
\end{equation*}

The solution can then be made up to 10ml by adding solvent.

Although it is fairly straghtforward to determine mass concentration from molarity in this manner, it can be inconvenient, so lab recipe books often specify mass concentration (in mg/l or g/l) rather than molarity  (mM or M).

```{exercise}
How much NaCL must we weigh out to prepare a solution with concentration 0.15M?
```

```{toggle}
The relative molar mass of NaCl is 58.45g/mol and so the required amount is:

$(0.15\text{ mol/l})\times (58.45\text{ g/mol}) = 8.77\text{ g/l}$

or 8.77mg/ml if you prefer
________
```

```{exercise}
Suppose we have cells or a tissue suspended in 10ml of buffer, and we want to add atropine, molar mass 289.37 g/mol, to achieve a concentration of 1nM. What mass of drug must be added?
```

```{toggle}
$\begin{alignat*}{2}
1\text{ nM}&=1\times 10^{-9}\text{ mol/l}=(1\times 10^{-9}\text{ mol/l})\times(289.37\text{ g/mol})\\
&=2.89\times 10^{-7}\text{ g/l}=2.89\times 10^{-7}\times 10^{-2}\text{ g/}10^{-2}\text{l}\\
&=2.89\text{ng/}10\text{ml}.
\end{alignat*}$

*Practical note [from Mathematics for Biological Scientists, p22](https://www.taylorfrancis.com/books/mono/10.4324/9780203833520/mathematics-biological-scientists-mike-aitken-bill-broadhurst-steve-hladky):*

2.89ng is not an easy amount to handle - it is probably too small to see on the end of a spatula, so we add the required amount of drug by pipetting a small quantity of concentrated stock solution into our final solution.

The smallest amount of stock that we can reliably pipette is 10$\mu$l. Pipetting this quantity into 10ml willl produce a 100-fold dilution. Thus, the concentration of atropine in the stock solution must be 1$\mu$M so that the final solution can be 1nM.

Preparing a 1$\mu$M solution is still problematic, so we would first prepare a stock at 1mM and dilute to 1nM.
________
```

## Mass fraction

The concentration of a solution may also be given as a mass fraction %(w/w), which is the solute mass as a percentage of the total solution mass.

To convert between molarity and mass fraction it is necessary to know the mass:volume relationship for the solution, which depends on both temperature and pressure. There is no simple way to obtain the density of a solution from known densities of the solute and solvent, since the volume of a solvent changes when it is in solution.

Values for the density as a function of mass fraction can be found in tables. For instance, for an aqueous solution of sodium chloride NaCl(aq), the following values are given at standard temperature and pressure in the CRC Handbook of Chemistry and Physics Online:

```{table} NaCl(aq) density for different concentrations

| %(w/w) | 8.0 | 10.0 | 12.0 | 14.0 | 16.0 | 18.0 | 20.0 | 22.0 |
| :----- | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| $\rho$ kg/l | 1.0559 | 1.0707 | 1.0857 | 1.1008 | 1.1162 | 1.1319 | 1.1478 | 1.1640 |
```

The relationship between molarity $c$ and the mass fraction $r$ is given by

\begin{equation}
r = \frac{c \hat{x}}{\rho},
\end{equation}

where $\hat{x}$ is the molar mass of the solute in kg/mol. The numerator of this fraction is the mass of solute in a litre of solution. The denominator is the total mass of a litre of solution. We should check that the units balance:
* $c\hat{x}$ : (mol/l)$\times$(kg/mol) = kg/l
* $\rho$ : kg/l

The ratio of these two quantities is a pure number, as expected.

```{exercise}
Using the given table for the density of NaCl(aq) at standard temperature and pressure (STP), calculate the molarity of a 10.0% (w/w) solution.
```

```{toggle}
\begin{equation*}c=\frac{\rho r}{\hat{x}}=\frac{(1.0707\text{ kg/l})\times0.10}{0.058443\text{ kg/l}}=1.832\text{M}\end{equation*}
________
```

```{exercise}
When sodium chloride is dissolved in water, there is a small contraction in the total volume of the solution. For a 8% (w/w) solution of NaCl(aq), estimate the size of the contraction as a percentage, given that the density of NaCl is approximately 2.17kg/l and the density of water is approximately 0.997kg/l.

Hint: The total mass of the solution is given by adding the mass of the solute and solvent, but the total volume does not follow a similar rule.
```

````{toggle}
At 8% w/w, $\rho=1.0559\text{ kg/l}$, so we may say that in a litre of solution:
\begin{equation*}
(m+M)=1.0559\text{ kg},
\end{equation*}
where $m$ is the mass of the solute and $M$ is the mass of the solvent.

Furthermore at 8% w/w, $m=0.08(m+M)$ and $M=0.92(m+M)$. Thus, for a litre of solution the required volumes of solute and solvent are given respectively by:
\begin{equation*}
v=\frac{0.08\times 1.0559\text{ kg}}{2.17\text{ kg/l}}, \qquad V=\frac{0.92\times 1.0559\text{ kg}}{0.997\text{ kg/l}}.
\end{equation*}
The percentage change in volume in our one litre reference solution is given by
\begin{equation*}
\frac{(v+V)-1}{1},
\end{equation*}

The result is approximately 1.33%. The graph below illustrates the volume contraction for different concentrations of NaCl(aq).

```{image} imgs/mass-contraction.png
:alt: mass-contraction
:align: center
```
________
````


## Molality

Molality is the standardized measure of concentration (but not the most common!). It is defined in similar manner to the molarity, but uses **mass of the solvent** rather than the **volume of the solution**. The SI unit for concentation is therefore mol/kg referred to as the *molality*.

We can express a straightforward ratio between the % (w/w) and the molality as follows, where $\hat{x}$ is the molar mass of the solute in kg/mol:

```{math}
b=\frac{r}{\hat{x}(1-r)}
```

**Explanation:**

The mass:mass ratio of solute:solvent is given by $r:(1-r)$. To convert the numerator to a measurement in moles we divide by the molar mass of the solute.

```{exercise}
Given that the molar mass of NaCl is 58.443, find the molality of an 8.0% (w/w) solution.
```
```{toggle}
$\hat{x}=58.443\times 10^{-3}=0.058443$kg/mol.

$b=\left(\frac{0.08}{1-0.08}\right)\left(\frac{1}{0.058443}\right)=1.488$mol/l.
________
```

To convert between molarity and molality we need to know the density of the solution. For example, consider a 0.1500 M NaCl solution with density 1.0064 kg/l. The molar mass of NaCl is $8.77\times 10^{-3}\text{ kg/l}$, and therefore the relative mass of the solvent is

\begin{equation*}
(1.0064 - 8.77\times 10^{-3})\text{ kg/l}
\end{equation*}

Thus, the molarity is
\begin{equation*}
\frac{0.15 \text{ mol/l}}{(1.0064 -0.0087)\text{ kg/l}}=0.1504 \text{ mol/kg}
\end{equation*}

```{exercise}
The molar mass of sucrose is 342.3 g/mol and the density of a 2.555M solution of sucrose is 1.2887 kg/l.

(a) What is the concentration of sucrose expressed as % (w/w)?

(b) What is the concentration expressed as molarity? (mol/kg)
```

```{toggle}
$2.555\text{M}=(2.555\text{ mol/l})(342.3\text{ g/mol})=874.577\text{ g/l}$

Mass of solvent: $(1.2887-0.874)\text{ kg/l}=0.4141 \text{ kg/l}$

(a) As % (w/w):
\begin{equation*}
\frac{0.8746\text{ kg/l}}{1.2887\text{ kg/l}}=0.6787\qquad \text{(67.87%)}
\end{equation*}

(b) As mol/kg:
\begin{equation*}
\frac{2.555\text{ mol/l}}{0.4141\text{ kg/l}}=6.17\text{ mol/kg}
\end{equation*}
```

## Summary of measurements

```{table} Measurement definitions used in this section

| name</th> <th>symbol</th> <th>units</th> <th>definition</th></tr><tr style="background-color:#FFC0CB"><td align="left">$\hat{x}$</td> <td align="left">molar mass of solute</td> <td align="left">kg/mol</td> <td align="left">mass of 1 mol of solute (in kg)</td></tr><tr><td align="left">$\rho$</td> <td align="left">density of solution</td> <td align="left">kg/l</td> <td align="left">mass of 1 litre of solution (in kg)</td></tr><tr style="background-color:#FFC0CB"><td align="left">$r$</td> <td align="left">mass fraction % (w/w)</td> <td align="left">%</td> <td align="left">Solute mass as % of solution mass</td></tr><tr><td align="left">$c$</td> <td align="left">molarity</td> <td align="left">mol/l</td> <td align="left">amount of solute (mol) in 1 litre of solution</td></tr><tr style="background-color:#FFC0CB"><td align="left">$b$</td> <td align="left">molality</td> <td align="left">mol/kg</td> <td align="left">amount of solute (mol) to be added to 1kg of solvent</td></tr>
|---|
||
```

```{exercise}
Write down an expression relating the molality $b$, molarity $c$, density $\rho$, and molar mass $\hat{x}$. Your answer should NOT feature the mass fraction $r$.
```

```{toggle}
\begin{equation*}
b=\frac{c}{\rho-c \hat{x}}
\end{equation*}
```
