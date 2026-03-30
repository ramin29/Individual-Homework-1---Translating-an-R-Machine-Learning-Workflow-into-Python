# Individual-Homework-1
# Translating-an-R-Machine-Learning-Workflow-into-Python
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
| `summary(factor)` | `factor.value_counts()` |
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

Step 1: Environment Setup

Install required libraries:

    pip install pandas numpy matplotlib seaborn statsmodels scipy scikit-learn shap lime dice-ml

Or check if libraries are already installed:

    pip list

Step 2: Dataset

The analysis uses the COMPAS recidivism dataset from ProPublica.

Load data directly from URL:

    import pandas as pd
    url = "https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv"
    data = pd.read_csv(url)

Step 3: Running the Analysis

Option A - Jupyter Notebook (Google Colab):
1. Upload the notebook to Google Colab
2. Run the installation cell first: !pip install shap lime dice-ml
3. Execute cells sequentially from top to bottom

Option B - Local Jupyter Notebook:
1. Install Jupyter: pip install jupyter
2. Launch: jupyter notebook
3. Open the .ipynb file and run cells sequentially

Option C - Python Script:
1. Run: python compas_explainability_analysis.py

Step 4: Expected Outputs
