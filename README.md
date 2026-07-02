# Credit Risk Explainer

An end-to-end credit risk pipeline: model comparison (Logistic Regression vs.
XGBoost) → SHAP-based explainability → LLM-generated plain-English explanations
→ drift monitoring → FastAPI backend → frontend → deployment.

Built on the Kaggle ["Give Me Some Credit"](https://www.kaggle.com/c/GiveMeSomeCredit)
dataset (predicting the probability a borrower will experience serious
delinquency in the next two years).

## Status

Work in progress. Current stage: baseline modeling + SHAP explainability
(see `notebooks/credit_risk.ipynb`).

## Roadmap

- [x] EDA, cleaning, stratified train/test split
- [x] Baseline models: Logistic Regression + XGBoost, evaluated on AUC / KS / classification report
- [x] SHAP explainability (TreeExplainer, summary plot)
- [ ] LLM explanation layer (turn SHAP output into plain-English risk explanations)
- [ ] Drift monitoring
- [ ] FastAPI backend serving predictions + explanations
- [ ] Frontend
- [ ] Deployment

## Project structure

```
credit-risk-explainer/
├── data/
│   └── raw/          # Kaggle source files (gitignored — see Data section)
├── notebooks/         # exploratory + modeling notebooks
├── src/                # reusable pipeline code (in progress)
└── README.md
```

## Data

Raw data isn't committed to this repo (see `.gitignore`). To reproduce:

1. Download the dataset from the [Kaggle competition page](https://www.kaggle.com/c/GiveMeSomeCredit/data).
2. Place `cs-training.csv`, `cs-test.csv`, `sampleEntry.csv`, and
   `Data Dictionary.xls` into `data/raw/`.

Note: `cs-test.csv` is Kaggle's unlabeled competition test set, used only for
submission scoring — it's not used for local model evaluation. Evaluation here
uses a held-out split from `cs-training.csv`.

## Setup

_TODO: add environment/dependency setup once `src/` and requirements are in place._
