# Apple (AAPL) Stock Price Prediction

## Task Objective

The aim of this project is to predict the next day’s closing stock price for Apple Inc. (AAPL) using historical stock data. This is accomplished using regression models trained on features such as opening price, highest and lowest price of the day, and trading volume.


## Dataset Used

The dataset is obtained using the `yfinance` API and consists of daily stock prices from:

- **Start Date**: January 1, 2020  
- **End Date**: May 31, 2025  

Each row in the dataset includes the following features:

| Column     | Description                              |
|------------|------------------------------------------|
| Open       | Opening price of the stock               |
| High       | Highest price of the stock for the day   |
| Low        | Lowest price of the stock for the day    |
| Close      | Closing price of the stock (used as target) |
| Volume     | Total volume of stock traded             |
| Target     | Next day's closing price (prediction goal) |


## Models Applied

Two machine learning regression models were applied using `scikit-learn`:

- **Linear Regression**
- **Random Forest Regressor** (with 100 estimators)

### Preprocessing Steps:
- Created the `Target` variable by shifting the Close column by -1
- Dropped any resulting missing values
- Features used: Open, High, Low, and Volume
- Train-test split (80% train, 20% test) without shuffling to preserve time sequence

---

## Key Results and Findings

| Model               | Mean Squared Error (MSE) |
|---------------------|--------------------------|
| Linear Regression   | ~ 20.098259329302387   |
| Random Forest       | ~ 968.3444568537238   |


### Observations:
- **Linear Regression** performed reasonably and showed general trend alignment with actual values.
- **Random Forest** had higher error in this case, potentially due to overfitting.
- Time-based splitting (without shuffling) preserved the temporal integrity of financial data.

## Visualization

A line plot was generated comparing:

- Actual closing prices (test set)
- Predictions from Linear Regression and Random Forest models

This allowed us to visually inspect how well each model followed the true price trend over time.
