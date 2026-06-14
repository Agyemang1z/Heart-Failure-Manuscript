# Development and External Validation of Explainable Machine Learning Models for Cardiovascular Disease Prediction

## Overview

This repository provides reproducible code and data resources for a cardiovascular disease prediction study using machine learning, explainable artificial intelligence, and external validation. The analysis evaluates multiple supervised learning algorithms for heart failure prediction and examines whether optimized models retain acceptable performance when applied to an independent cardiovascular dataset.

## Repository

- **Repository name:** `Heart-Failure-Manuscript`
- **Repository type:** Jupyter Notebook research repository
- **Repository link:** https://github.com/Agyemang1z/Heart-Failure-Manuscript
- **Authors:** Farhana Chaudhry, Edmund Fosu Agyemang, Daniela Candanedo, Taylor Franks, Bailey Taylor, Kevin Siliezar, Desmond Yemeh, Ema Akter, Adeshola Lawal,
 Samuel Assefa, and Samuel Kakraba 

- **Academic identifier:** ORCID: https://orcid.org/0000-0001-8124-4493

## Repository Contents

The public repository listing identifies the following files:

- `Cardio.csv`
- `Heart Failure.ipynb`
- `README.md`
- `heart failure dataset.csv`

## Research Objectives

- Develop and compare supervised machine learning models for cardiovascular disease prediction.
- Use explainable artificial intelligence to identify clinically relevant predictors.
- Assess external validity using a separate cardiovascular dataset.
- Provide transparent computational materials that support manuscript reproducibility.

## Analytical Workflow

1. Load and inspect the heart failure and external cardiovascular datasets.
2. Preprocess clinical variables and define the target outcome.
3. Train and evaluate logistic regression, tree-based models, support vector machine, and boosting algorithms.
4. Estimate model performance using discrimination, classification, and validation metrics.
5. Use SHAP-based interpretation to assess the contribution of clinical predictors.
6. Compare internal model performance with external validation results.

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

## Reproducibility Guide

Run the project from a clean working directory. The following commands provide a suggested starting point:

```bash
git clone https://github.com/Agyemang1z/Heart-Failure-Manuscript.git
cd Heart-Failure-Manuscript
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install pandas numpy scikit-learn matplotlib shap xgboost lightgbm catboost jupyter
jupyter notebook "Heart Failure.ipynb"
```

If file names include spaces, keep quotation marks around the file name when launching notebooks or scripts from the terminal.

## Expected Outputs

- Model comparison tables
- Performance metrics for internal and external validation
- Feature importance and SHAP interpretation outputs
- Figures and tables suitable for manuscript reporting

## Data Availability and Responsible Use

The data and code are provided for scholarly, educational, and reproducibility purposes. Users should verify the original data source, data license, and any use restrictions before redistribution or secondary analysis. When the dataset contains human, health, financial, or election-related information, results should be interpreted responsibly and reported with appropriate methodological caution.

## Suggested Citation

Farhana Chaudhry et al. (2026). *Development and External Validation of Explainable Machine Learning Models for Cardiovascular Disease Prediction* [Source code and data]. GitHub. https://github.com/Agyemang1z/Heart-Failure-Manuscript


## Keywords

Cardiovascular disease, Heart failure, Machine learning, Explainable AI, SHAP, External validation

## Disclaimer
This repository is intended to support reproducible research. The code and outputs should not be used as a substitute for professional clinical, financial, legal, electoral, or policy judgment.

This repository is intended to support reproducible research. The code and outputs should not be used as a substitute for professional clinical, financial, legal, electoral, or policy judgment.
