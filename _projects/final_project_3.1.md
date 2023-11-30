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


# Final Project 3.1 of Group 4 (xj20, yuhanwu3, yunqi4)

## Interactive visualization
In the third part of the project, our group wants to explore electricity use by different property types. We first used heatmap to analyze the mean electricity use of different types of buildings for the year of construction. The code is as follows:

```
chart1 = alt.Chart(filtered_df).mark_rect().encode(
    alt.X('Year Built:O'),
    alt.Y('Primary Property Type:O'),
    alt.Color('Electricity Use (kBtu):Q', aggregate='mean',title='Mean Electricity Use(kBtu)')
).properties(width=400, height=200, title='Heatmap of Electricity Use by Property Type and Year'
            ).transform_filter(year).add_selection(brush, year)
```

Then, to provide a comprehensive snapshot of the building's energy performance, our group added a histogram of mean energy star scores for different types of buildings. The code is as follows:

```
chart2 = alt.Chart(filtered_df).mark_bar().encode(
    alt.X('Primary Property Type:O'),
    alt.Y('ENERGY STAR Score:Q',aggregate='mean',title='Mean ENERGY STAR Score'),
    alt.Color('ENERGY STAR Score:Q',aggregate='mean',title='Mean ENERGY STAR Score')
).properties(width=300,title='Mean ENERGY STAR Score by Property Type'
            ).transform_filter(brush).transform_filter(year)
```

In order to help the audience more intuitively see the energy usage of buildings built in a specific year, our team added a dropdown widget through which users can select a specific year and see the corresponding data.

<vegachart schema-url="{{ site.baseurl }}/assets/json/side_by_side_data_url.json" style="width: 100%"></vegachart>


## Write up: interactive visualization
By using the HConcatChart method provided by the altair library, we concat the two charts together. Interactive visualization completed successfully.

<img src="{{site.baseurl}}/assets/pngs/1_ReportingRate.png">