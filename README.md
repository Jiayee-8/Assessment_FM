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

## Exploratory Data Analysis
I plotted the overall daily sales to understand the sales pattern.
It shows the sales are increasing or decreasing, and shows the seasonal pattern over time.

## Feature Engineering
Prophet needs two main columns which are `ds` and `y`.
So I renamed `date` to `ds` and `sales` to `y`.

I also seperated the data by each store-item combination. It is because different stores and different items have different sales patterns.
Since there are 10 stores and 50 items, so total has 500 store-item combination.

I didn't included holiday features because the dataset description states that there are no holidays effects. It will increase noise when I add holiday features.

## Modelling Approach
Prophet is used to do sales forecast. I selected Prophet because it can capture trend and seasonality in time series data. 

Since I have 500 time-series, ARIMA need different parameters for every time series. And LSTM need more time to conduct.

The prophet model used:

- Weekly seasonality
- Yearly seasonality
- BUT no daily seasonality

to learn the pattern.

I had been add seasonality which is monthly but the error become higher, so I remove it.

## Validation 
I used a time-based validation split.

THe last 3 months of `train.csv` were used as validation set. The earlier date was used for training.

It is used to compared the actual sales with predicted sales.

## Evaluation
- MAE
- RMSE
- MAPE

## Final Prediction
After validation, I retrained the Prophet model using the full `train.csv` dataset to let model learn more patterns.

The trained model is used to predict sales for `test.csv`.

The final prediction was saved as `submission.csv`.

## How to run
1. Open the `Time_Series_Sales_Forecasting.ipynb` in Google Colab.
2. Change the runtime type to GPU.
3. Upload the following files:
   - `train.csv`
   - `test.csv`
4. RUn all cells from top to buttom.
5. Upload again the `sample_submission.csv` file.
6. The final prediction file `submission.csv` will be generated.
