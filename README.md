# COVID-19 Hospital Mortality Prediction Using LASSO and Bayesian Networks

## Project Overview

This project analyzes **in-hospital mortality among patients hospitalized with COVID-19** using clinical data from MIMIC-IV.

The project combines machine learning and probabilistic graphical modeling to identify important mortality predictors and examine relationships among patient demographics, comorbidities, first 24-hour laboratory measurements, and hospital mortality.

LASSO regression is used for feature selection, while a Bayesian network models conditional dependencies among selected variables. Markov blanket analysis identifies the variables most directly informative about mortality within the learned network.

## Dataset

**Source:** MIMIC-IV v3.1

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

MIMIC-IV is not included in this repository. Access must be obtained independently through PhysioNet.

## How It Works

| Stage | Analysis |
|---|---|
| 1 | Build COVID-19 cohort from MIMIC-IV |
| 2 | Extract demographics, comorbidities, and first 24-hour labs |
| 3 | Clean and preprocess clinical data |
| 4 | Perform LASSO feature selection and ROC/AUC evaluation |
| 5 | Build and fit the Bayesian network |
| 6 | Identify the mortality Markov blanket and perform probability inference |

## Machine Learning Models Used

**LASSO Logistic Regression** — selects important mortality predictors.
**Logistic Regression** — predicts mortality and evaluates ROC/AUC performance.
**Bayesian Network** — models probabilistic relationships among clinical variables.
**Markov Blanket Analysis** — identifies variables most directly related to mortality.

## Key Features

- COVID-19 cohort construction from MIMIC-IV
- LASSO-based feature selection
- ROC/AUC model evaluation
- Bayesian network structure learning
- Markov blanket identification
- Bayesian probability inference
- Clinical network visualization

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

## Tech Stack — Development

- **Python 3.12** — core programming language
- **Jupyter Notebook / JupyterLab** — analysis and model development
- **MIMIC-IV** — clinical EHR data source
- **GitHub** — version control and project repository

MIMIC-IV data must be obtained separately by an authorized user and are **not distributed through this repository**.

## Libraries Used in Python

- `pandas, numpy` — data processing
- `scikit-learn` — ML models
- `pgmpy` — Bayesian network structure learning, parameter estimation, and inference
- `networkx, matplotlib` — visualization
- `jupyterlab` — notebook environment

## Author

**Shalika Sharma**  
George Mason University  
Summer 2026
