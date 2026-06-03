# TRD.md — Smart Loan Intelligence System 

---

# 1. Project Overview

The Smart Loan Intelligence System is a Machine Learning-based decision support platform designed to automate and improve loan assessment processes. The system analyzes applicant information and provides intelligent recommendations through three predictive modules:

1. Loan Eligibility Prediction
2. Loan Approval Prediction
3. Credit Risk Classification

The platform aims to assist financial institutions in making faster, consistent, and data-driven lending decisions.

---

# 2. Scope

### Included

* Eligibility prediction
* Loan approval prediction
* Credit risk analysis

### Excluded

* Real-time banking API integration
* Online payment processing
* Credit bureau integration
* Automated loan disbursement

---

# 3. Technology Requirements

| Component        | Technology                  |
| ---------------- | --------------------------- |
| Frontend         | React.js                    |
| UI Design        | HTML5, CSS3, JavaScript     |
| Backend          | Flask (Python)              |
| Machine Learning | Scikit-Learn, Pandas, NumPy |
| Database         | PostgreSQL                  |
| API Format       | REST API (JSON)             |
| Authentication   | JWT                         |
| Version Control  | Git & GitHub                |
| Deployment       | Docker, Render/AWS          |

---

# 4. System Architecture

User Interface (React)

↓

REST API Requests

↓

Flask Backend

↓

Machine Learning Models

↓

Backend sends results to frontend

---

# 5. Functional Requirements

## FR-01 Loan Eligibility Prediction

### Purpose

Determine whether an applicant meets the minimum loan eligibility criteria.

### Input Features

* Age
* Income
* Employment Status
* Education
* Credit History
* Loan Amount

### Output

* Eligible
* Not Eligible

---

## FR-02 Loan Approval Prediction

### Purpose

Predict whether a loan application should be approved.

### Output

* Approved
* Rejected

---

## FR-03 Credit Risk Assessment

### Purpose

Classify borrowers based on repayment risk.

### Output Categories

* Low Risk
* Medium Risk
* High Risk

---

# 6. Data Preprocessing Requirements

The system shall perform:

* Missing value handling
* Duplicate removal
* Outlier treatment
* Label encoding
* Feature scaling
* Data validation

---

# 7. Machine Learning Requirements

## Model 1 – Eligibility Prediction

### Type

Binary Classification

### Target

Eligible / Not Eligible

### Candidate Algorithms

* Logistic Regression
* Decision Tree
* Random Forest

---

## Model 2 – Loan Approval Prediction

### Type

Binary Classification

### Target

Approved / Rejected

### Candidate Algorithms

* Random Forest
* XGBoost
* Gradient Boosting

---

## Model 3 – Credit Risk Modelling

### Type

Multi-Class Classification

### Target

* Low Risk
* Medium Risk
* High Risk

### Candidate Algorithms

* Random Forest
* XGBoost
* Neural Networks

---

# 8. Model Evaluation Requirements

## Binary Classification Metrics

* Accuracy
* Precision
* Recall
* F1 Score

## Multi-Class Metrics

* Accuracy
* Macro F1 Score
* Confusion Matrix
* Classification Report

### Acceptance Criteria

Minimum model accuracy:

85% or higher

---


## Prediction APIs

### POST /api/predict/eligibility

Returns eligibility prediction.

### POST /api/predict/approval

Returns approval prediction.

### POST /api/predict/risk

Returns risk classification.

---


# 9. Database Requirements

## Loan Applications Table

| Field             | Type      |
| ----------------- | --------- |
| application_id    | SERIAL    |
| user_id           | INT       |
| income            | NUMERIC   |
| loan_amount       | NUMERIC   |
| employment_status | VARCHAR   |
| application_date  | TIMESTAMP |

---

## Predictions Table

| Field           | Type      |
| --------------- | --------- |
| prediction_id   | SERIAL    |
| application_id  | INT       |
| eligibility     | VARCHAR   |
| approval        | VARCHAR   |
| risk_level      | VARCHAR   |
| prediction_date | TIMESTAMP |

---

# 10. Non-Functional Requirements

## Performance

The system shall provide prediction results with minimal delay.

Requirements:

* Prediction response time shall be less than 3 seconds.
* The system shall process user inputs and display results in real-time.
* The frontend shall remain responsive during prediction generation.

---

## Accuracy

The Machine Learning models shall provide reliable predictions.

Requirements:

* Eligibility prediction accuracy should be at least 85%.
* Loan approval prediction accuracy should be at least 85%.
* Credit risk classification should achieve acceptable precision and recall scores.
* Model performance shall be evaluated using standard ML metrics.
---
## Reliability

The system shall consistently generate predictions without failure.

Requirements:

* Valid input data shall always produce prediction results.
* The system shall handle invalid or incomplete inputs gracefully.
* Prediction APIs shall return appropriate error messages when failures occur.

# 11. Deployment Requirements

## Development Environment

* Python 3.12+
* Node.js 20+
* Git

## Production Environment

* Ubuntu Linux
* Docker
* Gunicorn
* Nginx
* PostgreSQL

---

# 12. Testing Requirements

## Backend Testing

* Unit Testing
* API Testing
* Database Testing

## Machine Learning Testing

* Cross Validation
* Hyperparameter Tuning
* Performance Evaluation

## Frontend Testing

* Form Validation
* Responsive Testing
* Integration Testing

---

# 13. Deliverables

### Software Deliverables

* React Frontend
* Flask Backend
* Trained ML Models

### Documentation Deliverables

* Technical Requirements Document
* Software Requirements Specification
* API Documentation
* User Manual

### Model Deliverables

* eligibility_model.pkl
* approval_model.pkl
* risk_model.pkl

---

# 14. Success Criteria

The Smart Loan Intelligence System shall be considered successful if:

* Eligibility prediction accuracy ≥ 85%.
* Approval prediction accuracy ≥ 85%.
* Risk classification achieves acceptable precision and recall.
* Complete integration of Frontend, Backend, Machine Learning, and Database components.
* End-to-end loan assessment workflow operates successfully.

