# Coronavirus modelling

Download data from [coronavirus.data.gov.uk](https://coronavirus.data.gov.uk/details/cases?areaType=nation&areaName=England)

The below plots are based on data to 22 Aug 2022. First we simply show the plots of daily reported cases. The background shading indicates periods of lockdown (red) and significant restriction (yellow).

```{figure} imgs/covid_cases.png
---
name: will replace
---
Will be replaced with a Python plot
```

By smoothing the data we can estimate daily growth rates in reporting over the period (as percentages). Despite being calculated by  crude methodology, the figures shown here roughly match official statistics.

```{figure} imgs/covid_gr.png
---
name: will replace
---
Will be replaced with a Python plot. Add axis labels!
```

Estimating the R-number is a much more complicated business. Government values are based on aggregating calculations produced by mathematical models from several UK institutions. However, we can obtain a very rough-and-ready estimate of what the R value was a week ago by using the  formula $R_{est} = (1+6G)$, where $G$ is the current growth rate as a decimal. Compare this plot with Fig 18 from a [Royal Society paper](https://royalsociety.org/-/media/policy/projects/set-c/set-covid-19-R-estimates.pdf)

```{figure} imgs/covid_rEst.png
---
name: will replace
---
Will be replaced with a Python plot
```

Now let's try to fit the data for the number of cases to a mathematical model. We will do this separately for each wave of the infection. The shading in the below plot is used to identify the infection waves that we will look at.

```{figure} imgs/covid_waves.png
---
name: will replace
---
Will be replaced with a Python plot
```

We fit the data to the derivative of logistic function

```{math}
\frac{L}{1+e^{-\lambda(t-\kappa)}}
```

Exception has been made for the first wave, which has been fitted to the derivative of the Frechet function, as it gives a slightly better fit than the logistic function where there is a very flat initial stage.


```{figure} imgs/covid_wave_fits.png
---
name: will replace
---
Will be replaced with a Python plot
```

Task is to identify one of the infection waves and fit a sigmoid to the data. The fitting will work better if you rescale the data so that it lies between 0 and 1 on each axis. You can either fit the derivative or you can fit to the accumulated data. The two approaches will give slightly different results, but either is acceptable.


Additional comment:

The unfitted period between the identified third and fourth waves is a strange one. The sharp drop in cases coincides with the announcement of 19 July when legal limits on social contact were removed in England, including re-opening of nightclubs. For a timeline of restrictions, see [this website](https://www.instituteforgovernment.org.uk/sites/default/files/chart-images/timeline-coronavirus-lockdown-december-2021_0.png).
