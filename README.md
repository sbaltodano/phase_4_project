#  Identifying Pneumonia in Guangzhou Children Ages 0-5

Samantha Baltodano

![](Visuals/guangzhou-medical-center.png)

## Table of Contents
* [Overview](#overview)
* [Business Understanding](#business-understanding)
* [Method](#method)
* [Analysis](#analysis)
* [Predictive Models](#predictive-models)
* [Conclusions](#conclusions)
* [Contributors](#contributors)
* [Project Structure](#project-structure)


## Repository Links
* [Data](/Data/chest_xray)
* [Images](/Visuals)


## Overview
For this project I evaluated a dataset of 5,863 X-Ray images of children under the age of 5 in Guangzhou, China. 3,555 of the chrildren were infected with pneumonia and the remainder of children were not infected with pneumonia. I conducted industry research to better understand the business problem, cleaned and processed the X-Rays for classification, and utilized machine learning models such as XGBoost, Random Forest, and Convulutional Neural Networks to identify whether or not a child had deveolped pneumonia. I then compare their performance on unseen images to decide on a final predictive model that optimized recall, due to the detrimental effects a false negative diagnosis would have on a child's mortality. My final model utilized `keras` Convolutional Neural Network and achieved a recall of 94%.


## Business Understanding

I have been employed by the Guangzhou Women and Children's Medical Center to identify areas of concern in hospital performance and determine creative solutions to address the problems I have found. 

Pneumonia is the single leading cause of death globally among children under 5 years of age accounting for over [800,000 deaths annually](https://ourworldindata.org/child-deaths-from-pneumonia). In China specifically, it is estimated that 2.5 million people a year are diagnosed and pneumonia is the cause of 17% of all child deaths in the nation. As alarming as these numbers seem, they draw added concern when you are aware that pneumonia mortality is completely preventable. This raised the question: why are so many infants dying from a curable illness? 

![](Visuals/causes.png)



## Method

I first cleaned and processed my data to prepare for modeling. Given the severe class imbalance between the X-Rays of infected lungs and the X-Rays of healthy lungs, have oversampled using SMOTE to ensure that my minorty class is properly represented. If my model just predicted that a child had pneumonia every single time, I would have a model that was accurate 74% of the time with a recall of xx%. As I move forward with my modeling This is the number that I will need my model to beat. 

#### Treating Type Errors
In dealing with type errors, i.e the balance between false negatives and false positives in my models, I decided that it would cause more harm to incorrectly diagnose a child as not having pnuemonia when they actually have been infected (false negative) than it would be to diagnose a child with no pnuemonia as having pnuemonia (false positive). Given the expedient onset of pnuemonia syptoms and possibly death, I will be optimizing recall so as to minimze my false negatives moving forward.

## Analysis
Time is the biggest enemy to a child diagnosed with pneumonia. In severe case, the victim can die within hours, the lungs fill with fluid and the patient effectively drowns. The Guangzhou Women and Children's Medical Center must diagnose and treat these infants as quickly as possible to prevent unneccessary deaths. Unfortunately, China like so many other countries are facing a severe physician shortage. It is estimated that by the end of the decade, in a world where we will need a sum total of 80 million physicians globally to properly treat the growing population, the worl will be short some 18 million. As it stands right now, China has approximately 2 physicians for every 1,000 members of their population. Depicted below is the physician to population ratio for China against the top 4 countries with the best ratios. Portugal and Denmark have around 2.5x more physicians to treat their populations than China does and those countries too are considered to be in a physician deficeit. 

![](Visuals/doctors.png)

Current physicians are overworked, fatiqued, and burnt out trying to adequately treat the growing volume of patients. It is not enough to say that we need to increase the physician to population ratio when globally, the majority of countries are facing a similar struggle. Luckily the answer is simple, cheap, and has already been created: Artifical Intelligence. On average, machine learning disease and illness diagnoses classifiers are just as accurate as radiologists, accurately classifying patients 87% of the time comapred to the 86% accuracy of the human eye. This prompted me to build a machine learning classifier to diagnose patients under 5 as having or not having pneumonia. My method went as follows.

## Predictive Models

As a final model, I would recommend either the Gradient Boost or the Decision Tree Classifier. The final Gradient Boost model had a higher accuracy overall at 94% with a recall of 74%. On the other hand, the best Decision Tree Classifier had a lower accuracy of 90%, but a higher recall at 83%. Based on my initial recommendations to reduce type 2 errors, the best Decision Tree Classifier my be a better fit.


## Conclusions

Based on my feature analysis and the results from my final machine learning program, it is clear that customer service calls and day call charges have the strongest impact on customer satisfaction. SyriaTel can do the following to reduce churn:

1) Track metrics from customer service calls. Are clients calling about the same issues? Are these issues with billing? Service? Once we know why these clients are calling we can better alleviate their pain by addressing and correcting these issues.

2) Re-evaluate pricing structure for day calls. Consider a tiered pricing structure past a certain dollar amount 

After implementing the model onto our current database of clients, I would reccommend reaching out to the 'likely to churn' clients individually and discussing their experience with the company and identifying their pain points.


## Contributors
- Samantha Baltodano <br>
    Github: [sbaltodano](https://github.com/sbaltodano)<br>
    
## Project Structure
```
├── project.ipynb
├── README.md
├── visuals
└── Data
    ├── chest_xray
    └── pickles
```
