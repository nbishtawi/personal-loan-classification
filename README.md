# Personal Loan Classification (AIML)

## Overview
This project predicts whether a banking customer will accept a **personal loan offer** based on demographic, financial, and product-usage attributes. The dataset contains 5,000 customer records with 14 variables. The task helps financial institutions target likely customers, reduce marketing costs, and optimize campaign effectiveness.

---

## Goals
- Predict the probability that a customer will accept a personal loan  
- Balance accuracy with interpretability for business use  
- Identify customer characteristics most associated with loan acceptance  

---

## Methodology

### 1) Data Preparation
- Loaded structured data from `Loan_Modelling.csv`
- Target: `Personal_Loan` (1 = accepted, 0 = not accepted)
- Features include demographics (`Age`, `Experience`, `Family`, `Education`), financials (`Income`, `Mortgage`, `CCAvg`), and banking products (`Securities_Account`, `CD_Account`, `Online`, `CreditCard`)
- Train/test split using `train_test_split`

### 2) Modeling
- Baselines and tuned models:
  - **Logistic Regression** (interpretable baseline)
  - **Decision Tree Classifier** (non-linear segmentation)
- Hyperparameter tuning via **GridSearchCV**
- Threshold tuning for Logistic Regression to improve recall/F1

### 3) Evaluation
- Reported **Accuracy**, **Precision**, **Recall**, **F1-score** on the test set
- Reviewed feature importance / coefficients for interpretability

---

## Repository Structure
```
Personal-Loan-Classification/
├── loan_classification.ipynb # Main notebook (rename from LoanModellingClassificationProject.ipynb)
├── Loan_Modelling.csv # Dataset
└── README.md # Project documentation
```

---

## Dataset
- Rows: 5,000
- Columns: 14
- Target: `Personal_Loan`
- Feature highlights: `Income`, `CCAvg` (avg credit card spend), `Education`, `Family`, `Mortgage`, `Online`, `CD_Account`, `Securities_Account`, `CreditCard`

---

## Results
- **Final model:** Logistic Regression (with threshold tuning)
- **Test set performance:**
  - Accuracy: **0.913**
  - Recall: **0.805**
  - Precision: **0.541**
  - F1-score: **0.647**

**Key drivers of acceptance (directionally from model analysis):**
- Higher **Income** and **CCAvg** → more likely to accept
- **Education** level positively associated with acceptance
- Ownership of **CD Account** correlated with higher acceptance
