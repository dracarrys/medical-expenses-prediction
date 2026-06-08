# Medical Expenses Prediction — Regression Analysis in R

A statistical modeling project predicting individual medical insurance charges using regression techniques in R. Built as part of Math 644 (Statistical Learning), the project applies linear regression, polynomial regression, and regression trees to a 1,338-patient insurance dataset.

## Objective

Health insurers need accurate medical expense forecasts to price premiums correctly. This project builds and compares multiple regression models to estimate yearly medical costs based on patient demographics and lifestyle factors — enabling actuarial table construction for premium pricing.

## Tech Stack

| Area | Tools |
|------|-------|
| Language | R |
| Modeling | caret, lmtest |
| Visualization | ggplot2, ggcorrplot |
| Metrics | MLmetrics (MAE, RMSE) |
| Feature Engineering | Polynomial regression (degree 2) |
| Variable Selection | VIF (car), backward stepwise selection |

## Dataset

**Insurance dataset** — 1,338 observations × 7 variables:

| Variable | Description |
|----------|-------------|
| `age` | Age of primary beneficiary |
| `sex` | Gender (male/female) |
| `bmi` | Body Mass Index |
| `children` | Number of dependents covered |
| `smoker` | Smoking status (yes/no) |
| `region` | US residential region (NE/SE/SW/NW) |
| `charges` | Individual medical costs billed by insurance (**target**) |

## Models Compared

### 1. Multiple Linear Regression
- Backward stepwise selection identified `age`, `bmi`, `children`, and `smoker` as significant predictors
- `sex` and `region` showed no significant effect and were dropped

### 2. Polynomial Regression (degree 2)
- Generated interaction terms between numeric features
- Captured non-linear relationships between BMI, age, and charges

### 3. Regression Trees
- Non-parametric alternative to handle the right-skewed distribution of charges
- Evaluated on same 70/30 train-test split

## Key Findings

- **Smoker status** is the single strongest predictor — smokers incur dramatically higher medical costs regardless of other factors
- **Age** and **BMI** have a positive linear relationship with charges
- The distribution of charges is **right-skewed** with a secondary bump near $40,000 (likely a hidden sub-population of high-cost patients)
- **Sex** and **region** showed minimal impact and were excluded from the final model

## Files

| File | Description |
|------|-------------|
| `Math644_Project_Gkeri_Pepelasi.Rmd` | Full R Markdown source — EDA, modeling, evaluation |
| `Math644_Project_Gkeri_Pepelasi (2).pdf` | Rendered PDF report |
| `Math644.pptx` | Presentation slides |

## Author

Gkeri Pepelasi
