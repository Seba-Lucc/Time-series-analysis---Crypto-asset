# Data Mining and Text Analytics project
This project was conducted by Sebastiano Lucchetti e Martina Butti

# Time-series-analysis---Crypto-asset
This project uses Python and Jupyter Notebook to compare statistical models, such as the ARIMA model, with deep learning algorithms, such as the LSTM architecture, for forecasting Bitcoin prices. By comparing these methods, we aim to understand their predictive capabilities and identify which technique provides more accurate and reliable forecasts. 

## Project Overview
Bitcoin’s price is influenced by numerous factors and can exhibit highly non-linear and non-stationary behavior. Time series models are commonly used to forecast future values based on historical data. In this repository, we implement two primary approaches:

# ARIMA 
The ARIMA model is a statistical technique widely used for stationary time series. It combines Autoregressive (AR) and Moving Average (MA) components, and introduces an additional parameter for differencing to achieve stationarity. In general, ARIMA models capture autocorrelations in data, making them suitable as baseline or benchmark forecasting methods.

# LSTM 
The LSTM model is a deep learning technique evolved from Recurrent Neural Networks (RNNs) and is capable of learning complex, long-term dependencies in time series data. LSTMs are particularly well-suited to non-stationary, volatile datasets like cryptocurrency prices due to their ability to handle temporal dependencies more flexibly.



# Techniques and Steps
## Data Collection & Preprocessing:
1. Historical Bitcoin price data is fetched using yfinance and then cleaned and prepared for modeling.
2. The dataset is split into training and testing sets.
3. For ARIMA, differencing and stationarity checks are applied as needed.
4. For LSTM, data is normalized and structured into a supervised learning format (windowed sequences).

## Modeling & Training:
### ARIMA:
1. The model’s parameters (p, d, q) are selected using techniques like the AIC and PACF/ACF plots.
2. The ARIMA model is fitted to the training data and used to generate forecasts.
### LSTM:
1. An LSTM architecture is defined with layers appropriate for handling time series sequences.
2. The LSTM model is trained on the normalized windowed data, learning from historical patterns to predict future prices.
	
 ## Model Evaluation & Comparison:
1. The predictions from both models are compared against the test set using metrics such as RMSE or MAE.
2. Visualization tools are used to plot predicted vs. actual prices, highlighting strengths and weaknesses of each approach.

## Interpretation:
1. We discuss the results, assessing which model performs better under various conditions.
2. The project also offers insights into the complexities of forecasting high-volatility assets like Bitcoin.


## Library
### ARIMA
Analysis: numpy, pandas, yfinance
Rappresentation: matplotlib 
Model implementation: statsmodels, sklearn
	
 	•	pip install numpy, pandas, yfinance, matplotlib, statsmodels, sklearn

### LSTM
Analysis: numpy, pandas, yfinance 
Rappresentation: matplotlib 
Model implementation: sklearn, tensorflow, keras
	
 	•	pip install numpy, pandas, yfinance, matplotlib, sklearn, tensorflow, keras


