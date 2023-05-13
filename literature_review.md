## Leaderboard

Best result: 0.8294
￼
## Discussion

- Exploratory data analysis: https://rpubs.com/lovepeacejoy404/tanzania_wells

- People use Random Forests

- A lot of feature transformations

- Mysterious 90.6% neural network https://community.drivendata.org/t/90-6-may-need-the-help-of-a-stronger-computer/2426

## Other Approaches

### **Solution 0**

https://github.com/MattBrown88/Pump-it-Up-XGBoost-Ensemble

**Score:** 0.8247

**Language:** R

**Classification method:** XGBoost (ensemble of 11)

Brief Model Description: Ensemble of 11 XGBoost models with equal weight to each solution

Feature Selection
The original data set contained 40 variables. I reduced it down to 26 variables by removing variables
that were similar/duplicates of other variables.

Feature Engineering
For the construction_year and gps_height I used the median of them to replace the 0 values.

I first built a model using all of the available variables. I then removed variables that were duplicates and tested the model to understand how it changed the performance. I also used the xgb.importance function to understand the variable’s influence on the model.

I used an ensemble of XGBoost 11 XGBoost models only updating the random seed for each iteration. This turned out to be more accurate than a single XGBoost model with a large number of iterations and a low eta (learning rate).

I think that there is still some room for improvement with this model. I removed the installer variable but it may have predictive power if you could reduce the number of factors by grouping some of them together. Please share any suggestions you have on this as I wasn’t sure about the best way to do it.

### **Solution 1**

https://github.com/dipetkov/DrivenData-PumpItUp

**Score:** 0.821

**Language:** R

**Classification method:** Random Forest

### **Solution 2**

**Score:** 0.8205

**Classification method:** Random Forest

My approach is very simple and uses RandomForest Classifier with 200 estimators. I ignored “wpt_name”, “subvillage”, “funder”, “installer” from the dataset.

### **Solution 3**

Logic: https://zlatankr.github.io/posts/2017/01/23/pump-it-up

Code: https://github.com/zlatankr/Projects/tree/master/Tanzania

**Score:** 0.8181

**Language:** Python

**Classification method:** Random Forest

I briefly tried a couple other algorithms (Logistic Regression, SVM, AdaBoost, XGBoost), but none of them returned good results for me. I know that others have used XGBoost to get good results, but the model was taking way too long to run on my machine, so I couldn’t commit enough energy to it.

As far as over-fitting, I was getting some of it initially; however, I just found a bug in my code yesterday, and once I fixed it, not only did the overall score go up, but the over-fitting disappeared (in fact, my test scores were higher than my cross-validation score).

### **Solution 4**

**Score:** 0.8125

Cleaned a little bit. Replaced some 0 and NaN
Created 1 new feature
Transformed all categorical feature with <100 cats
Dropped some highly correlated feature
Used Random Forest & Gradient Boosting Tree Army. The Army performed much better
Watched out for overfitting

Remember, when choosing your model: split your labeled data into train (which can be further splitted for crosvalidation) and test set. But in the end retrain your best model on the entire labeled set for final prediction of unlabeled data
Also please make sure to double check that your labeled set used for training and unlabeled set have identical set of independent features!!

### **Solution 5**

https://github.com/NicolasGrimault/Project-IA

**Score:** 0.7991

**Language:** Python

**Classification method:** Random Forest

Well documented

### **Solution 6**

https://github.com/mldataanalysis/Water-Pump-Classification

**Score:** 0.7318, 0.8073, 0.6936

**Language:** R

**Classification method:** Support Vector Classifier, Gradient Boosting Classifier, XGBoost

In the first notebook I explored the data set and made it suitable for running models on. The first model I attempted was a Linear Support Vector Classifier which achieved a score of 0.7318 (the scale is from 0 to 1 with 1 being a perfect score). Then I used a more Gradient Boosting Classifier which gave the best score out of all the models I used: 0.8073. Finally, I used XGBoost which produced a score of 0.6936.

### **Solution 7**

Medium articles: https://medium.com/@brendaloznik_48450

Code: https://github.com/BrendaLoznik/waterpumps

**Score:** 0.8235

**Language:** Python

**Classification method:** Random Forests

### **Solution 8**

**Score:** 0.8240

**Language:** Python

**Classification method:** EDA + CatBoost

## Papers

