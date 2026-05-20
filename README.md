# 🦴 Osteoarthritis Risk Prediction Using Machine Learning

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-EB0028?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-success)

End-to-end machine learning pipeline for predicting osteoarthritis (OA) risk in older adults using self-reported, non-invasive data from the English Longitudinal Study of Ageing (ELSA Wave 9). MSc Health Data Science thesis project, University of Birmingham, 2025.

---

## 🎯 At a Glance

- **Sample:** 4,723 adults aged 60+ from ELSA Wave 9 (2018–2019)
- **Outcome:** Self-reported osteoarthritis status
- **Models compared:** Logistic Regression, Random Forest, XGBoost, CatBoost
- **Best clinical model:** Logistic Regression with upsampling (AUC 0.755) — selected for **high sensitivity** in early screening
- **Feature selection:** 4-stage pipeline (literature → bivariate → Boruta → VIF + Spearman), reducing 32 features to 25
- **Class imbalance:** Addressed via upsampling and threshold tuning
- **Clinical framing:** Low-cost OA screening using self-report data only — no labs or imaging required

---

## 📋 Project Description

**Academic context:** Completed as part of my MSc Health Data Science at the University of Birmingham (2025).  
**Thesis title:** *Predicting Osteoarthritis in Older Adults Using Literature-Based, Non-Invasive Risk Factors: A Cross-Sectional Analysis of ELSA Wave 9.*

The project develops and evaluates machine learning models to predict osteoarthritis risk in older adults using only non-invasive, self-reported survey data — exploring the feasibility of OA screening in primary care and digital health settings where radiographic or lab-based assessment isn't available.

---

## 🎯 Research Objectives

- Develop predictive models for osteoarthritis risk in adults aged 60+ using ELSA Wave 9
- Evaluate the predictive value of non-invasive, literature-based risk factors
- Assess whether OA prediction is feasible without radiographic or lab-based data
- Explore low-cost screening applications for primary care and digital health

---

## 📁 Repository Structure

```
osteoarthritis-risk-prediction/
├── codes/          # Data cleaning, feature selection, and modelling scripts
└── results/
    ├── plots/      # Visualizations (feature importance, histograms, workflow diagrams)
    ├── roc-curves/ # ROC curves for each model
    └── tables/     # Descriptive summaries, bivariate analysis, performance results
```

---

## 📊 Dataset

- **Source:** English Longitudinal Study of Ageing (ELSA), Wave 9 (2018–2019)
- **Sample size:** 4,723 participants aged ≥ 60 years
- **Outcome:** Self-reported osteoarthritis status
- **Predictors:** 32 literature-based, non-invasive features (reduced to 25 after feature selection)

> 🔒 **Data privacy:** The original ELSA dataset is **not included** in this repository to maintain confidentiality. All shared results are derived, aggregated, and anonymized.

---

## 🧪 Methods

The methodological workflow included literature-guided feature selection, preprocessing, model training, and evaluation.

![Study Design & Machine Learning Workflow](results/plots/study%20design%20and%20machine%20learning%20workflow.png)
*Figure 1: Overview of the study design and machine learning workflow for osteoarthritis prediction using ELSA Wave 9 data.*

- **Models:** Logistic Regression, Random Forest, XGBoost, CatBoost
- **Feature selection:** Bivariate analysis → Boruta → Variance Inflation Factor (VIF) for multicollinearity → Spearman correlation
- **Class imbalance handling:** Upsampling + threshold tuning
- **Evaluation metrics:** AUC, accuracy, precision, recall, F1, confusion matrix, ROC curves

![Experimental Setup](results/plots/Experimental%20setup.png)
*Figure 2: Experimental setup for model development and evaluation, from data splitting to test-set prediction.*

---

## 🏆 Key Findings

![Performance Evaluation](results/tables/performance%20evaluation.png)
*Table 1: Performance of four optimized machine learning models for osteoarthritis prediction.*

- **Best clinical model: Logistic Regression with upsampling (AUC 0.755)** — chosen over slightly higher-AUC alternatives because of its **highest sensitivity**, making it most appropriate for early-detection screening where missed cases are costlier than false positives.
- **Top 15 predictors:** Difficulty stooping/kneeling, sex, pain severity (most of the time), hip pain, knee pain, age, difficulty shopping for groceries, grip strength, pain while walking, pain elsewhere, difficulty dressing, difficulty sitting for 2 hours, difficulty reaching overhead, back pain, foot pain.

---

## 🏥 Potential Applications

- **Logistic Regression model:** Screening tool with high sensitivity for early OA detection
- **CatBoost model:** Rule-out tool with high specificity to reduce unnecessary further testing
- **Integration target:** Digital health platforms and primary care screening in resource-limited settings, where access to imaging or lab tests may be restricted

---

## ⚠️ Limitations

- **Cross-sectional design** — cannot establish temporal precedence between predictors and OA onset
- **Self-reported outcome** — no radiographic or clinical confirmation of OA status
- **Cohort generalizability** — ELSA is predominantly White British; external validation in more diverse populations is needed
- **Single-dataset validation** — models were tuned and tested on ELSA Wave 9 only; external validation on independent cohorts remains pending

---

## 👩‍💻 Author

**Tesneem Fnais** — MSc Health Data Science  
University of Birmingham, 2025

Feel free to connect or reach out if you'd like to discuss the project!
