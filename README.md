# nih-grant-activity-classifier
Predict NIH grant activity series (F/T/K/R) from funding &amp; duration signals (FY18–FY23, 118k+ records).

# NIH Grant Activity Classifier (F/T/K/R)

Predict NIH grant activity series (F/T/K/R) from funding & duration signals using NIH RePORTER data (FY18–FY23, 118k+ records).

## What this does
Given basic award attributes (e.g., total cost, grant length), the model predicts the activity series:
- F: Fellowship
- T: Training
- K: Career Development
- R: Research

## Data
NIH RePORTER (public), FY2018–FY2023.

## Results (baseline)
Best model: Histogram-based Gradient Boosting, ~0.93 validation score (benchmark vs. Decision Tree / MLP / Logistic Regression).

## Repo contents
- `slides/` final presentation
- `notebooks/` original experimentation notebook

## Roadmap
- Refactor notebook into reproducible training/inference scripts
- Add a minimal demo (Streamlit) + short report
- Improve features and evaluation (macro-F1, imbalance handling)
