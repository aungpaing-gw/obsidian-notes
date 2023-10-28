- Forecasting one-dimensional time series data
- Use RNN's
- Allow to trian the same model over several related time series.
- Finds frequencies and seasonality

## Inputs
- JOSN lines format
	- Gzip or Parquet
- Each record must contain
	- Start : The starting time stamp
	- Target : The tmie series values
	- Dynamic_feat : dynamic features ( eg. was a promotion applied to a product in a time series of product purchases)
	- Cat : categorical features

## Usage
- Always include entire time series for training, testing and inference
- Use entire dataset as training set, remove last time points for testing.
- Evaluate on withheld values
- Don't use very large values for prediction
- Train on many time series and not just one when possible

## Hyperparameters
- context_length
	- Number of time points the model sees before making a prediction
	- Can be smaller than seasonalities
- Epochs
- lr, batch_size, number of cells

## Instance Types
- Can use CPU or GPU
- Single or multi machine
- Start with CPU (C4.2xlarge, C4.4xlarge)
- Move up to GPU if necessary
- CPU-only for inference
- May need larger instances for tuning