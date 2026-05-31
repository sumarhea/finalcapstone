# 🏥 Health Insurance Claims Prediction

##  Project Overview

This project develops and evaluates machine learning models to predict health insurance claim outcomes using patient, provider, and claim-related information.

The goal is to classify claims into one of three categories:
- Approved
- Denied
- Pending

The project demonstrates a complete machine learning workflow including data preprocessing, exploratory data analysis (EDA), feature engineering, model training, hyperparameter tuning, and evaluation.

---

##  Objective

The main objectives of this project are to:

- Analyze health insurance claims data
- Prepare and clean data for machine learning
- Engineer meaningful predictive features
- Build classification models to predict claim outcomes
- Compare model performance using multiple evaluation metrics
- Identify key factors influencing claim status

---

##  Dataset

**Source:**  
Kaggle – Enhanced Health Insurance Claims Dataset  
https://www.kaggle.com/datasets/leandrenash/enhanced-health-insurance-claims-dataset/data

### Dataset Features

- Claim Amount  
- Patient Age  
- Patient Income  
- Claim Type  
- Provider Location  
- Claim Submission Method  
- Claim Status *(Target Variable)*  

---

##  Data Preparation

### Feature Selection

The following identifier columns were removed as they do not contribute to prediction:

- ClaimID  
- PatientID  
- ProviderID  

---

### Encoding

- **Label Encoding** was applied to the target variable (`ClaimStatus`)
- **One-Hot Encoding** was applied to categorical features

---

### Feature Engineering

A new feature was created:

\[
ClaimPerAge = \frac{ClaimAmount}{(PatientAge + 1)}
\]

This feature helps normalize claim amount relative to patient age.

---

### Train-Test Split

- Training Set: 80%
- Testing Set: 20%

Stratified sampling was used to maintain class distribution across splits.

---

### Feature Scaling

- `StandardScaler` was applied for Logistic Regression
- Random Forest was trained without dependency on scaling, but scaling was kept for consistency

---

##  Exploratory Data Analysis (EDA)

The following analyses were performed:

- Claim Status Distribution
- Claim Type Distribution
- Histograms of numerical features
- Correlation heatmap
- Feature importance analysis

These helped identify patterns and relationships in the dataset.

---

##  Machine Learning Models

### 1. Dummy Classifier (Baseline)

Used as a benchmark model that predicts the most frequent class.

---

### 2. Logistic Regression

- Interpretable baseline model
- Effective for multi-class classification
- Used as a comparison model

---

### 3. Random Forest Classifier

- Captures nonlinear relationships
- Handles feature interactions
- Reduces overfitting using ensemble learning
- Provides feature importance scores

---

##  Hyperparameter Tuning

Grid Search Cross Validation was used:

```python
param_grid = {
    "n_estimators": [100, 200, 300],
    "max_depth": [5, 10, 15]
}
```

## Model Performance

| Model                | Accuracy |
|---------------------|----------|
| Dummy Classifier    | 33.89%   |
| Logistic Regression | 34.56%   |
| Random Forest       | 34.78%   |


## How to Run the Project

    1. Clone the repository:
    git clone sumarhea/finalcapstone

    2.Install dependencies:
    pip install pandas numpy matplotlib seaborn scikit-learn

    3.Run the Jupyter Notebook:
    jupyter notebook

### Conclusion

This project provides a strong baseline for predicting insurance claim outcomes. The combination of EDA, feature engineering, and machine learning offers valuable insights that can be expanded further in future modules
