# Freshwater solutions

## {numref}`ex-fw1`

```{table}

| Country<br></br><th>TRWR<br>litres/person/day</th> <th>Dependency<br>%</th> <th>TFWW<br>litres/person/day</th><th>TFWW/TRWR<br>%</th></tr><tr style="background-color:#FFC0CB"><td align="left">Brazil</td><td align="right">113097.00</td><td align="right">34.53</td><td align="right">845.06</td><td align="right">0.75</td></tr><tr><td align="left">China</td><td align="right">5332.02</td><td align="right">0.96</td><td align="right">1111.00</td><td align="right">20.84</td></tr><tr style="background-color:#FFC0CB"><td align="left">Egypt</td><td align="right">1600.57</td><td align="right">98.26</td><td align="right">2157.30</td><td align="right">134.78</td></tr><tr><td align="left">India</td><td align="right">3870.46</td><td align="right">24.33</td><td align="right">1311.49</td><td align="right">33.88</td></tr><tr style="background-color:#FFC0CB"><td align="left">Pakistan</td><td align="right">3186.02</td><td align="right">77.71</td><td align="right">2488.15</td><td align="right">78.10</td></tr><tr><td align="left">United Kingdom</td><td align="right">5998.36</td><td align="right">1.36</td><td align="right">345.58</td><td align="right">5.73</td></tr><tr style="background-color:#FFC0CB"><td align="left">United States of America</td><td align="right">25705.60</td><td align="right">8.18</td><td align="right">3722.25</td><td align="right">14.48</td></tr><tr style="font-style:italic"><td align="left">World</td><td align="right">19663.90</td><td align="right">N/A</td><td align="right">1421.09</td><td align="right">7.23</td></tr>
| --- |
||
```

*Some observations:*

When measured in this way, the USA is the largest user of freshwater, withdrawing 3700 litres of water per resident every day. It may seem striking that the USA uses ten times as much water per resident as the UK. Can you think why this might be? The United States Geological Survey's (USGS) [Water Science School](https://www.usgs.gov/special-topics/water-science-school/science/freshwater-withdrawals-united-states#overview) may provide some further insight.

Egypt has a very high water dependency ratio, depending on external resources for more than 98% of its total renewable water resource. It is also highly water stressed, with water use exceeding the total renewable supply by 50 billion litres each day (500 litres per capita).

Brazil's apparent water wealth masks huge national disparities. A combination of geographic and enviromental factors, enormous levels of [agricultural exports](https://www.ers.usda.gov/topics/international-markets-u-s-trade/countries-regions/brazil) and decades of water mismanagement have resulted in a [water crisis](https://www.nature.com/articles/d41586-021-03625-w). Europe is imports vast amounts of "virtual water commodities" from Brazil, which is captured in the water footprint statstics explored in the next section.

And what about the UK? Although our WSI is relatively low, this statistic masks significant variation in regional water stress. The South East including London is particularly vulnerable to water stress. Some parts of England are already "[over-abstracted](http://www.environmentdata.org/archive/vocabpref:21152)" and if current trends continue it is likely that the UK will struggle to meet its water needs [by 2050](https://www.nationalgeographic.co.uk/environment-and-conservation/uks-looming-water-crisis).

For a brief overview of the UK situation, see the Environment Agency's report on [Meeting our Future Water Needs](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/873100/National_Framework_for_water_resources_summary.pdf) (notably pages 3,4,8).



## {numref}`ex-fw2`

The score for the UK is easiest to calculate since this datapoint lies on the line passing through the origin.

`````{grid} 2
````{grid-item}
```{image} imgs/tri1.png
:alt: rise-over-run
:align: center
```
````
````{grid-item}
\begin{equation*}\frac{r}{14.35}=\frac{2}{20}\quad \Rightarrow \quad r=1.44.\end{equation*}
`````


The score for India lies on the line connecting the point $(40,3)$ to the point $(80,4)$.

`````{grid} 2
````{grid-item}
```{image} imgs/tri2.png
:alt: rise-over-run
:align: center
````
````{grid-item}
\begin{equation*}\frac{r-3}{26.49}=\frac{1}{40}\quad \Rightarrow \quad r=3.66.\end{equation*}
````
`````

The score for Pakistan lies on the line connecting the point $(80,4)$ to the point $(160,5)$.

`````{grid} 2
````{grid-item}
```{image} imgs/tri3.png
:alt: rise-over-run
:align: center
````
````{grid-item}
\begin{equation*}\frac{r-4}{38.24}=\frac{1}{80}\quad \Rightarrow \quad r=4.48.\end{equation*}
`````

**Side note:** The coding scheme of the WRI does not actually use linear "pieces" to connect the data points as we did here. Instead, the data points are fitted using a curve:
\begin{equation*}
r=1+\log_{2}(\text{WSI}/10),
\end{equation*}
A plot of this curve is shown in the image below, together with the "piecewise" fit that we have employed. The log function and data fitting techniques are discussed in chapters 3 and 4.

```{image} imgs/ws-fit.png
:alt: fitted data
:align: center
```

## {numref}`ex-fw3`

According to the given information, the world TFWW is around 3956 Gm3.

Of this figure,
* The portion consumed by agriculture is around 35% of 69%
* The portion consumed by industry is around 5% of 19%
* The portion consumed by households is around 10% of 12%

Therefore in Gm3 the total consumed portion of TFWW (our global BWF) is around
\begin{equation*}
3965(0.69\times 0.35 + 0.19\times 0.05 + 0.12\times 0.10) \simeq 1000
\end{equation*}

This can be converted to a daily per-capita figure by dividing by the global population and the number of days in a year:
\begin{equation*}
\frac{1000\times 10^9 \text{m}^3}{365\times 7.3\times 10^9}\simeq 0.375\text{m}^3=375\text{l}.
\end{equation*}

Note: Taking this to represent 11% of the total WF suggest that the global average daily per-capita WF is aorund 4000 litres.

To convert the UK annual BWF to a daily per-capita figure we divide by the UK population and the number of days in a year:
\begin{equation*}
\frac{8880\times 10^6 \text{m}^3}{365\times 65.12\times 10^6}\simeq 0.374\text{m}^3=374\text{l}.
\end{equation*}

This figure seems to be extremely close to the global average. However, the UK is a net importer of "virtual water commodities" from other countries, and according to the results given in the paper, more than half of the UK’s blue water footprint was in areas of high water stress such as India and Pakistan.
