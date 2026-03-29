# Individual-Homework-1---Translating-an-R-Machine-Learning-Workflow-into-Python
Translating an R Machine Learning Workflow into Python
# Purpose of the Analysis
This project translates a machine learning workflow from R to Python, replicating an analysis of the COMPAS (Correctional Offender Management Profiling for Alternative Sanctions) recidivism prediction algorithm.
## Background
COMPAS is a risk assessment tool used in the U.S. criminal justice system to predict the likelihood that a defendant will reoffend. This analysis, originally conducted in R, examines:

1. Exploratory Data Analysis (EDA): Understanding the structure and distribution of defendant data, including demographics, criminal history, and risk scores.
2. Racial Disparities in Risk Scores: Comparing the distribution of COMPAS decile scores across racial groups (African-American vs. Caucasian defendants).
3. Logistic Regression Modeling: Building a predictive model for high-risk classification using demographic and criminal history variables.
4. Fairness Evaluation: Assessing model performance disparities across racial groups by examining:
  - False Positive Rate (FPR): Rate at which low-risk individuals are incorrectly classified as high-risk
  - False Negative Rate (FNR): Rate at which high-risk individuals are incorrectly classified as low-risk

## Key Research Questions
- Are COMPAS risk scores distributed differently across racial groups?
- Does the predictive model exhibit differential error rates by race?
- What are the relative risks associated with demographic factors in predicting high-risk classification?
