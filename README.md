# Capstone Final Project: Predicting Developmental Screening in Early Childhood

## 🎯 Project Overview

Early childhood developmental screening is a critical preventive health service that helps identify developmental delays and connect children to early intervention. Despite national guidelines recommending routine screening, many children do not receive these assessments.

This project develops machine learning models to predict whether children aged 0–3 received a developmental screening questionnaire, using nationally representative survey data.

The goal is to identify risk factors associated with missed screenings and provide actionable insights for public health decision-makers.

---

## 🎯 Objectives

- Predict whether a child received developmental screening (Yes/No)
- Identify socioeconomic and healthcare access factors associated with screening
- Compare multiple classification models
- Evaluate models using appropriate metrics for decision support
- Translate findings into practical public health recommendations

**Data task definition:**  
Using demographic, socioeconomic, and healthcare access variables, build and evaluate classification models to estimate the likelihood that a child received developmental screening.

---

## 🔍 Data Source

**National Survey of Children’s Health (NSCH), 2022 Public Use File**  
U.S. Census Bureau

- Nationally representative survey of child health and well-being
- Includes demographics, family context, healthcare access, and health indicators
- Focused subset: children ages 0–3

The dataset is not included in this repository due to size restrictions and licensing.

---

## 🧩 CRISP-DM Summary

### 1. Business Understanding

Missed developmental screenings delay identification of developmental concerns and reduce the effectiveness of early intervention programs. Public health agencies need a data-driven approach to identify populations at risk.

---

### 2. Data Understanding

The NSCH dataset contains detailed information on:

- Child demographics
- Household socioeconomic status
- Healthcare access and utilization
- Preventive care indicators
- Developmental screening questionnaire responses

The target variable was derived from survey item **k6q12**, indicating whether a developmental screening questionnaire was completed.

---

### 3. Data Cleaning and Preparation

Key steps included:

- Restricting the dataset to children ages 0–3
- Creating a binary target variable (DEV_SCREEN)
- Handling missing values and survey codes
- Processing imputed income variables
- Creating interpretable socioeconomic categories
- Encoding categorical variables for modeling
- Train/test split with stratification

---

### 4. Exploratory Data Analysis (EDA)

Visual analysis examined relationships between screening and key factors:

- Household income (Federal Poverty Level)
- Race and ethnicity
- Access to preventive care
- Demographic characteristics

Findings suggested disparities associated with socioeconomic status and healthcare access.

---

### 5. Feature Engineering

Feature engineering included:

- Aggregating multiple imputed income variables
- Creating poverty-level categories
- Combining race and Hispanic origin variables
- Selecting relevant predictors for classification
- Preprocessing pipelines for consistent transformations

---

## 🤖 Modeling Approach

Three supervised classification models were developed:

- Logistic Regression (baseline, interpretable)
- Random Forest (ensemble tree model)
- Gradient Boosting (sequential ensemble model)

Cross-validation and Grid Search were used to improve model robustness and performance.

---

## 📊 Evaluation Metrics

Because the goal is decision support rather than pure prediction accuracy, evaluation emphasized:

- Precision
- Recall
- F1-score
- ROC-AUC
- Cross-validated ROC-AUC

ROC-AUC was used as the primary metric because it measures discrimination across classification thresholds.

---

## 🏆 Model Comparison

Models were compared on:

- Test-set performance
- Cross-validation results
- Stability
- Interpretability

Tuned ensemble models improved predictive performance but increased complexity.

---

## 🔎 Key Findings & Insights

- Developmental screening is associated with socioeconomic status and access to preventive healthcare.
- Children without a usual preventive care provider are less likely to receive screening.
- Disparities exist across demographic groups.
- Ensemble models capture complex relationships but may be harder to interpret for policy use.

---

## ⚠️ Limitations

- Observational survey data cannot establish causation
- Potential reporting bias in self-reported survey responses
- Some relevant predictors may be unavailable
- Class imbalance may affect performance metrics
- Models do not capture local policy differences or program availability

---

## 🚀 Recommendations & Next Steps

- Use predictive insights to target outreach toward underserved populations
- Incorporate additional healthcare utilization variables
- Explore cost-sensitive learning approaches
- Evaluate models using weighted survey estimates
- Test models on future NSCH waves for stability
- Develop decision-support tools for policymakers and providers
- Target distribution of developmental screening
- Screening disparities by income, race/ethnicity, and preventive care access
- Correlation heatmap of predictors
- Confusion matrices for all models
- Model comparison using ROC-AUC

---

## 📓 Notebook

Main analysis notebook:  
[Capstone_Final_Modeling.ipynb](https://github.com/cheddara/capstone_final/blob/main/notebook/Capstone_Final_Modeling.ipynb)

---

## 📈 Visualizations

Example outputs:

- Screening by income level
- Screening by race/ethnicity
- Preventive care access effects
- Confusion matrices for models
- Model comparison by ROC-AUC

(See `/images` folder)

---

## 🛠 Tools & Libraries Used

- Python
- Jupyter Notebook
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

---

## 📎 Notes

The NSCH dataset is not included due to size and distribution restrictions.  
It can be obtained from the U.S. Census Bureau NSCH data portal.

---

## 👩‍💻 Author

**Annette Angel**  
UC Berkeley — Professional Certificate in Machine Learning & AI  
Cheddar Advertising & Consulting
