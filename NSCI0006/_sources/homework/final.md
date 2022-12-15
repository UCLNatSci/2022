# Maths coursework 2

Your submission of the two case studies is worth 50% of the mark for this module. There are 25 marks available for the case study on *Peak oil* and 25 marks available for the case study on *Climate tipping points*.

You will submit one pdf file for each of the case studies. For each case study I recommend that you collate all of your work into a single jupyter notebook, which you can then download as a pdf for submission.

```{toggle}
To include handwritten scans and text in your jupyter notebook (within CoCalc) select
`Cell > Change to markdown`.

* To insert a scanned image, select the picture icon in a markdown cell.
* To include typeset mathematics, select "Edit" in a markdown cell.

Within the text editor you can toggle between Text (display) mode and Markdown mode. In markdown mode you can use LaTeX syntax to write mathematical equations.
```

## Peak oil

### {numref}`ex-po1` [2pt]

There is one mark for importing and plotting the growth rate data and one mark for commenting on key features you observe.

### {numref}`ex-po2` [3pt]

Solving the logistic equation numerically should result in the familiar sigmoidal (S-shaped) curve. This exercise is very similar to the examples given in chapter 10.

### {numref}`ex-po3` [2pt]

There is one mark for correctly differentiating both sides with respect to $t$, and another mark for rearranging to obtain an expression for $\mathrm{d}x/\mathrm{d}t$ fully in terms of $x$. You should obtain the logistic differential equation!


### {numref}`ex-po4` [2pt]

There is one mark for the rearrangement to obtain $x$ as a function of $t$, and one mark for demonstrating the limiting values for $t\to\pm\infty$. Think: do your results agree with the shape of the curve you obtained when you solved the equation numerically?

### {numref}`ex-po5` [3pt]

There is one mark for plotting $P(x)$ and two marks for the commentary about the growth rates.

### {numref}`ex-po6` [2pt]

This question is about finding the maximum growth rate, and the time when it occurs. When you are asked to show something analytically it means using a mathematical derivation rather than a numerical or graphical method.

### {numref}`ex-po7` [6pt]

In this question marks are awarded as follows:

* [3] Plot $\left(x,\frac{1}{x}\frac{\mathrm{d}x}{\mathrm{d}t}\right)$. This result shows how the relative growth rate changes as a function of the total amount of oil extracted.

* [2] Fit a straight line to the portion of the data that follows an approximately linear trend

* [1] State estimates for the parameters $C,r$ based on your the fitted line

### {numref}`ex-po8` [2pt]

There is one mark for estimating $x_0$ using the given formula, and one mark for plotting the fitted curve with the data.

### {numref}`ex-po9` [3pt]

The written commentary is worth three points. This means that you should aim to provide three critical comments or assertions. You should do some reading to support your understanding of the merits and limitations of the logistic model as a model for oil production.

## Climate tipping points

### {numref}`ex-ct1` [4pt]

This question requires a numeric solution, which is similar to what you did to solve the logistic equation in the case study on *Peak oil*. You need to solve it for two different initial conditions and show the solutions on the same axes.

There are two points for the plotted solutions, and one point for correctly labelling the axes. Your plots must clearly illustrate how the two curves approach to an equilibrium state.

### {numref}`ex-ct2` [2pt]

There is one point for the solution, which is a simple rearrangement of the inflow=outflow condition. Convert your answer from Kelvin to Celsius! For the other point, say whether you think the solution is realistic and why.

### {numref}`ex-ct3` [1pt]

To answer this question only requires a rearrangement of the inflow=outflow condition. Don't forget that in the model $T$ is in Kelvin.

### {numref}`ex-ct4` [4pt]

This question requires you to plot the function, for selected values of $A,B,k,T_m$. To obtain the marks you need to choose parameter values that give a result similar to the one shown in {numref}`albedo-model`.

### {numref}`ex-ct5` [9pt]

You are encouraged to watch the video linked in this case study before attempting this investigation. Marks will be awarded as follows:

* [3] Plots illustrating the inflow together with the outflow for different values of the greenhouse parameter $g$.
* [3] Supporting commentary that clearly explains what happens in the system as $g$ decreases, with reference to plots.
* [3] Identification of the approximate values of $g,T$ at the tipping point, with clear details of how it was found.

### {numref}`ex-ct6` [5pt]

This question requires a description of the dynamics, supported by plots where appropriate. The number of marks awarded will be based on both the accuracy and clarity of your explanation.