[Fault detection for circulating water pump using time series forecasting and outlier detection](https://ieeexplore.ieee.org/abstract/document/7886095)

Based on more technical features like vibration signal, oil wear particle analysis, temperature, current, and voltage.

[Prediction of Bearing Fault Effect on the Hydraulic Performances of a Centrifugal Water Pump](https://link.springer.com/article/10.1007/s42417-022-00490-3)

Predicting the effect of a bearing fault.

[Application of Data-Driven Yield Surface to Prediction of Failure Probability for Centrifugal Pump](https://link.springer.com/chapter/10.1007/978-3-030-75890-5_17)

Can't access. Predicting probability of failure-free operation.

[Benchmarking of Supervised Machine Learning Algorithms in the Early Failure Prediction of a Water Pumping System](https://link.springer.com/chapter/10.1007/978-981-16-4126-8_48)

Can't access. Benchmarking SVM, Random Forest and ANNs. RFs the best.

> This paper performs a comparative analysis of three classification algorithms, random forest, support vector machines, and artificial neural networks, to predict failures in a water pumping system

Dataset includes 55 sensor-based features like pressure, water level and flow. 

[A mixture Weibull proportional hazard model for mechanical system failure prediction utilising lifetime and monitoring data](https://www.sciencedirect.com/science/article/pii/S0888327013005165)

Doesn't really mention the parameter used. Might need to take another look at it.

[Pump it Up: Data Mining the Water Table](https://www.researchgate.net/publication/345888631_Pump_it_Up_Data_Mining_the_Water_Table)

Weird paper but its exactly about this dataset. DO NOT CITE THIS.

[A Novel Approach Based on Machine Learning and Public Engagement to Predict Water-Scarcity Risk in Urban Areas](https://www.mdpi.com/2220-9964/11/12/606)

Predicting water shortage risk using weighted combination of differebt ML models: support vector machine (SVM), multilayer perceptron, K-nearest neighbour, random forest and naïve Bayes. It's not focused on water pumps but it uses some interesting features:
- Age of the Network Pipes (C5)
- Capacity of Reservoir (C6)
- Population (C8)

Good description of feature reduction methods - can help.

> three ranking algorithms, InfoGainAttributeEval, GainRatioAttributeEval and CorrelationAttributeEval

[A review of water quality factors in water main failure prediction models](https://watermark.silverchair.com/wpt0170060.pdf?token=AQECAHi208BE49Ooan9kkhW_Ercy7Dm3ZL_9Cf3qfKAc485ysgAAA4IwggN-BgkqhkiG9w0BBwagggNvMIIDawIBADCCA2QGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQM2V_0l-hLzF7SewjuAgEQgIIDNVBw2aNK0WQmflAcujKnGEbUFNJ6xGInMezs2SuBZWjdHd0s5O4n_K9_j5m22J-XPcGiM9W4Jlk_8zXBpJScEcFeNS448Tfm6jiHyzymxCLtzq7ZFw1xhec8GIwVQE15A_Ge5ZqrFVGM6AyJNWHwBwETjxQ6GN1t3QwI-No3qjX19coE7OiwGmkSMJT5hu0nGui7q56WKRU-b_fazeesBGl0cBs4ZjiHIiJUK18ERJZcqDrU1u0x41qqB5Buf5qraFBWHhP9lvir5os_Qhcj9zVDPW3LL-SL130-8QwRlntg-JNuW6_pRCWoD7FdYX4ywQVfWzI0LvZ9F3HfBJOD3032J--goooZzYwrcw89bfsrVmJW3Eu4DOqtzg3JTdBsdNCc_se_WgHE5l09tYOGLHEUwJ3ClfmDeOmx7lJhV4Fpa03TqT9GQQxUnOc5IXHGS0davmrGAiIVOzfPNYMiryVaUyqxQMCQb1YGz84hN31Geo16cXyKEaNwVTSxQnyqLQAWLjOmahH05MNgo0aBY2SBXeph5sdoYjJgtO_oe7bARN7N3jGn9LthrXwuDUkDWCiIgLr6rjr8tTsLo4KzEHFknWTEMYJP4vG50TZOAnxREgEEKfhuTFUw4RBhsijq3iBX7EtMKVeQpHskREBdhDQYIZ6ODFOBMCLBJ6BSJpl5opxoQSsD10APzfhqoCa2cd3BvBfH1sAQWwoQ-qKQu-98aZ28UEf4B5L93wIn21GY2Uc_JikbPAcoqa2fGpVRQRcgjrubalptCcPbS1nYQuWILTQKStQSZUMoPhbvg0O3DWqEPcu8vXn5XMi0m6GWtAypZVDPP07po3YEvUY-uOx3PHWvruJKB0y4uIjTtA-lRbDlSt41fZ-2dUbB8JrE9JLyQf-edzVASTZBO71F08jSu1Hwc1Pz0QcIxpOfM97AzzgeI-kAYw52zWSbWcWkq0f9VnzTq8SwTvf4yMLRfoYC9e-QrvlRFZOt4WJXEFoyotRCwyv3IWKmBRpvu4-HJzT5ZaRjkpoP-wk1ULcth3eDg0MW7O8u41lZWzTEjSwyeJHCXZDpYwK1BS9L4BBsSRyLsVHw)

A review of papers modelling failure prediction based on water quality factor like pH, temperature, etc..

Water quality has a significant impact on pumps failure, but we don't have any information about this.

> Most research papers on water main prediction models include only physical factors (e.g., pipe material, diameter, age, and length). Although it has been observed that water quality is a significant factor in making decisions regarding replacement or rehabilitation of water mains (...).

relationship between chlorine consumption and corrosion rate

> CI (uncoated) pipes, not plastic ones, are associated with the most chlorine consumption. Tamminen et al. (2008) and Yamini & Lence (2007) also reported that chlorine consumption is higher in CI than PE networks.

But we don't really have info about pipe materials in our study.

**[Predicting the Status of Water Pumps Using Data Mining Approach](https://ieeexplore.ieee.org/document/7872890)**

Literally the same dataset. Uses XGBoost. The achieved result show 80.38% in accuracy.

> Recursive Feature Elimination (RFE) is also proposed to select the important features of the data to obtain an accurate model

[Predictive Analytics for Smart Water Management in Developing Regions](https://ieeexplore.ieee.org/document/8421404)

The same dataset + similar from Nigeria.

> we first perform feature engineering to select relevant features, use them to develop the XGBoost and Random Forest ensemble learning models, and then perform extensive feature analysis to identify the most predictive features

They use precision, recall and f1. They try to predict different features, which can give more information about their importance.

[Water Pipe Failure Prediction and Risk Models: State-of-the-Art Review](https://cdnsciencepub.com/doi/10.1139/cjce-2019-0481)

Awful formatting. I'll come back to it later.

[Integrated Performance Assessment Model for Water Networks](https://ascelibrary.org/doi/10.1061/%28ASCE%29IS.1943-555X.0000419)

Idk if its useful. Needs a deeper review.

[Comparative evaluation of machine learning models for groundwater quality assessment](https://link.springer.com/article/10.1007/s10661-020-08695-3)

comparing ANNs, SVMs and XGBs to predict the nitrate and pesticide contamination levels in groundwater wells. Also examines oversampling techniques.

[SWaP: Probabilistic Graphical and Deep Learning Models for Water Consumption Prediction](https://dl.acm.org/doi/10.1145/3360322.3360846)

predicts water consumption. probably not useful.

[Know-what, know-when and know-how: A web and mobile-based android application for early detection of pump failures in rural water supply projects, Tanzania](https://iwaponline.com/wpt/article/17/11/2447/91797/Know-what-know-when-and-know-how-A-web-and-mobile)

A new app to help predict failures. Can be useful to mention background about the issue.

[Failure Prediction of Mine De-watering Pumps](https://www.researchgate.net/publication/325494442_Failure_Prediction_of_Mine_De-watering_Pumps)

Uses a Weibull distribution model, which is used for many product failure prediction methods apparently. Cannot access full text.

[Failure Prediction of Municipal Water Pipes Using Machine Learning Algorithms](https://link.springer.com/article/10.1007/s11269-022-03080-w)

Random Forest - Synthetic minority oversampling performed best, followed by undersampling, an imbalanced method, and oversampling. All RF methods outperformed a logistic regression.

[Fault diagnosis and classification of water pump using adaptive neuro-fuzzy inference system based on vibration signals](https://journals.sagepub.com/doi/epub/10.1177/1475921715591873)

Uses ANFIS - neural networks used to optimise a fuzzy logic system. Probably useless.

[https://www.academia.edu/9859291/Introduction_Classification_AND_Selection_OF_Pumps_W_C_Krutzch_Paul_Cooper_Chapter_1_](Introduction: Classification AND Selection OF Pumps W. C. Krutzch Paul Cooper)

Complete bullshit

