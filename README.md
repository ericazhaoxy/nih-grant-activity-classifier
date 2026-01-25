# NIH Grant Activity Classifier

Multi-class classification of NIH award activity series (F/T/K/R) from structured NIH RePORTER signals.

Predict NIH grant activity series (F/T/K/R) from structured award signals (e.g., total cost and grant length) using NIH RePORTER data (FY2018–FY2023, 118k+ records).

**Best baseline:** Histogram-based Gradient Boosting  
**Validation metric:** ~0.93 **macro-F1**

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
- Repo includes: sample CSVs in `data/sample/` (full processed datasets excluded due to GitHub size limits)
- To reproduce full-scale training, download NIH RePORTER exports for FY2018–FY2023 and place the raw files under `data/raw/` (ignored by git), then run the notebook/pipeline steps.

## Baseline results

Best baseline: **Histogram-based Gradient Boosting (~0.93 macro-F1 on validation)**  
Benchmarked against: Decision Tree, MLP, Logistic Regression.

---

## Project artifacts

**Notebook:** [`notebooks/NIH_Grant_Activity_Classifier.ipynb`](notebooks/NIH_Grant_Activity_Classifier.ipynb)  
**Slides:** [`slides/NIH_Grant_Activity_Classifier_Slides.pdf`](slides/NIH_Grant_Activity_Classifier_Slides.pdf)  
**Project report:** [`reports/report.md`](reports/report.md)

## Quickstart

    python3 -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt

Open and run: `NIH_Grant_Activity_Classifier.ipynb`

---

## Repository structure

- `notebooks/` analysis + training notebook
- `src/` reusable utilities (data cleaning / feature helpers)
- `data/sample/` small sample dataset (tracked)
- `data/raw/` full dataset (NOT tracked)
- `reports/` write-up
- `slides/` presentation slides

---

## Roadmap

- Add stronger features (e.g., IC/Institute, FY, direct vs indirect costs)
- Evaluate with macro-F1; handle class imbalance
- Add explainability (feature importance / SHAP)
- Ship a minimal demo (Streamlit) and/or API (FastAPI)

### Full dataset note

This repository includes **sample CSVs** under `data/sample/`. Full processed datasets are excluded due to GitHub file size limits.  
Full-data reproduction can be done by downloading NIH RePORTER exports (FY2018–FY2023) and running the notebook to regenerate splits locally.

## License

MIT
