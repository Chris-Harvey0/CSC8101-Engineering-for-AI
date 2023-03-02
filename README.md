# CSC8101-Engineering-for-AI
## Overview
This project was split into two parts; an Azure Databricks component and a Neo4j component.
Both of these parts involved a dataset of taxi trips which we needed to perform certain operations on in order to make some findings from the data.
## Azure Databricks
For this section of the project we had to write code in PySpark to make findings about the dataset of taxi trips.
Once this was complete I undertook performance testing of my code with five different sized datasets.
The smallest of these datasets had around 3,000,000 trips, while the largest had over 140,000,000.
From the performance testing it could clearly be seen that some operations do not parallelise well.
Calculating the median of a column in the dataframe was on such operation that did not perform well.
When this operation was removed from the execution the execution time remained constant irrelevant of the size of the dataset being used.
## Neo4j
For this part of the project we had to make findings from the graph database of taxi trips.
I used the Louvain algorithm to perform community detection, and the Pagerank algorithm to perform centrality analysis.
We then used a an app to visualise the results of these queries, the resulting images can be seen in neo4j/visuals.
## Reflection
I had not used Azure Databricks or Neo4j previously so this project allowed me to gain experience with a couple of new tools.
The Azure Databricks part of this project allowed me to gain a better understanding of what operations scale well across large datasets.
Through the use of Neo4j I have increased my knowledge of graph databases and the advantages and disadvantages they have over relational databases.
