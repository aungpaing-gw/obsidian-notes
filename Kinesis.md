# AWS Kinesis Overview

Kinesis is managed alternative to Apache Kafka
Great for real-time, application logs, metrics, IoT, clickstreams
Great for streaming processing frameworks (Spark, NiFi, etc)
Data is automatically replicated synchronously to 3 AZ.

Collect, process and analyze real-time streaming data.
Genereate timely insights
Respond in real time.

Four services in Kinesis
- Kinesis Streams
	- Low Latency Streaming Ingest at scale
- Kinesis Analytics
	- Perform real-time analytics on streams using SQL
- Kinesis Firehose
	- Load streams into S3, Redshift, ElasticSearch & Splunk
- Kinesis Video Streams
	- Meant for streaming video in real time

![Kinesis](Kinesis.png)

---
## Kinesis Streams
- Streams are divided in ordered Shards / Partitions
- Data retention is 1 day by default, can go up to 1 year
- Ability to reprocess / replay data
- multiple applications can consume the same stream
- Once data is inserted in Kinesis, it cannot be deleted ( immutable )
- Records can be up to 1MB in size.
- Small, fast data stream. Not for batch analysis

![kinesis_streams](kinesis_streams.png)

### Capacity Modes
#### Provisioned Mode
- manually choose number of shards provisioned.
- Each shard gets 1MB/s in (1000 records per second)
- Each shard gets 2MB/s out (classic or [fan-out](fan-out.md) consumer)
- Pay per shard provisioned per hour
#### On-demand mode
- no need to provision or manage the capacity
- Default capacity provisioned ( 4MB/s in  or 4000 records per second)
- Scales automatically based on observed throughput peak during the last 30 days.
- Pay per stream per hour & data in/out per GB

---
## Kinesis Data Firehose (Delivery)
Store data into the target destination with batch, not real time.
- Fully managed Service, no administration
- Near Real Time (60 seconds latency minimum for non full batches)
- Data ingestion into Redshift / Amazon S3 / ElasticSearch / Splunk (as long as there is HTTP endpoint)
- Automatic scaling
- Support many data formats.
- Data conversions from CSV / JSON to Parquet / ORC (only for S3)
- Data Transformation through AWS Lambda (eg. CSV => JSON)
- Support compression when target is Amazon S3 (GZIP, ZIP and SNAPPY)
- Pay for the data going through firehose

![kinesis_data_firehose](kinesis_data_firehose.png)![data_firehose_delivery](data_firehose_delivery.png)

## Difference between Stream and Firehose
### Streams
- Going to write custom code (producer / consumer)
- Real time (~200 ms latency for classic, ~70 ms latency for enhanced [fan-out](fan-out.md))
- Automatic scaling with On-Demand Mode
- Data Storage for 1 to 365 days, replay capability, multi consumers
### Firehose
- Fully managed, send to S3, Splunk, Redshift, ElasticSearch
- [Serverless](Serverless.md) data transformations with Lambda
- Near Real time (lowest buffer time is 1 minute)
- Automated Scaling
- No data Storage

---
## Kinesis Analytics

![kinesis_analytics](kinesis_analytics.png)

### Use cases
- Streaming ETL
	- Select columns, make simple transformations
- Continuous metric generations 
	- live leaderboard for a mobile game
- Responsive analytics
	- Look for certain criteria and build alerting (filtering)
- Able to send processed results to S3, Redshift, Elasticsearch, or own custom destination for further analysis.
 
### Features
- pay only for resources consumed
- [Serverless](Serverless.md) , scales automatically
- Use IAM permissions to access streaming source and destination(s)
- SQL or [[Flink]] to write the computation
- Schema discovery
- Lambda can be used for pre-processing

### On Machine Learning
- RANDOM_CUT_FOREST : anomaly detection
- HOTSPOTS : locate and return information about relatively dense region

### Streaming Applications
- Apache [[Flink]] (standard, heavy code, cannot connect to Kinesis firehose)
- SQL Applications (legacy)


---
## Kinesis Video Stream

- Producers
	- Security camera, body-worn camera, AWS DeepLens, etc.
	- One producer per video stream
- Video playback capability
- Consumers
	- build your own (MXNet, Tensorflow)
	- AWS SageMaker
	- AWS Rekognition Video
- Keep data for 1 hour to 10 years

 ![kinesis_video_stream](kinesis_video_stream.png)