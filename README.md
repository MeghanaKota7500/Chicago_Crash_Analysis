# 🚗 Chicago Crash Data Analysis (2020–2024)

## 📊 Overview

This project analyzes traffic crash data from the City of Chicago between 2020 and 2024 to uncover patterns, assess contributing factors, and forecast future crash trends. Using machine learning models and time-series forecasting, we provide actionable insights to improve traffic safety and guide policymaking.

---

## 🎯 Objectives

- Identify key factors contributing to crash severity
- Explore temporal and environmental crash patterns
- Build predictive models to classify crash severity
- Forecast crash volume trends for 2025
- Recommend strategies for reducing crash severity

---

## 📁 Dataset

- **Source:** [City of Chicago - Traffic Crashes](https://catalog.data.gov/dataset/traffic-crashes-crashes)
- **Period Covered:** 2020–2024
- **Initial Records:** 540,032
- **Final Used Records:** 532,037 (after cleaning and excluding incomplete 2025 data)
- **Target Variable:** `MOST_SEVERE_INJURY` (Multiclass)

---

## 🧹 Data Preprocessing

- Dropped columns with >5% missing values
- Handled missing categorical data (`'Unknown'`)
- Filled missing numerical values with mean
- Converted categorical features to numerical encoding
- Removed "Unknown" from target variable during modeling
- Applied SMOTE to handle class imbalance

---

## 🔍 Exploratory Data Analysis

Key insights from EDA:

- **Peak crash hours:** 4 PM to 6 PM (rush hours)
- **Most crashes:** Occur under **clear weather** and **daylight**
- **Top causes:** Speeding, failure to yield, following too closely
- **Speed Zones:** Most crashes happen at 30–40 mph
- **Seasonality:** Higher crash frequency during warmer months (May–October)

Visualizations include:
- Yearly crash trends
- Speed limit distribution
- Crash severity and contributory causes
- Weather & lighting conditions
- Hourly and monthly distributions

---

## 🤖 Modeling

### 1. Multinomial Logistic Regression
- **Accuracy:** 49%
- **F1-score (No Injury):** 0.91
- **Limitations:** Struggled with minority classes; not effective for nonlinear relationships

### 2. XGBoost Classifier
- **Accuracy:** 72%
- **Macro F1-score:** 0.71
- **Strength:** Better prediction for both “Fatal” and “No Indication of Injury” classes
- **Top Features:** `CRASH_TYPE`, `LIGHTING_CONDITION`, `NUM_UNITS`, `CONTRIBUTING_CAUSE`

---

## 📈 Time Series Forecasting

- **Model Used:** Prophet
- **Forecast:** Crashes projected to rise from 92,973 (2020) to 112,684 (2025) – a 21% increase
- Indicates a need for preventive traffic strategies and infrastructure planning

---

## 🔦 Interpretation & Key Takeaways

- **Fatal crashes** mostly occur under **clear weather** and at **night under artificial lighting**
- **Speed limits, lighting, time of day**, and **weather** significantly affect severity
- Rush hour and poorly lit areas are high-risk zones
- ML models can guide **policy** and **intervention planning** effectively

---

## 🛠 Technologies Used

- **Languages:** Python
- **Libraries:** `pandas`, `scikit-learn`, `xgboost`, `seaborn`, `matplotlib`, `Prophet`
- **Tools:** Jupyter Notebook, GitHub

---

## ⚠️ Limitations

- Behavioral factors like distraction, intoxication, or seatbelt use were not available
- SMOTE may introduce synthetic bias
- Data limited to police reports – no hospital/insurance integrations

---

## 💡 Future Work

- Incorporate real-time IoT traffic data and connected vehicle signals
- Integrate behavioral data from hospital/insurance reports
- Deploy AI-driven traffic monitoring tools
- Expand to other urban cities for comparative studies

---

## 📚 References

- City of Chicago Data Portal
- Research papers on crash modeling, injury severity, and urban safety strategies

---

## 👥 Contributors

- Meghana Kota  
- Harshad Gupta Pasumarthy 
