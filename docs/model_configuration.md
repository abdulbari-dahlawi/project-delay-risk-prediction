# Model Configuration

## Classical models

The baseline classical models are instantiated before test-set evaluation; Notebook 02 exports the complete parameter dictionaries and a publication-ready configuration table.

### Logistic Regression
- `max_iter=3000`
- `class_weight="balanced"`
- `random_state=42`
- Other parameters: scikit-learn defaults, exported at runtime

### Decision Tree
- `max_depth=None`
- `min_samples_leaf=2`
- `class_weight="balanced"`
- `random_state=42`

### Random Forest
- `n_estimators=300`
- `max_depth=None`
- `min_samples_leaf=2`
- `class_weight="balanced_subsample"`
- `random_state=42`
- `n_jobs=-1`

### Gradient Boosting
- `random_state=42`
- Other parameters: scikit-learn defaults, exported at runtime

### XGBoost
- `n_estimators=350`
- `max_depth=5`
- `learning_rate=0.05`
- `subsample=0.90`
- `colsample_bytree=0.90`
- `eval_metric="logloss"`
- `random_state=42`
- `n_jobs=-1`

## Deep-learning MLP

- Hidden units: `128 -> 64 -> 32`
- Activation: ReLU
- Kernel initializer: Glorot uniform
- Bias initializer: zeros
- Batch normalization: after 128- and 64-unit layers
- Dropout: `0.30, 0.25, 0.15`
- Output: 1 sigmoid unit
- Optimizer: Adam
- Initial learning rate: 0.001
- Loss: binary cross-entropy
- Validation split: 20%
- Maximum epochs: 100
- Batch size: 128
- Classification threshold: 0.50
- Early stopping monitor: validation AUC
- Early-stopping patience: 10
- Restore best weights: yes
- Reduce LR factor: 0.5
- Reduce LR patience: 4
- Minimum LR: 1e-5
- Random seed: 42
- TensorFlow deterministic operations enabled where supported

Notebook 02 also runs an MLP sensitivity check **without class weighting**, because the synthetic target is approximately balanced.
