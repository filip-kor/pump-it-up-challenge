## Solution 1

https://community.drivendata.org/t/share-your-approach/65/26

Solution is currently in 8th place

**Score**: .8247

**Software Tools**: XGBoost package in R

**Brief Model Description**: Ensemble of 11 XGBoost models with equal weight to each solution

### Feature Selection
The original data set contained 40 variables. I reduced it down to 26 variables by removing variables that were similar/duplicates of other variables.

### Feature Engineering
For the construction_year and gps_height I used the median of them to replace the 0 values.

I first built a model using all of the available variables. I then removed variables that were duplicates and tested the model to understand how it changed the performance. I also used the xgb.importance function to understand the variable’s influence on the model.

I used an ensemble of XGBoost 11 XGBoost models only updating the random seed for each iteration. This turned out to be more accurate than a single XGBoost model with a large number of iterations and a low eta (learning rate).

I think that there is still some room for improvement with this model. I removed the installer variable but it may have predictive power if you could reduce the number of factors by grouping some of them together. Please share any suggestions you have on this as I wasn’t sure about the best way to do it.

Here’s is a link to the R code https://github.com/MattBrown88/Pump-it-Up-XGBoost-Ensemble 402.

Please let me know if you have any questions on my methodology.