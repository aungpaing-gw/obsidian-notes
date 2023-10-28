Glue is a serverless data integration service that helps you discover, prepare, and combine data for analytics, machine learning ( ML ), and application development.
Glue provides both visual and code-based interfaces to help with data integration.

Users can find and access data through the AWS Glue Data Catalog.
Data Engineers can visually create, run and monitor ETL workflows in Glue Studio.
Data Analysts and Data scientists use AWS Glue DataBrew to visually enrich, clean and normalize data without writing code.

Real world implementations of AWS Glue can consist of complex ETL activities involving multiple crawlers, job, and trigger. To help visualize and orchestrate these activities, AWS Glue workflows can be created using the console or through AWS CloudFormation for developers to create their infrastructure as code in JSON or YAML format.

In Glue, user can use workflows to create and visualize activities such as crawlers, triggers and jobs. Each workflow manages and monitors all of its jobs and crawleres.
As workflow runs each component, it records job progress and status for an overview of the larger task and also details of each step.

## Main Focus
- Taking care of provisioning and managing resources, such as servers, storage and runtime environment, which are required to run your ETL operations. When an Glue ETL job is started, the service allocates capacity from its warm pool of resources to run the workload.
- Avoiding tasks such as installing, patching or updating ETL software because Glue is a fully managed service.
- Generating code, based on the job configuration, to transform the data from source to target. User can also provide scripts in the AWS Glue console or API to access your data.
- Including both visual and code-based interfaces to help make data preparation and movement fast and cost optimized.

## Glue Data Catalog
- metadata repository for all your tables
	- Automated schema inference
	- Schemas are versioned
- Integrates with Athena or Redshift Spectrum (schema & data discovery)
- Glue Crawlers can help build the Glue Data Catalog

---
## Glue Crawlers
- Crawlers go through the data to infer schema and partitions
- Datatype : Works JSON, Parquet, CSV, relational store
- Data Storage : S3, Amazon Redshift, AWS RDS
- Run on Schedule or on demand
- Need IAM role / credentials to access the data stores.
- Will extract partitions based on how the S3 data is organized.
- Think up front about how querying (anthena) the data lake in S3.
- Query By date or By device?
- can crawl an on-premise database or a database running in AWS to perform ETL jobs.

---
## Glue ETL
- Generate ETL code in Python or Scala, code can be modified
- Can provide your own Spark or PySpark scripts
- Target can be S3, JDBC (RDS, Redshift), or in Glue Data Catalog
- Fully managed, cost effective, pay only for the resources consumed
- Jobs are run on a serverless [Spark](Apache%20Spark.md) platform
- Glue Scheduler to schedule the jobs
- Glue Triggers to automate job runs based on "events"

### Glue ETL - Transformation
#### Bundled Transformations
- DropField, DropNullFields : remove ( null ) fields
- Filter : specify a function to filter records
- Join : to enrich data
- Map : add fields, delete fields, perform external lookups
- Raw source data coming in as uncompressed CSV files --> Apache Parquet format and compress with snappy compression.
- Glue ETL to pre-aggregate data to speed up analytical queries.
- Glue comes with powerful built-in transformations to help flatten JSON, join datasets, map fields to data types, and much more.
#### Machine Learning Transformations
- FindMatches ML : Identify duplicate or matching records in your dataset
#### [Apache Spark](Apache%20Spark.md) transformations
- K-Means

----------------------------------------------------------------------
## Glue Streaming ETL
- consume real-time data from either an Amazon Kinesis data stream or an Amazon Managed Streaming for Apache Kafka stream by using the Data Catalog to register the stream as a source.
- Why ? as data comes in from a stream, user are able to use all the powerful AWS Glue ETL transformations. Then output the transformed data to S3 bucket or target that is JDBC compatible. 

-----------------------------------------------------------------------
## DataBrew
- Visual data preparation tool to clean, enrich, format and normalize the dataset with over 250 build-in transformation.
- User can create "recipe" for dataset using the transformation of choice, and then reuse that recipe repeatedly as the business continues to collect new data.

-----
## Others
- Partitioning
	- Glue Crawlers automatically identify partitions in S3 data.
- Compression and File Format
	- Use the right format, such as Parquet, can help increase performance. This is due to the format being columnar, instead of row based. So user can fetch only the required columns. As a general rule, fewer large files work better than many smaller files when querying data stores in S3.
- Security
	- Glue supports encryption at rest and in motion. data encryption at rest while authoring jobs and developing scripts using development endpoints.
- Job Monitoring
	- EventBridge
	- Cloudwatch logs
	- CloudTrail


## Billing
- Glue ETL jobs and Development endpoints
	- charged an hourly rate based on the number of data processing units (DPU) used to run ETL job. A single DPU provides 4 vCPU and 16GB of memory.
	- Development endpoints are optional, and billing applies only if choose to interactively develop your ETL code. Glue Development endpoint requires minimum of 2 DPUs.
- Data Catalog and storage requests
	- Can store up to 1 million objects for free. If store more than 1 million objects, will be charged 1 USD per 100,000 objects over 1 million, per month.
	- An object in the Data Catalog is a table, table version, partition or database.
- Glue Crawler
	- Billed in increment of 1 second, rounded up to the nearest second, with 10-mins minimum duration for each crawl.
- DataBrew interactive sessions
	- You initiate a session when you open a DataBrew project. You are billed for the total number of session used. Each session is 30 mins.