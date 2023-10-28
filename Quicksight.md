- Fast, easy, cloud-powered business analytics service
- employees (general customer) oriented.
	- Build visualization
	- Perform ad-hoc analysis
	- Quickly get business insights from data
	- Anytime, on any device (browsers, mobile)
- [Serverless](Serverless.md)

### Data Sources
Data preparation allows limited ETL
- [S3](S3%20Data%20Lakes.md)
- [Redshift](Redshift.md)
- [RDS](RDS.md)
- [Athena](Athena.md)
- EC2-hosted databases

### SPICE
- Datasets are imported into SPICE
	- Super-fast, Parallel, In-memory Calculation Engine
	- Uses columnar storage, in-memory machine code generation
	- Accelerates interactvie queries on large datasets.
- Each user gets 10GB of SPICE
- Highly available / durable
- Scales to hundreds of thousands of users

### Use Cases
- interactive ad-hoc exploration / visualization of data.
- Dashboards and KPI's
- Analyze / Visualize data from
	- Logs in [S3](S3%20Data%20Lakes.md)
	- AWS (RDS, Redshift, Athena, S3)
	- On-premise databases

### Machine Learning Insights
- anomaly detection ( Random Cut Forest )
- Forecasting ( Random Cut Forest)
- Auto-narratives ( Build the dashboard automatically )

### Visual Types
- AutoGraph
- Bar charts
	- For comparison and distribution (histograms)
- Line graphs
	- For changes over time
- Scatter Plots, heat maps
	- For correlation
- Pie Graphs, Tree maps
	- For aggregation
- Pivot Tables
	- For tabular data
- Stories
 

### Anti-patterns
- Highly formatted **canned** reports
	- quicksight is for **ad-hoc** queries, analysis and visualization