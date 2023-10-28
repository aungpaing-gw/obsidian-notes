## Research and production code
- Research code promote exploration and validate models using iterative proceses. which might lack formal quality, stability or scaling requirements.
- Production code must meet objective and fixed requirements, facilitate collaboration through version control, maintain a code deployment history, and meet code reliabiitliy standards.
| Research code                | Production code              |
| ---------------------------- | ---------------------------- |
| Exploratory                  | Fixed requirements           |
| Iterative                    | Version Controlled           |
| Few tests or errors handling | Production-level reliability |


## Question to ask before deploy
These are questions that arise quite frequently when talking to customers
- Computational Cost of inference
- How quickly the data change
- How significant are the changes needed to deploy
- Does the model performance meet the business need