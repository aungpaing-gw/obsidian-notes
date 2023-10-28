- Both input and output are sequences of tokens.
- Machine Translation
- Text summarization
- Speech to Text
- Implemented with RNN's and CNN's with attention

## Inputs
- RecordIO-[[Protocol Buffer (Protobuf)|protobuf]]
	- Tokens must be integers (most algorithms want floating point data)
- Start with tokenized text files
- Convert to [[protobuf]] using sample code
	- Packs into integer tensors with vocabulary files
	- A lot like TF/IDF
- Must provide training data, validation data and vocabulary files

## Usage
- Training for Machine Translation can take days
- Pre-trained models are available
- Public training datasets are available for specific translation tasks.

## Hyperparameters
- optimizer_type
- lr, batch_size
- num_layers_encoder, num_layers_decoder
- Metrics
	- Accuracy, BLEU, Perplexity

## Instance Types
- Can only use GPU instance types (eg. P3)
- Can only use a single machien for training
	- Can use multi-GPU's on one machine.