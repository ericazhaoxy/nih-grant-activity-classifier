# NIH Grant Activity Classifier

Predict NIH grant activity series (F/T/K/R) from structured award signals (e.g., total cost and grant length) using NIH RePORTER data (FY2018–FY2023, 118k+ records).

**Status:** Portfolio version (report published; reproducible pipeline + demo in progress)  
**Slides / full notebook:** Available upon request

## Why this matters

NIH awards include an **Activity** code (e.g., R01, K08, T32).  
This project frames a **multi-class classification** problem to infer the **activity series**:

- **F**: Fellowship
- **T**: Training
- **K**: Career Development
- **R**: Research

## Data

- Source: NIH RePORTER (public)
- Window: FY2018–FY2023
- Scale: 118,355 records (after filtering/alignment)

## Baseline results

Best baseline: **Histogram-based Gradient Boosting (~0.93 validation score)**  
Benchmarked against: Decision Tree, MLP, Logistic Regression.

## Project report

- See: [`reports/report.md`](reports/report.md)

## Repository structure (WIP)

- `reports/` short write-up
- `assets/` figures and screenshots (coming)
- `src/` training / inference scripts (coming)
- `app/` minimal demo (coming)

## Roadmap

- Add stronger features (e.g., IC/Institute, FY, direct vs indirect costs)
- Evaluate with macro-F1; handle class imbalance
- Add explainability (feature importance / SHAP)
- Ship a minimal demo (Streamlit) and/or API (FastAPI)

## License

MIT
