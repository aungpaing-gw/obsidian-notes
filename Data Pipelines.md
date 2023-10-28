- Destintations include S3, RDS, DynamoDB, Redshift and EMR
- Manages task dependencies
- Retries and notifies on failures
- Data sources may be on-premises
- Highly available

![datapipelines](datapipelines.png)

## Difference between Glue ETL and DataPipelines
- Glue ETL
	- Run [Spark](Apache%20Spark.md) code, Scala or Python based, **focus on ETL.**
	- Do not worry about configuring or managing the resources
	- Data Catalog to make the data available to Athena or Redshift Spectrum
- Data Pipeline
	- Orchestration service
	- More control over the environment, compute resources that run code
	- Allow access to **EC2 or EMR** instances