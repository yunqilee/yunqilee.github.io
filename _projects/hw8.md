---
name: "hw8: Jekyll Webpage"
tools: [Python, HTML, vega-lite]
image: assets/pngs/mean_square_footage.png
description: This is a "showcase" project that uses vega-lite for interactive viz!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Interactive visualizations of building inventory data

## First Plot
The interactivity of this visualization is mainly reflected in hovering the mouse over a column chart of a county. The column chart will change color and display specific data. The code to implement this interactivity is as follows:

```
county_hover = alt.selection_single(
    name="countyHover",
    on="mouseover",
    nearest=True,
    empty="none",
    fields=["County"]
)
```

<vegachart schema-url="{{ site.baseurl }}/assets/json/mean_square_footage.json" style="width: 100%"></vegachart>


## Write up: first plot
Compared with last week's visualization, this visualization has increased interactivity. The audience can more intuitively view the mean square footage of a certain county. The color changes also make it easier to compare the selected data to other data.



## Second Plot
According to the first visualization, we can further analyze the building information of the county in the top 30 mean square footages and view the distribution of Year Acquired and Square Footage.


The code to achieve interactivity is as follows. In the Year Acquired and Square Footage charts of the county in the top 30 mean square footage, the add_selection and transform_filter methods are used respectively.

```
brush = alt.selection_interval(encodings=['x','y'])
```



<vegachart schema-url="{{ site.baseurl }}/assets/json/interactive_chart.json" style="width: 100%"></vegachart>


## Write up: second plot

Since the scatter plot display effect last week was not good, I used the example in class for the second plot this week. By further analyzing the results of the first visualization, an interactive visualization design was performed on the filtered data through pandas.

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>

