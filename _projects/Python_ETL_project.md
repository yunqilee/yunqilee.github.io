---
name: Python ETL Data Engineering Project
tools: [ETL, Python, pandas]
image: assets/pngs/etl-process-explained-diagram.png
description: An ETL Project
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Python ETL Project (Processing Market Cap Data of the bank)

## Introduction
This project is a part of IBM data engineering certificate's content. The technologies used in this project mainly include Python, ETL, and data processing using pandas. By completing this project. I have a deeper understanding of the ETL process.


## Data Source
In the extract stage, two types of data are processed. They are the name of the bank, market cap data and exchange rate data respectively. The data is shown below:

### Market Cap data:
<img src="{{site.baseurl}}/assets/pngs/data_market_cap.png">

### exchange rates:
<img src="{{site.baseurl}}/assets/pngs/exchange_rates.png">


## Data Processing
In the transform stage, the transform function is defined to process the extracted data. Combined with the US dollar and pound exchange rates obtained in the extract stage, the data is converted to obtain market cap data in pounds sterling and loaded into the specified csv file, also used the log function to log the entire process of ETL.

<img src="{{site.baseurl}}/assets/pngs/completed ETL.png">

<!-- these are written in a combo of html and liquid --> 


<div class="right">
{% include elements/button.html link="https://github.com/yunqilee/yunqilee.github.io/blob/main/python_notebooks/Python ETL Data Engineering Project.ipynb" text="Source Code" %}
</div>