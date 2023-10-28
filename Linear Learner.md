- Linear Regression
	- Fit a line to the training data
	- Predictions based on that line
- Can handle both regression and classification
	- For classification, a linear-threshold function is used.
	- Can do binary or multi-class classification

## Inputs
- RecordIO-warpped, [[Protocol Buffer (Protobuf)|protobuf]]
	- Float32 data only!
- CSV
	- First column assumed to be the label
- File or Pipe mode both supported

## Notes
- Preprocessing
	- Training data must be normalized
	- Linear Learner can do this automatically.
- Training
	- Use SGD, Adam, AdaGrad, etc.
	- Multiple models are optimized in parallel
	- Tune L1, L2 regularization
- Validation
	- Most optimal model is selected

## Hyper-parameters
- Balance_multiclass_weights
	- Give each class equal importance in loss funcitons
- lr, batch_size
- L1, L2(weight decay)

## Instance Types
- Training
	- Single or multi-machine CPU or GPU
	- Multi-GPU does not help?