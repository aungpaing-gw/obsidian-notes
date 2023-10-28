- K-Nearest-Neighbors
- simple classification or regression algorithm
- Classification
	- Find the K closest points to a sample point and return the most frequent label
- Regression
	- Find the K closest points to a sample point and return the average value
 
## Inputs
- Train channel contains data
- Test channel emits accuracy or MSE
- recordIO-[[Protocol Buffer (Protobuf)|protobuf]] or CSV training
	- First column is label
- File or pipe mode

## Principle
- Data is first sampled
- SageMaker includes a dimensionality reduction stage
	- Avoid sparse data ("curse of dimensionality")
	- At cost of noise / accuracy
	- "sign" or  "fjlt" method
- Build an index for looking up neighbors
- Serialize the model
- Query the model for a given K

## Hyperparameters
- K
- Sample size

## Instance Types
- Training on CPU or GPU
	- ml.m5.2xlarge
	- ml.p2.xlarge
- Inference
	- CPU for low latency
	- GPU for higher throughput on large batches
