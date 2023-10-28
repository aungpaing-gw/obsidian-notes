- Interactive query service for S3 (SQL)
	- No need to load data, it stays in S3
- [[Presto]] under the hood
- [Serverless](Serverless.md)
- Supports many data formats
	- CSV, JSON, ORC, Parquet, Avro
- Unstructured, semi-structured or structured
- Pay-as-you-go
- Save LOTS of money by using columnar formats
- [Glue](Glue.md) and [S3](S3%20Data%20Lakes.md) have their own charges

## Examples
- ad-hoc queries of web logs
- Querying staging data before loading to Redshift
- Analyze CloudTrail / CloudFront / VPC / ELB etc log in S3
- Integration with Jupyter, Zeppelin, RStudio notebooks.
- Integration with [Quicksight](Quicksight.md)
- Integration vai ODBC / JDBC with other visualization tools

	Amazon S3 => AWS Glue (Crawler) => Amazon Athena => Amazon QuickSight

### Anti-patterns
- highly formatted reports / visualization
	- use QuickSight
- ETL
	- Use Glue