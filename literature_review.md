## Leaderboard

Best result: 0.8294
￼
## Discussion

- People use Random Forests

- A lot of feature transformations

## Other Approaches

### Solution 0

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

### Solution 1

https://github.com/dipetkov/DrivenData-PumpItUp

**Score:** 0.821

**Language:** R

**Classification method:** Random Forest

### Solution 2

**Score:** 0.8205

**Classification method:** Random Forest

My approach is very simple and uses RandomForest Classifier with 200 estimators. I ignored “wpt_name”, “subvillage”, “funder”, “installer” from the dataset.

### Solution 3

Logic: https://zlatankr.github.io/posts/2017/01/23/pump-it-up

Code: https://github.com/zlatankr/Projects/tree/master/Tanzania

**Score:** 0.8181

**Language:** Python

**Classification method:** Random Forest

I briefly tried a couple other algorithms (Logistic Regression, SVM, AdaBoost, XGBoost), but none of them returned good results for me. I know that others have used XGBoost to get good results, but the model was taking way too long to run on my machine, so I couldn’t commit enough energy to it.

As far as over-fitting, I was getting some of it initially; however, I just found a bug in my code yesterday, and once I fixed it, not only did the overall score go up, but the over-fitting disappeared (in fact, my test scores were higher than my cross-validation score).

### Solution 4

**Score:** 0.8125

Cleaned a little bit. Replaced some 0 and NaN
Created 1 new feature
Transformed all categorical feature with <100 cats
Dropped some highly correlated feature
Used Random Forest & Gradient Boosting Tree Army. The Army performed much better
Watched out for overfitting

Remember, when choosing your model: split your labeled data into train (which can be further splitted for crosvalidation) and test set. But in the end retrain your best model on the entire labeled set for final prediction of unlabeled data
Also please make sure to double check that your labeled set used for training and unlabeled set have identical set of independent features!!

### Solution 5

https://github.com/NicolasGrimault/Project-IA

**Score:** 0.7991

**Language:** Python

**Classification method:** Random Forest

Well documented