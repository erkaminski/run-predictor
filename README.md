> ⚠️ This project was developed in 2023 as part of the final team project for the Le Wagon bootcamp.  
> Some design choices and code structure reflect the practices and tools used at that time.

# Trail Running Race Predictor

Predict race times using machine learning based on running activity data.

---

## Overview

This project builds a regression model to predict race time from features such as distance, elevation, heart rate, and time of day.

Dataset:  
https://www.kaggle.com/datasets/olegoaer/running-races-strava

- ~42,000 races  
- 105 runners  
- 7 initial features → 26 after preprocessing  

The model outputs three predictions based on different performance levels.

---

## Data

Main features:

- athlete (ID)
- gender
- timestamp
- distance (m)
- elapsed time (s)
- elevation gain (m)
- average heart rate (BPM)

---

## Pipeline

The workflow is split into several steps:

**1. Data cleaning (`a_cleaning.py`)**
- remove duplicates
- handle missing values
- remove outliers

**2. Train/test split (`b_splitting.py`)**

**3. Feature engineering (`c_feature_engineering.py`)**
- cyclical features (day / month)
- time-of-day categories
- season categories
- elevation categories (based on gain per km)
- race performance categories

**4. Balancing (`d_balancing.py`)**
- equalize number of male / female observations

**5. Scaling & encoding (`e_scaling_encoding.py`)**
- standard scaling
- one-hot encoding

---

## Final Dataset

26 features including:

- cyclical time features (sin/cos)
- time-of-day categories
- seasonal categories
- elevation categories
- race categories
- distance, elevation, heart rate

---

## 🤖 Model

Training script: `f_training.py`

Model used: **Stacking Regressor**
- Random Forest
- Gradient Boosting
- XGBoost
- Linear Regression (final estimator)

**Performance:**
- R² ≈ 0.97
- MAPE ≈ 5.4%

---

## ▶️ Usage

Install dependencies:

```bash
pip install -r requirements.txt
```

Install the package:
```bash
python setup.py install
```

Run predictions by providing input features (distance, elevation, heart rate, etc.).
The model returns predicted race time for different performance levels.

Demo:
https://benito-p-run-pred-front-page-web-roqy7e.streamlit.app/

---

## 📝 Notes
Built as a team project in 2023
Focus on feature engineering and pipeline structure
Results depend on dataset quality and distribution

---

## 👥 Authors

This project was developed collaboratively in 2023 by:

simonchartan-lewagon
TomP81
erkaminski
benito-p
