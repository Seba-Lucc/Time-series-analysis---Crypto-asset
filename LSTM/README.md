# LSTM Architecture and Financial Time Series Forecasting

This project explores the application of the **Long Short-Term Memory (LSTM)** neural network architecture for **financial time series forecasting**. Specifically, it focuses on predicting the price of Bitcoin (BTC:USD) using a dataset downloaded from **yfinance**.

---

## LSTM Architecture Overview

The **LSTM** was introduced by Hochreiter and Schmidhuber in 1997 as an enhancement of Recurrent Neural Networks (RNNs) to address the **Vanishing Gradient problem**. Its design enables the capture of long-term dependencies in sequential data through a combination of memory states and gated mechanisms.

### Key Components of the LSTM

1. **Cell State (\(C_t\))**:
   - Serves as the network's long-term memory, capable of retaining, updating, or discarding information across time steps.

2. **Hidden State (\(h_t\))**:
   - Acts as short-term memory, influencing the network’s output at each step.

3. **Gated Mechanism**:
   - Regulates the flow of information:
     - **Input Gate (\(i_t\))**: Decides the amount of new information to add to the cell state.
     - **Forget Gate (\(f_t\))**: Determines what information from the previous state should be discarded.
     - **Output Gate (\(o_t\))**: Controls which portion of the cell state contributes to the output and updates the hidden state.

### Core Functionality of LSTM
For each time step \(t\), the LSTM performs the following operations:
- Updates the **cell state** by combining previous memory (\(C_{t-1}\)), input data (\(x_t\)), and hidden state (\(h_{t-1}\)).
- Adjusts **hidden state** based on the gated mechanisms to produce the current output.

---

## Project Description

The LSTM model was adapted to perform **price forecasting** for **financial time series** data, specifically Bitcoin (BTC:USD). The dataset was obtained using **yfinance**, and the model was trained and tested with varying time steps and feature sets.

### Dataset and Preprocessing
- **Source**: BTC:USD data downloaded from yfinance.
- **Time Steps**:
  - **Monthly**: The primary focus of the project, aiming to predict the precise price at time \(t\).
  - **Daily and Minute**: Additional tests were conducted using higher-frequency data to compare performance.
- **Features**:
  - Model 1: Trained using only the **Close** series, similar to ARIMA-based analysis.
  - Model 2: Trained using **Open**, **Low**, **High**, **Close**, and **Volume**.

### Key Observations
- Models trained with **daily data** performed better than those trained with **monthly data**.
  - Likely due to the model's difficulty in adapting to the higher variance in the monthly series.
- Incorporating additional features (**Open**, **Low**, **High**, and **Volume**) slightly improved the model's predictive accuracy.

### Challenges and Considerations
- **Data Integrity**: Ensure proper handling of time intervals when downloading data from yfinance.
- **Reproducibility**:
  - Verify that the dataset has been successfully downloaded.
  - Align training data intervals with the desired time step for consistent results.

---

## Results and Insights

- The **daily model** achieved better accuracy and robustness due to its ability to capture smaller-scale patterns and less pronounced variance differences.
- The use of LSTM, compared to simpler statistical models like ARIMA, demonstrated superior capability in handling complex temporal relationships across multiple features.

---

## Reproducibility

To replicate the experiment:
1. **Download the BTC:USD dataset**:
   - Use the `yfinance` library, ensuring the correct time intervals (e.g., daily, monthly) are specified.
2. **Feature Selection**:
   - Decide whether to use only the **Close** series or include additional features.
3. **Model Training**:
   - Adjust hyperparameters (e.g., learning rate, batch size) based on the time step used.
4. **Evaluation**:
   - Test models on both short-term and long-term data intervals for comparative analysis.

---

## Conclusion

This project highlights the flexibility and effectiveness of LSTMs in forecasting financial time series data. By leveraging the gated mechanism, LSTMs excel at capturing both short-term and long-term dependencies, making them a robust choice for tasks requiring sequential data analysis.

---

For any questions or further details, feel free to reach out!
