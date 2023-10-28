- Create low-dimensional dense embeddings of high-dimensional objects.
- Basically Word2Vec, Generalized to handle things other than words.
- Computer nearest neighbors of objects
- Visualize clusters
- Recommendataoins (similar items or users)

## Inputs
- Data must be tokenized into integers
- Training data consists of pairs of tokens and/or sequences of tokens
	- Sentence - sentence
	- Labels-sequence (genre to description)
	- Customer - Customer
	- Product - Product
	- User-item

## Usages
- Process data into JSON lines and shuffle it
- Train with two input channels, tow encoders and a comparator
- Encoder choices:
	- Average-pooled
	- CNN
	- Bidirectional LSTM
- Comparator is followed by a feed-forward neural network.

## Hyperparameters
- lr, dropout, early stopping, batch_size, L1, L2, layers
- Encoder1_network, Encoder2_network
	- HCNN, BiLSTM, Pooled_Embedding

## Instance Types
- Can only train on a single machine (CPU or GPU, multi-GPU is OK)
	- MI.m5.2xlarge
	- MI.p2.xlarge
	- if needed, go up to ml.m5.4xlarge or ml.m5.12xlarge
- Inference : use ml.p2.2xlarge
	Use `INFERENCE_PREFERRED_MODE` env_var to optimize for encoder embedding rather than classification or regression.