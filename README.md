# Kaggle Intermediate Machine Learning

This repo contains my notes and hands-on notebooks from Kaggle's **Intermediate Machine Learning** course, worked on the Melbourne Housing and AER Credit Card datasets.

## Topics Covered

- **Missing Values** — Imputation strategies (`SimpleImputer`) for numeric and categorical columns, including the "missing value indicator" extension approach
- **Categorical Variables** — One-Hot Encoding vs Ordinal Encoding, and when to use each
- **Pipelines** — Bundling preprocessing (`ColumnTransformer`) and modeling (`Pipeline`) into a single, reusable object
- **Cross-Validation** — Why a single train/valid split can be misleading, and how k-fold CV gives a more reliable estimate of model quality
- **XGBoost** — Gradient boosting fundamentals: sequential tree building, `learning_rate`, `n_estimators`, and early stopping
- **Data Leakage** — Identifying and removing target leakage (e.g. the `expenditure` feature in the credit card dataset) and train-test contamination

## Key Takeaways

- Always `fit()` on training data only, and `transform()` (never re-fit) on validation/test data — refitting on combined data causes train-test contamination.
- A feature is leaky if its value could only exist *after* the outcome is already known — verify with the data itself, not just the column name.
- Pipelines reduce bugs significantly: they remove the need to manually track train/valid transformations step by step.
- Cross-validation gives more trustworthy comparisons between modeling choices (imputation strategy, encoding, hyperparameters) than a single split.

## Tools & Libraries

`pandas` · `scikit-learn` · `XGBoost`

## Next Steps

Applying these techniques to the Titanic competition (classification) next.

---
*Part of my self-directed path toward becoming a Machine Learning Engineer.*
