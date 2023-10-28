- Text classification
	- Predict labels for a sentence
	- Useful in web searches, information retrieval
	- Supervised
- Word2Vec
	- Blazing Text use Word2Vec to convert strings to vectors?
	- Semantically similar words are represented by vectors close to each other
	- Useful for NLP, not an NLP algorithm
		- Used in machine translation, sentiment analysis
	- It only works on individual words, not sentences or documents.

## Inputs
- For supervised text classification
	- One sentence per line
	- First word in the sentence is the string `__label__` followed by the label
- Word2Vec wants a text file with one training sentence per line.bow ()

## Hyperparameters
- Word2Vec:
	- mode (cbow, skip_gram, batch_skipgram)
	- lr
	- window_size
	- vector_dim
	- negative_samples
- Text classification
	- Epochs
	- lr
	- word_ngrams
	- vector_dim

## Instance Types
- For cbow and skipgram
	- single ml.p3.2xlarge
	- Any single CPU or single GPU instance will work
- For batch_skipgram, can use single or multiple CPU instances
- For Text classification
	- IF less than 2GB training data => C5
	- Single GPU instance (ml.p2.xlarge or ml.p3.2xlarge) for large dataset.