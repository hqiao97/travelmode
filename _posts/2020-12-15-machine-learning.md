---
title: "SkLearn: Machine Learning Methods for Travel Mode Prediction"
date: 2020-12-15
published: true
tags: [machine learning, SkLearn, altair]
excerpt: "Comparing 4 machine learning methods for predicting mode choice."
altair-loader:
  altair-chart-1: "charts/ml_f1_score.json"

toc: true
toc_sticky: true
---
## Introduction
In this section, we looked into the 2017 US National Household Travel Survey data to predict travel mode choices of trips using various social-economic factors, trip factors and land use factors through adopting four machine learning methods: logistic regression,
random forest, bagging, boosting. We learned about random forest in class and we were able to apply the techniques of implementing a random forest classifier to the other models reading through the SkLearn documentation.

## Data
The data used in prediction is the [2017 US National Household Travel Survey (NHTS)](https://nhts.ornl.gov/).
The NHTS is conducted by the Federal Highway Administration and it is the authoritative source on the
travel behavior of the American public. This survey includes four datasets: trip dataset, person dataset,
household dataset and vehicle dataset. Trip dataset contains 923,572 entries. 

## Feature Engineering
Features we selected fall into three categories: socio-economic characteristics, trip characteristics and land
use characteristics. Socio-economic characteristics include age, race, gender, education attainment, occu-
pation, home ownership, and health status etc. Trip characteristics include trip duration, trip distance, trip
purpose, count of people on trip, travel day of the week etc. Land use characteristics include urban area
classification, population density, job density and housing density etc.
![confusion_matrix_lr]({{ site.url }}{{ site.baseurl }}/assets/images/ml_features.png)

## Logistic Regression
The logistic regression model was implemented using the scikit learn library. The model did not do a good job with testing mean square error of 0.479 and testing accuracy of 0.89. Especially when looking at the confusion matrix below, we can see that because of the imbalance nature of how people travel -- people travel mostly by car, the model has a bias toward private vehicles and tries to predict everything into that category.
<br/>
![confusion_matrix_lr]({{ site.url }}{{ site.baseurl }}/assets/images/ml_cm_lr.png)

## Random Forest
The random forest classifier was implemented using the scikit learn library. We performed several sets of grid search on the optimal number of estimators and maximum depths. The final model produces a mean squared error of 0.305 and an accuracy score of 0.930. We can see that the performance of the random forest classifier is significantly improved compared to the logistic regression. From the confusion matrix below we can also see that the random forest classifier overpredicts the private vehicle class.
<br/>
![confusion_matrix_lr]({{ site.url }}{{ site.baseurl }}/assets/images/ml_cm_rf.png)

## Bagging
The bagging classifier was also implemented using the scikit learn library. In our study, the bagging model was trained in parallel using bootstrap samples of the data, 100 decision trees were bagged. Compared to the random forest classifier which trains many decision trees in parallel, each split at the nodes of the trees is determined only by a random subset of features, the bagging model considers all features for splitting a node. The result shows that the bagging classifier has a great predictive performance in travel choice prediction, with a mean squared error of 0.265 and an accuracy score of 0.943. The accuracy score is improved significantly compared to logistic regression and slightly better than random forest classifier. From the confusion matrix below, we can see that the bagging classifier performs well in predicting travel by walking, private car and school bus, and the model still needs to be improved in predicting travel by biking, public transit and other modes.
<br/>
![confusion_matrix_lr]({{ site.url }}{{ site.baseurl }}/assets/images/ml_cm_bagging.png)

## Ada-boosting
The predictive performance of boosting is worse than bagging but slightly better than random forest and logistic regression. The boosting classifier also was trained using the scikit learn library. The result shows that the mean squared error of the boosting classifier is 0.461 and the accuracy score in the test set is 0.899. The confusion matrix below shows that although the accuracy score of boosting is only slightly higher than logistic regression, the boosting model has a significantly better performance in classifying trips traveled by walking, public transit, school bus and long-distance transit than random forest and logistic regression model, but still mispredicted a large proportion of trips made by biking, public transit and other modes.
<br/>
![confusion_matrix_lr]({{ site.url }}{{ site.baseurl }}/assets/images/ml_cm_boosting.png)

## Conclusion and Discussion
Generally, bagging produced the most accurate prediction in travel choice with an accuracy of 0.943. Random Forest
also has high testing accuracy, but misclassified a large number of trips made by biking, public transit,
long-distance transit and other modes to private vehicle class. The random forest is one of the ensemble methods and very close to bagging, while bagging considers all the features when spliting the nodes, which makes running bagging slower than random forest model but slightly improves the testing accuracy.
<br/>
![confusion_matrix_lr]({{ site.url }}{{ site.baseurl }}/assets/images/ml_evaluation.png)

Since the imbalance of data in different travel mode groups, the prediction accuracies for the travel mode lables are varied. The trips made by private vehicle account for a large proportion of the dataset, all of the machine learning model has very high F1 score (over 0.9 ) in predicting trips made by private vehicle. While the prediction performances in predicting Biking, other travel modes are generally bad since the data in these two lable groups is scarce. 
<br/>
<div id="altair-chart-1"></div>

Through exploring different machine learning models, we see that the models’ performance varies in terms of accuracy and F1 score on the testing set and if we can choose a good model for prediction, good results can be obtained. We also noticed that a major problem of machine learning classification models is that the class with the largest number of observations have the highest performance and the class with the least number of observations have the worst performance, which reflects an overfitting problem. Therefore, future planners should keep these biases in mind when applying these models. 
