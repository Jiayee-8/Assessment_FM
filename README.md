# Time Series Sales Forecasting 

## Objective:
Build a predictive model to forecast sales for the next 3 months. 

## Dataset:
https://www.kaggle.com/competitions/demand-forecasting-kernels-only/data
Given 5 years of store-item sales data, and asked to predict 3 months of sales for 50 different items at 10 different stores.

## Tools and Libraries Used
- Python
- Pandas
- NumPy
- Matplotlib
- Prophet
- Scikit-learn

## Data Cleaning
Before train the model, I check the data first although already mention is clean data in Kaggle.
- Checked missing values
- Checked duplicated values
- Converted the `date` column into datetime format
  
(Prophet needs time-based data for forecasting.)

