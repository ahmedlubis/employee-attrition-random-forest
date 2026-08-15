# 👥 Employee Attrition Prediction Using Random Forest

A machine learning project that uses **Random Forest classification** to predict employee attrition and identify the workforce characteristics that contribute most to predictive performance.

## 🎯 Problem

Employee turnover can create significant recruitment, training, and productivity costs.

This project asks:

> **Can employee characteristics and workplace conditions be used to predict whether an employee will leave the organization?**

The objectives are to:

* Build a classification model for employee attrition
* Evaluate predictive performance on unseen data
* Identify the most important features for prediction
* Translate model results into practical HR insights

## 📊 Dataset

The analysis uses an **HR Employee Attrition dataset** containing information about employee satisfaction, performance, workload, tenure, compensation, and other workplace characteristics.

The original dataset contains **14,999 observations and 10 variables**.

After removing observations with missing values, **14,430 observations** remain for modeling.

### Main Variables

| Variable                | Description                                           |
| ----------------------- | ----------------------------------------------------- |
| `left`                  | Target: 1 = employee left, 0 = stayed                 |
| `satisfaction_level`    | Employee job satisfaction                             |
| `last_evaluation`       | Latest performance evaluation score                   |
| `number_project`        | Number of projects handled                            |
| `average_montly_hours`  | Average monthly working hours                         |
| `time_spend_company`    | Years spent at the company                            |
| `work_accident`         | Whether the employee experienced a workplace accident |
| `promotion_last_5years` | Whether the employee received a recent promotion      |
| `department`            | Employee department                                   |
| `salary`                | Salary category                                       |

## 🔬 Method

The analysis follows a supervised machine-learning workflow.

### 1. Data Preparation

* Handle missing observations
* Define employee attrition as the binary target
* Prepare categorical and numerical variables
* Split the data using a **70/30 stratified train-test split**

### 2. Random Forest

A **Random Forest classifier** is trained using:

* **500 decision trees**
* Stratified training data
* Ensemble learning to reduce the variance of individual decision trees

Random Forest is particularly useful here because it can capture nonlinear relationships and interactions between employee characteristics without requiring a specific functional form.

### 3. Model Evaluation

Performance is evaluated using:

* Out-of-Bag (OOB) error
* Test accuracy
* Sensitivity
* Specificity
* Feature importance

Feature importance is evaluated using:

* **Mean Decrease Accuracy (MDA)**
* **Mean Decrease Gini (MDG)**

## 📈 Results

### Model Performance

| Metric               |     Result |
| -------------------- | ---------: |
| **Test Accuracy**    | **98.75%** |
| **OOB Error Rate**   |  **1.00%** |
| Sensitivity — Stayed | **99.82%** |
| Specificity — Left   | **94.67%** |
| Baseline Accuracy    | **79.21%** |

The Random Forest substantially outperforms the baseline accuracy on the test set.

### Feature Importance

The most influential variables according to Mean Decrease Gini include:

| Feature                | Mean Decrease Gini |
| ---------------------- | -----------------: |
| `satisfaction_level`   |       **1,124.48** |
| `time_spend_company`   |         **593.85** |
| `number_project`       |         **581.12** |
| `average_montly_hours` |         **484.80** |
| `last_evaluation`      |         **419.98** |

### Key Finding

**Job satisfaction is the most important feature in the Random Forest model by a substantial margin.**

Workload-related variables such as number of projects and monthly working hours, together with employee tenure and performance evaluation, also contribute strongly to predictive performance.

Variables such as department, salary, workplace accidents, and recent promotion contribute comparatively less according to the model's feature-importance measures.

> **Important:** Feature importance indicates predictive contribution, not causal impact.

## 📊 Visualization

### Feature Importance

![Random Forest Feature Importance](analysis_bar.png)

The visualization highlights the relative importance of employee characteristics in the Random Forest model.

The results show that **job satisfaction** is substantially more influential than the other variables included in the model.

## 💡 Conclusion

The Random Forest model demonstrates strong predictive performance for employee attrition in this dataset, achieving **98.75% test accuracy** and a **1.00% OOB error rate**.

The model identifies **job satisfaction** as the strongest predictive feature, followed by employee tenure, number of projects, working hours, and performance evaluation.

From an HR analytics perspective, these results suggest that employee experience and workload-related variables deserve particular attention when analyzing attrition risk.

However, the findings should be interpreted as **predictive associations rather than causal relationships**. A feature being important to the Random Forest does not mean changing that feature will necessarily reduce employee turnover.

### Future Improvements

A stronger production-oriented model could include:

* Cross-validation
* Hyperparameter tuning
* Class-imbalance analysis
* ROC-AUC and PR-AUC
* SHAP-based model interpretation
* Comparison with Logistic Regression and Gradient Boosting
* Calibration of predicted attrition probabilities

## 🛠️ Technologies

* **R**
* **R Markdown**
* **Random Forest**
* **Classification**
* **Machine Learning**
* **Pandas / Data Manipulation**
* **Statistical Analysis**
* **Data Visualization**

### Methods

`Random Forest` `Classification` `Feature Importance` `Ensemble Learning` `Predictive Modeling`

## 📁 Repository Structure

```text
employee-attrition-random-forest/
│
├── hr_data.csv
├── employee-attrition-random-forest.Rmd
├── employee-attrition-random-forest.md
├── analysis_bar.png
└── README.md
```

## 📌 Topics

`R` `Random Forest` `Machine Learning` `Employee Attrition` `HR Analytics` `Classification` `Predictive Modeling` `Feature Importance` `Data Science`
