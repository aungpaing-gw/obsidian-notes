---
aliases : [Spark]
---
Developed in 2009
open source in 2010
Add to Apache foundation in 2013
Top level project in 2014

The goal of spark is to provide a fast general-purpose cluster framework for a large scale data processing designed to overcome the limitations of **mapreduce**, the most common data processing method in **[Hadoop](hadoop.md)** at the time.

The foundation of Spark is based on the resilient distributed dataset (RDD), which is a programming abstration that represents a collections of read-only objects split across a computing cluster.

RDD can be created from text files, sql databases, nosql databases, [HDFS](HDFS.md), cloud storage and pretty much anything else.
RDD allows for standard mapreduces, join, filter and aggregations.
Computation are done in memory.

The processing of RDD is done via the Driver and Executor. 
DAG : Directed Acyclic Graph.
![spark](spark.png)

Disadvantages : Mass amount of RAM required to do the computations.

## Spark Components

Spark CORE
	- Spark Streaming
	- Spark SQL
	- MLLib
	- GraphX

### Spark Streaming
![spark_streaming](spark_streaming.png)

### Spark MLLib
Distributed and scalable
- classification : Logistic regression, navie Bayes
- Regression
- Decision Trees
- Recommendataion engine (ALS)
- Cluster (K-Means)
- LDA (topic modeling)****
- ML workflow utilities (pipelines, features transformation, persistence)
- SVD, PCA, statistics

### Zeppeling + Spark
- can run spark code interactively
- Can execute SQL queries directly against SparkSQL
- Query results may be visualized in charts and graphs
- Makes Spark feel more like a data science tool
![zeppelin](zeppelin.png)