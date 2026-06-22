# Cat Adoption Outcome Prediction
**Predicting shelter outcomes for cats using machine learning on 79,000+ intake records**

---

## Overview

Animal shelters make daily decisions about resource allocation, medical care, 
and promotional efforts — often without a clear picture of which animals are 
most at risk of poor outcomes. This project uses intake and outcome data from 
the Austin Animal Center to identify the factors most strongly associated with 
whether a cat is adopted, returned to owner, or euthanized.

Two classification models were built and compared: multinomial logistic 
regression for interpretability and random forest for predictive performance. 
The goal was to surface actionable insights that shelter staff could use to 
improve live-release rates.

---

## Key Findings

- The random forest model achieved 91.4% accuracy and a Macro-F1 of 0.783, 
  outperforming logistic regression (89.3% accuracy, Macro-F1 0.731)
- Length of stay, intake condition, and age were the strongest predictors of outcome
- Kittens had the highest adoption rates; senior cats and cats with medical 
  conditions faced significantly worse outcomes
- Cats that arrived already spayed or neutered moved to adoption faster

---

## Business Recommendations

| Finding | Recommended Action |
|---|---|
| Seniors and medical cats have worse outcomes | Prioritize foster recruitment and targeted promotion for these groups |
| Kittens and altered cats adopt faster | Fast-track surgeries, photos, and listings for highest-probability adopters |
| Long shelter stays predict poor outcomes | Assess intake condition early to allocate resources before stays extend |

---

## Dataset

Source: Kaggle - Austin Animal Center Shelter Intakes and Outcomes
https://www.kaggle.com/datasets/aaronschlegel/austin-animal-center-shelter-intakes-and-outcomes

~79,000 animal records filtered to cats only. Key fields used:
- Age at intake (parsed into days, grouped into life stages)
- Intake type and intake condition
- Spay/neuter status at intake
- Length of stay (calculated from intake to outcome date)
- Outcome type (simplified to: Adoption, Return to Owner, Euthanasia)

---

## Methods

Two models were trained and evaluated:

Multinomial Logistic Regression
- Interpretable coefficients for each predictor
- Accuracy: 89.3% | Macro-F1: 0.731

Random Forest Classifier
- Captures non-linear interactions between features
- Feature importance used to rank predictors
- Accuracy: 91.4% | Macro-F1: 0.783

Both models were evaluated using accuracy and Macro-F1 to account for 
class imbalance across outcome categories.

Note: Length of stay is partially shaped by events that happen after intake, 
so its predictive power should be interpreted carefully. Results are 
associative, not causal.

---

## Tech Stack

- Python: pandas, numpy, scikit-learn, matplotlib
- Models: RandomForestClassifier, LogisticRegression (sklearn pipelines)
- Evaluation: accuracy score, classification report, Macro-F1

---

## Repository Structure

cat-adoption-outcomes/
├── notebooks/
│   └── cat-adoption-analysis.ipynb
├── presentation/
│   └── cat-adoption-outcomes-presentation.pptx
├── figures/
├── artifacts/
├── data/
│   └── README.md
├── requirements.txt
└── README.md

---

## About

Built as a graduate capstone project for the M.S. Data Analytics program 
at Western Governors University (2025).
