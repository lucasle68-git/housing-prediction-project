# Boston Housing Price Prediction

A machine learning project demonstrating end-to-end data analysis and predictive modeling for housing prices using multivariable linear regression.

---

## Project Overview

This project analyzes the Boston Housing dataset to build a predictive model for housing prices. The workflow includes:

- **Exploratory Data Analysis**: Understanding distributions, correlations, and outliers
- **Feature Engineering**: Log transformations for skewed variables, categorical encoding for bimodal features
- **Multicollinearity Treatment**: Identifying and removing highly correlated predictors
- **Model Optimization**: Comparing original vs. transformed models to improve performance

---

## Dataset Overview

| Attribute | Description |
|-----------|-------------|
| **CRIM** | Per capita crime rate by town |
| **ZN** | Proportion of residential land zoned for large lots |
| **INDUS** | Proportion of non-retail business acres |
| **CHAS** | Charles River proximity (1 = near, 0 = not near) |
| **RM** | Average number of rooms per dwelling |
| **DIS** | Distance to employment centers |
| **RAD** | Accessibility to radial highways |
| **PTRATIO** | Pupil-teacher ratio by town |
| **LSTAT** | Percentage of lower status population |
| **PRICE** | Median home value (target variable) |

**Dataset Size:** 506 observations × 10 features (after preprocessing)

---

## Key Findings

### Feature Transformations Applied
| Variable | Issue | Solution |
|----------|-------|----------|
| PRICE | Right-skewed | Log transform |
| CRIM | Extreme right-skew | Log transform |
| DIS | Right-skewed | Log transform |
| LSTAT | Right-skewed | Log transform |
| ZN | Zero-inflated (73% = 0) | Binary encoding |
| RAD | Bimodal distribution | Categorical encoding |

### Variables Removed (Multicollinearity)
- **NOX** — Correlated with DIS (-0.77), INDUS (0.76), AGE (0.73)
- **TAX** — Correlated with RAD (0.91)
- **AGE** — Correlated with DIS (-0.75)
- **B** — Removed due to ethical concerns

### Top Price Drivers
| Factor | Impact | Direction |
|--------|--------|-----------|
| **RM** (Rooms) | ~9% per room | ↑ Positive |
| **CHAS** (River proximity) | ~9% premium | ↑ Positive |
| **LSTAT** (Lower status %) | ~3% per 1% | ↓ Negative |
| **PTRATIO** (Class size) | ~3% per unit | ↓ Negative |

---

## Technologies

```
Python 3.x
├── pandas          # Data manipulation
├── numpy           # Numerical operations
├── scikit-learn    # Machine learning
├── seaborn         # Statistical visualization
├── matplotlib      # Plotting
└── plotly          # Interactive charts
```

---

## Model Performance

### Comparison: Original vs. Transformed Model

| Metric | Original Model | Transformed Model | Improvement |
|--------|----------------|-------------------|-------------|
| **R² (Train)** | 0.712 | 0.730 | +2.5% |
| **R² (Test)** | 0.706 | 0.754 | +6.8% |
| **RMSE (Train)** | 4.886 | 0.210* | — |
| **RMSE (Test)** | 5.100 | 0.203* | — |

*RMSE in log units (not directly comparable to original)

### Key Improvements
✅ **Better generalization** — Test R² improved from 0.706 to 0.754  
✅ **Reduced heteroscedasticity** — More uniform residual distribution  
✅ **Improved high-value predictions** — Less underprediction at price ceiling  

---

## Project Structure

```
boston-housing-prediction/
├── Code.ipynb          # Main analysis notebook
├── boston.csv          # Dataset
└── README.md           # Project documentation
```

---

## Quick Start

```bash
# Clone repository
git clone https://github.com/lucasle68-git/data-project.git

# Install dependencies
pip install pandas numpy scikit-learn seaborn matplotlib plotly

# Run notebook
jupyter notebook Housing_Project_code.ipynb
```

---

## Contact

**Lucas Le**  
📍 Glasgow, Scotland  
📫 luong.ldd.work@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/lucasle68/)

---

*This project was developed as part of my Data Science & Machine Learning portfolio.*
