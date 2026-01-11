# Regression & Data Analysis Mini-Projects (Colab)

A collection of small **machine learning + data analysis** exercises built in **Google Colab**.  
Includes salary prediction with linear regression (scikit-learn + from-scratch gradient descent) and a car price prediction pipeline with feature engineering and model evaluation.

---

## Table of Contents

- [Preview](#preview)
- [Features](#features)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Controls](#controls)
- [How it works](#how-it-works)
- [Program Flow Overview](#program-flow-overview)
- [Customization](#customization)
- [Credits](#credits)

---

## Preview

This repo contains 3 main exercises:

- **Salary vs Experience (EDA + visualization)** using Pandas + Seaborn
- **Salary prediction (Linear Regression)** using scikit-learn
- **Salary prediction (from scratch)** using NumPy + Gradient Descent + Cost tracking
- **Car price prediction** using Pandas + Seaborn + scikit-learn with preprocessing and evaluation

---

## Features

- Upload and analyze CSV datasets in Colab
- Visualize relationships using scatter/joint plots and regression plots
- Train a **Linear Regression** model (scikit-learn)
- Implement **Gradient Descent** manually (NumPy only)
- Track and plot **cost over iterations**
- Build a full preprocessing pipeline for car price prediction:
  - Feature cleaning (extract car company)
  - Fix inconsistent labels (misspellings)
  - Bucket companies by median price (low/med/high)
  - One-hot encoding of categorical features
  - Train/test split + scaling + regression model
  - Evaluate with **R² score**

---

## Requirements

- Google Colab (recommended) or local Python **3.x**
- For the Salary (Pandas/Seaborn + scikit-learn) notebooks:
  - `pandas`
  - `seaborn`
  - `matplotlib`
  - `scikit-learn`
- For the Salary (NumPy-only) notebook:
  - `numpy`
  - `matplotlib`
- For the Car price notebook:
  - `pandas`
  - `seaborn`
  - `matplotlib`
  - `numpy`
  - `scikit-learn`

> Note: These projects were written for Colab-style execution (file upload widgets, cell-based workflow).

---

## How to Run

### Option A — Run in Google Colab (recommended)

1. Open the notebook in Colab
2. Upload the required dataset when prompted:
   - `Salary_dataset.csv` (for the salary exercises)
   - `Car_Price.csv` (for the car price exercise)
3. Run the cells top-to-bottom

### Option B — Run locally (if converted to `.py` / Jupyter)

1. Install dependencies:
```
pip install pandas seaborn matplotlib scikit-learn numpy
```

2. Ensure the CSV files are in the working directory:
- `Salary_dataset.csv`
- `Car_Price.csv`

3. Run the notebook or script as normal

---

## Controls

| Action | How |
|------|-----|
| Upload dataset | Use Colab’s file upload widget |
| Change test values | Edit the `years_experience` variable |
| Change training settings | Modify `alpha` and `num_iters` |
| View plots | Run visualization cells |

---

## How it works

### Salary Prediction (scikit-learn)
- Load salary dataset
- Fit `LinearRegression()` on `YearsExperience → Salary`
- Use `.predict()` to estimate salary for a chosen experience value (example: 10 years)

### Salary Prediction (NumPy only)
- Load dataset using `np.loadtxt()`
- Implement:
- `predict(X, theta)` (line equation)
- `fit(X, y, theta, alpha, num_iters)` (gradient descent)
- `cost(X, y, theta)` (MSE-based cost)
- `fit_with_cost(...)` (stores cost history)
- Plot the fitted line + cost curve

### Car Price Prediction
- Load dataset
- Clean and normalize car company names
- Visualize price distributions with boxplots
- Build engineered features:
- Bucket companies into `low/med/high` price groups (based on median)
- One-hot encode categorical features
- Train/test split, scale features, train regression model
- Evaluate predictions with **R²** (example shown: ~0.88)

---

## Program Flow Overview

### 1) Salary Dataset — Visualization + Linear Regression (Pandas/Seaborn)
1. Read CSV using Pandas
2. Plot relationships (jointplot / lmplot)
3. Train `LinearRegression()`
4. Predict salary for a chosen experience value

### 2) Salary Dataset — From Scratch (NumPy)
1. Load CSV with NumPy only
2. Visualize raw points (matplotlib)
3. Train with gradient descent
4. Visualize fitted line
5. Compute cost and plot cost trend over iterations
6. Predict salary for a new experience input

### 3) Car Price Regression Pipeline
1. Read dataset with Pandas
2. Explore data shape/info/stats
3. Extract & clean `CarCompany`
4. Visualize price patterns (boxplots)
5. Feature engineering + one-hot encoding
6. Train/test split + scaling
7. Train Linear Regression + predict
8. Evaluate with R² and compare `y_test` vs `y_pred`

---

## Customization

You can tweak files easily:

- Salary dataset:
  - Change `years_experience` for prediction tests (e.g. 5, 10, 15)
- Tune learning rate and iterations:
   - `alpha` (e.g. `0.001`, `0.01`)
   - `num_iters` (e.g. `100`, `1000`)
- Visualizations:
  - Switch between scatter, jointplot, and lmplot
  - Change plot titles and labels
- Experiment with different bucketing logic
- Add/remove features or scale differently
- Evaluate using MAE/MSE in addition to R²

---

## Credits

Colab-based regression and data analysis exercises using NumPy, Pandas, Seaborn, Matplotlib, and scikit-learn.
