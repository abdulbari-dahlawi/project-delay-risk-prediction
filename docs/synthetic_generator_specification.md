# Synthetic Generator Specification

## Baseline settings

- Records: 500,000
- Seed: 42
- Target noise: Gaussian, SD = 0.45
- Binary target: median threshold of synthetic probability, deliberately producing an approximately 50/50 benchmark
- Risk categories: one-third and two-thirds quantiles of the synthetic probability

The class balance is **artificial** and must not be interpreted as real-world project-delay prevalence.

## Important evidence classification

No numeric generator parameter was estimated from real Saudi, Vision 2030, or organizational project records. Predictor *directions* are literature-informed where stated in the manuscript; numeric distributions, clipping ranges, category probabilities, coefficient magnitudes, and thresholds are researcher-defined simulation settings unless a cited source directly supports a specific value.

Notebook 01 exports publication-ready audit tables:

- `FINAL_generation_specification_with_rationale.csv`
- `FINAL_target_coefficient_rationale.csv`
- `FINAL_target_rule_rationale.csv`
- `FINAL_post_target_generation_specification.csv`
- `FINAL_alternative_structural_generator.json`
- `FINAL_artificial_prevalence_note.json`

## Core deterministic dependencies

- `Complexity_Score`: Low=1, Medium=2, High=3, Mega=4
- `Approval_Duration_Days = Authorities_Involved × Approval_Per_Authority_Days`
- `External_Risk_Score = 0.27×Weather + 0.30×Permit + 0.22×Inflation + 0.21×Site + 1.5×Force_Majeure`, clipped to 1–10

Several variables are generated conditionally on complexity, including planned duration, planned budget, design changes, change requests, procurement lead time, and safety incidents.

## Continuous target equation

The latent score is:

```text
z = -2.40
    + 0.34*Complexity_Score
    + 0.015*(Planned_Duration_Days/10)
    + 0.020*log1p(Planned_Budget_Million)
    + 0.10*Design_Change_Count
    + 0.09*Change_Request_Count
    + 0.012*Approval_Duration_Days
    + 0.012*Procurement_Lead_Time_Days
    + 0.018*Payment_Delay_Days
    + 0.11*External_Risk_Score
    + 0.06*Quality_Defect_Rate
    + 0.18*Safety_Incident_Count
    - 0.12*Scope_Clarity_Score
    - 0.10*Stakeholder_Communication_Score
    - 0.09*Coordination_Score
    - 0.08*Contractor_Experience_Score
    - 0.08*Resource_Availability_Score
    - 0.07*Labor_Productivity_Score
    - 0.06*Equipment_Availability_Score
    - 0.06*Supplier_Reliability_Score
    - 0.06*Contractor_Financial_Stability
    - 0.05*Owner_Decision_Speed_Score
    - 0.035*Schedule_Buffer_Percent
    - 0.18*BIM_Adoption_Level
    - 0.12*AI_Tools_Adoption_Level
    + Rule_Score
    + epsilon
```

where `epsilon ~ Normal(0, 0.45^2)`.

The continuous synthetic probability is `p = 1/(1 + exp(-z))`.

## Interaction rules

The baseline generator adds/subtracts the following exact rule contributions:

1. `+0.85` if `Authorities_Involved > 4` and `Approval_Duration_Days > 35`
2. `+0.90` if `Design_Change_Count >= 5` and `Scope_Clarity_Score < 6`
3. `+0.80` if `Stakeholder_Communication_Score < 5` and `Coordination_Score < 5`
4. `+0.65` if `Resource_Availability_Score < 5` or `Labor_Productivity_Score < 5`
5. `+0.70` if `Supplier_Reliability_Score < 5` and `Procurement_Lead_Time_Days > 45`
6. `+0.75` if `Contractor_Financial_Stability < 5` and `Payment_Delay_Days > 20`
7. `+0.95` if `External_Risk_Score > 7` or `Force_Majeure_Flag == 1`
8. `+0.65` if `Schedule_Buffer_Percent < 5` and `Complexity_Score >= 3`
9. `-0.45` if `BIM_Adoption_Level >= 2` and `Coordination_Score >= 7`
10. `-0.35` if `AI_Tools_Adoption_Level >= 2` and `Project_Manager_Experience_Years >= 8`
11. `-0.35` if `Schedule_Buffer_Percent >= 12` and `Scope_Clarity_Score >= 7`

These rule magnitudes and thresholds are simulation assumptions, not estimated population effects.

## Leakage exclusions

The following are excluded from model predictors:

- `Project_ID`
- `Delayed`
- `Delay_Risk_Level`
- `Delay_Probability_True`
- `Actual_Duration_Days`
- `Time_Overrun_Percent`
- `Rule_Score`

## Post-target fields

`Actual_Duration_Days` and `Time_Overrun_Percent` are generated after the synthetic target and are descriptive only; they are never used for training.
