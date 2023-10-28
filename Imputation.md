Handling the missing data

Methods for imputation for missing data
- Mean Replacement ( not preferred )
- Dropping ( not preferred )
- Machine Learning
	- KNN : Find K 'nearest' samples and average their values
- Deep Learning
	- Works well for categorical data
- Regression
	- Find linear or non-linear relationships between the missing feature and other features
	- SOTA : MICE (Multiple Imputation by Chained Equation)
- Get more data