# Petrol Price Forecasting using Machine Learning (ARIMA)

## 📌 Project Overview
This project focuses on forecasting petrol prices using historical time-series data.  
The objective is to predict future petrol prices based on past trends using a classical machine learning time-series model.

The dataset is divided into:
- **Training data (`train.csv`)**: Contains historical petrol prices
- **Test data (`test.csv`)**: Contains only future dates (no actual prices)

The model is trained **only on training data** and used to forecast prices for the test period.

---

## 🛢️ Domain
Oil & Energy

---

## 🧠 Technology Used
- Python
- Machine Learning (Time Series Forecasting)
- ARIMA (AutoRegressive Integrated Moving Average)

---

## 📂 Dataset Description

### `train.csv`
| Column | Description |
|------|------------|
| Date | Weekly date |
| Petrol (USD) | Petrol price in USD |

### `test.csv`
| Column | Description |
|------|------------|
| Date | Future dates only |

> Note: Test data does **not** contain actual petrol prices. It is used only for forecasting.

---

## 🔄 Project Workflow

### 1️⃣ Data Loading
- Loaded `train.csv` and `test.csv` using pandas
- Converted `Date` column to datetime format

### 2️⃣ Data Preprocessing
- Sorted data by date
- Handled missing values using **linear interpolation**
- Set `Date` as index for time-series operations

### 3️⃣ Exploratory Data Analysis
- Visualized historical petrol price trends using line plots
- Observed long-term trends and fluctuations

### 4️⃣ Stationarity Check
- Applied **Augmented Dickey-Fuller (ADF) Test**
- Identified non-stationarity
- Used differencing (d = 1) to make the series stationary

### 5️⃣ Model Training
- Trained an **ARIMA(5,1,0)** model using only the training dataset
- Model learned temporal dependencies from historical prices

### 6️⃣ Forecasting
- Generated forecasts for the test period
- Filled predicted values into the test dataset

### 7️⃣ Visualization
- Plotted:
  - Training data (historical prices)
  - Forecasted petrol prices for future dates

### 8️⃣ Output Generation
- Exported predictions to a CSV file for further analysis

---

## 🧪 Model Used

### ARIMA (5,1,0)
- **p = 5** → Autoregressive terms
- **d = 1** → Differencing for stationarity
- **q = 0** → Moving average terms

ARIMA was chosen because:
- It is well-suited for univariate time-series data
- It captures trend and temporal dependence effectively

---

## 📊 Evaluation Strategy
Since the test dataset contains **only future dates and no actual prices**, traditional evaluation metrics such as MAE or RMSE were **not calculated**.

> This approach avoids data leakage and follows standard forecasting practices.

---

## 📁 Output File

### `petrol_price_forecast.csv`
| Date | Predicted Petrol Price |
|------|------------------------|
| 2019-01-01 | 121.63 |
| 2019-01-02 | 121.34 |
| ... | ... |

---

## ▶️ How to Run the Project

1. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib statsmodels scikit-learn
   ```
2. Place train.csv and test.csv in the project directory

3. Run the Jupyter Notebook or Python script step by step

4. Generated forecast will be saved as: petrol_price_forecast.csv

---



