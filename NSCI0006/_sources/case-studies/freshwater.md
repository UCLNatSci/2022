# Freshwater sustainability

This case study on freshwater sustainability is provided for you to practice solving mathematical problems in context and using your results to make informed conclusions or judgements.

The case study also includes a question on fitting straight lines to data points, which is an important background technique for the work that we will do on calculus.

```{admonition} [Mami Mitzuri](https://twitter.com/HeadUNDRR), UN Special Representative for Disaster Risk Reduction
:class: quote

Drought could be next pandemic and there is no vaccine to cure it. Drought has directly affected 1.5 billion people this century. This number will grow dramatically unless we manage this risk, understand its root causes and take preventive action [[Twitter](https://twitter.com/headundrr/status/1405653654636535820)]

```

## Water Stress

To use our freshwater resource sustainably, the rate at which we make withdrawals must be below the rate at which stocks are replenished (e.g. by rainfall). If we consume more than the amount restored by nature, the resulting decrease in water levels can cause damage to the environment.

When assessing water resources within countries we may distinguish between *internal* renewable water resource (**IRWR**) and *external* renewable water resource (**ERWR**). The latter consists of deposits into the country, which may come from natural flows such as rivers or from delivery by pipes or freight. Together, the IRWR and ERWR make up the *total* renewable water resource (**TRWR**). The other key measure that we are interested in is total freshwater withdrawals (**TFWW**).

