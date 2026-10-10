# Student Performance Analysis and Grade Prediction

**Prepared for:** BharatiCares Certificate Verification  
**Prepared by:** Shashwat Pandey  
**Project type:** Exploratory Data Analysis (EDA) + introductory machine learning  
**Language:** Python

## Overview
This project explores the UCI Student Performance dataset and predicts the final mathematics grade (`G3`) using a Random Forest regressor. It includes data-quality checks, visualisations, a mean baseline, and held-out test metrics (MAE, RMSE, and R²).

## Dataset
- Canonical source: UCI Machine Learning Repository, [Student Performance](https://archive.ics.uci.edu/dataset/320/student+performance)
- File used: `student-mat.csv` (mathematics subject; 395 rows in the source dataset)
- The notebook downloads the official UCI ZIP archive first. If unavailable, it attempts a public mirror; you can also download the CSV manually from the UCI page and put it next to the notebook.
- The source data was collected from two Portuguese schools. It may not represent other school systems.

## Files
- `ShashwatPandey_StudentPerformanceAnalysis.ipynb` — full notebook and analysis
- `requirements.txt` — Python dependencies
- `ShashwatPandey_StudentPerformanceReport.docx` — project report

## Setup and run
Recommended: Python 3.10 or newer.

```bash
python -m venv .venv
```

Activate the environment:
- Windows: `.venv\Scripts\activate`
- macOS/Linux: `source .venv/bin/activate`

Install dependencies:
```bash
python -m pip install -r requirements.txt
```

Launch Jupyter:
```bash
jupyter notebook
```
Open `ShashwatPandey_StudentPerformanceAnalysis.ipynb` and choose **Run All**. Internet access is needed to download the dataset, unless you have placed `student-mat.csv` beside the notebook.

## Reproducibility
- Random seed: `42`
- Test size: `20%`
- Model: `RandomForestRegressor(n_estimators=300, min_samples_leaf=2)`
- Baseline: `DummyRegressor(strategy="mean")`
- Metrics: MAE, RMSE, and R², calculated at runtime on the held-out test set.

Metrics are deliberately not hard-coded into this README; use the output produced by running the notebook. Minor numerical differences can occur across library versions.

## Interpretation and responsible use
The model is for learning and demonstration only, not for admissions, grading, discipline, or other high-stakes decisions. Correlation is not causation. The model uses `G1` and `G2` (earlier-period grades), so it is not a pure early-term predictor. Remove these features and re-evaluate if the goal is to predict before prior grades are available.

## Suggested submission checklist
- [ ] Run all notebook cells successfully.
- [ ] Read the actual metric values and write 2–3 observations based on the plots/results.
- [ ] Confirm your name and project title match the submission instructions.
- [ ] Submit the notebook, `requirements.txt`, this README, and the report.
