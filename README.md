# rossmann_store_sales_TS

# Rossmann Store Sales Time Series Forecasting

This project aims to forecast daily sales for Rossmann stores using a variety of time series and machine learning models. The workflow includes data preprocessing, exploratory data analysis (EDA), feature engineering, model training, evaluation, and submission preparation for a Kaggle-style competition.

## 📁 Project Structure

```
.
├── LICENSE
├── Project.ipynb
├── requirements.txt
├── submission_lgb.csv
├── submission_rf.csv
├── rossmann-store-sales/
│   ├── train.csv
│   ├── test.csv
│   ├── store.csv
│   └── sample_submission.csv
└── ...
```

## 📊 Data Description

- **Store**: Unique ID for each store
- **Sales**: Turnover for any given day (target variable)
- **Customers**: Number of customers on a given day
- **Open**: Store open indicator (0 = closed, 1 = open)
- **StateHoliday**: State holiday flag (a = public, b = Easter, c = Christmas, 0 = None)
- **SchoolHoliday**: School closure impact flag
- **StoreType**: Store model type (a, b, c, d)
- **Assortment**: Assortment level (a = basic, b = extra, c = extended)
- **CompetitionDistance**: Distance to nearest competitor
- **CompetitionOpenSince[Month/Year]**: When nearest competitor opened
- **Promo**: Promo running on that day
- **Promo2**: Ongoing promotion flag
- **Promo2Since[Year/Week]**: When store started Promo2
- **PromoInterval**: Months when Promo2 starts anew

## 🛠️ Features

- **EDA**: Outlier detection, time series visualization, seasonality analysis
- **Preprocessing**: Handling missing values, encoding categorical variables, scaling, interpolation
- **Feature Engineering**: Date features, lag features, rolling means
- **Models**:
  - Naive, Moving Average, Weighted Moving Average
  - Exponential Smoothing (SES, Holt, Holt-Winters)
  - ARIMA, SARIMA (with auto_arima)
  - Prophet (with and without regressors)
  - Machine Learning: Random Forest, Gradient Boosting, LightGBM, XGBoost
- **Evaluation**: MAE, RMSE, RMSPE, MAPE, sMAPE, MASE
- **Submission**: Generates CSV files for competition submission

## 🚀 How to Run

1. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

2. **Download data:**  
   Place `train.csv`, `test.csv`, and `store.csv` in the `rossmann-store-sales/` directory.

3. **Run the notebook:**  
   Open `Project.ipynb` in VS Code or Jupyter and execute cells sequentially.

4. **Generate submissions:**  
   The notebook will output `submission_lgb.csv` and `submission_rf.csv` for LightGBM and Random Forest predictions.

## 📝 Results

- **Top models:**  
  - LightGBM Regressor (lowest RMSPE)
  - Random Forest Regressor (competitive performance)
- **Feature importance:**  
  - Open, Promo, SchoolHoliday, PromoInterval, Assortment

## 📦 Requirements

See [requirements.txt](requirements.txt) for the full list.

## 📄 License

This project is licensed under the [Apache License 2.0](LICENSE).

---

*Inspired by the Kaggle Rossmann Store Sales competition.*