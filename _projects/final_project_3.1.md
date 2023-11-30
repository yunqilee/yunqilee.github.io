---
name: final project 3.1
tools: [Altair, Interactive visualization, Python, Javascript]
image: assets/pngs/final_project_3.1_cover.png
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

## contextual visualizations
We complete the contextual visualizations, which includes two parts-'Overall Energy Performance' and 'Trend Analysis', by referring to the 2020 Energy Benchmark Report of Chicago city. In this section, we compare the city's perfomance from 2016, the year we analysed heavily in previous work, to 2020, the year of most recent data. And we conclude that Chicago city has done well in maintain its performance level for this 5 years, but it failed to provide any proof for significant improvements.

Source: <a href="https://www.chicago.gov/content/dam/city/progs/env/Energy-Benchmark-Reports/2020_Chicago_Energy_Benchmarking_Report.pdf">2020 Chicago Energy Benchmarking Report</a>

### overall energy performance
<img src="{{site.baseurl}}/assets/pngs/1_ReportingRate.png">

Figure 1 displays the Energy Benchmarking Reporting Rate from 2016 to 2020.

In 2020, 2,841 properties submitted reports to the City of Chicago, and 80 additional properties submitted on a voluntary basis, for a total of 2,921 reports. 118 properties received temporary exemptions, leading to 2,959 “covered properties” (required by ordinance to report) reporting or exempt out of 3,491 total, resulting in a 85% reporting rate.

In 2016, 2,695 properties spanning nearly threefourths of a billion square feet tracked and reported energy use. Over 3,500 properties are now included in the policy’s coverage. The reporting properties represent 23% of citywide energy use.

<img src="{{site.baseurl}}/assets/pngs/2_EnergyStar.png">

Figure 2 displays the Median ENERGY STAR Scores from 2016 to 2020.

The 1-100 ENERGY STAR score represents a property’s overall energy performance relative to similar building types across the nation, while normalizing for different climates. A score of 50 indicates energy performance at the national median, while a score of 100 represents extremely high energy performance. Scores below 50 indicate significant opportunities for improvement.

In 2020, the median ENERGY STAR score for all analyzed properties in Chicago was 60 out of 100, an increase of three points from the median of 57 in 2019. 

<img src="{{site.baseurl}}/assets/pngs/3_StarByBuilding.png">
Figure 3 displays ENERGY STAR Scores by Building Sector Reported from 2016 to 2020.

The median ENERGY STAR score has increased in the Retail, Office, and K-12 School property sectors, while the Multifamily Housing, Lodging, Other, and Healthcare sectors saw declines from 2019 to 2020. A median score of 60 is well above the national median of 50, indicating the Chicago properties over 50,000 square feet are performing slightly better than the majority of comparable buildings in the U.S.

### trend analysis
<img src="{{site.baseurl}}/assets/pngs/4_GHG.png">
Figure 4 display the trend of Median GHG Intensity from 2016 to 2020.

Overall, the carbon emissions per sq. ft. of space continued to decline rapidly and decreased by 25% from 2016 to 2020. All building sectors have seen decreases in the GHG intensity as shown in this figure. When comparing total GHG emissions from nearly 2,000 properties that reported in 2017 and again reported in 2020, total GHG emissions are down 9%, which equates to over 200,000 metric tons of carbon dioxide equivalents (CO2e). This reduction is equivalent to removing nearly 55,000 passenger cars from the road each year.

<img src="{{site.baseurl}}/assets/pngs/5_EUI.png">
Figure 5 display the trend of Median Source EUI from 2016 to 2020.

Now, the final figure demonstrate the comparison over the past five years of benchmarking information shows that the median weather-normalized source energy use per sq. ft. for all reporting buildings has dropped by 7% from the 2016 to 2020 reporting years. All sectors saw decreases since the 2016 reporting year, with the exception of Retail and College/ University. The greatest improvements have been seen in the Lodging sector (18% improvement) and Office sector (15% improvement).