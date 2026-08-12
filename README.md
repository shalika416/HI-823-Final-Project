# COVID-19 Hospital Mortality Prediction Using LASSO and Bayesian Networks

## Topic

**Explainable COVID-19 Hospital Mortality Prediction Using LASSO, Markov Blanket Analysis, and Bayesian Networks**

## Project Overview

This project analyzes **in-hospital mortality among patients hospitalized with COVID-19** using clinical data from MIMIC-IV.

The project combines machine learning and probabilistic graphical modeling to identify important mortality predictors and examine relationships among patient demographics, comorbidities, first 24-hour laboratory measurements, and hospital mortality.

LASSO regression is used for feature selection, while a Bayesian network models conditional dependencies among selected variables. Markov blanket analysis identifies the variables most directly informative about mortality within the learned network.

## Dataset

**Source:** MIMIC-IV

The COVID-19 cohort is identified using **ICD-10-CM diagnosis code U07.1** and combines patient demographics, hospital admission information, comorbidities, laboratory measurements, and mortality outcomes.

### MIMIC-IV Tables Used

| MIMIC-IV Table | Purpose in Project |
|---|---|
| `patients.csv` | Patient demographics including sex and age-related variables |
| `admissions.csv` | Hospital admission information, admission/discharge times, race, insurance, and in-hospital mortality |
| `diagnoses_icd.csv` | Identifies COVID-19 admissions using ICD-10-CM U07.1 and derives patient comorbidities |
| `d_icd_diagnoses.csv` | ICD diagnosis dictionary used to confirm diagnosis codes and descriptions |
| `labevents.csv` | Patient laboratory results used to construct first 24-hour laboratory features |
| `d_labitems.csv` | Laboratory item dictionary used to identify laboratory test item IDs |

### Variables Analyzed

**Demographics**
- Age
- Sex

**Comorbidities**
- Hypertension
- Diabetes
- Obesity
- COPD
- Asthma
- Chronic kidney disease
- Heart failure
- Coronary artery disease
- Cancer
- Liver disease
- Cerebrovascular disease
- Dementia
- Comorbidity count

**First 24-Hour Laboratory Measurements**
- Creatinine
- White blood cell count
- Glucose
- Potassium
- Sodium
- Platelets
- Hemoglobin
- Lactate
- Additional available laboratory measurements

**Target Outcome**
- In-hospital mortality

MIMIC-IV patient-level data are not included in this GitHub repository.

## How It Works

| Stage | Analysis |
|---|---|
| 1 | Load required MIMIC-IV tables |
| 2 | Identify COVID-19 admissions using ICD-10-CM U07.1 |
| 3 | Construct admission-level COVID-19 cohort |
| 4 | Extract demographics and hospital outcomes |
| 5 | Generate comorbidity indicators from ICD diagnoses |
| 6 | Extract first 24-hour laboratory measurements |
| 7 | Clean, impute, and preprocess clinical variables |
| 8 | Perform LASSO feature selection |
| 9 | Evaluate mortality prediction using ROC/AUC |
| 10 | Learn Bayesian network structure |
| 11 | Estimate Bayesian network parameters |
| 12 | Identify the Markov blanket of mortality |
| 13 | Perform Bayesian probability inference |
| 14 | Generate clinical network visualizations |

## Machine Learning Models Used

**LASSO Logistic Regression** — performs regularized feature selection and identifies important predictors of in-hospital mortality.

**Logistic Regression** — estimates mortality probabilities and supports ROC/AUC evaluation.

**Bayesian Network** — models conditional dependencies among demographics, comorbidities, laboratory measurements, and mortality.

**Markov Blanket Analysis** — identifies the subset of variables most directly informative about in-hospital mortality within the learned Bayesian network.

## Key Features

- MIMIC-IV COVID-19 cohort construction
- ICD-10-CM U07.1 COVID-19 identification
- Automated comorbidity feature engineering
- First 24-hour laboratory extraction
- Missing-data preprocessing and imputation
- LASSO-based feature selection
- ROC/AUC model evaluation
- LASSO coefficient visualization
- Bayesian network structure learning
- Bayesian parameter estimation
- Markov blanket identification
- Conditional probability inference
- Clinically organized network visualization

## Output

The project generates:

- COVID-19 admission-level analytical dataset
- Descriptive cohort statistics
- LASSO-selected mortality predictors
- LASSO coefficient plot
- ROC curve and AUC
- Bayesian network
- Markov blanket of in-hospital mortality
- Markov blanket visualization
- Bayesian probability estimates
- Publication-quality figures and result tables

## Deployment

**Development Environment:** Jupyter Notebook / JupyterLab  
**Programming Language:** Python  
**Version Control:** GitHub

The project is provided as a reproducible Jupyter Notebook containing the complete data processing, machine learning, Bayesian modeling, evaluation, and visualization workflow.

MIMIC-IV data must be obtained separately by an authorized user and are **not distributed through this repository**.

## Libraries Used in Python

- `pandas` — MIMIC-IV data processing and cohort construction
- `numpy` — numerical operations
- `scikit-learn` — LASSO logistic regression, preprocessing, cross-validation, and ROC/AUC
- `pgmpy` — Bayesian network structure learning, parameter estimation, and inference
- `networkx` — Bayesian network and Markov blanket visualization
- `matplotlib` — statistical and network visualizations

## Author

**Shalika Sharma**  
George Mason University  
Summer 2026
