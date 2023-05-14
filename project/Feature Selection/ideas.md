1. amount_tsh - submodel
- 0 values are more likely to be non-functional
- can check how predictive the non-missing values are

2. keep recorded month as a separate feature apart from engineered age (time from created to recorded)

3. Region code + Region name? Maybe drop region name which is more general
- districts are a subfeature of region -> merge them?
- each region has actually a different lga so a merge of region name + lga + ward + subvillage could also make sense (maybe check which has higher predictibility?); they use ward for imputation but it's dropped for modelling (?)
- maybe assign a sorted number from 1 (lowest functionality) to 20k or sth (highest functionality) - target encoding

5. longitude and latitude 0s

6. big cardinality of funder and installer

7. population bins? missing values in population

8. permit is rather useless

9. extraction_class - some are rare; assing 'wind-powered' to 'motorpump' and 'rope pump' to 'handpump'

10. management_group - 88% of data is one class and the rest very small

11. For each column with missing values - does the value being missing predict water pump functionality? Could we create extra binary features for each column where values are missing?