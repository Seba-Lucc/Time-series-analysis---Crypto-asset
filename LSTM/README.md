# **Bitcoin Price Prediction with LSTM**

This repository contains a Jupyter Notebook that implements an LSTM (Long Short-Term Memory) model for predicting the closing price of Bitcoin using historical data. The notebook provides a complete pipeline for data processing, model training, evaluation, and visualization of the results.

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

The project demonstrates how to use an LSTM neural network to predict the price of Bitcoin based on historical data. The goal is to capture the temporal patterns in the data to make accurate short-term predictions. The notebook includes all necessary steps for:
- Preprocessing raw Bitcoin price data.
- Training a predictive model using LSTM.
- Evaluating the model's performance.
- Visualizing the predictions alongside actual values.

---

## **Data Source**

The historical data for Bitcoin is retrieved using the `yfinance` library. The dataset includes:
- **Date**: the trading date.
- **Close**: the closing price of Bitcoin for each day.
- **High**: the highest price of Bitcoin for each day.
- **Low**: the lowest price of Bitcoin for each day.
- **Open**: the opening price of Bitcoin for each day.
- **Volume**: the volume of Bitcoin for each day.

### **Preprocessing Steps:**
1. Normalization: features are scaled to the range [0, 1] for better model performance.
2. Sequence Preparation: data is transformed into sequences of fixed length (`seq_length`) to serve as input to the LSTM model.
3. Train-Test Split: the data is split into training and testing subsets.

---

## **Model Description**

The predictive model is based on an LSTM architecture:
- **LSTM Layer**: Captures temporal dependencies in the data.
- **Dense Layer**: Outputs a single value (predicted closing price).

The model is trained using:
- **Loss Function**: Mean Squared Error (MSE).
- **Optimizer**: Adam optimizer.

The trained model is saved as `model.h5` for reuse.

---

## **Pipeline Workflow**

1. **Data Loading and Preprocessing**:
   - The dataset is downloaded using `yfinance`.
   - Features and Target are normalized and structured into sequences for training.

2. **Model Training**:
   - The LSTM model is built, compiled, and trained on the prepared dataset.
   - Training progress is monitored using the loss function.

3. **Prediction**:
   - The model predicts the next day's-minutes' closing price based on recent data.
   - Predicted values are denormalized to the original price scale.

4. **Visualization**:
   - A graph is plotted to compare the predicted value with actual closing prices.

5. **Evaluation**:
   - The model's performance is measured using metrics like MAE, MSE, RMSE, and MAPE.

---

## **Evaluation Metrics**

The following metrics are calculated to assess the model's accuracy:

1. **Mean Absolute Error (MAE)**: Measures the average magnitude of errors in the predictions.
2. **Mean Squared Error (MSE)**: Penalizes larger errors more than smaller ones.
3. **Root Mean Squared Error (RMSE)**: Provides a measure of error in the same units as the target variable.
4. **Mean Absolute Percentage Error (MAPE)**: Expresses prediction errors as a percentage of actual values.

---

## **Usage**

### **Requirements**
Ensure the following Python libraries are installed:
- `yfinance`
- `numpy`
- `pandas`
- `matplotlib`
- `tensorflow`
- `scikit-learn`

### **Running the Notebook**
1. Clone the repository:
   ```bash
   git clone https://github.com/Seba-Lucc/Time-series-analysis---Crypto-asset.git
   cd LSTM

2. Clone the repository:
   ```bash
   pip install -r requirements.txt

3. Open the notebook:
   ```bash
   jupyter notebook LSTM.ipynb

4. Run all cells in sequence to reproduce the analysis.

---

## **Future Improvements**

To enhance the model’s accuracy and usability, the following improvements can be made:
1.	Feature Engineering:
	•	Include additional predictors like trading volume, moving averages, and other technical indicators.

2.	Model Optimization:
	•	Experiment with hyperparameter tuning, deeper LSTM layers, and dropout layers.

3.	Extended Data:
	•	Use a larger dataset with more historical data points for training.

4.	Model Ensemble:
	•	Combine LSTM with other models (e.g., GRU or Transformer models) for improved predictions.

---

## **Contributions**
Contributions to this project are welcome! Feel free to open an issue or submit a pull request to suggest improvements or fix bugs.

---

## **License**
This project is licensed under the Apache License. See the LICENSE file for details
This project is licensed under the Apache License. See the LICENSE file for details
