# Predicting Mental Health Outcomes in International Students

**View the analysis:** [notebooks/analysis.ipynb](notebooks/analysis.ipynb)

## Overview
This project applies machine learning to explore and predict mental health outcomes (depression, acculturative stress, and suicidal ideation) among international and domestic students at Ritsumeikan Asia Pacific University in Japan.

A full pipeline was implemented, including data cleaning, feature selection, preprocessing, and cross-validated evaluation for both regression and classification tasks.

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

---

## Key Takeaway
This project demonstrates that **model performance is constrained by data quality and signal**, not just model choice — a critical consideration in applied data science.