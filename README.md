# Term Deposit Prediction -- Data Analytics

End-to-end data analytics project predicting whether a bank client will subscribe to a term deposit product. Full pipeline from raw data through to business-level interpretation of results, with every decision documented and justified.

---

## What this demonstrates

This project is deliberately not just a notebook that runs a model. It follows the workflow a data analyst or analytics engineer uses in practice:

1. Understand the business question before touching the data
2. Explore the data to find what actually predicts the outcome
3. Engineer features that encode domain knowledge
4. Select and evaluate models with the right metrics for the problem
5. Interpret results in terms the business can act on

---

## The business question

A bank runs outbound marketing campaigns for term deposit subscriptions. Each call costs money. The goal is to predict which clients are most likely to subscribe so the campaign can be targeted at high-probability clients, reducing cost per acquisition.

---

## Pipeline

```
Raw Data (banking_full.csv)
    |
    v
Exploratory Data Analysis
  - Class imbalance analysis
  - Feature correlation heatmap
  - Distribution plots by subscription outcome
  - Missing value audit
    |
    v
Preprocessing Pipeline
  - Categorical encoding
  - Numerical scaling
  - Train/test split with stratification
    |
    v
Feature Engineering
  - Contact frequency features
  - Campaign outcome history
  - Economic indicator interactions
    |
    v
Model Training and Selection
  - Logistic Regression (baseline)
  - Random Forest
  - XGBoost
  - Cross-validation with stratified folds
    |
    v
Evaluation
  - ROC-AUC (primary metric -- imbalanced classes)
  - Precision-recall curve
  - Confusion matrix at business-relevant threshold
    |
    v
Business Interpretation
  - Top predictive features with business explanation
  - Threshold recommendation based on campaign economics
  - Expected reduction in campaign cost at recommended threshold
```

---

## Results summary

| Model | ROC-AUC | Notes |
|---|---|---|
| Logistic Regression | 0.78 | Strong baseline, interpretable |
| Random Forest | 0.84 | Better non-linear capture |
| XGBoost | 0.87 | Best overall performance |

At the recommended threshold, the model reduces the required call volume by approximately 40% while retaining 80% of actual subscribers in the target list.

---

## Tech stack

| Component | Technology |
|---|---|
| Data processing | pandas, NumPy |
| Modelling | scikit-learn, XGBoost |
| Visualisation | Matplotlib, Seaborn |
| Feature selection | scikit-learn SelectKBest, feature importance |
| SQL queries | SQLite (data exploration queries) |

---

## Getting started

```bash
git clone https://github.com/parthInAI/Data-Analytics-term-deposit-prediction
cd Data-Analytics-term-deposit-prediction

pip install -r requirements.txt

jupyter notebook term_deposit_prediction.ipynb
```

---

## Skills demonstrated

- Business-framed problem definition
- Exploratory data analysis on real banking data
- Feature engineering with domain reasoning
- Imbalanced classification handling
- Model selection and cross-validation
- Threshold optimisation for business objectives
- Results interpretation for non-technical stakeholders
- SQL queries for data exploration

---

## Related projects

- [Finance and Economics AI](https://github.com/parthInAI/finance-economics) — fraud, churn, trading, sentiment, bankruptcy
- [Portfolio](https://parthinai.github.io/)
