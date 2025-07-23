
# Vaccine Acceptance Prediction

This project predicts individual willingness to receive:
- **H1N1 influenza vaccine**
- **Seasonal influenza vaccine**

It is based on demographic, behavioral, and health-related features using supervised machine learning techniques.

---

## Files Overview

| File                        | Description |
|-----------------------------|-------------|
| `training_set_features.csv` | Feature set for training the model |
| `training_set_labels.csv`   | Binary labels for H1N1 and seasonal vaccine acceptance |
| `test_set_features.csv`     | Test set features (no labels) |
| `submission_format.csv`     | Required format for submission |
| `Predictions_final.csv`     | Final predicted probabilities for test set |
| `vaccine-prediction.ipynb`  | Jupyter notebook with full ML workflow |

---

## Problem Statement

The objective is to build predictive models that estimate the probability that a person will receive:
- the **H1N1 vaccine**
- the **Seasonal flu vaccine**

Each prediction is a probability (between 0 and 1).

---

## Workflow

1. **Data Preprocessing**
   - Handled missing values
   - Encoded categorical variables
   - Normalized or standardized numeric features

2. **Model Training**
   - Trained separate models for:
     - `h1n1_vaccine`
     - `seasonal_vaccine`
   - Models used: `XGBoost`, `RandomForest`, or similar (see notebook for details)

3. **Evaluation**
   - Performance measured using AUC and accuracy (on validation sets)
   - Model selection based on cross-validation scores

4. **Prediction**
   - Applied trained models to the `test_set_features.csv`
   - Final predictions saved in `Predictions_final.csv`

---

## Output Format

The `Predictions_final.csv` file should follow this structure:

| respondent_id | xyz_vaccine | seasonal_vaccine |
|---------------|--------------|------------------|
| 0             | 0.132        | 0.554            |
| 1             | 0.768        | 0.321            |
| ...           | ...          | ...              |

---

## How to Run the Notebook

### Requirements
Install the following Python packages:
```bash
pip install pandas numpy scikit-learn xgboost
```

### Run
Open and run all cells in the notebook:
```bash
jupyter notebook vaccine-prediction.ipynb
```

---

## Notes

- Each prediction is a probability, not a binary class.
- Ensure the order of `respondent_id` is preserved in the final output.
- Evaluation metrics may differ based on the train/test split used.
