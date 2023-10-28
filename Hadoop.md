Standard big data platform
Scalable data storage and batch processing framework.
Complement existing data-system by simultaneously ingesting, processing large volume of data, structure or not, from any number of sources.

Store and Process vast amount of data efficiently using cluster of computation hardware.


## Components

### 1. Storage Unit
[HDFS](HDFS.md) : Hadoop Distributed File system
It use Replication method, each splitted data is replicated in many blocks, to prevent the data loss.

### 2. Process
Hadoop MapReduce

### 3. Hadoop YARN : Yet Another resource manager
It consists of four main parties
- Resource manager
- Node manager
- Application master
- Container
Application master and container request resource to Resource manager via Node manager.

In additional, hadoop ecosystem consists of other components like Hive, Pig, Apache Spark

### 4. Hadoop Common
Common utility and library that support the other Hadoop module.