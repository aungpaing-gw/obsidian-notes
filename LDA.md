- Latent Dirichlet Allocation
- Another topic modeling Algorithm, The other is [[Neural Topic Model]]
	- Not deep learning
- Unsupervised
	- The topic themselves are unlabeled; they are just grouping of documents with a shared subset of words
- Can be used for things other than words
	- Cluster customers based on purchases
	- Harmonic analysis in music
 
## Inputs
- Train channel, optional test channel
- recordIO-[[Protocol Buffer (Protobuf)|protobuf]] or CSV
- each document has counts for every word in vocabulary 
- Pipe mode only support with recordIO

## Principle
- unsupervised : generate however many topic you specify
- Optional test channel can be used for scoring results
	- Per-word log likelihood
- Functionally similar to [[Neural Topic Model]], but CPU-based
	- Therefore maybe cheaper / more efficient


## Instance Types
- Single-instance CPU training