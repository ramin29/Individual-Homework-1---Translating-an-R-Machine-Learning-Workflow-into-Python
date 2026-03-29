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

## Python Libraries Used
### Core Data Manipulation
- pandas: Data manipulation and analysis (equivalent to R's dplyr)
- numpy: Numerical computations
### Visualization
- matplotlib: Base plotting library
- seaborn: Statistical visualizations (equivalent to R's ggplot2)

### Statistical Modeling
- statsmodels: Logistic regression with formula interface (equivalent to R's glm())
- scipy: Statistical functions (e.g., expit for logistic transformation)

### Model Evaluation
- scikit-learn: Confusion matrix, classification metrics

## R to Python Translation Reference

| R Function | Python Equivalent |
|------------|-------------------|
| `library(dplyr)` | `import pandas as pd` |
| `library(ggplot2)` | `import seaborn as sns; import matplotlib.pyplot as plt` |
| `read.csv()` | `pd.read_csv()` |
| `head(df, n)` | `df.head(n)` |
| `nrow(df)` | `len(df)` |
| `glimpse(df)` | `df.info()` |
| `summary(factor)` | `series.value_counts()` |
| `filter(df, cond)` | `df[cond]` or `df.query()` |
| `mutate(df, col=val)` | `df["col"] = val` |
| `select(df, cols)` | `df[cols]` |
| `group_by() %>% summarise()` | `df.groupby().agg()` or `.apply()` |
| `xtabs(~ a + b)` | `pd.crosstab(df["a"], df["b"])` |
| `as.factor()` | `.astype("category")` |
| `relevel(factor, ref)` | `.cat.reorder_categories([ref, ...])` |
| `glm(..., family=binomial)` | `smf.logit()` or `smf.glm(..., family=Binomial())` |
| `predict(model, type="response")` | `model.predict()` |
| `table(pred, actual)` | `pd.crosstab()` or `confusion_matrix()` |

## Instructions for Reproducing the Results
### Install necessary libraries: 
- pip install pandas
- pip install numpy
- pip install matplotlib
- pip install seaborn
- pip install statsmodels
- pip install scipy
- pip install scikit-learn
