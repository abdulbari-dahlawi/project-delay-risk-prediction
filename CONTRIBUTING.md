# Contributing

This repository accompanies an academic reproducibility package.

1. Open an issue describing the proposed change.
2. Do not commit generated 500,000-row datasets or trained binary model files directly to Git.
3. Preserve the synthetic-only scope statement and non-causal interpretation of scenario results.
4. Use deterministic seeds where applicable and document any changed data-generating assumptions.
5. Run `python scripts/validate_repository.py` before creating a pull request.

For manuscript-linked changes, record the affected notebook, output artifact, and manuscript section.
