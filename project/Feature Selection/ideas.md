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

12. management group and scheme management - target encoding?
- scheme_management is associated with extraction_type - private operators prefer submersible extraction_type and VWC prefer gravity
- "management" and "scheme_management" are very misleading, they have some similar classes but are sometimes mixed; "management" should be dropped

13. "Payment" and "Payment type" are the same. drop one.

14. quality group can depend on a season. good idea to plot the quality with the recorded month to check if thats true and drop (or engineer) "quality_group" it if thats the case.
- water_quality is basically the same with some salty and fluaride further separated, but the resulting classes have very few datapoints. better leave "quality_group".

15. quantity_group also needs a check between redorded month. can be seasonal.
- quantity has the exact same information -> can be dropped

16. "source type" and "source class" should probably be dropped. they're less detailed versions of "source".
- merge "unknown" and "other"