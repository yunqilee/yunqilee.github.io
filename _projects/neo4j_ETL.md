---
name: Analyze IMDb data via Neo4j
tools: [non-relational database, ETL, Neo4j]
image: assets/pngs/neo4j_project/neo4j.png
description: An ETL Project using Neo4j
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Analyze IMDb data via neo4j

### Background information
<a href="https://www.imdb.com/">IMDb</a> is an online database of information related to a variety of media forms including films, television series, home videos and so on. This project aims to use the mature data of IMDb to better understand the characteristics of non-relational databases, as well as the actual work of data import and query using neo4j's cypher shell.
### Data Cleaning
The data sources used for this project is given in the link below. Unfortunately, some of the tab-separated values are not compatible with Neo4j's LOAD CSV command. Thanks to the contribution of ybull in Github, the <a href="https://github.com/ybull/IMDB-to-Neo4j-imports/tree/master"> repository</a> he created helped me fix the quote issue of the source data.

By running the fix_quotes_for_neo4j_imports.py script, I can modify the form of the data to make them compatible with LOAD CSV command. Now the data is ready to import.

### Realistic query
After successfully imported the data, we can finally see the whole picture of the data.
<img src="{{site.baseurl}}/assets/pngs/neo4j_project/imdb_data.png">
We can see now we have 23,437,503 nodes and 45,850,648 relations, it is indeed a huge amount of data, and a little bit difficult to deal with. But on the positive side, through some appropriate methods, we can significantly improve the efficiency of our query and analysis of data.

### Write up: From data source to insight, implemented by Neo4j






<div class="left">
{% include elements/button.html link="https://developer.imdb.com/non-commercial-datasets/" text="The Data" %}
</div>