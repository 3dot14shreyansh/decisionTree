# Decision Tree
Ensemble technique:
- Bagging
  - Linear Regression 
  - Logistic Regression
  - Random Forest
- Boosting 
  - Gradient boosted tree
  - Adoptive boosting
  - XG Boosting
- Stocking
### Ensemble Technique: 
Where we involve multiple decision maker. Here decision makers are machine learning algorithums.
### 3. Bagging:
-  (a) - Where multiple number of decision makers are invloved but all are of same type. There recomondation or output is averaged to arrive on to a conclusion.
- This technique uses ***Bootstrapping*** for splitting a dataset and then these are assigned to each decision maker (Machine learning algorithum). It should be noted split of dataset has  ***replacement nature***  of split. Another way of splitting dataset is known as ***Pasting (refer to .)*** which not deployed in bagging technique because of the ***high bais and high variance*** of the output. 
- The average of all decision maker is considered as the prediction of the respective algorithum.
- ***All the decision maker in bagging techinque should be same.*** For example if a data set is splitted in 3 sub-dataset and then bagging technique is applied, then each subset will be fitted with same machine learning algorithum.
- Disadvantage - Whenever a random forest algorithum is used in bagging technique, it is impossible to know the decision tree's branch and decision maker nodes in any way. ***This is the only disadvantage of Bagging technique.***
### Boosting:
Multiple decision makers will be involved with some less weightage and some with more weightage 
