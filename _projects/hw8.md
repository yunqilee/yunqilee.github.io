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

## From the vega-editor

Simple barplot specification:

<vegachart schema-url="{{ site.baseurl }}/assets/json/firstViz_take2.json" style="width: 100%"></vegachart>



## Search The Data & Methods

Below is where we can put some links to both the data and the analysis code as buttons:

```
<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://blog.4dcu.be/programming/2021/05/03/Interactive-Visualizations.html" text="The Analysis" %}
</div>
```

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>

