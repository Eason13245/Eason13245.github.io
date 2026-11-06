---
title: Exploring BFRO Reports Across the United States
tags: [Data Visualization, Altair, IS455]
style: fill
color: primary
description: An interactive exploration of BFRO reports across U.S. states and over time.
date: 2026-11-06
permalink: /bfro-reports/
---

This project explores reported Bigfoot sightings documented in the Bigfoot Field Researchers Organization (BFRO) dataset. 
Using Python, Pandas, and Altair, I created two visualizations to examine the geographic distribution and historical patterns of reported sightings across the United States. 
The first visualization compares the states with the highest numbers of reports, while the second allows users to interactively explore 
how reported sightings have changed over time in individual states.

## Visualization 1: Top 15 States by BFRO Reports

<div id="bfro-chart1"></div>

My first visualization is a horizontal bar chart displaying the 15 states in the United States with the highest number of reported Bigfoot sightings in the selected BFRO dataset. 
The x-axis uses quantitative encoding for report counts, while the y-axis uses nominal encoding for state names. 
The state bars are sorted alphabetically. I also used a sequential blue color scheme, so states with higher report counts have darker shades, emphasizing differences between states. 
Lastly, to prepare the data, I used groupby to group reports by state for the calculation of the total number of reports by each state, and selected the top 15 to improve readability.

## Visualization 2: BFRO Reports Over Time by State

<div id="bfro-chart2"></div>

For the second visualization, I created an interactive line chart showing changes in reported Bigfoot sightings from 1980 to 2018 for individual U.S. states. 
For the x-axis, I used quantitative encoding to represent years, and quantitative encoding to show annual report counts on the y-axis. 
I used a fixed steel-blue color because only one state is displayed at a time, so a color scheme is unnecessary. When preparing the data, I removed records with missing dates, 
converted the column to datetime format, extracted the year, and grouped reports by year and state. 
I also filtered the data to include only reports from 1980 to 2018 to emphasize more recent trends. 
For interactivity, I implemented a dropdown menu using Altair’s binding_select() and selection_point() functions. 
The transform_filter function also updates the chart based on the states users select, allowing them to investigate individual reporting trends directly.

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed(
    '#bfro-chart1',
    '/assets/bfro/chart1.json',
    {actions: false}
  ).catch(console.error);

  vegaEmbed(
    '#bfro-chart2',
    '/assets/bfro/chart2.json',
    {actions: false}
  ).catch(console.error);
</script>

---

## Data and Analysis

[The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv)

[The Analysis](https://github.com/Eason13245/Eason13245.github.io/blob/main/python_notebooks/IS455_HW5_BFRO_Analysis.ipynb)
