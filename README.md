# COVID-19 Hospital Mortality Prediction and Clinical Network Analysis Using MIMIC-IV

## Project Overview

This project analyzes **in-hospital mortality among patients hospitalized with COVID-19** using clinical data from MIMIC-IV. It combines statistical analysis, machine learning, and probabilistic graphical modeling to identify important mortality predictors and examine relationships among patient demographics, comorbidities, first 24-hour laboratory measurements, and hospital mortality. Logistic Regression, LASSO Logistic Regression, and XGBoost are used to predict in-hospital mortality and compare model performance. Pairwise association analysis examines relationships among clinical variables. A Bayesian network models conditional dependencies, while Markov blanket analysis identifies variables most directly informative about mortality.

## Dataset

**Source:** MIMIC-IV v3.1

The COVID-19 cohort is identified using **ICD-10-CM diagnosis code U07.1**.

The final analytical cohort contains:

- **3,978 COVID-19 hospital admissions**
- **3,620 unique patients**
- **412 in-hospital deaths**
- **10.4% in-hospital mortality**
- **23 candidate predictors**

Predictors include demographics, comorbidities, and first 24-hour laboratory measurements.

### MIMIC-IV Tables Used

| MIMIC-IV Table | Purpose |
|---|---|
| `patients.csv` | Patient demographics |
| `admissions.csv` | Hospital admission information and mortality outcome |
| `diagnoses_icd.csv` | COVID-19 identification and comorbidity definitions |
| `d_icd_diagnoses.csv` | ICD diagnosis dictionary |
| `labevents.csv` | First 24-hour laboratory measurements |
| `d_labitems.csv` | Laboratory item dictionary |

MIMIC-IV data are not included in this repository. Access must be obtained independently through PhysioNet.

## How It Works

| Stage | Analysis |
|---|---|
| 1 | Construct the MIMIC-IV COVID-19 cohort |
| 2 | Extract and preprocess demographics, comorbidities, and first 24-hour labs |
| 3 | Assign variables to temporal tiers and calculate pairwise 2×2 associations |
| 4 | Train Logistic Regression, LASSO, and XGBoost models |
| 5 | Compare model performance and identify important predictors |
| 6 | Perform Bayesian network, Markov blanket, and temporal network analysis |

## Machine Learning and Network Models

- **Logistic Regression** — baseline model
- **LASSO Logistic Regression** — feature selection
- **XGBoost** — best performing model
- **Bayesian Network** — models conditional dependencies among clinical variables
- **Markov Blanket Analysis** — identifies direct predictors of mortality

## Key Features

- MIMIC-IV COVID-19 cohort construction
- Pairwise 2×2 association analysis
- Logistic Regression, LASSO, and XGBoost
- ROC/AUC model comparison
- Feature importance analysis
- Bayesian network structure learning
- Mortality Markov blanket identification
- Network visualization

## Output

The project generates:

- COVID-19 admission-level analytical dataset
- Cohort descriptive statistics
- Pairwise association results
- LASSO coefficient plot
- Logistic Regression, LASSO, and XGBoost performance metrics
- ROC curve comparison
- Bayesian network
- Mortality Markov blanket
- Markov blanket visualization
- Direct predictor network

## Tech Stack — Development

- **Python 3.12** — core programming language
- **Jupyter Notebook / JupyterLab** — analysis and model development
- **MIMIC-IV** — clinical EHR data source
- **GitHub** — version control and project repository

MIMIC-IV data must be obtained separately by an authorized user and are **not distributed through this repository**.

## Libraries Used in Python

- `pandas`, `numpy` — data processing and numerical analysis
- `scikit-learn` — Logistic Regression, LASSO, preprocessing, and model evaluation
- `xgboost` — XGBoost classification and feature importance
- `pgmpy` — Bayesian network structure learning and Markov blanket analysis
- `networkx`, `matplotlib` — visualization 
- `jupyterlab` — notebook environment

## Author

**Shalika Sharma**  
George Mason University  
Summer 2026
