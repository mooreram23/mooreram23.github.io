---
name: Illinois Building Inventory - HW5
tools: [Python, HTML, vega-lite]
image: assets/pngs/buildings.png
description: This looks at buildings in Illinois!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Building Dataset (HW5)

I created two visuals from the Illinois Owned Building Dataset. In this dataset I looked at how buildings' square footage changed over time and how different agencies' buildings look.

## Here is Visualization 1: Square Footaage vs. Total Floors

This scatter plot shows off the square footage of each building by its total floors. I thought this might be interesting to see since some buildings have lots of floors but not much space. While others are one floor with tons of space. I also thought it might be interesting to see how what agency it is with changes things too. For example, do some have more floors than others?

For the x and y axis I used the Quantitative encoding since both represent numbers. While for the agency I used Nominal since it is names of departments and such. I also dropped any buildings that had zero floors or zero square footage. This is because they buildings don't make logical sense. I also removed any construction year that was zero as well since this seemed to be a common value for buildings that had missing info. Every building must be one floor and have some amount of sqaure footage even if very little. I also added in the all agencies selection. This way you can easily see the differences between agencies. This is really the only area that I decided to add in some form of coloring that way you can tell different agencies apart on this selection. This is because it allows for the viewer to tell agencies apart easily. When there is only one agency selected it is just one color.

The interactivity for this chart is the agency selector dropdown. I added this to allow the viewer to pick one agency at a time to view. This way they can look more into specific agencies spread of buildings' floors and square footage. It also allows the viewer to be able to grasp similarities between buildings of one agency. For example, department of State Police have a lot of buildings that are one floor and under 10,000 sq ft. I also added the .interactive() for this graph. This way the viewer would be able to zoom in and pan around to look at different points. This is because floors are integer numbers so each value on the y axis tends to be crowded.


<vegachart schema-url="{{ site.baseurl }}/assets/json/HW5scatter.json" style="width: 100%"></vegachart>

---

## Here is Visualization 2: Average Sqaure Footage Per Year Constructed

This plot shows the average square footage for the year the building was constructed. I thought this might be interesting to look at since it would show if there was a trend in how newer buildings were being made. I was expecting it to climb each year, but that isn't really the case. It seems to spike every few years and then die down for awhile. I did average here because I wanted it to show what the typical building might have for square footage for the year.

The encoding types I used on this chart was Temporal for the year. This way it could be a continuous timeline as we move across the years. Then I used Quantiative for the square footage. This is because it is a measurement. I did not use any colors here. This is because it is one simple line and adding in other colors would be not needed and take away from the simple messsage of the graph. For this chart I made sure the construction year was not zero and the square footage was also not zero. This is because those buildings would clearly be missing data and cause issues for the graph. I chose the average because it gives a better idea of teh size of buildings being made were. I also did not add any interactive elements to this graph. The other chart fulfills the interactive requirement.

<vegachart schema-url="{{ site.baseurl }}/assets/json/HW5line_chart.json" style="width: 100%"></vegachart>

## Search The Data & Methods

Below is where we can put some links to both the data and the analysis code as buttons:

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/mooreram23/mooreram23.github.io/blob/main/python_notebooks/HW5Workbook.ipynb" text="The Analysis" %}
</div>

