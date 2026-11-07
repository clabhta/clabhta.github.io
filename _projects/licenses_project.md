---
layout: page
title: "Professional License Visualisations"
description: "Exploring the dist. of professional licenses and their corresponding statuses using UIUC iSchool data from Fall 2022."
permalink: /projects/licenses_project/
tools: [Python, Altair, vega-lite]
---
<p>
IS445 HW5.1 Submission.<br>
Data is from Fall 2022.<br>
Original Dataset:
<a href="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv">licenses_fall2022.csv</a><br>
Python Notebook:
<a href="https://github.com/clabhta/clabhta.github.io/blob/main/python_notebooks/licenses.ipynb" target="_blank">licenses.ipynb</a>
</p>
<h2>15 Most Common License Descriptions</h2>
<div id="licenses_chart1"></div>
<p>
My first chart examines the dist. of professional licenses across the 15 most common license descriptions in the Fall 2022 dataset. I chose a horiz. bar chart to make comparisons between the different categories easier, especially given the length of some license descriptions. The x-axis uses quantitative encoding to represent the number of licenses, while the y-axis uses nominal encoding to distinguish between license categories. I chose purple (my favourite colour) for the bars, although it doesn't represent any additional variable in this visualisation. Regarding data transformations, I used Pandas to count the occurrences of each license desc., selected the most common categories, and sorted them in descending order. The visualisation also includes tooltips displaying the license desc. and its corresponding count, allowing users to examine individual categories more precisely. Notably, permanent employee registrations and licensed cosmetologists account for a substantial majority of the records represented.
</p>
<h2>License Descriptions by Status</h2>
<div id="licenses_chart2"></div>
<p>
My second chart examines the dist. of professional licenses across different license statuses, using the same 15 license descriptions from the first visualisation. I again chose a horiz. bar chart, using quantitative encoding for the number of licenses and nominal encoding for their descriptions, while maintaining the purple colouring for consistency. Regarding data transformations, I filtered the original dataset to include only the 15 most common descriptions, before using Altair to count the records associated with each status. Unlike the first chart, this visualisation includes a dropdown menu allowing users to select a particular license status, such as 'ACTIVE' or 'NOT RENEWED'. I chose this interactivity to allow users to examine how the dist. changes between statuses, rather than displaying them all simultaneously. However, I noticed a limitation when selecting statuses with relatively few records, such as 'CLOSED'. Given that Altair adjusts the axes based on the data being displayed, the remaining bars can appear disproportionately large. Although the actual counts remain unchanged, this could misrepresent the individual counts and differences between statuses if users don't pay attention to the axis values.
</p>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#licenses_chart1', '{{ "/assets/licenses_chart1.json" | relative_url }}');
  vegaEmbed('#licenses_chart2', '{{ "/assets/licenses_chart2.json" | relative_url }}');
</script>