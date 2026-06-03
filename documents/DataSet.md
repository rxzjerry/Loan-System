# DATASET.md — Smart Loan Intelligence System 

---

# 1. Dataset Overview

The Smart Loan Intelligence System uses a structured financial dataset to train machine learning models for:

- Loan Eligibility Prediction  
- Loan Approval Prediction  
- Credit Risk Classification  

The dataset contains applicant demographic, financial, and credit-related information used to simulate real-world banking scenarios.

---

# 2. Dataset Source

The dataset used for this project can be:

- Kaggle Loan Prediction Dataset (commonly used in ML finance projects)
- OR a custom synthetic dataset generated for training purposes

>  In real-world systems, bank datasets are confidential, so public datasets or synthetic data are used for development.

---

# 3. Problem Type

| Model | Problem Type |
|------|-------------|
| Eligibility Prediction | Binary Classification |
| Loan Approval Prediction | Binary Classification |
| Credit Risk Prediction | Multi-class Classification |

---

# 4. Dataset Features

The dataset contains the following types of features:

---

## 4.1 Personal Information

| Feature | Description |
|--------|-------------|
| Gender | Male / Female |
| Age | Age of applicant |
| Marital Status | Married / Single |
| Dependents | Number of dependents |
| Education | Graduate / Not Graduate |

---

## 4.2 Financial Information

| Feature | Description |
|--------|-------------|
| Applicant Income | Monthly income of applicant |
| Coapplicant Income | Income of co-applicant |
| Loan Amount | Requested loan amount |
| Loan Term | Duration of loan |
| Debt-to-Income Ratio | Financial burden indicator |

---

## 4.3 Employment Information

| Feature | Description |
|--------|-------------|
| Employment Status | Employed / Self-employed |
| Job Stability | Stable / Unstable |

---

## 4.4 Credit Information

| Feature | Description |
|--------|-------------|
| Credit History | Past repayment behavior (0/1) |
| Previous Defaults | Number of defaults |
| Bank Account Activity | Transaction behavior |

---

# 5. Target Variables

## 5.1 Eligibility Target

| Value | Meaning |
|------|--------|
| Yes | Eligible for loan |
| No | Not eligible |

---

## 5.2 Loan Approval Target

| Value | Meaning |
|------|--------|
| Approved | Loan approved |
| Rejected | Loan rejected |

---

## 5.3 Risk Target

| Value | Meaning |
|------|--------|
| Low Risk | Safe borrower |
| Medium Risk | Moderate risk |
| High Risk | High chance of default |

---

# 6. Data Preprocessing Steps

Before training ML models, the dataset undergoes preprocessing:

---

## 6.1 Handling Missing Values
- Numerical columns → filled using mean/median  
- Categorical columns → filled using mode  

---

## 6.2 Encoding Categorical Data
ML models require numerical input:

- Gender → 0/1  
- Education → 0/1  
- Employment → Label Encoding  

---

## 6.3 Feature Scaling
Used for numerical stability:

- StandardScaler or MinMaxScaler applied to:
  - Income
  - Loan Amount
  - Debt ratio

---

## 6.4 Feature Engineering

New features created:

- Debt-to-Income Ratio  
- Income per dependent  
- Loan-to-Income Ratio  

---

## 6.5 Outlier Handling
- Extreme income or loan values are clipped or removed

---

# 7. Feature Selection

Not all features are used in all models.

### Example:

| Model | Features Used |
|------|--------------|
| Eligibility | Basic demographic + income |
| Approval | Financial + credit history |
| Risk | Full feature set |

Techniques used:
- Correlation analysis  
- Feature importance (Random Forest / XGBoost)  
- Recursive Feature Elimination (RFE)  

---

# 8. Dataset Splitting

Dataset is divided into:

- Training Set → 80%  
- Testing Set → 20%  

Used to evaluate model generalization.

---

# 9. Data Quality Considerations

To ensure good ML performance:

- No duplicate records  
- No inconsistent categorical values  
- Balanced class distribution (or handled using SMOTE if needed)  
- Cleaned missing and noisy data  

---

# 10. Challenges in Dataset

- Real-world loan datasets are highly imbalanced  
- Credit risk labels may be subjective  
- Missing financial history is common  
- Bias in demographic features must be controlled  

---

# 11. Output Labels Summary

| Model | Output |
|------|--------|
| Eligibility Model | Eligible / Not Eligible |
| Approval Model | Approved / Rejected |
| Risk Model | Low / Medium / High Risk |

---

# 12. Conclusion

The dataset serves as the foundation of the Smart Loan Intelligence System. Proper preprocessing, feature engineering, and selection ensure that the machine learning models can make accurate, fair, and reliable predictions for loan decision-making.

---
