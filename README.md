# Development and External Validation of Explainable Machine Learning Models for Cardiovascular Disease Prediction

Farhana Chaudhry1,a, Edmund Fosu Agyemang1,a, Daniela Candanedo2, Taylor Franks2, 
Bailey Taylor2, Kevin Siliezar2, Desmond Yemeh1, Ema Akter1, Adeshola Lawal1,
 Samuel Assefa1, and Samuel Kakraba 1,3,4,a*
1Department of Biostatistics and Data Science, Celia Scott Weatherhead School of Public Health and Tropical Medicine at Tulane University, New Orleans, LA, USA
2Department of Epidemiology, Celia Scott Weatherhead School of Public Health and Tropical Medicine at Tulane University, New Orleans, LA, USA
3Center for Aging, School of Medicine, Tulane University, New Orleans, LA, 70112, USA
4Conolly Alexander Institute of Data Science (CAIDS), Tulane University, New Orleans, LA, 70112, USA

a These authors have contributed equally to this work. 

Corresponding author: Samuel Kakraba, PhD; 1440 Canal St, New Orleans, LA 70112; skakraba@tulane.edu; 

## Overview

This repository provides reproducible code and data resources for a cardiovascular disease prediction study using machine learning, explainable artificial intelligence, and external validation. The analysis evaluates multiple supervised learning algorithms for heart failure prediction and examines whether optimized models retain acceptable performance when applied to an independent cardiovascular dataset.

**This version (Revision 1)** adds a self-contained robustness-check section (Section 6 of the notebook) written in response to peer review, covering bootstrap confidence intervals, a data-leakage sensitivity analysis, a feature-parsimony analysis, a Kendall's W robustness check, a scaling-invariance check, and an Associate-Editor-spec-compliant summary figure. See "Revision 1: Reviewer-Requested Robustness Checks" below.

## Repository

- **Repository name:** `Heart-Failure-Manuscript`
- **Repository type:** Jupyter Notebook research repository
- **Repository link:** https://github.com/Agyemang1z/Heart-Failure-Manuscript
- **Authors:** Farhana Chaudhry, Edmund Fosu Agyemang, Daniela Candanedo, Taylor Franks, Bailey Taylor, Kevin Siliezar, Desmond Yemeh, Ema Akter, Adeshola Lawal,
 Samuel Assefa, and Samuel Kakraba


## Repository Contents

- `Cardio.csv` — external validation dataset (Kaggle cardiovascular disease, n = 70,000)
- `Heart Failure.ipynb` — original analysis notebook (Sections 1-5: EDA, model training/tuning, SHAP, external validation)
- `heart failure dataset.csv` — internal dataset (UCI Heart Failure Clinical Records, n = 299)
- `README.md` — this file

## Research Objectives

- Develop and compare supervised machine learning models for cardiovascular disease prediction.
- Use explainable artificial intelligence to identify clinically relevant predictors.
- Assess external validity using a separate cardiovascular dataset.
- Provide transparent computational materials that support manuscript reproducibility.
- Quantify uncertainty in internal test performance, test the sensitivity of results to a possible data-leakage feature (`time`), and test whether a small, clinically transparent feature set retains acceptable performance.

## Analytical Workflow

1. Load and inspect the heart failure and external cardiovascular datasets.
2. Preprocess clinical variables and define the target outcome.
3. Train and evaluate logistic regression, tree-based models, support vector machine, and boosting algorithms.
4. Estimate model performance using discrimination, classification, and validation metrics.
5. Use SHAP-based interpretation to assess the contribution of clinical predictors.
6. Compare internal model performance with external validation results.
7.Bootstrap CIs, time-feature sensitivity analysis, feature-reduction analysis, Kendall's W robustness check, scaling-invariance check, and summary figure — see below.

## Software Requirements

Recommended software and packages include:

- Python 3.10 or later
- Jupyter Notebook or JupyterLab
- pandas
- numpy
- scikit-learn
- matplotlib
- shap
- xgboost
- lightgbm
- catboost
- scipy (used by Section 6.4; already a transitive dependency of scikit-learn)

**Compatibility note:** the original notebook's AdaBoost hyperparameter grid includes an `algorithm` key. This was removed from `AdaBoostClassifier` in scikit-learn ≥ 1.8. If you are running a newer scikit-learn and hit `ValueError: Invalid parameter 'algorithm'`, either pin `scikit-learn<1.8` (recommended, matches the originally reported results exactly) or drop the `'algorithm'` entry from `param_grids["AdaBoost_Clf"]` in Section 2. This does not affect any other model.

## Reproducibility Guide

Run the project from a clean working directory. The following commands provide a suggested starting point:

```bash
git clone https://github.com/Agyemang1z/Heart-Failure-Manuscript.git
cd Heart-Failure-Manuscript
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install "pandas" "numpy" "scikit-learn<1.8" "matplotlib" "shap" "xgboost" "lightgbm" "catboost" "jupyter" "scipy"
jupyter notebook "Heart_Failure_REVISED.ipynb"
```

Run all cells top to bottom in a single kernel session. Section 6 depends on variables defined in Sections 1-5 (`data`, `X`, `y`, `X_train`, `X_test`, `X_train_scaled`, `X_test_scaled`, `classification_models`, `param_grids`, `classification_metrics`, `df`) and will not run correctly in isolation or out of order.

If file names include spaces, keep quotation marks around the file name when launching notebooks or scripts from the terminal.

## Data Availability and Responsible Use

The data and code are provided for scholarly, educational, and reproducibility purposes. Users should verify the original data source, data license, and any use restrictions before redistribution or secondary analysis. When the dataset contains human, health, financial, or election-related information, results should be interpreted responsibly and reported with appropriate methodological caution.

## Suggested Citation

Farhana Chaudhry et al. (2026). *Development and External Validation of Explainable Machine Learning Models for Cardiovascular Disease Prediction* [Source code and data]. GitHub. https://github.com/Agyemang1z/Heart-Failure-Manuscript

## Keywords

Cardiovascular disease, Heart failure, Machine learning, Explainable AI, SHAP, External validation, Bootstrap confidence intervals, Data leakage, Feature parsimony

## Disclaimer
This repository is intended to support reproducible research. The code and outputs should not be used as a substitute for professional clinical, financial, legal, electoral, or policy judgment.
