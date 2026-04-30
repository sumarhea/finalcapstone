# Project Overview

This project focuses on analyzing health insurance claims data and building a machine learning model to predict claim outcomes (e.g., approved, denied, pending). The goal is to identify key factors influencing claim status and evaluate model performance using classification techniques.

# Objective

    - Perform Exploratory Data Analysis (EDA) on insurance claims data
    - Clean and preprocess the dataset
    - Engineer useful features to improve prediction
    - Build classification models to predict claim status
    - Evaluate model performance using accuracy and classification metrics

## Dataset

The dataset contains health insurance claim information including:

    - Claim amount
    - Patient age
    - Patient income
    - Claim type
    - Provider location
    - Claim submission method
    - Claim status (target variable)

## Data Cleaning 

The following steps were performed:

    - Removed duplicate records
    - Handled missing values (median for numeric, mode for categorical)
    - Dropped ID columns (e.g., ClaimID, PatientID)
    - Encoded categorical variables
    - Created new feature: ClaimPerAge

### Exploratory Data Analysis (EDA)

    EDA was performed to understand:

    - Distribution of claim status (target imbalance check)
    - Distribution of numerical features
    - Correlation between variables
    - Outlier detection using box plots
    - Feature relationships with target variable

### Machine Learning Models

    The following models were used:

    - Logistic Regression
    - Random Forest Classifier

## Feature Engineering

    A new feature was created:

    - ClaimPerAge = ClaimAmount / (PatientAge + 1)

## Model Training Process

- Dataset split into training (80%) and testing (20%)
- One-hot encoding used for categorical variables
- Label encoding applied to target variable
- Random Forest model trained with 300 estimators
- Stratified split used to preserve class distribution

## Evaluation Metrics

    Model performance was evaluated using:
    - Accuracy Score
    - Precision
    - Recall
    - F1-Score
    - Confusion Matrix

## Results

    - Model achieved an accuracy of approximately 0.41 (41%)
    - Performance indicates class imbalance and feature complexity
    - Further tuning and feature engineering may improve results

## Key Insights

    - Claim status distribution is imbalanced
    - Certain features have stronger influence on prediction
    - Feature importance shows key drivers of model decisions 

## Future Improvements

    - Handle class imbalance (SMOTE / class weighting)
    - Hyperparameter tuning (GridSearchCV)
    - Try advanced models (XGBoost, LightGBM)
    - Improve feature selection
    - Remove high-cardinality noise features (e.g., IDs)

## Tech Stack

    Python
    Pandas, NumPy
    Matplotlib, Seaborn
    Scikit-learn

## How to Run the Project

    1. Clone the repository:
    git clone sumarhea/finalcapstone

    2.Install dependencies:
    pip install pandas numpy matplotlib seaborn scikit-learn

    3.Run the Jupyter Notebook:
    jupyter notebook

### Conclusion

This project provides a strong baseline for predicting insurance claim outcomes. The combination of EDA, feature engineering, and machine learning offers valuable insights that can be expanded further in future modules