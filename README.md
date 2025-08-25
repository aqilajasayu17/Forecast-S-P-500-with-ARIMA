# Forecast S&P 500 with ARIMA
### **Time Series Prediction for S&P 500**
Dataset:https://finance.yahoo.com/quote/%5EGSPC/history/

The dataset in this research is derived from S&P 500 data, with the observation period spanning from August 23, 2024 to August 23, 2025. There are six variables in total, and the variable utilized in this research is the “Close” variable. The purpose of using this variable is to serve as a reference in making investment decisions, such as determining the appropriate time to buy, hold, or sell.

### **Plot Actual Data**

<img width="1032" height="575" alt="Image" src="https://github.com/user-attachments/assets/957ee466-b33c-4d9b-8bde-f097a52b5128" />

The plot illustrates that the data frequently fluctuates, where prices initially increased from late 2024 to early 2025, reaching approximately 6200–6300, before experiencing a significant decline between March and April 2025. Subsequently, the prices returned to normal, as indicated by an upward trend, surpassing 6400 in August 2025. The conclusion drawn from the actual data plot is that prices experienced a sharp drop in early 2025 but quickly recovered, regaining higher values by the end of 2025. Therefore, this period provides an overview of a market that underwent volatility but demonstrated a strong recovery.

### **Check Stationary with ADF and ACF PAC Plot**
Since the actual data exhibits an inconsistent trend pattern from the beginning to the end of the period, the model is likely to capture this trend, which may lead to biased predictions. Therefore, prior to conducting the analysis, the Augmented Dickey-Fuller (ADF) test as well as the ACF and PACF plots will be performed to examine the stationarity of the data.

<img width="748" height="572" alt="image" src="https://github.com/user-attachments/assets/c86ac4fb-31b1-408c-a9ff-812fe3fa7f55" />

<img width="754" height="571" alt="image" src="https://github.com/user-attachments/assets/9cde0d2e-559b-41cc-9b5a-3d8652a4c477" />

The ACF plot shows a gradually decreasing lag, while the PACF plot indicates significant values at lag 1 and lag 2. Furthermore, the ADF test produces a p-value of 0.6417290206734335, which implies that the data is not stationary, as the value exceeds the alpha level of 0.05.

### **Transform to stationary: Differencing**
Differencing is one of the methods used to transform data into a stationary form, thereby producing the following plot.

<img width="1000" height="513" alt="image" src="https://github.com/user-attachments/assets/60e53161-e1a2-4316-a13c-06d9002428b6" />

From the differenced plot, it can be observed that the values are closer to around 0 and no longer exhibit a significant trend, indicating that the data has become more stationary compared to before differencing. The ADF test result also shows a p-value of 8.479058744395605e-16, which is smaller than the alpha level of 0.05, confirming that the data is stationary.

<img width="662" height="509" alt="image" src="https://github.com/user-attachments/assets/bbe1d480-c989-4e4e-8241-d73b9a11daf2" />

<img width="668" height="525" alt="image" src="https://github.com/user-attachments/assets/f80d8efc-07be-488e-9c12-5be5ada7411c" />

Based on the ACF and PACF plots, the ARMA(p,q) model can be determined. At lag 1, the values exceed the significance boundary, leading to the selection of the ARMA(1,1) model.

### **ARIMA Model Manual (1,1,1)**
<img width="272" height="407" alt="image" src="https://github.com/user-attachments/assets/bdf3c552-a69a-44fd-afd3-3dba0bb00d91" />

<img width="1178" height="568" alt="image" src="https://github.com/user-attachments/assets/5f0acbf6-9df7-4450-ace8-b5c015c404ad" />

The ARIMA prediction results indicate an increase in prices after August 2025, where the forecast shows a gradual rise that continues to increase in the near future.

### **ARIMA Model Auto (0,1,4)**
By applying the auto ARIMA method, the ARIMA(0,1,4) model was obtained, which subsequently produced the following prediction values.

<img width="281" height="422" alt="image" src="https://github.com/user-attachments/assets/532b67cf-a1c2-4bd4-a019-1a36f9d59b28" />

<img width="1330" height="646" alt="image" src="https://github.com/user-attachments/assets/c9300fdd-c5fd-4d45-9a55-305a8c67f026" />

From the comparison plot between the manual ARIMA and the auto ARIMA models, it can be concluded that the manual ARIMA (1,2,1) provides a better fit for forecasting several future periods compared to the auto ARIMA model.

### **Comparison of Manual MAPE Values ​​(1,2,1) with Auto MAPE (0,1,4)**
<img width="418" height="46" alt="image" src="https://github.com/user-attachments/assets/7cac2bc2-f51e-4e0a-97ef-89844c76eef3" />

<img width="395" height="47" alt="image" src="https://github.com/user-attachments/assets/b7f5f7bc-7487-45fc-be89-1a475b2a9c18" />

The comparison between the manual ARIMA model and the auto ARIMA model can be evaluated using the MAPE and RMSE values, where smaller values indicate better prediction accuracy. The manual ARIMA model demonstrates superior performance compared to the auto ARIMA model in terms of both MAPE and RMSE. Therefore, the ARIMA (1,2,1) model is considered more appropriate for forecasting S&P 500 stock data for several future periods.










