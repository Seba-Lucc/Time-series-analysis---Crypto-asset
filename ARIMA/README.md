# **Bitcoin Price Forecasting with ARIMA**

This repository contains a Jupyter Notebook that implements the ARIMA model for forecasting Bitcoin prices. The notebook demonstrates the complete pipeline, from data preprocessing to model evaluation and visualization.

---

## **Table of Contents**
1. [Overview](#overview)
2. [Data Source](#data-source)
3. [Model Description](#model-description)
4. [Pipeline Workflow](#pipeline-workflow)
5. [Evaluation Metrics](#evaluation-metrics)
6. [Usage](#usage)
7. [Future Improvements](#future-improvements)
8. [Contributions](#contributions)
9. [License](#license)

---

## **Overview**

The project showcases the application of the ARIMA model for time series forecasting. Bitcoin's historical price data is analyzed to predict future trends. The notebook includes the following:
- Data preprocessing and stationarity checks.
- Selection of ARIMA parameters based on ACF and PACF plots.
- Training and evaluation of the ARIMA model.
- Visualization of the forecast results against actual values.

---

## **Data Source**

The Bitcoin historical price data is retrieved using the `yfinance` library. The dataset includes:
- **Date**: The trading date.
- **Close**: The closing price of Bitcoin for each day.

### **Preprocessing Steps:**
1. **Stationarity Check**:
   - The Augmented Dickey-Fuller (ADF) test is performed to determine if the data is stationary.
   - Non-stationary data is differenced to make it stationary.
2. **Feature Selection**:
   - The `Close` column is selected as the target for forecasting.

---

## **Model Description**

The ARIMA model combines three components:
- **Auto-Regressive (AR)**: Captures dependencies between current and past values.
- **Integrated (I)**: Differencing applied to make the data stationary.
- **Moving Average (MA)**: Models dependencies between current residuals and past residuals.

The optimal parameters `(p, d, q)` for the ARIMA model are selected using ACF and PACF plots and verified through experimentation.

---

## **Pipeline Workflow**

1. **Data Loading and Preprocessing**:
   - Historical Bitcoin data is downloaded using `yfinance`.
   - The target column (`Close`) is selected and made stationary using differencing if needed.

2. **ACF and PACF Analysis**:
   - MINIC (Minimum Information Criterion): this method utilises the Akaike Information Criterion (AIC) to select the optimal values of `p` and `q`. The AIC evaluates model quality by balancing goodness-of-fit with model complexity. A range of value combinations is tested, and the one with the lowest AIC value is selected as the optimal choice.

   - SCAN: this technique focuses on analysing the residuals of the ARIMA model for each combination of `p` and `q`. The quality of the residuals is assessed through the autocorrelation function (ACF) and the partial autocorrelation function (PACF). The model with the highest-quality residuals—those closest to the absence of correlation—is selected.

   - ESACF (Extended Sample Autocorrelation Function): this approach provides extended ACF and PACF plots to enable manual selection of the parameters `p` and `q`. Users can visually inspect the patterns in the plots to identify appropriate values.

3. **Model Training**:
   - The ARIMA model is trained on the processed time series data.

4. **Prediction**:
   - The model is used to forecast future prices, which are compared against actual values for evaluation.

5. **Visualization**:
   - Forecast results are plotted alongside actual data to visually assess model performance.

---

## **Evaluation Metrics**

To evaluate the ARIMA model's performance, the following metrics are calculated:
1. **Mean Absolute Error (MAE)**: Average magnitude of errors in the predictions.
2. **Root Mean Squared Error (RMSE)**: Provides a measure of error in the same units as the target variable.

---

## **Usage**

### **Requirements**
Ensure the following Python libraries are installed:
- `yfinance`
- `numpy`
- `pandas`
- `matplotlib`
- `statsmodels`
- `scikit-learn`

### **Running the Notebook**
1. Clone the repository:
   ```bash
   git clone https://github.com/Seba-Lucc/Time-series-analysis---Crypto-asset.git

2. Install dependencies:
   ```bash
   pip install -r requirements.txt

3. Open the notebook:
   ```bash
   jupyter notebook ARIMA.ipynb

4. Run all cells in sequence to reproduce the analysis.

---

## **Future Improvements**

To enhance the accuracy and usability of the model:
1.	Feature Engineering:
	•	Include additional predictors like trading volume, economic indicators, and sentiment analysis.
	
 2.	Advanced Models:
	•	Explore other models such as SARIMA, SARIMAX, or hybrid models combining ARIMA with machine learning approaches.
	
 3.	Hyperparameter Optimization:
	•	Use automated tools (e.g., Grid Search) to fine-tune ARIMA parameters.

---

## **Contributions**
Contributions are welcome! If you encounter issues or have suggestions for improvement, feel free to submit a pull request or open an issue.

---

## **License**
This project is licensed under the Apache License. See the LICENSE file for details.
