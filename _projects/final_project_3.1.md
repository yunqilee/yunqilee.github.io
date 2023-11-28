---
name: final project 3.1
tools: [Altair, Interactive visualization, Python, Javascript]
image: assets/pngs/interactive_legends.png
description: Final project 3.1 for interactive viz!
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
Compared with last week's visualization, this visualization has increased interactivity. Regarding the encoding type, I use nominal for the x-axis and quantitative for the y-axis. When a county is selected, the column will change from blue to red. The audience can more intuitively view the mean square footage of it. The color changes also make it easier to compare the selected data to other data.