Allows businesses to rapidly develop personalized recommendation systems to provide a better customer experience to their end customers.

## Usages
- Financial Services
- E-commerce Platform
- Travel Company
- Media and Entertainment Business

## Data
Personalization mainly reply on three forms of data:
- User data
	- User's age, location, income, gender, personal preferences
- Item Data
	- Data about actual product
- User-Item Interaction Data
	- Data about how the set of users have interacted with these items
> The goal of any personalization is to take this data and extract meaningful insights that can lead to a customer purchasing a product or item.

## Methods
- Content-based filtering
	- Cluster users into similar groups and recommend items in that cluster
- Collaborative filtering
	- Decompose large sparse user-item interaction matrices into smaller matrices (matrix factorization) to extract hidden or latent vectors for each user and each item.
Although this is a highly popular technique, if there is no a lot of items, matrix factorization  can often not work as well. In this case use [[XGBoost]] and [[Factorization Machines]]

## Receipes
Personalize employs the concept of recipes, 
- User Personalization Recipes
- Ranking-Based Recipes
- Related Item Recipe

## Metrics
- Precision at K 
	- of the K items recommended, how many were actually relevant, divided by K
- Mean Reciprocal Rank at K
	- The mean of the reciprocal rank of the first recommendation out of K, where the mean is taken over all queries.

![[personalize_workflow.png]]