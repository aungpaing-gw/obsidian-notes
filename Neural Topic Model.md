- Organize documents into topics
- Classify or summarize documents based on topics
- not just TF / IDF
	- "bike", "car", "train", "mileage might classify a document as "transportation"
- Unsupervised
	- Algorithm is "Neural Variational Inference"

## Inputs
- Four data channels
	- Train is required
	- vlaidation, test and auxiliary are optional
- RecordIO-protobuf or CSV
- Words must be tokenized into integers
	- Every document must contain a count for every word in the vocabulary in CSV
- File or Pipe mode

## Principle
- define how many topics you want
- These topics are a latent representation based on top ranking words
- One of two topic modeling algorithms in [[SageMaker]]

## Instance Types
- GPU or CPU