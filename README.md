# Kaggle Playground: Predicting Loan Payback

## Project Overview

This project develops a machine learning pipeline to predict whether a loan will be paid back based on applicant demographic, financial, and loan-related attributes. The intent is to model default risk as a supervised classification problem and evaluate the performance of multiple learning algorithms.

The problem is motivated by real-world applications in:

* Credit risk modeling,
* Financial decision systems,
* Automated loan approval processes,
* Risk-based pricing and underwriting.

The notebook applies a full end-to-end workflow, including data exploration, feature preprocessing, model training, validation, and evaluation using principled performance metrics.

---

## Methodology

### 1. Model Training

Two primary models are trained and compared:

#### Logistic Regression (Baseline)

A linear probabilistic classifier used as a baseline model. It provides:

* Interpretability,
* Fast convergence,
* Benchmark calibration.

Performance is evaluated using **ROC-AUC** on the validation set.

#### Random Forest Classifier

A nonlinear ensemble method trained to capture:

* Feature interactions,
* Nonlinear effects,
* Decision boundaries not accessible to linear models.

This model is also evaluated using ROC-AUC and compared against logistic regression.

---

### 2. Hyperparameter Optimization


#### Grid Search

Exhaustive parameter sweep using:

* Number of estimators,
* Maximum feature count,
* Bootstrapping options.

Cross-validation is used to estimate generalization error via negative MSE (though classification is the main framing of the project).

#### Randomized Search

Stochastic parameter sampling provides:

* Faster exploration,
* Broader coverage over large hyperparameter spaces,
* Strong empirical performance using limited compute.

---

### 3. Feature Importance & Model Interpretation

The best-performing Random Forest model is analyzed via:

* Feature importance scores,
* Ranking of variables based on predictive contribution,
* Identification of high-value financial or demographic predictors.

This step helps surface:

* Which signals drive loan repayment likelihood,
* Potential bias risks,
* Features worth further engineering.

---

### 4. Model Evaluation

Model performance is evaluated using:

* **ROC-AUC** (primary classification metric),
* RMSE and MAE where applicable,
* Calibration through probability outputs,
* Confidence intervals for RMSE.
