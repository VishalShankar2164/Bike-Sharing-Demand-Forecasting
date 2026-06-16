# Bike Sharing Demand Forecasting

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue" alt="Python">
  <img src="https://img.shields.io/badge/Scikit--Learn-ML-orange" alt="Scikit-Learn">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-green" alt="Pandas">
  <img src="https://img.shields.io/badge/License-MIT-yellow" alt="License">
</p>

Machine Learning-based bike rental demand forecasting system that predicts bike-sharing demand using historical rental, weather, and time-based data. The project applies exploratory data analysis, feature engineering, and multiple regression models to identify the most effective approach for forecasting future bike rental demand.

---

## Overview

Bike-sharing systems generate large volumes of usage data influenced by weather conditions, seasonal patterns, holidays, and time-based trends. Accurate demand forecasting helps operators optimize resource allocation, improve customer satisfaction, and reduce operational inefficiencies.

This project develops and evaluates multiple regression-based machine learning models to predict bike rental demand using historical data and engineered temporal features.

### Objectives

* Analyze historical bike-sharing demand patterns.
* Identify factors influencing rental activity.
* Engineer meaningful predictive features.
* Train and compare multiple regression models.
* Evaluate model performance using RMSLE.
* Generate demand predictions for unseen data.

### Key Benefits

* Improved demand forecasting accuracy.
* Better resource planning and bike availability.
* Data-driven decision making.
* Practical application of machine learning regression techniques.

---

## Features

### Data Analysis

* Exploratory Data Analysis (EDA)
* Missing value inspection
* Correlation analysis
* Distribution analysis
* Outlier identification

### Feature Engineering

* Datetime decomposition
* Hour extraction
* Day of week extraction
* Month extraction
* Cyclical time encoding using sine and cosine transformations
* Target variable transformation using logarithmic scaling

### Machine Learning Models

* Linear Regression
* Polynomial Regression (Degree 2)
* Polynomial Regression (Degree 3)
* Ridge Regression
* Lasso Regression

### Model Evaluation

* RMSLE (Root Mean Squared Logarithmic Error)
* Residual analysis
* Model comparison and selection

### Prediction Pipeline

* Training workflow
* Validation workflow
* Test data prediction
* Submission file generation

## Tech Stack

| Category                | Technology          |
| ----------------------- | ------------------- |
| Language                | Python              |
| Data Processing         | Pandas, NumPy       |
| Visualization           | Matplotlib, Seaborn |
| Machine Learning        | Scikit-Learn        |
| Development Environment | Jupyter Notebook    |
| Evaluation Metric       | RMSLE               |


### Directory Description

| File / Folder                         | Purpose                          |
| ------------------------------------- | -------------------------------- |
| bike_train.xlsx                       | Training dataset                 |
| bike_test.xlsx                        | Test dataset                     |
| Bike_Sharing_Demand_Forecasting.ipynb | Complete ML workflow             |
| README.md                             | Project documentation            |

---

## Dataset Information

### Training Dataset

Contains historical bike rental information along with weather and temporal variables.

### Features

| Feature    | Description            |
| ---------- | ---------------------- |
| datetime   | Date and time          |
| season     | Season category        |
| holiday    | Holiday indicator      |
| workingday | Working day indicator  |
| weather    | Weather condition      |
| temp       | Temperature            |
| atemp      | Feels-like temperature |
| humidity   | Humidity level         |
| windspeed  | Wind speed             |
| casual     | Casual users           |
| registered | Registered users       |
| count      | Total rentals (Target) |

### Test Dataset

Contains the same predictive features excluding the target variable.

---



## Running Locally

### Launch Jupyter Notebook

```bash
jupyter notebook
```

### Open Notebook

```text
Bike_Sharing_Demand_Forecasting.ipynb
```

### Execute Cells

Run all notebook cells sequentially to:

1. Load datasets
2. Perform EDA
3. Engineer features
4. Train models
5. Evaluate performance
6. Generate predictions

---

## Build Instructions

No build process is required.

The notebook executes the complete machine learning workflow.


## Usage

### Load Dataset

```python
train = pd.read_excel("bike_train.xlsx")
test = pd.read_excel("bike_test.xlsx")
```

### Train Model

```python
lasso_model.fit(X_train, y_train)
```

### Generate Predictions

```python
predictions = lasso_model.predict(X_test)
```

### Save Predictions

```python
submission.to_csv("submission.csv", index=False)
```

---

## Modeling Approach

### Feature Engineering

Datetime is decomposed into:

```text
datetime
├── hour
├── dayofweek
└── month
```

### Cyclical Encoding

```python
hour_sin = np.sin(2 * np.pi * hour / 24)
hour_cos = np.cos(2 * np.pi * hour / 24)
```

### Target Transformation

```python
y_log = np.log1p(count)
```

### Evaluation Metric

```text
Root Mean Squared Logarithmic Error (RMSLE)
```

---

## Model Comparison

| Model                            | Purpose                              |
| -------------------------------- | ------------------------------------ |
| Linear Regression                | Baseline model                       |
| Polynomial Regression (Degree 2) | Captures nonlinear relationships     |
| Polynomial Regression (Degree 3) | Higher-order interactions            |
| Ridge Regression                 | L2 regularization                    |
| Lasso Regression                 | Feature selection and regularization |

---

## Configuration

Key parameters can be adjusted within the notebook:

| Parameter         | Purpose                    |
| ----------------- | -------------------------- |
| Polynomial Degree | Controls feature expansion |
| Alpha Values      | Ridge/Lasso regularization |
| Train/Test Split  | Validation strategy        |
| Feature Selection | Input variables            |

---

## Development Workflow

### Data Preparation

```text
Load Data
   ↓
Clean Data
   ↓
EDA
   ↓
Feature Engineering
```

### Model Development

```text
Feature Matrix
      ↓
Model Training
      ↓
Validation
      ↓
Evaluation
      ↓
Selection
```

### Output Generation

```text
Best Model
      ↓
Prediction
      ↓
submission.csv
```

---

## Performance Optimizations

Implemented optimizations include:

* Log transformation of target variable.
* Cyclical encoding of temporal features.
* Regularized regression techniques.
* Polynomial feature engineering.
* Cross-validation for hyperparameter tuning.


* Open Source Machine Learning Community

