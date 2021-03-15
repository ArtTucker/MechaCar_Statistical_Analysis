# MechaCar Statistical Analysis
Statisitical analysis of automobile performance with R

## Overview
AutosRUs' new MechaCar is "suffering from production troubles" and the company is hoping that an analytical review may help provide some insight. The goal of this project is to:
* discover which variables predict the MPG for vehicle prototypes;
* collect summary stats on the PSI of suspension coils;
* determine if manufacturing lots are statistically different from the mean population;
* design a study to compare the MechaCar performance against vehicles from other manufacturers.

## Results

### Linear Regression to Predict MPG
![Multiple Linear Regression on MPG](images/mpg_line_regres_summry.png)

* The most significant variables in our dataset which show a non-random effect on the MPG of the MechaCar are the **Vehicle Length** and the **Ground Clearance**. As indicated by the yellow arrows in the image above, a linear regression model run on these variables against figures for MPG, resulted in p-values of 2.6x10<sup>-12</sup> and 5.21x10<sup>-8</sup>, respectively. The intercept was also statistically significant, indicating that there are likely other factors, not included in our dataset, that have a strong impact on the MPG.
* The slope of the linear model can not be considered to be zero, as the p-value of 5.35x10<sup>-11</sup>, indicated by the orange arrow above, is lower than even an extreme level of significance, and thus the null hypothesis must be rejected. This means that the relationship between our variables and the miles per gallon is subject to more than random chance.
* Although there are still unconsidered factors, this model does predict the mpg of the MechaCar prototype with some relative effectiveness. The r-squared value of 0.7149, highlighted in the purple box, indicates that the model is 71% accurate... though it could probably do better.

### Summary Statistics on Suspension Coils
![Suspension Coil Total Summary](images/sus_coil_tot_sum.png)
![Suspension Coil Lot Summary](images/sus_coil_lot_sum.png)
* While the overall variance, as shown in the Total Summary data above, is under 100 psi and meets specifications, there is a problem with one of the individual lots. As shown in the Lot Summary stats, the variance for Lot 3 is well over the acceptable threshold, at 170.28.

### T-Tests on Suspension Coils
Suspension Coils Cumulative T-test
![Suspension Coils Cumulative T-test](images/sus_coil_one_samp_ttest.png)
* A review of the results of the T-test for the suspension coils across all manufacturing lots shows that they are not statistically different from the population mean, and the p-value is not low enough (0.0603) for us to reject the null hypothesis.
![Suspension Coil Lot 1 T-test](images/sus_coil_lot1_samp_ttest.png)
* A review of the results of the T-test for the suspension coils for Lot 1 shows that they are not statistically different from the population mean, and the p-value is not low enough (1) for us to reject the null hypothesis.
![Suspension Coil Lot 2 T-test](images/sus_coil_lot2_samp_ttest.png)
* A review of the results of the T-test for the suspension coils for Lot 2 shows that they are not statistically different from the population mean, and the p-value is not low enough (0.6072) for us to reject the null hypothesis.
![Suspension Coil Lot 3 T-test](images/sus_coil_lot3_samp_ttest.png)
* A review of the results of the T-test for the suspension coils for Lot 3 shows that they are slightly statistically different from the population mean, and the p-value is just low enough (0.0417) for us to reject the null hypothesis. This lot may be need to be discarded, or at least more closely evaluated.

## Study Design: MechaCar vs Competition
There are many factors that consumers take into consideration when evaluating a car to purchase. However, in a world where ridesharing is becoming more ubiquitous and it's easy and cheap to get around in other people's vehicles, customers looking to purchase a car are looking for more than just a conveyance. They will be looking to buy a car that is an economical means to regularly transport themselves and their items on a reliable, regular basis.
### Metric to test
To narrow down our test, we should evaluate MechaCar's carrying capacity, in cubic inches, in comparison to various competitors' vehicles.
### Null and Alternate Hypothesis
H<sub>0</sub>: MechaCar prototypes' average carrying capacity is similar to competitor's vehicles in the same vehicle class
H<sub>a</sub>: MechaCar prototypes' average carrying capacity is statistically above or below that of competitor vehicles.
### Statistical Test Used
The best statistical test for this would be two-sample t-tests.
### What data is needed
We would need to gather cubic space data from the carrying compartments of all MechaCar prototypes, as well as from all major competitor vehicles.