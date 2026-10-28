# RetailPulse — Strategic Revenue Analytics & Time-Series Forecasting

**Gamma GLM | SARIMAX | Statistical Modeling | Revenue Analytics | Python & R**

## 📌 Overview

This project analyzes daily revenue patterns from the **UCI Online Retail dataset**, containing approximately **541,909 transactions**, using statistical regression and time-series forecasting.

The objective is to understand revenue variability, identify seasonal purchasing patterns, and evaluate forecasting methods that can support retail planning and decision-making.

**Key objectives:**
- Analyze weekday, weekend, and seasonal revenue patterns.
- Investigate associations between high-revenue days and sales performance.
- Build an interpretable **Gamma Generalized Linear Model (GLM)**.
- Develop and evaluate a **SARIMAX model** for a 90-day forecasting horizon.

<img width="728" height="773" alt="Retail revenue analytical framework" src="https://github.com/user-attachments/assets/a3a1b240-8080-4497-bef8-d8deed555b51" />

## 🧠 Key Insights

### 1. Revenue Spike Analysis

The Gamma GLM reported approximately **105% higher revenue on identified high-revenue days**, with statistical significance (p < 0.001).

These days were identified using revenue-derived indicators rather than actual promotion records. Therefore, the result is descriptive and does not establish a causal marketing effect.

### 2. Weekend Revenue Patterns

The regression estimated approximately **50% lower daily revenue on weekends**, holding the included model variables constant.

This suggests meaningful differences between weekday and weekend purchasing activity.

### 3. Seasonal Trends

The analysis identified:
- A recurring **7-day seasonal pattern**.
- Higher revenue activity during parts of Q4.
- Variation in purchasing activity across months.

### 4. Forecasting Performance

| Metric | Reported Result |
|---|---:|
| Test RMSE | £21,619 |
| Test MAE | £13,914 |
| Forecast evaluation horizon | 90 days |

The SARIMAX model captured broad revenue patterns but showed greater prediction errors during unusually high-revenue periods.

## 🛠️ Methodology

### 1. Data Preparation & Feature Engineering

The Python preprocessing pipeline:
- Filters the dataset to UK transactions.
- Removes invalid quantities and prices.
- Computes transaction revenue.
- Aggregates transactions into daily observations.
- Creates calendar-based features.
- Identifies high-revenue days for exploratory analysis.

### 2. Gamma Generalized Linear Model

A **Gamma GLM with a log-link function** was used to analyze daily revenue.

**Predictors:**
- High-revenue-day indicator (`is_promotion` in the original code)
- Weekend indicator
- Month (categorical)

The model was used to estimate statistical associations between these variables and revenue.

### 3. SARIMAX Time-Series Forecasting

The forecasting workflow incorporated:
- **ARIMA(1,0,2)** nonseasonal order.
- Weekly seasonal frequency of 7.
- Exogenous variables for weekend and high-revenue-day indicators.
- Forecast evaluation over a 90-day holdout.

**Diagnostics included:**
- Augmented Dickey-Fuller (ADF) test
- KPSS stationarity test
- ACF and PACF analysis
- Ljung–Box residual autocorrelation test
- RMSE and MAE evaluation

## 📈 Results & Visualizations

### Revenue Patterns and Exploratory Analysis

<img width="899" height="599" alt="Retail revenue analysis visualization" src="https://github.com/user-attachments/assets/05f95b5d-bc93-4e1b-bb16-9ddaeddf0c39" />

### Regression and Time-Series Analysis

<img width="1155" height="676" alt="Regression and time-series analysis result" src="https://github.com/user-attachments/assets/48151ee5-86b3-44c9-b2ff-d46c5eb2dbfd" />

<img width="1182" height="796" alt="Statistical modeling and forecasting visualization" src="https://github.com/user-attachments/assets/b7198811-f7dd-4241-a6e1-99547cbbede5" />

### Additional Model Diagnostics

<img width="636" height="406" alt="Time-series diagnostic visualization" src="https://github.com/user-attachments/assets/4aeea625-ebde-44c6-b648-05ed9d19921c" />

<img width="638" height="369" alt="Forecasting model diagnostic visualization" src="https://github.com/user-attachments/assets/de56713e-0cc8-43ee-9159-3c3caa336ac7" />

## 💼 Business Applications

The project demonstrates how statistical modeling and forecasting can support:

- **Revenue planning:** Understanding recurring patterns in sales activity.
- **Operational planning:** Identifying periods with higher and lower demand.
- **Forecast evaluation:** Quantifying predictive uncertainty and model limitations.
- **Marketing experimentation:** Motivating future A/B tests using actual campaign records.
- **Inventory management:** Incorporating seasonal demand patterns into planning.

These are potential applications rather than verified financial improvements.

## ⚙️ Technologies

| Category | Tools |
|---|---|
| Programming | Python, R |
| Data Processing | Pandas, NumPy, dplyr |
| Statistical Modeling | Gamma GLM, Regression |
| Forecasting | SARIMAX, forecast |
| Diagnostics | ADF, KPSS, ACF, PACF, Ljung–Box |
| Visualization | Matplotlib, ggplot2 |
| Development | Jupyter Notebook, RStudio |

## 📎 How to Run

Clone the repository:

```bash
git clone https://github.com/MLAlchemy-cmd/A-Time-Series-Regression-Approach-to-Promotion-Optimization.git
```

**Step 1 — Python preprocessing**

Open the Jupyter notebook and run the data-cleaning and feature-engineering pipeline to generate `uk_daily_features.csv`.

**Step 2 — R modeling**

Install the required packages:

```r
install.packages(c(
  "forecast",
  "ggplot2",
  "tseries",
  "dplyr",
  "broom",
  "gridExtra"
))
```

Open `regression_study_r_code.R`, update the dataset path, and run the regression and forecasting analyses.

## ⚠️ Limitations & Future Work

- The high-revenue-day indicator is calculated from observed revenue and should not be interpreted as an actual promotion variable.
- Using that indicator during forecasting introduces information unavailable at prediction time.
- Residual autocorrelation suggests the model does not fully capture the time-series structure.
- Forecast accuracy decreases during extreme revenue fluctuations.

**Future improvements:** Incorporate verified promotional campaign data, holiday indicators, rolling-origin validation, and alternative forecasting models.

## 🎓 Project Context

Developed to demonstrate statistical modeling, time-series forecasting, model diagnostics, and business-oriented data interpretation using real-world retail transactions.

## 👩‍💻 Author

**Sahitya Avadhanam**  
M.S. Data Science | University of Minnesota, Twin Cities

[GitHub Profile](https://github.com/MLAlchemy-cmd)
