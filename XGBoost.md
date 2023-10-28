- eXtreme Gradient Boosting
	- Boosted group of decision trees
	- New trees made to correct the errors of previous trees
	- Use gradient descent ot minimize loss as new trees are added.
	- Comprise of weak learner and strong learner.
- Fast
- Can be used for classification and regression (regression tree)

## Inputs
- XGBoost is open source and not made for SageMaker
- Initially, it takes CSV or libsvm inputs.
- Recently extended input formats to accept recordIO-[[Protocol Buffer (Protobuf)|protobuf]] and Parquet as well.

## Usage
- Models are serialized / deserialized with Pickle in notebook
- Can use as a framework within notebooks
	- Sagemaker.xgboost
- Or as a built-in SageMaker algorithm

## Hyperparameters
- Subsample
	- Prevent overfitting
- Eta
	- step size shrinkage, prevent overfitting
- Gamma
	- Minimum loss reduction to create a partition
	- larger => more conservative
- Alpha
	- L1 regularization; larger => more conservative
- Lambda
	- L2 regularization; larger => more conservative
- eval_metric
	- Optimize on AUC, error, rmse
	- eg. if care about FP more than accuracy, use AUC
- scale_pos_weight
	- Adjust balance of positive and negative weight
	- for unbalanced classes
- max_depth
	- max depth for tree
	- Too high => Overfit

## Instance Types
- Use CPU's only for multiple instance training
- Is memory-bound, not compute-bound
- M5 is a good choice
- As of XGBoost 1.2, single-instance GPU training is available
	- eg. P3
	- must set tree_method hyperparamter to gpu_hist