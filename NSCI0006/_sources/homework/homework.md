# Maths coursework 1 [20%]

Your submission of the two case studies is worth 20% of the mark for this module. You will submit one pdf file for each of the case studies.

There are ten marks available for the case study on *Freshwater sustainability* and eight marks available for the case study on *Viral trends*. A further two marks are available for:

* **[1] quality of presentation** - your work should be submitted in finished form, not in the manner of a rough draft. Your answers should be presented in order, complete with written explanations and details of calculations where appropriate.

* **[1] standard of python code** - your code should be presented in an organised and systematic way, with each line of code presented in order. It should be clear from the script what each step is used for. It may help if you add comments to your code using hashtags.

## Freshwater sustainability

This part of the assignment can be completed either by hand or in word-processed format, or using a combination of both. However, your submission must be uploaded in the form of a single pdf document.

You can use the [Office Lens](https://wiki.ucl.ac.uk/display/ELearningStudentSupport/Office+Lens) app to scan in pages of work on your phone/tablet and then convert it to a .pdf.

### Exercise 2.15 [5pt]

**Calculations :**

Present the results of your calculations as a table of values. Give your answers to an appropriate level of precision and ensure that the units are correctly stated.

You do not have to show the calculation steps for every country, but you must provide an example calculation for one of the countries.

Consider how you want to do the calculations. Excel? Python? Your calculator? Use a tool that you think is most likely to give you an error-free answer.

Two points will be awarded for a fully correct table of values and a clear, correct example calculation.

```{toggle}
* A table of values that is provided without an example calculation will be awarded a maximum of one point

* An answer that contains numerical errors will be awarded a maximum of one point.

* An answer that does not handle units or precision correctly will be awarded a maximum of one point
```

**Written commentary:**

The written commentary is worth three points. This means that you should aim to provide three short paragraphs that each contain a critical comment or assertion.

The word "critical" is key. Descriptive statements such as "this one is bigger than that one" won't earn any credit. Try to comment on explanations, implications, complexities and issues. This may require you to do a small amount of independent reading, but take care to write in your own words and give credit to any information sources you use.

### Exercise 2.16 [2pt]

For this question you are required to calculate the WSI value for each of the three countries listed. Your answer for each country should be a number.

You must present your calculations because method marks will be awarded for this question. A drawing might help the clarity of your explanation.

Your answer is worth two points. There is one point for a correct method and one point for correctly calculated values.

### Exercise 2.17 [3pt]

One point will be awarded for correct calculation of the per-capita daily world BFW using the data given in the tables.

One point will be awarded for the UK per-capita BWF using the value of 8880Mm3 given in the research paper.

The question also asks for a comment, which is worth one point. Skim through the research paper to inform your answer!

## Viral trends

This part of the assignment should be completed in Python, with accompanying written comments.

In CoCalc you can download your work as a pdf by selecting File > Save and Download as ... PDF.

### Exercise 3.20 [3pt]

In this question points will be awarded as follows:

* [1] Import the data, isolate a wave "by eye" and apply the given transforms to the $(x,y)$ data.

* [1] Fit a logistic function to the transformed data to obtain the coefficients

* [1] Use the calculated coefficients to plot the fitted function with the datapoints on the scale of the original data.

You should be able to obtain a plot similar to the one shown in the lecture slides:

```{image} imgs/hwk1.png
:alt: covidius-maximus
:width: 50%
:align: center
```

### Exercise 3.21 [3pt]

In this question points will be awarded as follows:

* [1] import the data, accumulate and normalise it

* [1] fit the Fréchet function to obtain the coefficients

* [1] present suitable plot(s) to illustrate the quality of fit


### Exercise 3.22 [2pt]

The method here is identical to the previous exercise. Marks will be awarded for:

* [1] Identification of a suitable dataset and choice of function to fit

* [1] A thoughtful attempt to explain the goodness of fit with reference to the data and the model
