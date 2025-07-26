# Predicting COVID-19 Using a Bayesian Network

This project demonstrates how a Bayesian Network can be used to predict COVID-19 status and long COVID risk using clinical symptoms, demographic features, and comorbidity data. It was developed as part of a postgraduate data science capstone at Western Sydney University and showcases technical and analytical expertise in probabilistic modeling.

---

##  Overview

Bayesian Networks are powerful probabilistic graphical models capable of handling uncertainty, incomplete data, and causal relationships. This project leverages these properties to:

- Predict the probability of COVID-19 infection based on observable symptoms and background factors.
- Estimate the likelihood of developing long COVID using initial symptom profiles and comorbidities.

The model was constructed using real-world research data and open-source datasets, and will be tested on anonymized hospital data in future phases.

---

##  Objectives

- Build a Bayesian Network using Python and `pgmpy` to model COVID-19 infection probability.
- Extend the model to predict long COVID risk using inferred post-infection symptoms.
- Compare model performance with traditional ML approaches.
- Evaluate how the model handles missing or incomplete data.
- Document a reproducible, modular framework for Bayesian inference in healthcare.

---

##  Core Research Questions

- Which symptoms and risk factors most accurately predict COVID-19?
- Can the severity or persistence of symptoms (i.e. long COVID) be predicted from initial observations?
- How do demographic and occupational factors influence infection risk?
- Can Bayesian Networks handle uncertainty and still yield robust predictions in medical settings?

---

##  Methodology

###  Literature Review
A deep dive into prior work using Bayesian networks in medical diagnostics, especially those applied to infectious diseases like COVID-19. Key models were drawn from peer-reviewed literature including Eyheramendy et al. (2021) and Butcher & Fenton (2020).

###  Data Sources
- Publicly available dataset from [Eyheramendy et al. (2021)](https://www.medrxiv.org/content/10.1101/2021.03.08.21252800v1)
- Future data pipeline planned using anonymized patient data from Liverpool Hospital, Sydney

###  Data Preparation
- Majority of variables are binary (symptom present: 1, absent: 0)
- Additional features: demographic attributes (age, sex, occupation, household size), comorbidities (e.g. diabetes, organ transplants)
- Missing values allowed due to the inherent flexibility of Bayesian networks

###  Model Architecture
- Built using `pgmpy` in Python
- Nodes represent:
  - **Symptoms** (e.g., fever, cough, nausea, headache)
  - **Demographics** (e.g., age, sex, occupation)
  - **Comorbidities** (e.g., diabetes, cancer)
  - **Target Outcomes**: `COVID-19`, `Long COVID`
- Conditional Probability Tables (CPTs) were constructed from literature-based prevalence data and empirical frequency analysis
- Structural learning was manually curated based on domain knowledge

### ⚙ Tools & Libraries

| Tool           | Purpose                                      |
|----------------|----------------------------------------------|
| `pgmpy`        | Bayesian Network modeling & inference        |
| `pandas`       | Data processing and exploration              |
| `networkx`     | Graph visualization of Bayesian structure    |
| `matplotlib`   | Exploratory visualizations                   |
| `AISpace2`     | Initial prototyping of network logic         |
| `AgenaRisk`    | (Planned) Advanced probabilistic reasoning   |

---

##  Expected Outcomes

-  A trained Bayesian Network model to predict COVID-19 and long COVID
-  Performance comparison with ML models (e.g., Decision Trees, Logistic Regression)
-  Insight into false positives/negatives and their effect on hospital resource usage
-  Adaptation to incomplete and dynamic patient data
-  Publishable documentation and final academic report

###  Model Performance (Preliminary)
The initial model using the Eyheramendy et al. dataset shows strong classification performance with high sensitivity to core COVID-19 symptoms (fever, cough, loss of smell). The Bayesian Network:
- Effectively handled missing data points without performance degradation.
- Provided interpretable probabilistic outcomes for clinicians and decision-makers.
- Demonstrated comparable performance to decision trees in early evaluations, with improved interpretability.

---

##  References

- Butcher & Fenton (2020) - *Bayesian network for predictive diagnosis of COVID-19*
- Eyheramendy et al. (2021) - *Bayesian model with olfactory testing*
- CDC & WHO - COVID-19 symptom data
- Wang et al. (2014) - *Bayesian networks in cancer metastasis prediction*

---

##  Connect with Me

📇 [LinkedIn Profile](https://www.linkedin.com/in/your-linkedin-handle)

---

##  License

This repository is for academic and portfolio use only. Reuse or distribution should credit the original source and institution.
