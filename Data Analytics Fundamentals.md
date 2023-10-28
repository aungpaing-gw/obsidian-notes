[AWS Skill Builder](https://explore.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1688104800/woCKEDZ-Gge80JE1PGoPFA/tincan/749a775db5551f9ad044b80ea3316377a6934652/index.html?enhanced_signature=maVURmKRRVz3SgtNqH1R4FrSq9VhUBAmod29naeTLlk&endpoint=https%3A%2F%2Fexplore.skillbuilder.aws%2Flrs-api%2F&auth=Basic%20MTFkZWNlZjgtMjQ1OC00ODQ0LTlhOTgtYzNmY2YwMWM4MGY2OmM0YmQ5OTY5NTNkYTMxM2Q4YjNhZGJiYWM4NmQ0ZmVh&actor=%7B%22name%22%3A%224zW7uQcOg0alZ8LN7KOHiQ%3D%3D+CtWR4lajlQQMIHeotJ%2FZwQ%3D%3D%22%2C%22mbox%22%3A%22mailto%3Aaungpaing%40globalwalkers.co.jp%22%7D&registration=17fcb7f7-491b-4db5-9df1-b038e84ebad3&activity_id=http%3A%2F%2Fj_bvR-AyYKi4T-Ah6n8otLWVG_tcsFET_rise&Accept-Language=en&course_id=44&content_token=17fcb7f7-491b-4db5-9df1-b038e84ebad3&session_context=lms&host=kfase3bzbc.execute-api.us-east-1.amazonaws.com&path=/v1/xApi/&rs=649e4faba294f&crct=f66a56fe67e03aecb9e5a5d2992bb7f889cc7eaa59ba9c1f16ef9bd451b71448e453f4e0472a69ad73fc5d350998cf4e4e2563c2923e0cc6b13b3e4259194114&course_code=TCAA-DIG-100-ANNFUN-0101-EN-US&course_id=44&username=8182f424-d4b2-446f-a509-f47cebeb93a4&user_id=3234356&hash=9e325216fc7167e72fc397c9b5f32a5ba1b34736072aee1a07f37806b793d822#/lessons/9l1OnTcZa6Y9fJIO0A2Xp8N6Oj2LQo9l)

The main purpose of data analytics
- Answer your questions on the data.

## 1. Data analytics and data analysis solutions

**Analysis** is a detailed examination of something in order to understand its nature or determine its essential features.
**Data Analysis** is the process of compiling, processing and analyzing data so that you can use it to make decisions.

**Analytics** is the systematic analysis of data.
**Data Analytics** is the specific analytical process being applied.

**Analysis solution** help to manage the entire data management circle, from data collection, processing and visualization.

Organizations spend **millions** of dollars on data storage. 
The problem isn't **finding** the data -- but **failing** to do anything with it.

**Effective** data analysis solutions require both storage and the ability to analyze data in **near real time**, with **low latency**, while yielding **high-value returns.** 

### Ingest / Collect
A good data analysis solution allows developers to ingest a wide **variety** of data -- structured, semi-structured, and unstructured -- at any speed, from batch to streaming.

### Store
A good data analysis solution should provide secure, scalable, and durable storage. This storage should include data stores that can house structured, semi-structured, and un-structured data.

### Process / Analyze
First data must be processed, transforming it to make the data more consumable. As part of the processing, the data will also be analyzed.
This usually means sorting, aggregating, joining and applying business logic to produce meaningful analytical data sets.
The final step is to load this analytical data set into a new storage location, like a data ake, database or data warehouse.

### Consume / Visualize
You have two ways to consume data : by querying or by using BI tools.
Querying produces results that are great for quick analysis by data analysts.
BI tools produce visualization that are grouped into reports and dashboards to help users explore data and determine the best actions to take.

---
## 2. Challenges of data analytics
5 mains challenges of data analytics
- Volume
- Velocity
- Variety
- Veracity
	- Veracity is the degree to which data is accurate, precise, and trusted. It is contingent on the integrity and trustworthiness of the data.
	- Solutions should be able to identify the common flaws in the data and fix them before the data is stored. This is known as data cleansing. This process must be able to be completed within the time requirements of the solution, up to and including real-time processing speeds.
- Value

A data lake is a **centralized** repository that allows you to store **structured**, **semi-structured**, and **unstructured** data at any scale.

Data lakes promise the ability to store all data for a business in a single repository. You can leverage data lakes to store large volumes of data instead of persisting that data in data warehouses. Data lakes, such as those built in Amazon S3, are generally less expensive than specialized big data storage solutions. That way, you only pay for the specialized solutions when using them for processing and analytics and not for long-term storage. Your extract, transform, and load (ETL) and analytic process can still access this data for analytics.


### Variety
Data come in from difference sources in difference data type.
Generally can be divided into
- [[Structure Data]]
	- Often stored within a database management system ( DBMS )
	- Row, Col, Tables, Schema
	- Transactional Database : Heavy write and update
	- Analytical Databases : Heavy Read
	- RDS, Aurora, MySQL, MariaDB, PostgresSQl, Microsoft SQL Server, Oracle.
- [[Semi-Structure]]
	- Element and attributes
	- NoSQL or non-relational database
	- No pre-defined schema, can be stored in files
	- Highly flexible
- Un-Structure
	- Stored as files
	- No pre-defined schema
	- Images, Videos, PDFs and CSV files
	- Must pre-processed all files
	- Use a service to add tags or Catalog the dataset.

### Veracity
The degree to which data is accurate, precise and trusted.
>When you have data that is ungoverned, coming from numerous, dissimilar systems and cannot curate the data in meaningful ways, you know you have a veracity problem.

Curation is the action or process of selecting, organizing and looking after the items in a collection.
Data integrity is the maintenance and assurance of the accuracy and consistency of data over its entire lifecycle.

Definitions
- [[Data Cleansing]]
- [[Referential Integrity]]