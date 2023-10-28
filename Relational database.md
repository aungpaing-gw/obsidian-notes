AWS Services :  [[RDS]], [[Redshift]]

RDS implement row base indexing, best for OLTP
Redshift implement columns base indexing, best for OLAP

a relational database is built to store [[Structure Data]] so it can be collected, updated, and queried easily.

Relational database rely on a series of structures, called tables, to hold the collected data.

These tables are navigated using the structured query language, or SQL.

### Advantages
- Provides [[ACID]] compliance
- Data is easily stored, edited and retrieved using a common SQL language
- can be scaled up quickly

### Disadvantages
- Struggle storing unstructured data
- Querying can be slow due to complex join requirements.
- The schema can make scaling out quite difficult.

### Types of Information Systems
Two main ways of information systems of organizing data within a relational database.
- OLTP, online transaction processing, focus on the storage of transactions.
- OLAP, online analytical processing, focus on the analyzing of transactions.


### SQL Example
```sql
CREATE TABLE distributors (
	did    integer PRIMARY KEY,
	name   varchar(40)
);
```
