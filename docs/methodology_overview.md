# Methodology Overview

## Study type

Quantitative synthetic-data proof of concept for project-delay risk prediction and decision-support methodology.

## Workflow

1. Generate 500,000 synthetic project records.
2. Create continuous synthetic delay probability and binary/multiclass labels.
3. Remove direct leakage and post-outcome fields.
4. Preprocess numerical/categorical predictors.
5. Compare five classical ML models plus one MLP.
6. Perform internal validation and robustness analyses.
7. Assess probability calibration.
8. Explain model behavior with permutation importance and SHAP.
9. Compare explanation rankings with the known synthetic generating mechanism.
10. Run constrained scenario-based sensitivity analysis.

## Interpretation boundary

The generator intentionally embeds predictor relationships in the target. Removing target-derived variables prevents **direct leakage**, but does not eliminate **structural circularity**. Therefore, high predictive performance partly reflects recovery of the synthetic generating structure. Cross-validation, multiple seeds, prevalence sensitivity, structural stress tests, and distribution-shift tests characterize internal behavior; they do not establish external validity.

The scenario engine is a model-based sensitivity tool. It does not estimate causal treatment effects, implementation cost, or guaranteed real-world delay reduction.
