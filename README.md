# Mobile Screen Time Analysis and Prediction

Exploratory analysis and linear regression model to predict daily screen time usage from behavioural signals — notifications received, number of app opens, and day of the week — with SHAP-based feature importance for interpretability.

## Dataset

- **Source**: [Screentime App Details Dataset — Kaggle](https://www.kaggle.com/datasets/prasertk/screentime-app-details-dataset)
- **Records**: 54 daily observations across 5 apps (Instagram, WhatsApp, etc.)
- **Columns**: `Date`, `Usage` (minutes), `Notifications`, `Times opened`, `App`
- **Target**: `Usage` (continuous, minutes/day)

| Stat | Usage (min) | Notifications | Times Opened |
|---|---|---|---|
| Mean | 65.0 | 117.7 | 61.5 |
| Std | 58.3 | 97.0 | 43.8 |
| Min | 1 | 8 | 2 |
| Max | 244 | 405 | 192 |

## Pipeline

```
Raw CSV
  → Null check (no missing values)
  → Feature engineering: Date → Day_of_week (0–6)
  → Features: [Day_of_week, Notifications, Times_opened]
  → Train/test split (80/20, random_state=42)
  → Linear Regression (scikit-learn)
  → Evaluation: MAE, cross-validation R², confusion matrix (binned usage categories)
  → SHAP Kernel Explainer → feature importance + summary plot
```

## Model & Results

**Model**: Linear Regression

**Cross-Validation (5-fold R² scores)**:

| Fold | R² Score |
|---|---|
| 1 | 0.44 |
| 2 | 0.65 |
| 3 | 0.82 |
| 4 | 0.23 |
| 5 | 0.53 |
| **Mean** | **~0.54** |

The moderate R² (~0.54) reflects the small dataset size (54 rows) and natural variability in app usage behaviour.

## Visualisations

- **Bar charts**: Usage by date, by notification count, by times opened (Plotly)
- **Scatter plot with OLS trendline**: Notifications vs. Usage (Plotly)
- **Actual vs. Predicted**: scatter comparison of model output vs. ground truth
- **Confusion matrix**: usage binned into 4 categories (Low <50 / Moderate <100 / High <150 / Very High)
- **Permutation feature importance**: bar chart of mean permutation importance per feature
- **SHAP summary plot**: per-sample contribution of each feature to predicted usage (KernelExplainer)

## Interpretation

- **Notifications** and **Times opened** are the strongest predictors of screen time.
- **Day of week** has lower but non-zero impact — weekend usage patterns differ from weekdays.
- SHAP values confirm feature directionality: higher notification count → higher predicted usage.

## Setup

```bash
pip install pandas numpy scikit-learn plotly matplotlib shap
```

Open `Mobile Screen time analysis.ipynb` in Jupyter or on Kaggle.

Download the dataset:
```bash
kaggle datasets download -d prasertk/screentime-app-details-dataset
```

## Notes

This is a small-scale analysis project. The primary value is in the SHAP-based interpretability pipeline and cross-validated regression evaluation, not the model's absolute performance — which is inherently limited by the 54-row dataset.
