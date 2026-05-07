# Predicting Mental Health Outcomes in International Students

**View the analysis:** [notebooks/analysis.ipynb](notebooks/analysis.ipynb)

To run the notebook, download the dataset from the Data Source section below and place it in `data/`.

## Overview
This project applies machine learning to explore and predict mental health outcomes (depression, acculturative stress, and suicidal ideation) among international and domestic students at Ritsumeikan Asia Pacific University in Japan.

An end-to-end machine learning pipeline was implemented, including data cleaning, feature selection, preprocessing, and cross-validated evaluation for both regression and classification tasks. Key variables used in the analysis are summarised below.

| Variable | Explanation | Original | Encoding |
|---|---|---|---|
| depression | Depression score (PHQ-9) | 0–25 | - |
| suicidal_ideation | Suicidal ideation (past 2 weeks, PHQ-9) | No / Yes | 0 / 1 |
| acculturative_stress | Acculturative stress score (ASISS) | 0–145 | - |
| inter_dom | Student status (domestic/international) | Dom / Inter | 0 / 1 |
| gender | Self-identified gender | Female / Male | 0 / 1 |
| academic | Current academic level | Under / Grad | 0 / 1 |
| intimate | Has intimate partner | No / Yes | 0 / 1 |
| religion | Is religious | No / Yes | 0 / 1 |
| age | Age | 17–31 | - |
| stay | Time enrolled (years) | 1–10 | - |
| japanese | Japanese proficiency (self-rated) | 1–5 | - |
| english | English proficiency (self-rated) | 1–5 | - |

Full variable definitions and mappings are available in `data/feature_target_explanations.xlsx`.

---

## Key Findings
- Regression models achieved **R² ≈ 0**, indicating no meaningful predictive signal  
- Classification models performed **near random (ROC-AUC ≈ 0.5)**  
- More complex models (Random Forest, XGBoost) **did not improve performance** and often overfit  

The available features do not support reliable prediction of mental health outcomes in this dataset.

---

## Interpretation
This project highlights an important distinction between statistical association and predictive usefulness. While some variables show correlations with the targets, these relationships do not generalise in a cross-validated setting.

The results suggest:

- mental health outcomes are influenced by factors not captured in the dataset
- self-reported survey data introduces noise
- small sample size limits model performance

---

## Methodology
- Feature selection uitilising a codebook  
- Binary variables encoded as 0/1  
- Preprocessing with `scikit-learn` pipelines (imputation + scaling)  
- Cross-validated evaluation  
- Models: Linear (OLS, Ridge, Lasso, Elastic Net), Random Forest, XGBoost  

---

## Data Source
Nguyen, M.-H. et al. (2019)  
*A Dataset of Students’ Mental Health and Help-Seeking Behaviors in a Multicultural Environment*  
https://doi.org/10.3390/data4030124  

The dataset and associated questionnaire can be accessed via the publication.

---

## Key Takeaway
This project demonstrates that **model performance is constrained by data quality and signal**, not just model choice — a critical consideration in applied data science.