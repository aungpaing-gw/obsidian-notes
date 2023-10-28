- Elastic MapReduce
- Managed [Hadoop](Hadoop.md) framework on EC2 instances
- Includes Spark, HBase, [Presto](Presto.md), [Flink](Flink.md), Hive & more
- EMR notebooks
- Several integration points with AWS
- Prepare big data for pre-processing for Machine learning

With EMR, user can process vast amounts of data efficiently using Apache Hadoop and services offered by AWS. Can be used to 
- run large-scale distributed data processing jobs, 
- interactivate queries, and 
- ML applications using open-source analytics frameworks such as Apache Spark, Apache hive and presto.
AWS EMR automates time-consuming tasks like setup, tuning, monitoring and capacity planning

### EMR Cluster
- Master node
	- Manage the cluster 
- Core node
	- Hosts [HDFS](HDFS.md) data and run tasks
- Task node
	- Run tasks, does not host data

Note:
	Each node is a separate EC2 instance.
	If a single machine can handle all processing, a master node is enough for the cluster.
	If multiple nodes are required in the cluster, there must be at least one core node. Taks node does not store any data and
	- HTTPS e just focus on computing.

### EMR Usage
- Transient (automative terminate) vs Long-Running (manual terminate) Clusters
	- Can spin up task nodes using spot instance for temporary capacity
	- Can use reserved instances on long-running clusters to save money.
- Connect directly to master to run jobs
- EMR [Serverless](Serverless.md) lets AWS scale your nodes automatically.

### Compute Option
EMR is a managed service with the option of running clustered on
- EC2
	- The closest deployment environment to a YARN-based Hadoop platform supporting various open-source frameworks.
- EKS ( Elastic Kubernetes Services )
	- Suitable for customers who wants to standardize on EKS to manage clusters across applications or use different versions of an open-source framework on the same clusters.
- serverless
- Outposts
	- This fully managed service offers the same AWS infrastructure and services, APIs, and tools to virtually any data center, co-location space, or on-premises facility for a consistent hybrid experience.
	- Amazon EMR on AWS Outposts is for customers who want to run Amazon EMR closer to their data center, within an Outpost.

### Storage Option
EMR supports virtually unlimited storage capacity throught the EMR File System ( EMRFS ) backed by S3.
This can be shared with across multiple EMR clusters or EMR Serverless.
As a standard storage choice in Apache Hadoop, EMR also provides HDFS ( Hadoop Distributed File System ).
This option stores data with three copies by default across local disks in your cluster. You can use HDFS along with S3 to improve durability, security and I/O performance.

### Storage
- [HDFS](HDFS.md)
- EMRFS : access S3 as if it were [HDFS](HDFS.md)
- Local file system
- EBS for [HDFS](HDFS.md)

### AWS Integration
- EC2 for the instances that comprise the nodes
- VPC to configure the virtual network
- S3 to store input and output data
- CloudWatch to monitor cluster performance and configure alarms
- IAM to configure permissions
- CloudTrail to audit requests made to the service
- Data Pipeline to schedule and start the cluster.

### Promises
- Charges by hour
	- Plus EC2 charges
- Provisions new nodes if a core node fails
- Can add and remove tasks nodes on the fly
- Can resize a running cluster's core nodes

### Security
- [IAM](IAM.md) policies
- Kerberos
- SSH
- [IAM](IAM.md) roles

### Choosing Instance Types
- Master node:
	- m4.large if < 50 nodes, m4.xlarge if > 50 nodes
- Core & task nodes:
	- m4.large is usually good
	- If cluster waits a lot on external dependencies (eg. web crawler), t2.medium
	- Computation-intensive : high CPU instances
	- Database, memory-caching : high memory instances
	- Network / CPU-intensive (NLP, ML) - cluster computer instances
- Spot instances
	- Good choice for task nodes
	- Only use on core & master if testing or very cost-sensitive : Risk partial data loss.

## Aspects to consider
- Job Orchestration
	- [[AWS Step Functions|Step Functions]]
	- [[Apache Airflow]]
	- [[Apache Oozie]]
- Auto Scaling on EMR on EC2
	- EMR managed scaling, EMR continuously evaluates cluster metrics every 5 to 10 seconds to make scaling decisions that optimize the clusters for cost and speed. Ths feature is available for clusters composed of either instance groups or instance fleets.
- Spot Instances
- Long-running and transient clusters
	- EMR on EC2 uses two cluster types: long-running and transient. The long running do not shutdown, even after a job has completed. These clusters are preferred when continuous jobs must run on the data. Clusters usually takes a few minutes to boot up and spin. Eg. with Spark Streaming or Apache Flink ( for stream processing ) in which the job is "infinite", Or Online Transaction Processing ( OLTP ) workload like Apache HBase. For transient cluster, eg. batch analytics and ad-hoc queries.
- Direct connect EMR  cluster from Amazon Sagemaker Studio
	- When data scientists and data engineers use Apache Spark, Hive, and Presto running on Amazon EMR for fast data preparation, they can discover and connect to EMR clusters in a single account or cross accounts directly from their SageMaker Studio. With one-click access to the Apache Spark UI, they can monitor and debug Spark jobs running on EMR right from SageMaker Studio Notebooks, simplifying their debugging workflow.
- External Hive MetaStore
	- By Default, hive metastore information is recorded in a build-int MySQL database on the primary node of an EMR cluster. When the cluster terminates, all nodes shut down, including the primary node. When this happend, local data is lost because node file systems are ephemeral. To persist the metastore data, user can create external metastore that exists outside the cluster.
		- AWS Glue Data Catalog
		- RDS or Aurora
- Security using AWS lake formation or Apache Ranger
- Transferring data between HDFS and EMRFS
	- [[S3DistCp]]
- Storage
	- S3 ( EMRFS ), HDFS, DynamoDB
- 