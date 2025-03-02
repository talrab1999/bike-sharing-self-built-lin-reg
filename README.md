# Bike Share Prediction with Custom Linear Regression

## Overview
This project implements a linear regression model from scratch to predict future bike share counts using historical data from London. The main goal was to deepen my understanding of linear regression and the mechanics of gradient descent by building the model without relying on pre-built libraries.

## Dataset
The dataset used is london_merged.csv, which contains the following features:

- timestamp: Timestamp field (dropped for modeling)
- t1: Real temperature in °C
- t2: "Feels like" temperature in °C
- hum: Humidity (in %)
- wind_speed: Wind speed in km/h
- weather_code: Categorical weather code
- is_holiday: Boolean (1 for holiday, 0 for non-holiday)
- is_weekend: Boolean (1 if weekend, 0 otherwise)
- season: Meteorological seasons (0: spring, 1: summer, 2: fall, 3: winter)
- cnt: Count of new bike shares (target variable; moved to the rightmost column)

# Data Preprocessing
- Timestamp Removal: The timestamp column was dropped since it is not directly used for prediction.
- Train-Test Split: Data was split into training and test sets using an 80/20 split.
- Feature Scaling: Numerical features (t1, t2, hum, wind_speed) were standardized (mean = 0, standard deviation = 1) to improve the stability and convergence of gradient descent.
- Categorical Features: Categorical features such as weather_code, is_holiday, is_weekend, and season were kept as-is. Future work might explore one-hot encoding if necessary.

# Evaluation
After training, predictions on the test set are computed using the same prediction function. 
The performance of the model is evaluated using MSE (and by extension, RMSE). 
For example, an RMSE of approximately 1100 indicates that, on average, the predictions are off by about 1100 bike shares. 
Although this error might be significant given the scale of the counts, the focus of this project was to understand and implement the learning algorithm rather than achieve a perfect model.

# Conclusion
The project successfully demonstrates the implementation of linear regression from scratch. 
While the model's performance (Test MSE and RMSE) leaves room for improvement, the primary objective was to understand the fundamentals of linear regression and gradient descent. 
Future improvements might include advanced feature engineering, experimenting with one-hot encoding for categorical features, and exploring more complex models.
