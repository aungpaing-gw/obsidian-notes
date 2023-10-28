- Run batch jobs as docker images
- Dynamic provisioning of the instances (EC2 & Spot Instances)
- Optimal quantity and type based on volume and requirements
- No need to manage clusters, fully **[Serverless](Serverless.md)**
- Schedule Batch Jobs using **CloudWatch Event**
- Orchestrate Batch Jobs using **[AWS Step Functions](AWS%20Step%20Functions.md)**

### Difference from Glue ETL
- Use for any computing job regardless of the job ( must provide Docker image )
- For any non-ETL related work, Batch is probably better
- Resources are created in the account, managed by Batch