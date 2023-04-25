---
title: Weekly Diary - Predicting COVID using BN
author: Andrew Opeta, Christine Pascual
date: March - November, 2023
bibliography: references.bib
---

## Weekly Diary

### Week 1: March 6, 2022
#### General:
+ time management
+ weekly meeting <b>Wednesday 12:00-13:00</b>
    - meeting id: 581 998 320
+ data might be available only in Spring
    - needs NPC and WWC
+ main aim is for detecting Long COVID given's patient symptoms
+ study how well the model works in [1](#1) in terms of Bayesian Model
    - change the network in terms of the data that we have
    - might not have the same data to work on
+ search for packages on python
#### Andrew:
+ Reading: [3](#3)
  - The purpose of the model is utilising BN to calculate the probability of having a serious infection after one has had covid19 and also probability of having covid given initial predictor variabbles
  - Variables for the BN were determined using the CDC’s COVID-19 Research Articles Downloadable Database (Centers for Disease Control and Prevention, 2020), \cite{centers for disease control and prevention_2020} , with the most appearing symptoms being given higher priority, a likelihood ration is calculated and symptom variables with a ratio greater than 1 are given high consideration when predicting the presence of covid infection.
  - The model is also made to be dynamic, and the predicting variables can be changed with respect to new received information
  - Symptoms are first identified via a frequency analysis of the papers in the covid 19 database 
  - Each symptom has a prior probability for a given disease associated with it 
  - Obvious symptoms that do not have a likelihood score greater than one, such as fatigue were also considered as they appear frequently in research articles 
  - Symptoms that are similar across different diseases were noted and if the RT-PCR test is negative then probabilities would deem it positive for a different disease away from covid 
  - AGENARISK was used to carry out analysis, it allows for dynamic variables
  - The contributors to covid 19 infection were discovered to be cough, loss of appetite, shortness of breath, chest pain and chills 
  - elevated respiratory rate and reduced oxygen saturation had the highest relative importance to severe infection 
  - There are other factors that if present e.g. increased respiratory rate show presence of non covid infections
  - They also have certain predictors that if present and have a high probability there is a possibility of being a false negative, this means that this can affect the system once it is fully implemented
#### Christine:
- 

### Week 2: March 13, 2022
#### General:
+ GitHub link created
+ Bibtex formatting learning
+ made a weekly diary (but in MS Word)
+ email authors for a copy of the data set: no response to date (1/04/23)
+ find more papers that has something to do with predicting COVID diagnosis using machine learning
+ try to find papers with code or data set we could temporarily work on
+ search on python libraries that deal with Bayesian Network:
    + try Kevin Murphy's works
    + update: We're using pgmpy in PGM which is of Kevin Murphy
#### Andrew:
- One of the symptoms of COVID 19 is a loss of smell, hence the author of this paper develops a Bayesian network that can identify olfactory impairment as an early warning sign for COVID 19. Olfactory function will be a key variable used in the computations as we attempt to predict Covid 19 using a Bayesian network. A created self-testing kit and application Gaussian mixed classifier are used to calculate a patient's anosmia score. This score is then employed as a predictive variable in our Bayesian network for covid19. To make this work, we also need to know how many people in the population have previously had olfactory impairment under various conditions.
- Based on a low-cost (about USD 0.50 per test), six-odor olfactory identification kit, they designed a quick psychophysical olfactory test (KOR) hosted on a web platform for automated reporting and traceability. Based on test results, they developed a Bayesian Network (BN) model that takes other symptoms into account to detect COVID-19, as well as an anosmia score, a classifier for olfactory impairment.

- They used used two populations to train and validate the BN model: healthy (asymptomatic) mining workers (n = 1,365; 1.1% COVID-19 prevalence) and suspected COVID-19 cases in five healthcare facilities (n = 926; 32% COVID-19 prevalence).
- By using an RT-PCR technique, COVID-19 was evaluated in each subject. In the healthcare sample, the BN model predicted COVID-19 status with 76% accuracy (AUC=0.79 [0.75 0.82]), and in the miner sample, it did so with 84% accuracy (AUC=0.71 [0.63 0.79]).
#### Christine:
-

### Week 3: March 20, 2022
#### General:
+ proposal
    + Program of work: weekly for Autumn, every 4 weeks for Spring(PPB)
    + submit one each with (slightly) different objectives
+ search for more related paper on Google Scholar
    + COVID prediction
    + Bayesian Network
    + Bayesian Network Prediction in python
    + etc
+ Summarise papers that you have read and take note if it has codes/data available
+ check medxriv too, some papers might just be in Archive 
#### Andrew:
- Here, we have a model that forecasts how cvid 19 status will affect an individual and how severe it might be. In order to produce an outcome, the BN is first filled with fundamental probabilities, such as the likelihood of being male, and then it descends to probabilities of pre-existic circumstances. BN is important since it allows us to understand the connections between the various variables. It was challenging to understand why the majority of Asian or Black persons suffered from COVID, but a BN showed that there were several characteristics related to this, including housing situation and employment environment.
- This study primarily focuses on background characteristics that should be entered into the BN, like race, occupation, and living situation. The probability of the parent and child nodes connected to the given node are impacted by entering observations into the nodes.
- The most significant element in determining exposure to the virus was occupation, but it's also vital to consider ethnicity because it has an impact on both the work and the living situation.
- Several additional probability, including pre-existing medical issues, religion, and living circumstances, might be influenced by ethnicity.
- The relationship between ethnicity and age is significant and serves as an illustration of the Simpson's paradox, which states that when qualities of a bigger group are considered individually, they lose their significance.
- This particular paper properly utilises Bayesian networks with the use of the agenarisk software, we will however not focus much on it as it does not predict covid19 using the person's symptoms but rather other conditions like environment, it was an informative read on the use of Bayesian Networks
#### Christine:
-

### Week 4: March 27, 2022
#### General:
+ proposal should first aim for (just) COVID symptoms and network model
+ work(search) on binary probabilies of some nodes/symptoms
+ find out how to "group" the symptoms similar to the paper
+ <a href="https://aispace.org/bayes/">AISpace </a>

#### Andrew:
-
#### Christine:
-

### Week 5: April 3, 2022
- #### General:
  + look for more Long COVID related papers
  + Search for prior probabilities of symptoms especially parent nodes
  + make the diary in `md` file for smaller file size
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 6: April 10, 2022
- #### General:
  + Latex Notes:
    - \userpackage{acronym}
    - \newacronym{LOWERCASE LABEL}{UPPERCASE LABEL}{THE FULL TERM}
    - \acrocite{}
    - \newcommand(\covid){COVID }
  + Finish up the Project Proposal and share it for review

- #### Andrew:
  + We implemented a Bayesian Network using the symptomatic dataset.
  + we formed it on the basic Naive Bayes level and had parent nodes as  smoker,musle pain,fever,cough , breathing difficulties, fever, Age and gender with our target variable being COVID.
  + Continuous research for a new dataset continued and we found one that gave a general summary for the symptoms of long covid and the general duration it takes.
  
- #### Christine:
  - 

### Week 7: April 17, 2022
- #### General:
  + There will be a presentation towards the end of the semester (combined with PPB students)
  + Produce a graph of the model
  + Set the treshold for determining the value of the target: could be initially set at 50-50
  + Find the medically accepted age grouping
  + Find out the memory capacity that our PC could handle - try converting it to python from notebook to lessen the load
  + LEARN MEMORY ALLOCATION
  + UPDATE GITHUB
  + Allign the project plan with weekly progress!
  + https://www.kaggle.com/datasets/hemanthhari/symptoms-and-covid-presence - could be used as a practice for the sake of modelling, but find a more reliable data set.
- #### Andrew:
  + Determined the procedure to conver our ipynb files to.py
  + we utilised the psutil function to determine the amount of memory used by code.
  + Printing out the appearance of the network using networkx and matplotlib.pyplot libraries
  + we selected a proper partition for the age groups , we will then group our data based on this partitioning,
<15,15-44,45-64,66-74,>74
  + Determining the prior probabilities for given parent nodes such as diabetes and hypertension for the network we are going to implement
  + Added more edges to the orginal network, taking it from the Basic Naive Bayes to a more advanced network.
- #### Christine:
  - 

### Week 8: April 24, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 9: May 1, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 10: May 8, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 11: May 15, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 12: May 22, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 13: May 29, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 14: June 5, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 15: June 12, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 16: June 19, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

### Week 17: June 26, 2022
- #### General:
  - 
- #### Andrew:
  - 
- #### Christine:
  - 

<!-- add weeks until needed -->

## References
- [Reference Guide](http://example.com) - Author, Year, Title of the article/book/etc., Publisher, Location.

-

