# Report — NIH Grant Activity Classifier (F/T/K/R)

## 1. Motivation

Predict NIH grant activity series (F/T/K/R) from structured award signals (e.g., total cost and grant length) to support portfolio and pipeline analysis.

## 2. Data

NIH RePORTER (public), FY2018–FY2023, 118k+ records (after filtering/alignment).

## 3. Labeling

Map each award's Activity code to its series label using the first character: F / T / K / R.

## 4. Features & Preprocessing (baseline)

- Features: total cost, grant length
- Mean imputation for missing values (baseline)
- Align schema across fiscal years; drop non-uniform fields

## 5. Modeling & Results

Benchmarked multiple tabular models.
Best baseline: Histogram-based Gradient Boosting (~0.93 validation score).

## 6. Error Analysis (next)

Planned: confusion matrix, slice analysis by funding/length buckets, review misclassified examples.

## 7. Limitations

Limited feature set, potential class imbalance, validation strategy to be strengthened.

## 8. Roadmap

Add richer features, macro-F1 + imbalance handling, explainability, refactor into scripts + demo.