Data for several countries are shown in {numref}`renewable-freshwater`. The rightmost column in the table is the **Water Stress Index (WSI)**, which is United Nations Sustainable Development Goal (SDG) [indicator 6.4.2](https://www.fao.org/sustainable-development-goals/indicators/642/en/). It is calculated by the equation

\begin{equation}
\text{WSI} = \frac{\text{TFWW}}{\text{TRWR}-\text{EFR}}.
\end{equation}

The environmental flow requirement (**EFR**) accounts for the downstream environmental impact of withdrawals, for example on aquatic life and biodiversity.


```{table} Renewable freshwater resources
:name: renewable-freshwater

| Country<br></br><th>IRWR<br>(Gm3/yr)</th> <th>ERWR<br>(Gm3/yr)</th> <th>TFWW<br>(Gm3/yr)</th> <th>Population<br>(millions)</th><th>WSI<br>%</th></tr><tr style="background-color:#FFC0CB"><td align="left">Brazil</td><td align="right">5661.00</td><td align="right">2986.00</td><td align="right">64.61</td><td align="right">209.46932</td><td align="right">1.42</td></tr><tr><td align="left">China</td><td align="right">2812.90</td><td align="right">27.32</td><td align="right">591.80</td><td align="right">1459.37761</td><td align="right">43.22</td></tr><tr style="background-color:#FFC0CB"><td align="left">Egypt</td><td align="right">1.00</td><td align="right">56.50</td><td align="right">77.50</td><td align="right">98.42360</td><td align="right">141.17</td></tr><tr><td align="left">India</td><td align="right">1446.00</td><td align="right">464.90</td><td align="right">647.50</td><td align="right">1352.64228</td><td align="right">66.49</td></tr><tr style="background-color:#FFC0CB"><td align="left">Pakistan</td><td align="right">55.00</td><td align="right">191.80</td><td align="right">192.74</td><td align="right">212.22829</td><td align="right">118.24</td></tr><tr><td align="left">United Kingdom</td><td align="right">145.00</td><td align="right">2.00</td><td align="right">8.42</td><td align="right">67.14168</td><td align="right">14.35</td></tr><tr style="background-color:#FFC0CB"><td align="left">United States of America</td><td align="right">2818.00</td><td align="right">251.00</td><td align="right">444.40</td><td align="right">327.09627</td><td align="right">28.16</td></tr><tr style="font-style:italic"><td align="left">World</td><td align="right">42808.60</td><td align="right">11928.50</td><td align="right">3955.78</td><td align="right">7626.37978</td><td align="right"></td></tr>
| --- |
||
```

If you want to find data for another country you can look this up using the [AQUASTAT](https://www.fao.org/aquastat/statistics/query/index.html?lang=en) database, provided by the Food and Agriculture Organization of the United Nations.

```{dropdown} Click for more information

The following AQUASTAT database variables are shown in {numref}`renewable-freshwater`. The database provides an extremely rich source of information about freshwater availability and use, and of the impacts of water management on human health. You may wish to explore some of the other variables by yourself.

<table><th>Category</th> <th> Subcategory</th><th>Variable</th></tr><tr><td align="left">Geography and population</td><td >Population</td><td>Total population</td></tr><tr><td>Water resources</td><td>Internal renewable water resources</td><td>Total internal renewable water resources (IRWR)</td></tr><tr><td align="center"></td><td>External renewable water resources</td><td> Total external renewable water resources (ERWR)</td></tr><tr><td>Water use</td><td>Water withdrawal by source</td><td>Total freshwater withdrawal</td></tr><tr><td align="center"></td><td>Pressure on water resources</td><td>SDG 6.4.2 Water Stress</td></tr></table>

```


```{exercise}
For each country in {numref}`renewable-freshwater`, calculate the values listed below:

* the [per-capita](https://www.dictionary.com/browse/per-capita) values for TRWR and TFWW
* the proportion of TRWR used, ignoring EFR
* the [dependency ratio](https://www.unescwa.org/sd-glossary/dependency-ratio-water) (external fraction of TRWR)

Based on your results, write down some of your initial thoughts about world water usage and distribution. We will explore the relationships between water distribution and water usage further in the next sections.

```

```{toggle}

**Hint:**

Per capita rates are calculated by dividing the relevant statistic by the country's population. Dependency ratios are calculated by taking ERWR/TRWR.

The proportion used is given by TFWW/TRWR, which was used as [Millennum Development Goal (MDG) indicator 7.5](https://millenniumindicators.un.org/unsd/mdg/Host.aspx?Content=Indicators/OfficialList.htm). This indicator is not as sophisticated as the WSI because it does not take account of the downstream impact of water withdrawals and therefore underestimates the level of water stress. The MDGs were succeeded by the SDGs in 2016.
```

``````{exercise}
In some literature, the WSI is rescaled and categorised. An example of how this may be done is given in the table below, which follows the [coding scheme of the WRI](https://www.wri.org/data/aqueduct-country-and-river-basin-rankings-map). Taking the relationship between WSI and Score to be linear within each category, as shown in the image, calculate the scores for each of UK, India and Pakistan.

`````{grid} 2
````{grid-item}
| Stress category | Score | WSI    |
| --------------- | ----- | ------ |
| Low             | 0-1   | <10%   |
| Low to medium   | 1-2   | 10-20% |
| Medium to high  | 2-3   | 20-40% |
| High            | 3-4   | 40-80% |
| Extremely high  | 4-5   | >80%   |
````
````{grid-item}
```{image} ../case-studies/imgs/water-stress-scores.png
:alt: water-stress-scores
:align: center
```
````
`````
``````


```{toggle}
**Hint:**

The key property of a straight line is that the "rise over run" is constant. In coordinates $(x,y)$ we may write the following relationship, where $\Delta y$ denotes the change in $y$ and $\Delta x$ denotes the change in $x$ :
\begin{equation*}
\frac{\Delta y}{\Delta x} = \text{constant}.
\end{equation*}
________
```

## Water scarcity innovations:

*Singapore* and *Dubai* are two of the world's most water stressed places, due to a lack of renewable water resources. Singapore gets a significant portion of its TFWW from its neighbour Malaysia, but has also developed an advanced system to turn sewage into clean, drinkable water that can meet 40% of demand [[VOA news](https://www.voanews.com/a/east-asia-pacific_singapore-turns-sewage-clean-drinkable-water-meeting-40-demand/6209374.html)]. In Dubai, around 90% of the city's needs are supplied by [desalinated](https://en.wikipedia.org/wiki/Desalination) seawater.

As global freshwater pressures intensify, such measures may become more common. The UK already has a desalination plant operated by Thames Water in [Beckton](https://www.water-technology.net/projects/water-desalination/), which can provide up to 150 million litres of drinking water each day. The Chief Executive of the UK Environment Agency has said that the UK will need more desalination plants [[speech, Mar/2019](https://www.gov.uk/government/speeches/escaping-the-jaws-of-death-ensuring-enough-water-in-2050)] and that people need to be 'less squeamish' about drinking water taken from sewage treatment plants [[BBC article, Aug/2022](https://www.bbc.co.uk/news/uk-62708413)].

Such solutions must be looked at carefully. For instance, the process of desalination requires large amounts of energy and therefore may substitute one scarce resource (freshwater) for another (energy). Desalination also produces a toxic brine by-product, which can damage coastal and marine ecosystems if it is pumped back into the ocean.

## Water footprint

If we only look at water withdrawals this masks some important truths about the characteristics of water consumption. We may marvel that the UK's water withdrawal per-capita is much lower than that of other countries. The source of these disparities lies in the "hidden water" that is used during the production of many of the items that we consume.

Water consumption by the UK is much higher than the TFWW, due to imports of food and manufactured products. In addition, when examining water usage it is helpful to consider not only water that is drawn from lakes, rivers and aquifiers (so-called "blue water"), but also water pollution and the use of water stored in soil. Finally, it is important to note that some of the water that we withdraw typically returns to rivers and aquifiers and can be re-used.

These considerations have led to the definition of a "water footprint" (WF), which is a measure of humanity’s appropriation of fresh water in volumes of water consumed and/or polluted [[waterfootprint.org](https://waterfootprint.org/en/water-footprint/what-is-water-footprint/)]

The WF is separated into green, blue and grey parts, which are defined in the table below. The percentage figures given in the table are estimates for the global average of all water-consuming activities.


```{table} [The water footprint of humanity](https://www.pnas.org/doi/10.1073/pnas.1109936109)
:name: water-footprint

| Type  <th>Description</th> <th>Fraction of WF</th></tr><tr><td align="left" width="33%">Green </td> <td align="left" width="33%">Rainwater (e.g. stored in soil)</td> <td align="left" width="33%">74%</td></tr><tr><td align="left">Blue</td> <td align="left">Surface and groundwater</td> <td align="left">11%</td></tr><tr><td align="left">Grey</td> <td align="left">Water pollution impact</td> <td align="left">15%</td></tr>
| --- |
||
```

The relationships between water withdrawals and the blue water footprint are estimated in the table below.

```{table} [Estimating our blue water footprint](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0032688)
:name: blue-footprint

| Type of supply <th>Fraction of TFWW</th> <th>Consumed portion</th></tr><tr><td align="left" width="33%">Agricultural</td> <td align="center" width="33%">69%</td> <td align="right" width="33%">~35% </td></tr><tr><td align="left">Industrial</td> <td align="center">19%</td> <td align="right">~5%</td></tr><tr><td align="left">Municipal</td> <td align="center">12%</td> <td align="right">~10%</td></tr>
| --- |
||
```

```{exercise}
Use the value for the world TFWW given in {numref}`renewable-freshwater`, together with the information in {numref}`blue-footprint` to estimate the world Blue Water Footprint (BFW). Convert your result to a per-capita daily figure in litres.


According to a [paper](https://www.tandfonline.com/doi/full/10.1080/13504851.2021.2009111?scroll=top&needAccess=true) published in 2021 , the UK daily BWF is approximately 8880 Mm3. Convert this to a per-capita value and comment whether the result is different to the global average.
```

```{toggle}

**Hint:**

According to the given information, the world TFWW is around 3956 Gm3.

Of this figure,
* The portion consumed by agriculture is around 35% of 69%
* The portion consumed by industry is around 5% of 19%
* The portion consumed by households is around 10% of 12%

Convert to a daily per-capita figure by dividing by the global population and the number of days in a year.
________
```

## Your personal water footprint
According to the [water footprint network](https://waterfootprint.org/en/water-footprint/national-water-footprint/), the average person in the UK has a "water footprint" of around 3400 litres per day. This figure is consistent with the values presented in the last section. You can use the [virtual explorer](https://www.waterfootprintassessmenttool.org/national-explorer/) on their website to see how it compares to the per-capita water footprint of other countries.

Having noted that domestic water use is a relatively small fraction of the overall freshwater budget, most people are still suprised to find out how much water they consume through day-to-day activties such as washing and flushing the toilet. Check your water statement if you get one! At home, the average UK person uses around [150 litres](https://www.statista.com/statistics/1211708/liters-per-day-per-person-water-usage-united-kingdom-uk/) of water per day.

A major additional contribution to your water footprint comes from the foods that you consume. Examples of indicative water footprints for some common food items can be found on the waterfootprint [product gallery](https://waterfootprint.org/en/resources/interactive-tools/product-gallery/).

However, every item that you consume has a water footprint. For example, in 2016 [WRAP](https://wrap.org.uk/sites/default/files/2020-10/WRAP-valuing-our-clothes-the-cost-of-uk-fashion_WRAP.pdf) estimated that the water footprint of clothes used in the UK was 8 trillion litres, a figure that is quoted in the House of Commons Environmental Audit Committee report on "[Fixing Fashion](https://publications.parliament.uk/pa/cm201719/cmselect/cmenvaud/1952/1952.pdf)". About one fifth of the global water footprint due to cotton consumption is related to pollution. Indicative values for the water footprints of a pair of jeans and t-shirt are given in the table below. It has also been [estimated](https://waterfootprint.org/media/downloads/Report46-WaterFootprintPaper_1.pdf) that the combined blue and green footprint of a single sheet of A4 paper is around 2-13 litres.

```{table} Global average virtual water content (litres)
:name: water-products

| Product | Blue WF | Green WF | Grey WF |
| ------- | ------- | -------- | ------- |
| Jeans   | 4900    | 4450     | 1500    |
| T-shirt | 4400    | 4000     | 1350    |

```

```{admonition} Further reading about water
:class: readmore

* [UNESCO 2021 report: valuing water](https://unesdoc.unesco.org/ark:/48223/pf0000375724) | See foreword by Audrey Azoulay, Director-General of UNESCO.
* [UN Progress report 2021](https://www.unwater.org/publications/progress-level-water-stress-2021-update) | Read the executive summary and download the [infographic](https://www.unwater.org/app/uploads/2022/03/SDG-642-Infographic_Introducing-water-stress_Dec-2021.pdf).
* [UK Water Footprint, WWF](https://wwfeu.awsassets.panda.org/downloads/wwf_uk_footprint.pdf) | includes case studies
```
