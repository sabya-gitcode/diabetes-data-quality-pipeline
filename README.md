# Diabetes Data Quality Pipeline for Reliable Prediction

This repository presents an applied data preprocessing and modeling pipeline focused on improving the reliability of diabetes prediction using structured clinical data.

The project emphasizes practical data cleaning decisions, handling of invalid values, and the impact of preprocessing choices on downstream model performance.

Rather than optimizing aggressively for model performance, the goal is to demonstrate a clear and defensible data preparation workflow, with attention to common issues in real-world datasets such as missing values, skewness, and outliers.

---

## Project Overview

The pipeline implements an end-to-end workflow including:

- Data loading and initial inspection  
- Identification and handling of medically unrealistic values (e.g., 'zero' entries in medical features)  
- Missing value imputation using median-based strategies  
- Visualization of distributions before and after imputation  
- Feature scaling using multiple techniques  
- Training and evaluation of a baseline classification model  

All preprocessing decisions are explained with reference to the underlying data characteristics.

---

## Data Cleaning Approach

The dataset contains several features where zero values are not medically meaningful (e.g., Glucose, Insulin, BMI). These values are treated as missing and replaced accordingly.

Median imputation is used for numerical features due to:

- Presence of skewed distributions  
- Sensitivity of mean to outliers  
- Need for robust central tendency estimation  

This approach preserves realistic data structure while minimizing distortion.

---

## Feature Scaling

Three scaling techniques are applied and compared:

- StandardScaler  
- MinMaxScaler  
- RobustScaler  

These methods are evaluated to understand how different scaling strategies interact with skewed data and outliers.

---

## Model and Evaluation

A Logistic Regression model is used as a baseline to evaluate the effect of preprocessing.

Performance is measured using:

- Accuracy  
- Precision  
- Recall  
- F1-score  

The goal is not to achieve maximum accuracy, but to assess how data preparation influences model behavior.

---

## Key Observations

- Median imputation preserved the overall distribution of features  
- Insulin remained highly skewed, indicating persistent variability  
- RobustScaler showed better handling of outliers compared to other methods  
- Data cleaning had a measurable impact on model performance  

---

## Limitations and Scope

This project is intentionally scoped as a preprocessing-focused exercise.

Known limitations include:

- Use of a single train–test split (no cross-validation)  
- No hyperparameter tuning  
- Use of a single baseline model  
- No deployment or inference layer  

These choices reflect a focus on clarity of preprocessing and workflow design rather than production-level optimization.

---

## Dataset

The project uses a publicly available diabetes dataset commonly used for educational and benchmarking purposes.

---

## Intended Use

This repository is intended to demonstrate:

- Practical understanding of data preprocessing workflows  
- Awareness of real-world data quality issues  
- Ability to reason about modeling decisions and trade-offs  

This project is shared for educational and portfolio purposes.
