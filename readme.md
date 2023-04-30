# Regression-Project-on-Coorporation-Favorita
Time Series Project on Corporation Favorita aimed to inform on the stocks of products it should have at a particular point in time by analysing the demand trend of all of its products by consumers by using machine learning model forcast
 

## Summary
| Code      | Name        | Published Article |  
|-----------|-------------|:-------------:|------:|
| LP2 | REGRESSION ANALYSIS |  [Best article of the world](/) |

## Project Description
 ### Project Introduction
 ---
 Corporation Favorita is a large Ecuadorian-based grocery retailer organization. A time series of machine learning models was to be built to forecast the demand of products in various locations. The organisation deal in the retail of different family of products from food supplies to automotives and real estates.

All analysis were conducted following the CRISP-DM framework.

### Insights from data analysis
---
The dataset provided were train, test, stores, oil, transaction, sample_submission and holiday_events. However, the main dataset used in the analysis were the train and test datasets whiles the other supplementary datasets were useful in answering the hypothesis and the questions of interest.

### Hypothesis and Questions
---
Three (3) hypothesis were stated for the regression analysis.

**One**
---
**H0** - The type of day does not play a significant role in determining the demand for oil

**H1** - the type of day play a significant roles in determining the demand for oil

**Two**
---
**H0** - The location does not have an impact for the for the demand for oil

**H1** - The location have an impact for the demand for oil

**Three**
---
**H0** - There is no significant correlation between oil price and increase sales

**H1** - There is significant correlation between oil price and increase sales

**Questions**
---
1. Is the train dataset complete (has all the required dates)?
2. Which dates have the lowest and highest sales for each year?
3. Are certain groups of stores selling more products? (Cluster, city, state, type)
4. Are sales affected by promotions, oil prices and holidays?
5. What analysis can we get from the date and its extractable features?
6. What is the difference between RMSLE, RMSE, MSE (or why is the MAE greater than all of them?)
7. What is the relationship between oil prices and sales?
8. What is the relationship between product and sales?
9. What is the trend of sales overtime ?
10. What is the relationship between oil prices and promotion ?

###  Overview
-- 
Introduction
The predicting grocery sales were to forecast product sales for Corporacion Favorita, an Ecuadorean Grocery shop with hundreds of stores and over thousands of unique products.

As part of the project, the following processes were followed
- Initial data import, cleanup, and overview
- Exploratory Data Analysis - This provided more insight to uncover the need for more data cleaning
- Model Development (I performed data processing, built models, chose algorithms, chose best-performing model, etc)
- Model evaluation and comparison

## Setup
### Library for EDA
- import pandas as pd
- import numpy as np 
- import seaborn as sns
- %matplotlib inline
- import matplotlib.pyplot as plt
- import matplotlib.dates as mdates
- from sklearn.impute import SimpleImputer
- from pandas_profiling import ProfileReport
- import warnings
warnings.filterwarnings('ignore')
- Data Import and Business Understanding

## App Execution
To perform an excellent analysis, a thorough business understanding was prerequisite. As a result, I loaded the datasets (train, test, transaction, oil, stores, holidays_events, and sample_submission). The train and test datasets were used in the analysis whiles the other datasets aid the EDA in answering most of the project questions where required.

#### Train Data CSV
--
The train data csv contained the following, time series of features from 2013/01/01 to 2017/08/15. Also, the following columns were found, store_nbr, family, target sales, and on_promotion respectively.
- The store_nbr indicated the store at which the products were sold.
- The On promotion column was the total number of items promoted at a store at a given date period.
- The target sales gave the total sales for a product class at a particular store at a given date.
- The family column identified the type of product sold.

#### Overview of the transaction, oil, stores, holidays_events, and sample_submission datasets

**Transaction csv**

There were three(3) columns in the transition csv. These are date, store number, and transactions

**Oil csv**

The oil csv were contained in it the date and dcoilwtico columns

**Stores csv**

The stores csv also had store number, city, state, type, and cluster as its columns

**Holiday_events csv**

This dataset had the following columns, data, type of event, locale, locale name, description and transferred.

**Sample_Submission csv**

The sample_submission had only two columns, thus, the Id and sales columns.

