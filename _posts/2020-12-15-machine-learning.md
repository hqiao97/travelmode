---
title: "SkLearn: Machine Learning Methods for Travel Mode Prediction"
date: 2020-12-15
published: true
tags: [dataviz, altair, hvplot]
excerpt: "Comparing 4 machine learning methods for predicting mode choice."
altair-loader:
  altair-chart-1: "charts/ml_f1_score.json"

toc: true
toc_sticky: true
---
## Introduction
Mobility is closely related with the environment and everyone's life { it impacts our accessibility to food, job
opportunities, education and recreational resources etc. In addition, transportation infrastructures shape
urban forms of a city and ways people live in that city. Understanding and predicting how people travel and
what modes of transportation they use is an essential part of urban planning. This project looks into the 2017 US
National Household Travel Survey data to predict travel mode choices of trips using various social-economic
factors, trip factors and land use factors through adopting four machine learning methods: logistic regression,
random forest, bagging, boosting.

## Logistic Regression
The logistic regression model was implemented using the scikit learn library. The model did not do a good job with testing mean square error of 0.479 and testing accuracy of 0.89. Especially when looking at the confusion matrix (Figure 1), we can see that because of the imbalance nature of how people travel -- people travel mostly by car, the model has a bias toward private vehicles and tries to predict everything into that category.
![confusion_matrix_lr]({{ site.url }}{{ site.baseurl }}/assets/images/ml_cm_lr.png)


<div id="altair-chart-1"></div>
