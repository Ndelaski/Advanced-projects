# covid-bayesian-prediction

**Predicting Long COVID risk using Bayesian Networks — multi-model comparison across 4-week and 6-month horizons**

[![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)](https://python.org)
[![pgmpy](https://img.shields.io/badge/pgmpy-0.1-green?style=flat-square)](https://pgmpy.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3-orange?style=flat-square)](https://scikit-learn.org)
[![Status](https://img.shields.io/badge/status-complete-brightgreen?style=flat-square)]()
[![Institution](https://img.shields.io/badge/Western%20Sydney%20University-Capstone-purple?style=flat-square)]()

---

## Overview

This project builds and evaluates probabilistic and classical ML models to predict COVID-19 infection 
and long COVID risk from clinical symptom data, demographic features, and comorbidities. It was 
completed as a postgraduate capstone at Western Sydney University.

The central contribution is a **Bayesian Network (pgmpy)** that models the conditional dependencies 
between symptoms, demographics, and outcomes — compared against Logistic Regression, Decision Trees, 
SVM, and Neural Networks across two clinically meaningful prediction horizons.

**Prediction horizons:**
- **4 weeks** post-infection — early risk triage
- **6 months** post-infection — long COVID persistence risk

**Dataset:** AIIMS BBSR Long COVID clinical dataset + Eyheramendy et al. (2021) symptom data  
**Features:** Binary symptom indicators, demographic attributes, comorbidities  
**Target:** COVID-19 infection status · Long COVID risk

---

## Why Bayesian Networks for this problem?

Standard classifiers treat patient features as independent inputs to a black-box function. A Bayesian 
Network instead models the **causal and probabilistic relationships** between symptoms, risk factors, 
and outcomes — making it interpretable to clinicians and robust to missing data, which is common in 
real clinical settings.

Key advantages demonstrated in this project:

- Handles missing values natively without imputation
- Provides probabilistic outputs (e.g. "72% probability of long COVID") rather than hard labels
- Exposes which symptom combinations drive predictions — actionable for clinical decision-making
- Comparable predictive performance to decision trees with significantly better interpretability

---

## Model results

### 4-week prediction horizon

| Model | Key finding |
|-------|-------------|
| Bayesian Network (pgmpy) | Strong sensitivity to core symptom combinations. Handles missing data without degradation. Interpretable CPTs for clinical use. |
| Logistic Regression | Solid linear baseline. Effective on well-represented symptom clusters. |
| Decision Tree | Comparable accuracy to Bayesian Network. Less robust to unseen symptom combinations. |
| SVM | Captures non-linear symptom interactions. Higher complexity with marginal gain. |
| Neural Network (MLP) | Best raw classification performance. Lowest interpretability — not recommended for clinical use. |

### 6-month prediction horizon

| Model | Key finding |
|-------|-------------|
| Bayesian Network (pgmpy) | Persistent symptoms (fatigue, cognitive impairment) emerge as dominant nodes. Network structure differs meaningfully from 4-week model. |
| Logistic Regression | Performance degrades vs 4-week — long COVID signal is more diffuse and non-linear. |
| Decision Tree | Overfits at 6-month horizon without pruning. |
| SVM | More competitive at 6-month horizon than 4-week. |
| Neural Network (MLP) | Strongest 6-month performance. Ensemble with Bayesian Network explored for combined output. |

> Bayesian Network is recommended for clinical deployment due to interpretability and missing-data 
> robustness. Neural Network is recommended where raw predictive accuracy is the primary objective.

---

## Repository structure