#### Checking columns and rows of each dataset
During the EDA it was found that each of the dataset had the following shape
- sample_submission csv had 28512 rows and 2 columns
- stores csv had 54 rows and 5 columns
- transaction csv had 83488 and 3 columns
oil csv had 1218 rows and 2 columns
- train csv had 30000888 rows and 6 columns
 - Lastly, test csv had 28512 rows and 5 columns

 #### Data Visualisations
 **Barplot**

A barplot was created with a seaborn library to 'transaction' against 'city' column to understand which city had more purchasing power. The barplot revealed that Quito had the highest purchasing power followed by the consumers of Cayambe. The other five followed cities that recorded high transactions are Ambato, Loja, Daule, Riobamba, and Ibbara all in Ecuador.

**Histogram**

Whiles exploring the transaction column, a histogram was created which revealed that the total transaction reach peak of $ 140000 against 8000 transactions. This clearly indicates increase in sales of corporation favorita products.

#### Questions Answered by the Time Series Regression Analysis
As part of the regression analysis, question were raised to achieve the objective of the analysis. Below are the queston 

-  **Is the train dataset complete (has all the required dates)?**

Findings of the analysis revealed that the datasets were complete and had all required dates

-  **Which dates have the lowest and highest sales for each year?**

The analysis revealed that 2013 had the lowest dale of the year whiles 2016 had the highest peak of sales amongs all the dates.

- **What analysis can we get from the date and its extractable features?**

For the date to aid in getting extratable features from the analysis, it was revealed that 

1. *With sales by year, **2016** recieved the highest sales*
2. *In comparing monthly sales, July received the highest sales* **followed by January, February and December**
3. *Also, in dividing the year by quarter sales, the second quarter of the year received the highest sales respectively*.

- **What is the difference between RMSLE, RMSE, MSE (or why is the MAE greater than all of them?)**

- RMSLE, RMSE, MSE, and MAE measure the difference between predicted and actual values.
- MAE was used to measure the average absolute difference between predicted and actual values, making it easier to interpret than other metrics.
- MSE was employed for an average squared difference between predicted and actual values, sensitive to outliers and larger errors.
- RMSE was calculated by taking the square root of the mean squared difference between predicted and actual values.
- RMSLE was calculated by taking the square root of the mean squared logarithmic difference between predicted and actual values.

MAE calculates the average absolute difference between predicted and actual values, which can be greater than all other metrics. When errors are large or the target variable has a wide range of values, the MAE may be greater than other metrics.

-  **What is the relationship between oil prices and sales?**

A scatter plot was created to visualize the relationship between oil prices against the sales columns to better the total sales made despite the amount of the price sold

- **What is the relationship between product and sales?**

The grocery product family was highly demanded following by bevearages and produce products.

- **vWhat is the trend of sales overtime**

In finding sales of time, it was identified that 2015, 2016, and 2017 recorded the highest sales among all other years in corporation favorita sales.

#### Machine Learning and Modeling

At this part of the project, 4 models were trained and validated. These are linear regression model, decision tree, XGBoost, and random forest regression model. Of these three, the decision tree had a good RMSLE and so was chosen as the model to predict sales for the training data. The RMSLE score was used for model selection because it produces minimal error.

**Evaluation Results for XGBoost:**
- MSE: 0.4
- RMSE: 0.63
- RMSLE: 0.2

 *In comparing evaluation results of my model selection on 'Linear Regression', 'Decision Tree', 'XGBoost', and 'Random Forest'. The below results were obtained.*

Comparison Table of Evaluation Results:

                **Model   MSE  RMSE  RMSLE**
     - 0  Linear Regression  0.72  0.85   0.26
-      1      Decision Tree  0.59  0.77   0.24
       - 2      XGBoost  0.40  0.63   0.20
-      3      Random Forest  0.44  0.66   0.21

#### Summary 
Lastly, in building machine learning model to forecast future sales of corporation favorita products, the encoded data was visualized with a subplot revealed that many quantities of dcoilwtico were sold between 2016 and 2017 across all cities in Ecuador. Regression is a critical statistical strategy used in time-series analysis and modeling. It aids in forecasting future trends, identifying patterns, and assessing the impact of past events on current data. The most common regression techniques used in time-series analysis are linear regression, ARIMA, and exponential smoothing. Understanding the advantages of using regression in time-series analysis allows data scientists to make more informed decisions and improve their data analysis techniques.

## Author
Marie Grace KAGAJU

