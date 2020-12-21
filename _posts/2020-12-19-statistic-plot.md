---
title: "Altair + Panel: Exploratory Data Analysis"
date: 2020-12-19
published: true
tags: [dataviz, hvplot, altair, panel]
excerpt: "Understand the 2017 NHTS using interactive charts."
hv-loader:
  hv-chart-1: ["charts/overallHvplot.html", "500"] # second argument is the height

toc: true
toc_sticky: true
---
## Introduction
In this section, we are going to explore the relationship between variables and trip mode choices. Both the numeric and categorical variables will be analyzed. In addition to the interactive plots, we also create a Panel webapp to gain understanding of multiple variables.

## Overall data distribution
We plot the percentage of each trip mode choice, private vehicle is the predominant way to travel, while walking is the second popular one.

<div id="hv-chart-1"></div>

## Mode vs. one variable
We first compare the travelers' age with their trip mode choices. The median age of people who travel by private vehicle, long-term transit, walking, and other means are higher than other groups.

![age]({{ site.url }}{{ site.baseurl }}/charts/age.png)

We also compare the trip distance with trip mode choices. Not surprisingly, the trip distances of people who travel by walking mostly short. Compared to other mode, the trip distance of people who take private vehicle or public transit is higher than other modes.

![distance]({{ site.url }}{{ site.baseurl }}/charts/distance.png)
