# Reproducibility Guide

## Recommended software environment

The manuscript-linked environment is based on:

- Python 3.11
- NumPy 2.4.4
- Pandas 3.0.2
- scikit-learn 1.8.0
- XGBoost 3.2.0
- TensorFlow 2.21.0
- SHAP 0.51.0
- Joblib 1.5.3

Notebook 02 exports runtime software and hardware metadata after execution. Those generated files should be treated as the final source of truth for the exact experiment run used in the manuscript.

## Run order

1. Notebook 01 generates the synthetic dataset and generator audit files.
2. Notebook 02 trains/compares models and runs validation, learning-curve, prevalence, structural, calibration, and class-weight analyses.
3. Notebook 03 loads the selected model and calibration artifacts for constrained scenario sensitivity.
4. Notebook 04 performs held-out XAI and synthetic-ground-truth comparison.

## Randomness

Baseline seed is 42. Additional holdout seeds 52 and 62 are used for stability checks. TensorFlow and NumPy/Python random seeds are set where applicable.

## Large artifacts

The 500,000-row synthetic CSV and fitted model files may exceed normal GitHub size limits. Do not commit them directly. Use Zenodo for archival release and link the DOI from the repository.

## Re-running the publication experiment

Run the notebooks from a clean clone and retain the generated `FINAL_*.csv` and `FINAL_*.json` artifacts used to populate the manuscript. If results are regenerated with changed dependency versions, record that as a new release rather than silently replacing the archived publication version.
