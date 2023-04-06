# Complete Data Analysis of Energy Consumption in France

### About the Dataset
This code analyzes a dataset named "eco2mix-regional-cons-def.csv", which contains information about the energy consumption and production of different regions in France from 2013 to 2022. The code performs several data cleaning steps, feature engineering, data analysis, and machine learning modeling to analyze the dataset.
The dataset can be downloaded from here:

https://opendata.reseaux-energies.fr/explore/dataset/eco2mix-regional-cons-def/information/?disjunctive.libelle_region&disjunctive.nature&sort=-date_heure

### Requirements
Python 3.x

pandas

numpy

matplotlib

seaborn

statsmodels

sklearn

scipy.stats

datetime

warnings

### Data Cleaning
Several data cleaning steps have been performed to prepare the dataset for analysis. The cleaning steps include removing unnecessary and irrelevant columns, handling missing values, and translating the column names from French to English. The data before 2019 was removed from the dataset, due to the inconsistency in previous years.

### Feature Engineering
After cleaning the data, new columns have been created to add more information to the dataset. The new columns include day and month columns, total production, and total renewable production.

### Data Analysis
Exploratory data analysis has been performed to understand the dataset better. The analysis includes descriptive statistics, ANOVA tests, and correlation heatmap. Additionally, Boxplots have been used to determine the outliers.

### Data Visualization
The data visualization includes various graphs and charts that illustrate the energy production and consumption in France from 2019 to 2022. It provides insights into the types of energy resources used, their regional contribution, and the share of renewable and non-renewable energy in the total production.

## Machine Learning
2 cases have been modelled:
- Predicting the consumption of energy 
- Predicting the blackout in France

### Predicting the Consumption of Energy
The regression model aims to predict the amount of energy consumption based on the average energy production daily throughout France.
Various regression analyses have been performed on the dataset, including:
- Gradient boosting
- Random forest
- Decision tree
- Linear regression
- Lasso regression 
 
Evaluation of model performance has been done using mean squared error, mean absolute error, and root mean squared error. 

### Predicting the Blackout in France
The classification model aims to predict whether there will be a blackout or not based on the difference between the total production and consumption of electricity. The code for the classification model is provided in the classification_model.py file.

The code first creates a new column named "Difference" which calculates the difference between the total production and consumption. Then, the data is grouped by day, month, and year, and the mean of the "Difference" column is calculated for each group. A new column named "Blackout" is created where 1 indicates a blackout and 0 indicates no blackout.

The following classification models are then used:

- Logistic Regression

- Bagging

- Boosting

- Decision Tree

- Random Forest

- Support Vector Machine (SVM)

- The hyperparameters of the SVM model are optimized using GridSearchCV.

The results of each model are printed and compared using the classification report and confusion matrix.

### Time Series
To overcome overfitting issues regarding the regression and classification models, time series analysis has been conducted. 
First, the original time series of energy consumption versus time has been plotted and seasonal decomposition of the time series has been performed. Both additive and multiplicative models were plotted.

Then, SARIMA model has been applied to it for forecasting. The order and seasonal_order parameters of the SARIMA model are set to (1,1,1) and (0,1,0,24), respectively. A forecast for the next 24 months using the get_forecast() method has been performed. A plot is generated showing the original time series and the forecasted values with a red vertical line indicating the end of the original data.

## Conclusion
The code provides a comprehensive analysis of energy consumption over time using various techniques, including data cleaning, data visualization, regression and classification models, time series analysis, and forecasting. The SARIMA model provides a useful forecast of energy consumption, which can be useful for energy companies and policymakers in planning and making decisions related to energy production and distribution. However, further analysis may be required to validate the accuracy of the model and to consider other factors that may affect energy consumption.

