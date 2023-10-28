- Anomaly detection
- Unsupervised
- Detect unexpected spikes in time series data
- Breaks in periodicity
- unclassificable data points
- assigns an anomaly score to each data point

## Inputs
- RecordIO-protobuf or CSV
- Can use File or Pipe mode
- Optional test channel for computing accuracy, precision, recall, and f1 on labeled data

## Principle
- Creates a forest of tree where each tree is a partition of the training data; looks at expected change in complexity of the tree as the result of adding a point into it.
- Data is sampled randomly, then trained.
- RCF shows up in Kinesis Analytics as well, it can work on streaming data too.

## Hyperparameters
- num_trees
- num_samples_per_tree

## Instance Types
- Does not take advantages of GPUs
- M4, C4, or C5 for training
- ml.c5.xl for inference

