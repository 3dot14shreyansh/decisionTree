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



### Design of Decision Tree 

1. Based on the model's need, ***Gini Impurity*** or ***Imformation Gain*** are used to design an efficient decision tree. These are the methods from which a tree's overall structure and the partition of branches are decided.

2. Different decision tree algorithms utilize different impurity metric:
   1. For ***C.A.R.T.***, decision tree uses ***Gini Impurity*** as impurity matrics.
   2. For **I.D. 3** and ***C.4.5.***, decision tree uses ***Imformation Gain*** as impurity matrics.

3. Gini Impurity :-
   1. **Value range**:- Gini Impurity ranges from 0 to 0.5, where 0 denotes minimum impurity and 0.5 denotes maximum impurity.
   2. **Computational expense**:- Gini Impurity uses division, multiplication, addition and substraction for its calculation, hence ***Gini Impurity    matric is faster when compared to Imformation Gain impurtity matric*** (as it uses logarthms in addition to DMAS).
  
4. Imformation Gain :-  
   1. **Value range**:- Imformation Gain ranges from 0 to 1, where 0 denotes minimum impurity and 1 denotes maximum impurity.
   2. **Computational expense**:- Gini Impurity uses division, multiplication, addition and substraction for its calculation, hence ***Gini Impurity    matric is faster when compared to Imformation Gain impurtity matric*** (as it uses logarthms in addition to DMAS).
   
5. ***Example of Gini Impurity calculation*** :- 

Gini impurity calculation based on the feature 'Class' <br />
| Class | Stayed in hostel (No) | Stayed in hostel (Yes) | Total (n) | Probability (No) | Probability (Yes) |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 8 | 1 | 2 | 3 | 1/3 | 2/3 |
| 9 | 1 | 2 | 3 | 1/3 | 2/3 |
| 10 | 3 | 1 | 4 | 3/4 | 1/4 |
| 11 | 1 | 3 | 4 | 1/4 | 3/4 | 
   
Let us denote Gini Impurity for Class 8 as G(8), probability of student stayed in hostel as P(Y) and probability of student did not stayed in hostel as P(N) 

G(8) = $1 - P(Y)^2 - P(Y)^2$ <br />
G(8) = $1 - (2/3)^2 - (1/3)^2$ <br />
G(8) = 4/9 <br />
Similarly G(9) = 4/9 <br />
G(10) = 6/16 <br />
G(11) = 6/16 <br />

Now Gini impurity based on faeture (Class) of a dataset = G(Class)

G(Class) = ${(n_8 / T) * G_8} + {(n_9 / T) * G_9}$ +  (n<sub>10</sub> / T) * G<sub>10</sub> + (n<sub>11</sub> / T) * G<sub>11</sub> <br />
G(Class) = (3/14 * 4/9) + (3/14 * 4/9) + (4/16 * 6/16) + (4/16 * 6/16) <br />
G(Class) = 0.404 ---------------------------------------------------------------------------------------------------------------------- (i)

Gini impurity based on feature 'Gender'. <br />

| Gender | Stayed in hostel (No) | Stayed in hostel (Yes) | Total (n) | Probability (No) | Probability (Yes) |
| :---: | :---: | :---: | :---: | :---: | :---: |
| M | 3 | 5 | 8 | 3/8 | 5/8 |
| F | 3 | 3 | 6 | 3/6 | 3/6 | 

Let ua denote Gini Impurity for Gender 'Male' as G(M), probability of student stayed in hostel as P(Y) and probability of student did not stayed in hostel as P(N) 

G(M) = $1 - P(Y)^2 - P(Y)^2$ <br />
G(M) = $1 - (5/8)^2 - (3/8)^2$ <br />
G(M) = 0.47 <br />
for G(F) = 0.5 <br />
Therefore G(Gender) = 0.482 ---------------------------------------------------------------------------------------------------------- (ii)

from (i) and (ii) we get to know that G(Gender) > G(Class), hence the first split between the tree will be based on Gender and not on class. This is because we shall let the least impure branch as the node of the tree for better stability and therefore leading to efficient **Decision tree design**.
 
6.  ***Example of Imformation Gain calculation*** :- 
    1. Let E = Entropy, I.E. = Entropy Gain and P = Probability. <br />
       where E = -P{log(P)} and I.E. = E(before) - E(after)
    2. Calculation of Entropy for 'Class' 8, 9, 10, 11 from the above table
       E(8) = $- P_y{log(P_y)} + P_n{log(P_n)}$ <br />
       E(8) = -2/3{log(2/3)} + 1/3{log(1/3)} <br />
       E(8) = 0.918
       
       Similarly E(9) = 0.918, E(10) = 0.811 and E(11) = 0.811
       
    3. Calculation of Imformation Gain (I.E.) from Entropy :- <br />
       
       E<sub>(class)</sub> = (Number of instance from class / Total number of class) * E<sub> class </sub> <br />
       E<sub>(class)</sub> = $(3/14 * 0.918) + (3/14 * 0.918) + (4/14 * 0.811) + (4/14 * 0.811)$
       Therefore E<sub>(class_after)</sub> = 0.854
       
       E<sub>(class_before)</sub> = $-P_y * log_2(P_y) + P_n * log_2(P_n)$ <br />
       E<sub>(class_before)</sub> = $-8/14 * P(8/14) + 6/14 * P(6/14)$ <br />
       E<sub>(class_before)</sub> = 0.9854
       
       IE<sub>(class)</sub> = E<sub>(class_before)</sub> - E<sub>(class_after)</sub> <br />
       IE<sub>(class)</sub> = 0.9854 - 0.854  <br />
       IE<sub>(class)</sub> = 0.1314
       
       Similarly we can calculate IE<sub>(gender)</sub> <br />
       IE<sub>(gender)</sub>  = 0.01
       
       Therefore IE<sub>(gender)</sub> < IE<sub>(class)</sub>
7. Hyperparameter of Decision tree
       
       
       
