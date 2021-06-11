# Insurance-cross-sell-prediction


## Exploratory Data Analysis:
1.	Customers who are interested in Vehicle Insurance almost all have driving license
2.	The indivisuals with region code 28 the highest as compared to the other ones
3.	Further we can analyze which region has highest intrested customers
4.	The variable perviosly insured almost has equal count
5.	Customer who are not perviosly insured are likely to be inetrested
6.	There is very less number of customers with vechicle age less than 2 years
7.	Customers with vechicle age 1-2 years are more likely to interested as compared to the other two
8.	Customers with vechicle damage(Yes and NO) are equally distributed with (50.48 % , 49.51 %)
9.	Customers with vechicle damage are more interested in Vehicle Insurance
10.	From the correlation plot we observe that policy sales channel has slightly greater correlation with Age variable, this may be the indication of multicollinearity. We can futher use VIF to check this
11.	Most of the data is collected from people living in region with code 28
12.	More than half of the data (52%) has samples with vehicle age between 1-2 years.
13.	We can't say from second graph that people with vehicle age between 1-2 years are more interested because other category '>2 years' has very few observations.
Model selection & feature Scaling:
LabelEncoder can be used to normalize labels. It can also be used to transform non-numerical labels (as long as they are hashable and comparable) to numerical labels. Transform labels back to original encoding. Transform labels to normalized encoding.
StandardScaler removes the mean and scales each feature/variable to unit variance. This operation is performed feature-wise in an independent way. StandardScaler can be influenced by outliers (if they exist in the dataset) since it involves the estimation of the empirical mean and standard deviation of each feature.

## Classification Models:

### KNN:
#### How to choose the optimal number of neighbors? And what are its effects on the classifier?
 The number of neighbors(K) in KNN is a hyperparameter that you need choose at the time of model building. You can think of K as a controlling variable for the prediction model.
 In the case of a small number of neighbors, the noise will have a higher influence on the result, and a large number of neighbors make it computationally expensive. Research has also shown that a small amount of neighbors are most flexible fit which will have low bias but high variance and a large number of neighbors will have a smoother decision boundary which means lower variance but higher bias.
 There is no need to train a model for generalization, That is why KNN is known as the simple and instance-based learning algorithm. KNN also not suitable for large dimensional data. consumes large memory

### Naive Bayes:
the calculation of Bayes Theorem can be simplified by making some assumptions, such as each input variable is independent of all other input variables. Although a dramatic and unrealistic assumption, this has the effect of making the calculations of the conditional probability tractable and results in an effective classification model referred to as Naive Bayes.

### Decision Tree, Random Forest & Gradient Boosting:
  These algorithms are tree-Based and they utilize rules such as series of inequalities. They basically rely on rules so that either doig normalization or not is not at all a problem. They are also not affected by monotonic transformations. Even if we do all these things then the remain same.

### SVM:
A kernel based and it is a semi-interpretable and semi-flexible. They turn the shape of decison boundary in how they want to tthat means they change the any shape into binary classification.


## Imbalanced Classification:
 
Undersampling the minority class gets you less data, and most classifiers' performance suffers with less data. An alternative, if your classifier allows it, is to reweight the data, giving a higher weight to the minority class and lower weight to the majority class.
 
#### So Why use something like SMOTE? 
Usually if the class you're interested in is rare, like finding defaults if predicting a credit score, a classifier giving 0-1 scores will say everyone doesn't default. In case we have an imbalanced dataset and we want to have the samples that contain same labels would actually help us derive better insights from the model else it will be very easy for the model to just predict the majority label whenever an unseen data is fed. Up-sampling and Down-Sampling both have their consequences. Up-Sampling will overfit as it just creates the duplicates and doesn't help the model while Down-Sampling can remove the data that can be very helpful for analysis. It is used to obtain a synthetically class-balanced or nearly class-balanced training set, which is then used to train the classifier. SMOTE isn't really about changing f-measure or accuracy... it's about the trade-off between precision vs. recall. By using SMOTE you can increase recall at the cost of precision, if that's something you want. The good results were based on both combining SMOTE and random under-sampling. This is because applying SMOTE to achieve an equal balance with the majority class is not necessarily the best case for the classifier and as your results show. 


## Hyperparameter Tuning: 
  Hyperparameters are all the parameters that can be arbitrarily set by the user before starting training (eg. number of estimators in Random Forest). Model parameters are instead learned during the model training (eg. weights in Neural Networks, Linear Regression). Hyperparameters control the parameters and direct them to reach the center which means finding either global maxima or global minima. Each algorithm has a predefine of tunning hyperparameters that are there and can’t summon them together. Some of the hyperparameter optimization techniques are manual search, random search and grid search, and genetic algorithm, etc.
According to a very popular book called “Applied Predictive Modelling” - “Many models have important parameters which cannot be directly estimated from the data. For example, in the K-nearest neighbor classification model … This type of model parameter is referred to as a tuning parameter because there is no analytical formula available to calculate an appropriate value.”

