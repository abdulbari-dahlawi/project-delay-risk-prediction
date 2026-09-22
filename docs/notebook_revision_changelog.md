# Notebook Revision Summary — Dr. Khaled Shaban R1 Comments

## Notebook 01 — Synthetic Data Generator
- Added evidence-basis/rationale classification for every generated predictor.
- Explicitly labels numerical distributions/ranges/probabilities as simulation choices unless externally supported.
- Added publication-ready target coefficient table with expected direction, exact value, rationale, and non-empirical status.
- Added interaction-rule rationale table.
- Added post-target variable generation specification.
- Added explicit artificial-prevalence statement.
- Added baseline missingness audit metadata.
- Added an alternative structural-generator specification for downstream robustness tests.

## Notebook 02 — Modeling, Validation, Calibration, Robustness
- Added full classical-model configuration export and tuning/selection documentation.
- Added baseline missingness audit.
- Added MLP initialization details and class-weight sensitivity analysis.
- Added paired bootstrap 95% CI for XGBoost vs MLP F1 difference.
- Added learning-curve experiment for 5k, 10k, 50k, 100k, and 500k total synthetic records.
- Added delayed-prevalence sensitivity at 20%, 30%, 40%, and 50%, including permutation-top-10 stability.
- Added rule ablation and alternative structural-generator transfer/retraining tests.
- Added Brier score and calibration-curve analysis on baseline and adverse distribution shift.
- Saves internal Platt calibration artifacts for Notebook 03.
- Generates requirements.txt, environment.yml, hardware metadata, and a public-repository manifest/template.

## Notebook 03 — Scenario-Based Decision Support
- Uses calibrated probabilities from Notebook 02 when calibration artifacts are available.
- Added full 11-action specification table: variables changed, exact numerical changes, constraints, feasibility assumptions, and evidence basis.
- Retains non-causal “model-based sensitivity analysis” framing.
- Added sensitivity tests for action magnitudes (0.5x, 1.0x, 1.5x) and budget/duration caps (5%, 10%).
- Retains evaluation on five illustrative cases and 500 high-risk synthetic projects.

## Notebook 04 — XAI
- Retains held-out permutation importance and SHAP.
- Added comparison of SHAP and permutation rankings against the known synthetic generator.
- Computes noise-free generator ground-truth sensitivity by feature permutation while preserving deterministic dependencies.
- Reports generator-vs-permutation and generator-vs-SHAP rank agreement.
- Exports direct target-term and interaction-rule participation for interpretation.

## Comments that still require non-notebook/manual work
- Create and publish the GitHub/Zenodo repository, then insert the permanent URL/DOI and license.
- Verify and strengthen literature citations and every reference entry.
- Revise title, abstract, Introduction, Literature Review/Table 1, Discussion, Conclusion, Future Work, CRediT roles, declarations, and AI-disclosure placement in the manuscript.
- Add any direct empirical sources used to support a specific real-world range/distribution; the notebooks intentionally do not invent such sources.
