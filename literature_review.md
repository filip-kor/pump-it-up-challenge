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

[A mixture Weibull proportional hazard model for mechanical system failure prediction utilising lifetime and monitoring data](https://www.sciencedirect.com/science/article/pii/S0888327013005165)

Doesn't really mention the parameter used. Might need to take another look at it.