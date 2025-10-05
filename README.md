# Traffic Congestion Analysis & Data Preprocessing

This repository contains my **Exploratory Data Analysis (EDA)** and **Data Preprocessing** work for a traffic congestion dataset.  
The goal of this project is to understand traffic flow dynamics, analyze temporal and spatial patterns, and prepare the dataset for predictive modeling.

---

## 📘 Project Overview

Traffic congestion is a critical issue in modern urban areas. This project aims to:
1. Collect and clean traffic data from various junctions.
2. Aggregate it into **hourly intervals** for better temporal analysis.
3. Engineer meaningful features (time-based, lag, rolling averages, event indicators).
4. Normalize and prepare the dataset for machine learning models.

This repository serves as the **complete data preparation pipeline** — from raw input to ready-for-model dataset.

---

## 📂 Files Included

| File | Description |
|------|--------------|
| **`Aggregated_Preprocessed_Data_Karthik.ipynb`** | Jupyter Notebook performing cleaning, EDA, feature engineering, and preprocessing. |
| **`aggregated_preprocessed_rawfeatures.csv`** | Aggregated dataset with all engineered features (unscaled). |
| **`aggregated_preprocessed_scaled.csv`** | Normalized and scaled version of the dataset ready for model training. |
| *(Optional)* `presentation.pdf` | Summary presentation of EDA findings and visual insights. |

---

## 🧹 Data Cleaning & Preprocessing

Key preprocessing steps performed:
- Handled missing values (`fillna`, `dropna`).
- Removed duplicates (`drop_duplicates`).
- Corrected data types (`astype`, datetime parsing).
- Standardized column names (`timestamp`, `junction_id`, `vehicle_count`).
- Aggregated data into **hourly intervals** per junction.

---

## 🧩 Feature Engineering

Created additional features to capture traffic patterns and external influences:
- **Time-based features:** `hour`, `day_of_week`, `month`, `is_weekend`.
- **Cyclical encoding:** `hour_sin`, `hour_cos` for time-of-day periodicity.
- **Lag features:** Traffic counts from previous hours/days (1, 2, 3, 24).
- **Rolling averages:** Mean vehicle count over past 3, 6, and 24 hours.
- **Event indicators:** Binary `is_event` feature for special events/holidays.

---

## 📊 Exploratory Data Analysis (EDA)

Performed detailed EDA to identify:
- Distribution and spread of hourly traffic volumes.
- Weekly and hourly trends (rush hour detection).
- Junction-wise variation in traffic density.
- Correlation between features and traffic count.
- RandomForest feature importances to select top predictive features.

**Visualizations included:**
- Histogram of hourly vehicle counts  
- Time-series plots for sample junctions  
- Average hourly traffic profile  
- Weekday boxplots  
- Feature importance charts  

---

## 🧮 Feature Selection

Used both statistical and machine learning methods:
- **Correlation analysis** with the target variable.  
- **RandomForestRegressor feature importance** to evaluate predictive power.  
- Selected top `K` most relevant features for model training.

---

## ⚙️ How to Run

### 1️⃣ Prerequisites
Install the required Python libraries:
```bash
pip install pandas numpy matplotlib scikit-learn jupyter
