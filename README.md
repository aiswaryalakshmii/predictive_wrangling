# Impact of Missing Data Handling on Predictive Model Performance

This project investigates how different missing data handling strategies affect the performance of machine learning models in a health dataset predicting 10-year coronary heart disease (CHD) risk.

---

## Objective

1. Compare common **imputation techniques**: Mean, Median, KNN, Iterative.
2. Simulate missingness under **MCAR, MAR, and MNAR** conditions.
3. Evaluate predictive performance using **Logistic Regression** and **Random Forest** models.
4. Visualize and interpret model behavior using **confusion matrices** and **performance bar charts**.

---

## Phase 1: Imputation Method Comparison

| Imputation Method      | Model               | Accuracy | ROC AUC |
|------------------------|---------------------|----------|---------|
| Iterative Imputation   | Logistic Regression | 0.8459   | 0.7013  |
| Iterative Imputation   | Random Forest       | **0.8475** | 0.6589  |
| KNN Imputation         | Logistic Regression | 0.8459   | **0.7031** |
| KNN Imputation         | Random Forest       | 0.8451   | 0.6615  |
| Mean Imputation        | Logistic Regression | 0.8451   | 0.7019  |
| Mean Imputation        | Random Forest       | 0.8451   | 0.6686  |
| Median Imputation      | Logistic Regression | 0.8451   | 0.7017  |
| Median Imputation      | Random Forest       | 0.8443   | 0.6437  |

**Interpretation**:
- Accuracy is stable across methods.
- KNN + Logistic Regression gave best ROC AUC.
- Iterative Imputation worked well overall.

---

## Phase 2: Simulation of Missingness Mechanisms

| Imputation Method        | Model               | Accuracy | ROC AUC |
|--------------------------|---------------------|----------|---------|
| MCAR - Iterative         | Logistic Regression | 0.8483   | 0.6997  |
| MCAR - Iterative         | Random Forest       | **0.8538** | 0.6721  |
| MAR - Iterative          | Logistic Regression | 0.8451   | **0.7025** |
| MAR - Iterative          | Random Forest       | 0.8404   | 0.6528  |
| MNAR - Iterative         | Logistic Regression | 0.8483   | 0.7011  |
| MNAR - Iterative         | Random Forest       | 0.8491   | 0.6544  |

**Interpretation**:
- **MCAR** showed the best overall accuracy — easier to impute.
- **MAR** gave highest **ROC AUC** with Logistic Regression.
- **MNAR** is hardest to handle, but Iterative Imputation still held up well.
- Logistic Regression gave more consistent ROC AUC across all missingness types.

---

##  Tools & Libraries

- Python, pandas, scikit-learn, seaborn, matplotlib, missingno
- Models: Logistic Regression, Random Forest
- Imputers: SimpleImputer, KNNImputer, IterativeImputer

---

## Author

**Aiswarya Lakshmi P R**  
MSc in Survey Research and Data Analytics  
International Institute for Population Sciences, Mumbai
