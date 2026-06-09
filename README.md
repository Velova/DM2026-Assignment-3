# DM2026 Assignment 3

This repository contains the Kaggle notebooks used for Assignment 3:
exploratory analysis, baseline models, the full LightGBM model, and feature
ablation studies.

## General Kaggle Notes

Upload the notebook you want to run to Kaggle, attach the assignment dataset,
replace the dataset path variables with your own Kaggle input paths, then run
the notebook from top to bottom.

The notebooks expect three dataset locations:

```python
TRAIN_DIR = "path/to/train/train"
TEST_DIR = "path/to/test/test"
SUB_PATH = "path/to/sample_submission.csv"
```

For notebooks that use `DATA_ROOT`, replace it with your own Kaggle dataset
root.

Generated CSV files are written to the Kaggle working directory.

## Recommended Run Order

1. `assignment3_EDA.ipynb`
2. `assignment3_naive-baselines.ipynb`
3. `assignment3_full_model.ipynb`
4. `assignment3_feature_additive_ablation_study(2).ipynb`
5. `assignment3_feature_removal_ablation_study.ipynb`
6. `assignment3_combine_feature_additive_ablation_study.ipynb`

Each notebook is independent, but this order follows the project workflow from
EDA to baselines, full model, and ablation studies.

## Files

### `assignment3_EDA.ipynb`

Explores the dataset, label distribution, user distribution, missing values,
sample sequences, PCA/t-SNE projections, and random forest feature importance.

Replace this path block with your own Kaggle paths:

```python
DATA_ROOT = "path/to/dataset/root"
TRAIN_DIR = os.path.join(DATA_ROOT, "train/train")
TEST_DIR = os.path.join(DATA_ROOT, "test/test")
SUB_PATH = os.path.join(DATA_ROOT, "sample_submission.csv")
```

Outputs:

- `train_metadata_eda.csv`
- `test_metadata_eda.csv`
- `train_file_features_eda.csv`
- `test_file_features_eda.csv`
- `rf_feature_importance_eda.csv`

### `assignment3_naive-baselines.ipynb`

Builds basic statistical features and compares Random Forest, LightGBM,
XGBoost, and CatBoost baselines with GroupKFold validation.

Replace:

```python
TRAIN_DIR = "path/to/train/train"
TEST_DIR = "path/to/test/test"
SUB_PATH = "path/to/sample_submission.csv"
```

Outputs:

- `submission_basic_stats_random_forest.csv`
- `submission_basic_stats_lightgbm.csv`
- `submission_basic_stats_xgboost.csv`
- `submission_basic_stats_catboost.csv`

### `assignment3_full_model.ipynb`

Trains the main rich-feature LightGBM model, evaluates it with GroupKFold,
shows feature importance, and creates the full-model submission.

Replace:

```python
TRAIN_DIR = "path/to/train/train"
TEST_DIR = "path/to/test/test"
SUB_PATH = "path/to/sample_submission.csv"
```

Output:

- `submission_lightgbm.csv`

### `assignment3_feature_additive_ablation_study(2).ipynb`

Runs additive ablation experiments by starting with simple features and adding
feature groups such as magnitude, rich statistics, temporal differences,
window features, FFT features, and peak features.

Replace:

```python
TRAIN_DIR = "path/to/train/train"
TEST_DIR = "path/to/test/test"
SUB_PATH = "path/to/sample_submission.csv"
```

Outputs:

- `train_full_features_for_ablation.csv`
- `test_full_features_for_ablation.csv`
- `submission_additive_<experiment_name>.csv`
- `additive_ablation_summary.csv`

### `assignment3_feature_removal_ablation_study.ipynb`

Runs removal ablation experiments by starting with the full feature set and
removing selected feature groups.

Replace:

```python
TRAIN_DIR = "path/to/train/train"
TEST_DIR = "path/to/test/test"
SUB_PATH = "path/to/sample_submission.csv"
```

Outputs:

- `train_full_features_for_ablation.csv`
- `test_full_features_for_ablation.csv`
- `submission_ablation_<experiment_name>.csv`
- `ablation_summary.csv`

### `assignment3_combine_feature_additive_ablation_study.ipynb`

Runs combined feature-set experiments, comparing richer temporal, magnitude,
peak, window, and FFT feature combinations.

Replace:

```python
TRAIN_DIR = "path/to/train/train"
TEST_DIR = "path/to/test/test"
SUB_PATH = "path/to/sample_submission.csv"
```

Outputs:

- `train_full_features_for_ablation.csv`
- `test_full_features_for_ablation.csv`
- `submission_combination_<experiment_name>.csv`
- `combination_ablation_summary.csv`

### `README.md`

Project documentation.

### `.gitattributes`

Git text-file normalization settings.
