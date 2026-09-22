# GitHub + Zenodo Release Guide

## 1. Create the GitHub repository

Recommended repository name:

`project-delay-risk-prediction`

Create it as **Private** first so you can verify all content before public release.

## 2. Upload this folder

From a terminal opened inside the repository folder:

```bash
git init
git add .
git commit -m "Initial reproducibility release"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/project-delay-risk-prediction.git
git push -u origin main
```

## 3. Validate before making it public

```bash
python scripts/validate_repository.py
```

Run all notebooks at least once in the exact publication environment. Confirm that generated outputs match the manuscript.

## 4. Create a GitHub release

Create tag/release `v1.0.0`. The release should correspond exactly to the repository version cited in the manuscript.

## 5. Connect GitHub to Zenodo

1. Sign in to Zenodo using GitHub.
2. Enable archiving for the repository.
3. Create the GitHub `v1.0.0` release.
4. Zenodo will archive the release and mint a DOI.
5. Add the DOI back into `README.md`, `CITATION.cff`, `.zenodo.json`, and the manuscript.

## 6. Recommended manuscript wording after DOI creation

**Data Availability:**  
The synthetic dataset, data dictionary, generator specification, and supporting outputs used in this study are publicly available in the project repository and archived on Zenodo at [DOI]. The dataset contains no real organizational, Saudi, or Vision 2030 project records.

**Code Availability:**  
The complete reproducible code for synthetic-data generation, preprocessing, model development, internal validation, probability calibration, explainability analysis, figures, and scenario-based sensitivity analysis is available at [GitHub URL] and archived on Zenodo at [DOI].
