# 📊 Credit Card Default Behaviour Score Prediction

This project aims to build a classification model that predicts whether a credit card customer will default in the next month. By analyzing financial and behavioral data of over 25,000 customers, the model helps banks and financial institutions mitigate risk and take early action.

---

## 🧠 Objective

- Perform exploratory data analysis (EDA) and clean the dataset
- Engineer meaningful features from payment behavior
- Develop multiple classification models and compare performance
- Optimize for **F2 score** to prioritize recall (catching defaulters)
- Interpret and communicate business implications of the results

---

## 📁 Dataset

The dataset contains anonymized information about:
- Customer demographics (age, sex, education, marriage)
- Past payment status (PAY_0 to PAY_6)
- Bill amounts and payment amounts over 6 months
- Default status in the next month (target variable)

---

## 🔧 Methodology

### 1. Data Preparation
- Dropped irrelevant columns (e.g., Customer ID)
- Handled missing values
- Label-encoded categorical features

### 2. Exploratory Data Analysis (EDA)
- Analyzed default trends by demographics
- Visualized credit limit and default distributions
- Identified key default signals in overdue payments and repayment ratios

### 3. Feature Engineering
- `pay_amt_total`: Total repayments over 6 months
- `avg_bill_amt`: Average bill exposure
- `pay_to_bill_ratio`: Repayment discipline indicator
- Delinquency patterns from `PAY_0` to `PAY_6`
- Age used both as binned groups (for EDA) and as continuous variable (for modeling)

### 4. Model Training
- Trained: Logistic Regression, Decision Tree, Random Forest, XGBoost, LightGBM
- Addressed class imbalance using **SMOTE**

### 5. Model Evaluation
- Metrics: Accuracy, Precision, Recall, F1, **F2**
- **Decision Tree** chosen as final model due to:
  - Highest Recall (0.615)
  - Strongest F2 Score (0.549)
  - Easier interpretability

### 6. Cutoff Optimization
- Chose probability threshold = **0.4**
- Balanced recall and precision to reduce **false negatives**

---

## 📈 Model Performance

| Model              | Accuracy | Precision | Recall | F1 Score | F2 Score |
|--------------------|----------|-----------|--------|----------|----------|
| Decision Tree      | 0.738    | 0.383     | 0.615  | 0.472    | 0.549    |
| Logistic Regression| 0.764    | 0.413     | 0.563  | 0.476    | 0.525    |
| XGBoost            | 0.821    | 0.543     | 0.398  | 0.459    | 0.421    |
| LightGBM           | 0.834    | 0.592     | 0.410  | 0.484    | 0.437    |
| Random Forest      | 0.836    | 0.649     | 0.300  | 0.410    | 0.336    |

---

## 💼 Business Implications

- Proactively flag high-risk customers for early intervention
- Support credit limit decisions based on repayment behavior
- Target personalized communication to demographics with higher default trends
- Use model transparency to explain decisions to non-technical stakeholders

---

## 📌 Key Insights

- Younger users (21–30) tend to default more than older ones
- Males and married customers show higher credit limits and slightly higher defaults
- Graduates and university-educated users have higher limits and more defaults

---

## 🔍 Summary

- Focused on **recall and F2 score** due to business need to catch defaulters
- Chose a Decision Tree for its explainability and high recall
- Designed features that closely reflect credit and repayment behavior
- Balanced model performance and interpretability for practical deployment

---


