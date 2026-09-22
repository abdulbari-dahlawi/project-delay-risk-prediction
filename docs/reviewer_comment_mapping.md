# Reviewer-Comment Mapping

This document maps the major methodological revision requests to repository components.

| Comment area | Repository implementation |
|---|---|
| Learning curve / justify 500k | Notebook 02: `FINAL_xgboost_learning_curve.csv` |
| Evidence basis for generator settings | Notebook 01: `FINAL_generation_specification_with_rationale.csv` |
| Target coefficient audit | Notebook 01: `FINAL_target_coefficient_rationale.csv` |
| Interaction-rule audit / structural sensitivity | Notebooks 01–02 |
| Artificial 50/50 prevalence | Notebook 01 note + Notebook 02 prevalence sensitivity |
| Direct leakage vs structural circularity | Notebook 01 + methodology documentation |
| Public repository / environment | This GitHub package + `requirements.txt` + `environment.yml` |
| Complete classical hyperparameters | Notebook 02: `FINAL_classical_model_configuration_summary.csv` |
| MLP class weighting | Notebook 02: `FINAL_mlp_class_weight_sensitivity.csv` |
| Alternative structural generator | Notebook 01 specification + Notebook 02 transfer/retraining analysis |
| Calibration / Brier score | Notebook 02 calibration outputs and plots |
| XAI vs known synthetic ground truth | Notebook 04 generator-ground-truth comparison |
| Exact scenario-action definitions | Notebook 03: `FINAL_scenario_action_specification.csv` |
| Scenario action-magnitude sensitivity | Notebook 03: `FINAL_scenario_magnitude_constraint_sensitivity.csv` |
| XGBoost vs MLP practical equivalence | Notebook 02 paired bootstrap output; manuscript should avoid unsupported superiority language |

Editorial requests such as title revision, literature synthesis, citation verification, CRediT wording, and final Data/Code Availability text remain manuscript tasks rather than notebook tasks.
