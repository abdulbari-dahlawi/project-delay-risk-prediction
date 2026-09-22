# GitHub / Zenodo Release Checklist

- [ ] Confirm author names and affiliations.
- [ ] Confirm repository title.
- [ ] Confirm code license and data/documentation license with both authors/institution.
- [ ] Replace `YOUR_GITHUB_USERNAME` placeholders.
- [ ] Run all four notebooks cleanly in order.
- [ ] Confirm all expected `FINAL_` outputs are generated.
- [ ] Run `python scripts/validate_repository.py`.
- [ ] Verify that no confidential, real organizational, Saudi, or Vision 2030 project data are present.
- [ ] Verify that no reviewer comments or private manuscript drafts are accidentally committed.
- [ ] Push to GitHub.
- [ ] Create GitHub Release `v1.0.0`.
- [ ] Connect the GitHub repository to Zenodo and archive the release.
- [ ] Add Zenodo DOI to `README.md`, `CITATION.cff`, `.zenodo.json`, and the manuscript Data/Code Availability statements.
- [ ] Add repository URL/DOI and license to the manuscript.
- [ ] Freeze the version used for journal submission.
