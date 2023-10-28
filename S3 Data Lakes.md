---
aliases : [ S3 ]
---
# AWS S3 Overview
- Allows people to store objects (files) in 'buckets' (directories)
- Buckets **must** have a **globally unique name**
- Objects (files) have a Key. The key is the **FULL** path
	- <my_bucket>/my_file.txt
	- <my_bucket>/my_folder/another_folder/my_file.txt
- Max Object Size is 5TB
- Object Tags ( key / value pair - up to 10 ) - useful for security / lifecycle
- Backbone for many AWS ML Services ( eg. SageMaker )
- Capable of creating a **"[Data Lake](Data%20Lake.md)"**
- Centralized Architecture
- Support any file format ( CSV, JSON, Parquet, ORC, Avro, [[protobuf]])

Benefits of datalake
- Catalogue, search and find the relevant data in the central repository
- Store any type of data, at any scale, and at low cost.
- Secure the data and prevent unauthorized access.
- Quickly perform new types of data analysis.

---
## AWS S3 Data Partitioning

Pattern for speeding up range queries (eg. AWS Athena)
Can define whatever partitioning strategy we like.
Some tools (eg. AWS Glue) will handle data partitioning automatically?

---
## AWS S3 Storage Classes

Can move between classes manually or using S3 Lifecycle configurations
| Class                                    | Purpose                                                                     | Availability         | Latency                                                       | Throughput | concurrent Facility | Use case                                                                     |
| ---------------------------------------- | --------------------------------------------------------------------------- | -------------------- | ------------------------------------------------------------- | ---------- | ------------------- | ---------------------------------------------------------------------------- |
| Standard                                 | General Purpose                                                             | 99.99%               | Low                                                           | High       | 2                   | Big Data Analytics, mobile & Gaming Applications, content distribution       |
| Standard-Infrequent Access (Standard-IA) | data that is less frequently accessed but requires rapid access when needed | 99.99%               |                                                               |            |                     | Disaster Recovery, backups                                                   |
| One Zone-Infrequent Access (One Zone-IA) | same as Standard-IA, data lost when AZ is destroyed                         | 99.5% in a single AZ |                                                               |            |                     | Storing Secondary backup copies of on-premise data or data you can recreate. |
| Glacier Instant Retrieval                | Data accessed once a quater                                                 |                      | Millisecond retrieval                                         |            |                     | Minimum storage duration of 90 days                                          |
| Glacier Flexible Retrieval               | formaly Amazon S3 Glacier                                                   |                      | Expedited (1~5 mins), Standard (3~5 hours), Bulk (5~12 hours) |            |                     | Minimum storage duration of 90 days                                          |
| Glacier Deep Archive                     | for long term storage                                                       |                      | Standard ( 12 hours ), Bulk (48 hours)                        |            |                     | Minimum storage duration of 180 days                                         |
| Intelligent-Tiering                      | Move objects automatically between Access Tiers based on usage              |                      |                                                               |            |                     | Frequent Access (default)  -> Infrequent Access (not accessed for 30 days) -> Archive Instant Access (90 days) -> Archive Access (90 days to 700+)                                                                          |

![storage_classes](storage_classes.png)

[AWS S3 Pricing](https://aws.amazon.com/s3/pricing/)

---
## AWS S3 Durability and Availability

### Durability
- high durability (99.99 || 9's)
### Availability
- Measure how readily available a service is
- Varies depending on storage class
- eg. S3 Standard has 99.99% availability = not available for 53 minutes a year.

---
## AWS S3 - Lifecycle Rules

Move bucket from between the Storage Classes by manually setting a rule.
- Rules can be created for a certain prefix (eg. s3://mybucket/mp3/\*)
- Rules can be created for certain objects Tags ( eg. Department : Finance)

### Transition Actions
Configure objects to transition to another storage class.
### Expiration Actions
Configure objects to expire (delete) after some time.
- access log files can be set to delete after 1 year.

---
## AWS S3 Analytics
Storage Class Analysis
- Help you decide when to transition objects to the right storage class
- Recommendations for Standard and Standard IA
	- Does NOT work for One-Zone IA or Glacier
- Report is updated daily
- 24 to 48 hours to start seeing data analysis
- Good first step to put together Lifecycle Rules (or improve them)

![S3_analytics](S3_analytics.png)

---
## S3 Versioning?

---
## S3 Security

### Encryption
- SSE-S3 (AES-256)
	- encrypts S3 objects using keys handled & managed by AWS
- SSE-KMS (AWS-KMS)
	- use AWS Key Management Service to manage encryption keys
	- Additional security (user must have access to KMS Key)
	- Audit trail for KMS key usage
- SSE-C (not use)
	- when you wanna manage your own encryption keys
- Client side encryption (not use)

### Access
- User Based
	- IAM Policies : Which API calls should be allowed for a specific user
- Resource Based
	- Bucket Policies : bucket wide rules from S3 console - allows across account
	- Object Access Control List (ACL) - finer grain
	- Bucket Access Control List (ACL) - less common

#### Bucket policies
- JSON based
- Grant public access to the bucket
- Force objects to be encrypted at upload
- Grant access to another account (Cross Account)
\* Bucket Policies are evaluated before "default encryption"

### Networking
#### VPC Endpoint Gateway
- allow traffic to stay within local VPC (instead of going through public web)
- Make sure private services (AWS SageMaker) can access S3
#### Logging and Audit
- Access Logs can be stored in other S3 bucket
- API calls can be logged in AWS CloudTrail
