# Explainable Project Delay Risk Prediction with Synthetic Data

Reproducibility package for a **synthetic-data proof-of-concept framework** that combines project-delay risk prediction, internal robustness testing, probability calibration, explainable AI, and constrained scenario-based sensitivity analysis.

> **Scope statement**  
> This repository does **not** contain real Saudi, Saudi Vision 2030, or organizational project records. The 500,000 project records are synthetic. Numerical distributions, category probabilities, clipping ranges, coefficients, thresholds, and interaction magnitudes are simulation settings unless explicitly supported by a cited source. 

## Authors

- **Abdulbari Othman Dahlawi** — study design, methodology, software, synthetic-data generation, analysis, visualization, manuscript drafting. ORCID: `0009-0009-5293-5901`
- **Khaled Shaban** — academic supervision, methodological review, critical manuscript review; corresponding author for the associated manuscript.

## Repository contents

```text
project-delay-risk-prediction/
├── README.md
├── CITATION.cff
├── .zenodo.json
├── .gitignore
├── .project-root
├── requirements.txt
├── environment.yml
├── CHANGELOG.md
├── CONTRIBUTING.md
├── RELEASE_CHECKLIST.md
├── notebooks/
│   ├── 01_generate_synthetic_dataset.ipynb
│   ├── 02_train_validate_models.ipynb
│   ├── 03_scenario_decision_support.ipynb
│   └── 04_explainable_ai.ipynb
├── docs/
│   ├── methodology_overview.md
│   ├── synthetic_generator_specification.md
│   ├── model_configuration.md
│   ├── reproducibility.md
│   ├── reviewer_comment_mapping.md
│   ├── github_zenodo_release_guide.md
│   └── artifact_manifest.md
├── data/
│   ├── README.md
│   └── new_project_template.csv
├── models/
│   └── README.md
├── results/
│   └── README.md
└── project_delay_outputs/
    └── README.md
    
```

## Main methodological components

1. **Transparent synthetic-data generation**  
   The generator creates 500,000 synthetic project scenarios from explicit probability distributions, deterministic dependencies, continuous target terms, interaction rules, Gaussian target noise, and an artificial prevalence threshold.

2. **Six predictive models**  
   Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, XGBoost, and a deep-learning multilayer perceptron (MLP).

3. **Internal validation and robustness analysis**  
   Includes a stratified 80/20 holdout, 5-fold cross-validation, multiple random seeds, learning curves, prevalence sensitivity, class-weight sensitivity, rule ablation, structural-generator stress testing, fresh/noisier target generation, and distribution shift.

4. **Probability calibration**  
   The model workflow reports Brier score and calibration-curve data, including calibration under distribution shift, because downstream scenario analysis compares predicted probabilities.

5. **Explainable AI**  
   Held-out permutation importance, model-native importance, SHAP, agreement between explanation methods, and comparison against the known synthetic data-generating mechanism.

6. **Scenario-based decision support**  
   Eleven constrained hypothetical actions are evaluated as **model-based sensitivity analysis**, not causal recommendations. Sensitivity to action magnitude and budget/duration constraints is also evaluated.

## Quick start

### Option A — Conda

```bash
conda env create -f environment.yml
conda activate project-delay-publication
jupyter lab
```

Run the notebooks in this order:

```text
01_generate_synthetic_dataset.ipynb
02_train_validate_models.ipynb
03_scenario_decision_support.ipynb
04_explainable_ai.ipynb
```

### Option B — pip

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

python -m pip install --upgrade pip
pip install -r requirements.txt
jupyter lab
```


Executed notebook copies are written to `executed_notebooks/`; research outputs are written to `project_delay_outputs/`.

## Output structure

Running the notebooks creates:

```text
project_delay_outputs/
├── data/      # synthetic dataset, data dictionary, generator audit artifacts
├── models/    # fitted pipelines/calibration artifacts/model metadata
├── results/   # FINAL_*.csv/json, model comparisons, validation and XAI outputs
└── plots/     # figures produced by the scenario engine
```



## Reproducibility notes

- Baseline random seed: **42**
- Additional holdout seeds: **52, 62**
- Baseline simulated records: **500,000**
- Baseline target noise SD: **0.45**
- Baseline binary class balance is intentionally created using a median probability threshold; it is **not** an estimate of real-world delay prevalence.
- Target-derived and post-outcome fields are excluded from training to avoid direct leakage; structural circularity remains because retained predictors participate in synthetic target generation.


## Data and code availability

The synthetic dataset is generated entirely by Notebook 01 and can be regenerated from the source code. 



