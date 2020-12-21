---
title: "Altair + Panel: Exploratory Data Analysis"
date: 2020-12-19
published: true
tags: [dataviz, hvplot, altair, panel]
excerpt: "Understand the 2017 NHTS using interactive charts."
hv-loader:
  hv-chart-1: ["charts/overallHvplot.html", "500"] # second argument is the height
  hv-chart-2: ["charts/race.html", "500"] # second argument is the height
  hv-chart-3: ["charts/origin.html", "500"] # second argument is the height
  hv-chart-4: ["charts/education.html", "500"] # second argument is the height

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

We also compare the trip distance with trip mode choices. Not surprisingly, the trip distances of people who travel by walking are mostly short. Compared to other mode, the trip distances of people who take private vehicle or public transit are longer than other modes.

![distance]({{ site.url }}{{ site.baseurl }}/charts/distance.png)

In terms of race, among all ethnic groups, a slightly lower proportion of Asian travel by private vehicle. However, there are apparently more Asian travel on foot than the other four groups; For the public transit trip or school bus, more Black/American rely on this mode, while fewer white population take transit; For the bicycle trip, there are fewer Black American travel by bike.

<div id="hv-chart-2"></div>

In terms of trip origins, for the trips that use private vehicles, a higher proportion of trips originate in small town or suburban area, while the ratio is lower for those trips that originate in urban area; For the walking trips, a higher proportion of them happen in urban area; For the people who travel by school bus, a higher percentage of them come from rural area or small town; poeple who travel by bike, a higher proportion of them originate in urban area; for the people who are transit riders or long term trnsit riders, a majority of them originates in urban area.

<div id="hv-chart-3"></div>

When we analyze the education attainment of the travelers, we find that for the travellers that used private vehicle, slightly more of them are high school graduate or GED OR with college or associates degree; higher proportion of people with graduate degree or professional degree travel on foot or by long-distance transit; biking is more popular with people with graduate degree or professional degree or who are less than a high school graduate; school bus are taken by those are less than a high school graduate.

<div id="hv-chart-4"></div>
