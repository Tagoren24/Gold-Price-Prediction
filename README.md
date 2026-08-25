# Gold Price Prediction Using Statistical and Time-Series Models

## 📌 Project Overview

This project focuses on analyzing and predicting **gold prices** using statistical analysis, multiple linear regression, and time-series forecasting techniques.

The analysis uses historical gold price data along with economic indicators such as **Crude Oil, Interest Rate, USD/INR, Sensex, CPI, and USD Index**. The project includes exploratory data analysis, correlation analysis, regression modeling, multicollinearity analysis, and ARIMA-based time-series forecasting.

---

## 🎯 Objectives

* Analyze historical gold price trends.
* Identify relationships between gold prices and economic indicators.
* Perform exploratory data analysis and correlation analysis.
* Build a Multiple Linear Regression model for gold price prediction.
* Evaluate multicollinearity using **Variance Inflation Factor (VIF)**.
* Perform OLS regression analysis to understand the statistical significance of predictors.
* Build an **ARIMA** time-series model for gold price forecasting.
* Compare actual and predicted gold prices visually and using error metrics.

---

## 📊 Dataset

The dataset contains **239 observations** and the following variables:

| Variable        | Description                             |
| --------------- | --------------------------------------- |
| `Date`          | Date of observation                     |
| `Gold_Price`    | Target variable representing gold price |
| `Crude_Oil`     | Crude oil price                         |
| `Interest_Rate` | Interest rate                           |
| `USD_INR`       | USD to INR exchange rate                |
| `Sensex`        | BSE Sensex index                        |
| `CPI`           | Consumer Price Index                    |
| `USD_Index`     | US Dollar Index                         |

The dataset contains **239 rows and 8 columns**, with no missing values in the analyzed variables.

---

## 🔍 Exploratory Data Analysis

The project performs several exploratory analyses:

* Dataset summary statistics
* Data type and structure analysis
* Gold price trend visualization
* Autocorrelation analysis
* Partial autocorrelation analysis
* Additive seasonal decomposition
* Multiplicative seasonal decomposition
* Correlation analysis
* Correlation heatmap
* Comparison of Gold Price with:

  * Crude Oil
  * Sensex
  * Interest Rate
  * USD/INR
  * USD Index

---

## 📈 Statistical Analysis

### Multiple Linear Regression

The initial regression model uses the following independent variables:

```text
Crude_Oil
Interest_Rate
USD_INR
Sensex
CPI
USD_Index
```

The target variable is:

```text
Gold_Price
```

The regression model achieved:

```text
R²     = 0.962
Adj R² = 0.961
```

This indicates that the selected explanatory variables collectively explain a large proportion of the variation in the observed gold prices.

---

## 🔬 Multicollinearity Analysis

**Variance Inflation Factor (VIF)** was calculated to identify multicollinearity among the independent variables.

The initial model showed high VIF values, particularly for variables such as:

* USD/INR
* CPI
* Sensex
* Interest Rate
* USD Index

Based on the analysis, **USD Index** was removed from the regression model and the model was refitted.

The revised model retained:

```text
Crude_Oil
Interest_Rate
USD_INR
Sensex
CPI
```

The revised model also achieved:

```text
R²     = 0.962
Adj R² = 0.961
```

---

## 🤖 Gold Price Prediction

A `LinearRegression` model from Scikit-learn was used to predict gold prices.

### Model Evaluation

For the revised regression model:

| Metric |        Value |
| ------ | -----------: |
| MSE    | 5,210,256.46 |
| MAE    |     1,669.45 |
| MAPE   |       0.1184 |

The notebook also compares predicted gold prices with actual values through visualization.

> **Note:** The regression evaluation in the notebook is performed on the same dataset used to fit the model, rather than on a separate train/test split.

---

## 📉 Time-Series Analysis

The project also investigates the time-series behavior of gold prices.

### Techniques Used

* Autocorrelation Function (ACF)
* Partial Autocorrelation Function (PACF)
* Autocorrelation plot
* Additive seasonal decomposition
* Multiplicative seasonal decomposition
* ARIMA forecasting

The gold price series was converted into a date-indexed time series for forecasting.

---

## 🔮 ARIMA Forecasting

An **ARIMA(1,2,2)** model was fitted to the gold price time series.

The dataset was divided into:

```text
Training observations: 200
Testing observations:   39
```

The ARIMA model was trained on the first 200 observations and used to forecast the remaining 39 observations.

### ARIMA Model

```text
ARIMA(1, 2, 2)
```

The fitted model produced the following information:

```text
AIC  = 3143.646
BIC  = 3156.799
HQIC = 3148.970
```

The project visualizes:

* Training data
* Actual test data
* ARIMA predictions

---

## 🛠️ Technologies & Libraries

### Programming Language

* Python

### Data Analysis

* NumPy
* Pandas

### Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn

### Statistical Modeling

* Statsmodels

### Time-Series Analysis

* ARIMA
* Seasonal Decomposition
* ACF
* PACF

---


## 📌 Key Results

* Analyzed **239 historical observations**.
* Used **6 economic indicators** to explain gold price movements.
* Multiple Linear Regression achieved **R² = 0.962**.
* Revised regression model achieved **MAE ≈ 1,669.45**.
* Revised model achieved **MAPE ≈ 11.84%**.
* Identified significant multicollinearity using **VIF analysis**.
* Built an **ARIMA(1,2,2)** time-series model.
* Used **200 observations for training** and **39 observations for testing**.

---

## 📊 Key Insights

The analysis demonstrates that gold prices have strong statistical relationships with several macroeconomic variables. The regression analysis indicates that variables such as **Crude Oil, Interest Rate, USD/INR, Sensex, and CPI** contribute significantly to explaining variations in gold prices in the fitted model.

The time-series analysis additionally demonstrates the importance of considering the temporal structure and autocorrelation of gold prices when performing forecasting.

---
