# data-project

# Boston Housing Price Prediction

## 📋 Project Overview
Predictive model for Boston housing prices using multivariable linear regression, 
featuring data exploration, multicollinearity analysis, and log transformation and category transformation.

## 🎯 Key Findings
- Log transformation improved R² from 0.71 to 0.75
- Room count (RM) and river proximity (CHAS) are strongest predictors
- Successfully addressed heteroscedasticity through log transformation

## 🛠️ Technologies
Python | Pandas | NumPy | Scikit-learn | Seaborn | Matplotlib

## 📊 Model Performance
| Model | R² (Train) | R² (Test) |
|-------|------------|-----------|
| Original | 0.71 | 0.706 |
| Transformed| 0.73 | 0.754 |
