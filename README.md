# Real Estate Price Prediction using Linear Regression

This project applies **simple and multiple linear regression models** to a large real estate dataset to analyze and predict housing prices.  
The goal is to understand which property features most strongly influence price, and to compare model performance between a single-variable (simple) and multi-variable (multiple) regression.

---

## 📘 Objectives
- Explore relationships between property features and price.  
- Apply and compare simple vs. multiple linear regression models.  
- Evaluate model performance using RMSE and R² metrics.  
- Diagnose model assumptions and check for multicollinearity.

---

## 🧰 Tools and Libraries
- **R packages:** `data.table`, `ggplot2`, `corrplot`, `car`, `forcats`
- **Environment:** R 4.4+, RStudio / Jupyter (R kernel)

---

## 🧮 Dataset
**Source:** [Kaggle – Realtor Real Estate Dataset](https://www.kaggle.com/)  
**Size:** ~2.2 million rows (after preprocessing)  
**Target Variable:** `log(price)`  
**Predictors:**  
- Numeric: `house_size`, `bed`, `bath`, `acre_lot`, `zip_code`  
- Categorical: `city`, `state`, `status`, `brokered_by`, `street`

---

## ⚙️ Workflow Overview
1. **Preprocessing**
   - Remove missing or invalid records.
   - Impute missing predictors (median/mode).
   - Encode categorical variables and cap high-cardinality factors.
   - Transform price → `log(price)` for normality.
   - Split into training (70%) and test (30%) sets.

2. **Exploratory Data Analysis (EDA)**
   - Summary statistics for numeric columns.
   - Histogram of `log(price)`.
   - Scatterplots of key predictors vs. price.
   - Correlation heatmap and multicollinearity check.

3. **Modeling**
   - **Simple model:** `log(price) ~ house_size`
   - **Multiple model:** `log(price) ~ bed + bath + acre_lot + city + state + status + ...`
   - Evaluate RMSE, R², residuals, QQ plots, and VIF.

4. **Interpretation**
   - Compare performance between models.
   - Identify key drivers of housing price variation.
   - Discuss limitations and next steps (e.g., regularization, spatial effects).

---

## 📊 Results Summary
| Model | RMSE | R² | Key Insights |
|-------|------|----|---------------|
| Simple Linear Regression | 1.17 | 0.00 | `house_size` alone explains almost no variance |
| Multiple Linear Regression | 1.02 | 0.25 | Location, baths, and state are strong predictors |


