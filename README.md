#  Solar Energy Optimization Using Time Series Forecasting

This project analyzes solar power generation data and applies machine learning and time series forecasting models to optimize predictions of solar energy output. The goal is to understand patterns in solar production and build accurate forecasting models for better planning and utilization of solar energy systems.

---

## 📁 Dataset

- **Source**: Custom solar dataset — `Actual_25.15_-80.95_2006_UPV_227MW_5_Min.csv`
- **Granularity**: Power output (in MW) recorded every 5 minutes
- **Preprocessing**:
  - Parsed and indexed `LocalTime` to extract: `date`, `hour`, `minute`, `day_of_week`, `month`
  - Enabled time-based grouping for seasonal and hourly analysis

---

##  Data Analysis

A thorough exploration of the dataset uncovered clear temporal patterns in solar power generation:

###  Monthly Trends
- **Peak Output**: Occurs in **March to August**, corresponding to longer daylight hours.
- **Lowest Output**: Found in **December and January**, likely due to shorter days and cloudier skies.
- **Insight**: Strong **seasonality** observed, which supports use of seasonal models for forecasting.

###  Daily Trends
- Minimal variation across the days of the week.
- Slightly **higher generation on weekends**, possibly due to lower grid interference or weather variation.

###  Hourly Trends
- **Sharp increase** in output from 6 AM to 10 AM.
- **Peak generation** between **11 AM and 2 PM**.
- **Zero output** from 6 PM to early morning hours, confirming the need for storage solutions for nighttime usage.

---

##  Key Findings

1. **Solar generation is highly dependent on the time of day and season**, reinforcing the need for time-aware models.
2. **Hourly plots show sharp ramp-up and ramp-down periods**, which are critical for battery and inverter design.
3. **Consistent weekly output** implies no major operational downtime or maintenance-based interruptions.
4. **Simple models like linear regression underperform**, particularly during sudden changes in solar activity.
5. **Prophet forecasts closely match actual outputs**, even during fluctuating periods — it also provides confidence intervals for uncertainty handling.

---

##  Modeling & Forecasting

###  Linear Regression
- Acts as a baseline model.
- Captures basic trend but misses variability.
- Less suitable for capturing seasonality.

###  Facebook Prophet
- Automatically detects seasonality, trends, and changepoints.
- More accurate and reliable for short-term and long-term forecasts.
- Includes confidence intervals to reflect uncertainty in predictions.

---

##  Model Evaluation

| Metric         | Linear Regression | Prophet      |
|----------------|-------------------|--------------|
| Mean Absolute Error (MAE) | Higher Error      | ✅ Lower Error |
| Root Mean Squared Error (RMSE) | Higher         | ✅ Lower        |
| R² Score        | Lower (poor fit) | ✅ Higher (better fit) |

**Prophet clearly outperformed Linear Regression** across all major evaluation metrics.

---

##  Technologies Used

- Python 3.x
- Pandas, NumPy
- Matplotlib
- Scikit-learn
- Facebook Prophet

---

##  Future Work

- Integrate external weather data (cloud cover, temperature)
- Experiment with deep learning models like **LSTM** for better sequence learning
- Extend the analysis to **multi-site solar farms** or national grid-level forecasting
- Build a **dashboard** for real-time solar power monitoring and prediction

---

##  License

This project is intended for academic, educational, and research purposes. Contact the authors for usage in commercial settings.

---

##  Contributors

- THRINAY KUMAR DEVI RAMAKRISHNA – Data Analysis, Forecasting Model Development, Visualization, Reporting

---

