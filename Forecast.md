an AI service that uses both 
- statistical 
- deep learning-based algorithms 
to provide highly accurate forecasts.

## Models
### Statistical
- Autoregressive in nature
- Algorithms
	- Autoregressive integrated Moving Average (ARIMA)
	- Seasonal ARIMA (S-ARIMA)
	- Prophet
	- ETS (Exponential Smoothing)

### Deep Learning
- Algorithms
	- DeepAR+ (LSTM)
		- train on many time series (>100s)
		- accept metadata about the itme in the form of related time series.
	- CNN-QR ( CNN-Quantile Regression ) 
		- Encoder-decoder
		- accept meta data

## Metrics
- RMSE (amplify outlier values)
- Weighted Absolute Percentage Error | Mean Absolute Percentage Error (WAPE)
- Weighted Quantile Loss (wQL)