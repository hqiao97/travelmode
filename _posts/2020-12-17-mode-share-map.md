---
title: "Panel: Trip Mode Distribution"
date: 2020-12-17
published: true
tags: [dataviz, hvplot]
excerpt: "Trip mode distribution by state and demographic information."
hv-loader:
  hv-chart-1: ["charts/modeHvplot.html", "500"] # second argument is the height
  hv-chart-2: ["charts/acsHvplot.html", "500"] # second argument is the height
toc: true
toc_sticky: true
---
## Introduction
In this Panel webapp, we present the share of trips by each mode choice in each state through interactive maps. Along with the mode share map, we also present some demographic information from ACS to allow users to compare and explore relationships between the two maps.

## User's guide
Users can select a mode choice to be presented in the mode share map through a drop down list and then select a demographic information variable through the other drop down list.

## Example map
Since the interactive map requires a dynamic page, we present two toy example that can be shown on a static page.

<div id="hv-chart-1"></div>
<div id="hv-chart-2"></div>

If you want to play around with the app, please click here!

