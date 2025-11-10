# Sales Forecasting using Multiple Linear Regression

This project uses **Multiple Linear Regression (MLR)** to predict sales revenue based on advertising expenditure across three channels — **TV**, **Radio**, and **Newspaper**.  
The analysis provides data-driven insights on which marketing investments most effectively drive sales.

---

## Files in This Repository

| File Name | Description |
|------------|--------------|
| `sales_forecasting.ipynb` | Jupyter Notebook containing full regression analysis and business insights |
| `advertising.csv` | Dataset with advertising spend and corresponding sales data |
| `requirements.txt` | Python dependencies to reproduce this analysis |
| `README.md` | Documentation with workflow, model interpretation, and business recommendations |

---

## Dataset Description

**Dataset:** `advertising.csv`  
**Records:** 200 rows  
**Source:** Advertising dataset from *Introduction to Statistical Learning (ISLR)*  

| Feature | Description |
|----------|--------------|
| `TV` | Advertising budget spent on TV (in $ thousands) |
| `Radio` | Advertising budget spent on Radio (in $ thousands) |
| `Newspaper` | Advertising budget spent on Newspaper (in $ thousands) |
| `Sales` | Units sold (in $ thousands) – dependent variable |

---

## Workflow

1. **Data Exploration**
   - Loaded dataset using pandas and checked for missing values.  
   - Performed correlation analysis to understand variable relationships.

2. **Model Building**
   - Defined `Sales` as dependent variable.  
   - Used `TV`, `Radio`, and `Newspaper` as independent variables.  
   - Applied **Ordinary Least Squares (OLS)** regression using `statsmodels`.

3. **Model Evaluation**
   - Checked R², Adjusted R², p-values, and F-statistic.  
   - Examined residuals for normality and homoscedasticity.

---

## Model Summary

| Metric | Value |
|--------|--------|
| **R²** | 0.903 |
| **Adjusted R²** | 0.9011 |
| **F-statistic (p-value)** | 8.13e-99 (Highly significant) |

### Coefficients (with correct values)

| Predictor | Coefficient | Interpretation | Significance |
|------------|--------------|----------------|---------------|
| **Intercept** | 4.6251 | Baseline sales when ad spend = 0 | — |
| **TV** | 0.0544 | Every additional \$1,000 spent on TV increases sales by **0.054 units** | ✅ Significant (p < 0.001) |
| **Radio** | 0.1070 | Every additional \$1,000 spent on Radio increases sales by **0.107 units** | ✅ Significant (p < 0.001) |
| **Newspaper** | 0.0003 | Newspaper spend has **no measurable effect** on sales | ❌ Not significant (p ≈ 0.95) |

---

## Model Fit Interpretation

- The model explains **~90% of the variation in sales (R² = 0.903)**, indicating an excellent fit.  
- Both **TV and Radio** have statistically significant positive effects on sales.  
- **Newspaper** advertising has an almost zero coefficient and is not statistically significant, meaning additional spend in this channel does not influence sales.  
- Residuals appear well-distributed → no major violations of regression assumptions.

---

## Business Insights

### **What’s Working**
- **TV Advertising:** Strong, positive, and consistent impact on sales — best-performing channel.  
- **Radio Advertising:** Also a strong and statistically significant driver of sales.  

### **What’s Not Working**
- **Newspaper Advertising:** No measurable impact (p ≈ 0.95). Indicates inefficiency and possible audience mismatch.

---

## Strategic Recommendations

### **1. Reallocate Budget**
- Shift marketing spend **away from Newspaper** toward **TV and Radio**, where returns are proven.
- Focus on **TV for brand awareness** and **Radio for regional/local campaigns.**


### **2. Newspaper spending**
- Cut newspaper ad spending


