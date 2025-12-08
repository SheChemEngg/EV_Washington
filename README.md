# ELECTRIC VEHICLES (EV) IN WASHINGTON STATE 

OBJECTIVE

The goal of this study is to create models to understand the practices and incentives of the population of the state of Washington regarding the use of EVs and to implement the main factors involved in predicting its future trend.
Understanding how various demographic, economic, and geographic factors influence EV ownership is key to predicting future adoption patterns and informing policy-making.

This project aims to analyze and model EV adoption trends across Washington’s counties using publicly available datasets.  Specifically, we seek to uncover how population size, median household income, and regional characteristics correlate with EV registration rates.

The goal of this Exploratory Data Analysis (EDA) is to understand the structure and quality of the data, identify key relationships, and highlight patterns that will later guide the development of predictive models.

--

DATA Cleaning 

 

Data (features) from all the resources are collected and merged into one master file.  Redundant features or information irrelevant to the study are eliminated. 

The following changes were made: 

EV location is split into two features:  ‘Latitude’, ‘Longitude’.  This useful in plotting density of EVs by location within Washington. 

2025 population data was extracted from the population resource file (Table 1) and merged with the original EV data file. 

Median Income per Family in each county is obtained from the Data Source, and added as a new feature in the master file. 

Clean Alternative Fuel Vehicle (CAFV) is the term designated by EPA for an EV that meets the requirement Electric Range of and EV Battery to qualify for state tax relief.  The clean energy law requirements were adopted by Washington in 2022. 

 

https://afdc.energy.gov/laws/6216#:~:text=Washington%20adopted%20the%20California%20vehicle%20emissions%20standards,see%20the%20Washington%20Clean%20Car%20Standards%20website. 

 

Under the current requirement, battery range for BEV should be ≥ 200 mi, and for PHEV should be ≥ 30 mi. 

Crucial information regarding base MSRP, and Electric Range was missing from 253868 instances, equivalent to data for 587 unique values of ‘Year_Make_Model’.  The data was manually collected from websites such as: 

api.marketcheck.com 

Edmunds 

audiclubna.org 

InsideEVs.com 

kbb.com 

TopElectricSUV 

.. 

..etc. 

Tax Credit could be a major factor in more consumers adopting EVs through lowered prices ($5000 to $7500).  Tax Credit, is available only for EVs manufactured in the past 5-7 years.  It is a function of sales of a particular make.  If the sales number exceeds a certain number set by federal government, the tax credit policy no longer applies.  The policy is honored only in some states, including Washington.  The sparse data could induce confidence in the results of a model.  Despite the sparsity,  the feature cannot be ignored.  Hence its inclusion in the list of features. 

--
RESULTS
--

Test Set Results of Random Forest Classifier on EV Data 

 Table 2 

                   Test Set 

                Precision Recall  F1-Score Support
Accuracy        0.88     64260 
Macro Avg       0.82     0.84    0.82      64260 

Weighted Avg    0.90     0.88    0.88      64260 


The average Accuracy from Cross Validation of the RF Classifier is : 0.8738;  Standard Deviation between the Accuracy values is 0.0027 

The Accuracy from Testing  of the RF Classifier is : 0.8845 

Test Set Results of Linear Regression on EV Data 

Table

Metric    R2 Score   RMSE     MAE     MSE   

Mean      0.8473     47.5851  36.2458 36.1088 

STD Dev   0.0032     0.4550   0.2572   29.0638 

INTERPRETATION OF LINEAR REGRESSION RESULTS 

The average R² Score from Cross Validation of the Linear Regression model is 0.8473, and the Standard Deviation between the R² values is 0.0032. 
The R² Score from Testing is 0.8467. 


