---
title: "Altair + Panel: Exploratory Data Analysis"
date: 2020-12-19
published: true
tags: [dataviz, hvplot, altair, panel]
excerpt: "Understand the 2017 NHTS using interactive charts."
hv-loader:
  hv-chart-1: ["charts/overallHvplot.html", "600"] # second argument is the height
  hv-chart-2: ["charts/race.html", "600"] # second argument is the height
  hv-chart-3: ["charts/origin.html", "500"] # second argument is the height
  hv-chart-4: ["charts/education.html", "500"] # second argument is the height
  hv-chart-5: ["charts/private_veh.html", "500"] # second argument is the height
  hv-chart-6: ["charts/duration_mode.html", "1000"] # second argument is the height
  hv-chart-7: ["charts/purpose_count.html", "1000"] # second argument is the height
  

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

## Mode vs. two variable
In this part, to better understand the effects of different variables, we will use Panel to create a webapp that allows multiple user input.
<strong>Note</strong> that we will leave out the "private vehicle" mode choice data first. 

For each ethnic group in every region, walking is the most popular way to travel. Among white population, public transit is only popular with those whose trip originate in urban area; for black population, public transit is slightly more frequently used for the trips that originate in second city, suburban, and small town area; for asian, public transit is also slightly more frequently used for the trips that originate in second city and suburban area.

Now we only look at the private vehicle trip. The differences are tiny.
<div id="hv-chart-5"></div>

## More Altair Charts
We then plotted more interesting Altair charts. For the one below, we plot the observations by trip purpose against trip duration using a scatter plot and then present the count of records by trip mode at the bottom for the selected points using a brush. As seen on the plot below, with a brush, we are able to select the trips with trip duration longer than 200 minutes and present their counts by mode choice.
<div id="hv-chart-6"></div>

![brush1-1]({{ site.url }}{{ site.baseurl }}/assets/images/brush1-1.png)

![brush1-2]({{ site.url }}{{ site.baseurl }}/assets/images/brush1-2.png)

For the second Altair interactive chart, we plot out the count of trips for each trip purpose. The interactive component comes in when the user uses the brush to select a trip purpose, then the plot below will show the count of selected trips in each travel mode.
<div id="hv-chart-7"></div>

![brush2-1]({{ site.url }}{{ site.baseurl }}/assets/images/brush2-1.png)

![brush2-2]({{ site.url }}{{ site.baseurl }}/assets/images/brush2-2.png)

The last two charts are heat maps plotted with Altair. The first heat map shows trip origin purpose against trip destination purpose. The brighter the color shows the more trips with that OD purpose pair. We see that the most popular trip purpose pairs are Regular Home Activities-Buy Goods and Regular Home Activities-Work.

![heat map 1]({{ site.url }}{{ site.baseurl }}/assets/images/hm-1.png)

The second heat map shows income level against trip mode. The auto-oriented culture is once again reflected in this chart. We see that no matter which income group we are in, car and SUV remains to be the most popular choice of transportation. We also see that some transportation mode choices are only adopted by people with income in the higher range, including airplane, boat, golf cart, RV and rental car.

![heat map 2]({{ site.url }}{{ site.baseurl }}/assets/images/hm-2.png)
