# MPLN_R_Demo
# Overview
Applying my understanding of statistics and hypothesis testing to analyze a series of datasets from the automotive industry. My analysis will include visualizations, statistical tests, and interpretation of the results.

# Tools 
**RStudio** - integrated development environment (IDE) used to help design and test RScripts.

**R Programming** - go-to programming languages for statistical modelling and hypothesis testing. R developers have extended R's capabilities to generate machine learning algorithms and other advanced models to ensure that R can be used in every stage of data analytics.

# Packages/Libraries
**install.packages("tidyverse")**

The tidyverse package contains libraries such as dplyr, tidyr, and ggplot2. These packages work together to help simplify the process of creating transformed data columns, grouping data using factors, reshaping our two-dimensional data structures, and visualizing our results using plots.

**install.packages("jsonlite")**

to read in JSON data structures and convert them to an R data frame


# Relevant Documentation
https://ggplot2.tidyverse.org/

https://ggplot2.tidyverse.org/reference/index.html

https://ggplot2.tidyverse.org/reference/geom_boxplot.html#aesthetics

https://github.com/rstudio/cheatsheets/blob/main/data-visualization.pdf

https://dplyr.tidyverse.org/

https://tidyr.tidyverse.org/reference/pivot_longer.html

https://cran.r-project.org/doc/manuals/r-release/R-intro.pdf

# Linear Regression to Predict MPG
![deliverable_one](https://github.com/dgeroux/MPLN_R_Demo/blob/main/Images/deliverable_one.png)

**1. Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?**

The coefficients that provided a non-random amount of variance to the mpg values are vehicle length, ground clearnace and the intercept. In other words, vehicle length and ground clearance have a signigicant impact on mpg. When an intercept is statistically significant, it means that the intercept term explains a significant amount of variability in the dependent variable (mpg) when all independent vairables are equal to zero. Depending on our dataset, a significant intercept could mean that the significant features (such as vehicle length and ground clearance) may need scaling or transforming to help improve the predictive power of the model. Alternatively, it may mean that there are other variables that can help explain the variability of our dependent variable that have not been included in our model. Depending on the dataset and desired performance of the model, you may want to change your independent variables and/or transform them and then re-evaluate your coefficients and significance.

**2. Is the slope of the linear model considered to be zero? Why or why not?**

The slope of the linear model is NOT considered to be zero.

In hypothesis testing, the **null hypothesis** is generally the hypothesis that can be explained by random chance and the **alternate hypothesis** is generally the hypothesis that is influenced by non-random events. 
The **p-value**, or probability value, tells us the likelihood that we would see similar results if we tested our data again, if the null hypothesis is true. Therefore, we use the p-value to provide quantitative evidence as to which of our hypothesis are true. 
When we compare our p-value of 5.25e-11 (seen in the image above) against a significance level of 0.05, we see that our p-value is much smaller than our significance level. Therefore, we can state that there is sufficient statistical evidence that our null hypothesis is NOT true, meaning our model shows that our dependent variable is effected by the non-random independent variables.

**3. Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?**

This linear model predicts mpg of MechaCar prototypes fairly well. From our linear regression model (seen in the image above), the r-squared value is 0.71, which means that roughly 71% of the variability of our dependent variable (mpg) is explained using this linear model.
The lack of significant variables is evidence of overfitting. Overfitting means that the performance of a model performs well with the current dataset, but fails to generalize and predict future data correctly. 

# Summary Statistics on Suspension Coils
![deliverable_two.one](https://github.com/dgeroux/MPLN_R_Demo/blob/main/Images/deliverable_two.one)

**1. The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?**

In the image above, we can see that when we combine the suspension data from all the manufacturing lots our variance is 62.29 pounds per square inch, which does NOT exceed the design specifications stating that the variance must not exceed 100 pounds per square inch.

![deliverable_two.two](https://github.com/dgeroux/MPLN_R_Demo/blob/main/Images/deliverable_two.two.png)

In the image above, we can see the following:
Lot1 has a variance of 0.98 pounds per square inch, which does NOT exceed the design specifications.
Lot2 has a variance of 7.47 pounds per square inch, which does NOT exceed the design specifications.
Lot3 has a variance of 170.29 pounds per square inch, which DOES exceed the design specifications. 

# T-Tests on Suspension Coils

![d3](https://github.com/dgeroux/MPLN_R_Demo/blob/main/Images/deliverable_three.png)

In the image above, we compared the mean PSI across all manufacturing lots against the population mean of 1500 pounds per square inch to determine if the mean is statistically different from the population mean. With a p-value of 0.06 measured against a signifcance level of 0.05, we can state that the null hypothesis is true, meaning we cannot reject the fact that the mean PSI across all manufacturing lots may be equivalent to the true population mean.

![d3.1](https://github.com/dgeroux/MPLN_R_Demo/blob/main/Images/deliverable_three_lot1.png)

In the image above, we compared the mean PSI of Manufacturing Lot#1 against the population mean of 1500 pounds per square inch to determine if the mean is statistically different from the population mean. With a p-value of 1 measured against a signifcance level of 0.05, we can state that the null hypothesis is true, meaning we cannot reject the fact that the mean PSI of Manufactoring Lot#1 may be equivalent to the true population mean.

![d3.2](https://github.com/dgeroux/MPLN_R_Demo/blob/main/Images/deliverable_three_lot2.png)

In the image above, we compared the mean PSI of Manufacturing Lot#2 against the population mean of 1500 pounds per square inch to determine if the mean is statistically different from the population mean. With a p-value of 0.61 measured against a signifcance level of 0.05, we can state that the null hypothesis is true, meaning we cannot reject the fact that the mean PSI of Manufactoring Lot#2 may be equivalent to the true population mean.

![d3.3](https://github.com/dgeroux/MPLN_R_Demo/blob/main/Images/deliverable_three_lot3.png)

In the image above, we compared the mean PSI of Manufacturing Lot#3 against the population mean of 1500 pounds per square inch to determine if the mean is statistically different from the population mean. With a p-value of 0.04 measured against a signifcance level of 0.05, we can state that the null hypothesis is false, meaning we can reject the idea that the mean PSI of Manufactoring Lot#3 may be equivalent to the true population mean.

# Study Design: MechaCar vs Competition 
**1. What metric or metrics are you going to test?**

To compare the performance of the MechaCar against the performance of vehicles from other manufacturers I'd test the following metrics:

+ horsepower (independent variable)
+ transmission (independent variable)
+ fuel efficiency (dependent variable)
+ safety rating (independent variable)
+ 0-60mph time (independent variable)
+ price (independent variable)

**2. What is the null hypothesis or alternative hypothesis?**

Null Hypothesis: The change in the dependent variable (fuel efficiency) can be explained by random chance (p-value > 0.05).
Alternative Hypothesis: The change in the dependent variable is influenced by non-random events (p-value < 0.05).

**3. What statistical test would you use to test the hypothesis? And why?**

I would use the multiple linear regression statistical test because this test accepts 2 or more independent variables, 1 dependent variable, and continuous data. This test measures how much variance in the dependent variable is accounted for in a linear combination of independent variables, which is exactly what we want to know!

**4. What data is needed to run the statistical test?**

We already have the fuel efficieny (mpg) data, so we would need the remaining variables:

* horsepower
* transmission
* safety rating
* 0-60mph time
* price
