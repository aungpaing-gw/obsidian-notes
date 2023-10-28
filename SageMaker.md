SageMaker can participate in all of the Machine Learning Lifecycle.
- Fetch, clean and prepare data
- Train and evaluate model
- Deploy model, Evaluate results in production
Sagemaker is a managed service.

After deploy, new data will be fetch and model wilil be retrained
![[phases_in_sagemaker.png]]

## Usage
- spin up training instances, training in large scale.
- Give notebook for data preparation
- Spin up instances in EC2 for deploy model as endpoint.

## Architecture
![[sagemaker_architecture.png]]

## SageMaker Notebook
- Notebook instances on EC2
	- S3 data access
	- Scikit_learn, Spark, Tensorflow
	- Wide variety of built-in models
	- Ability to spin up training instances
	- Ability to deploy trained models for makeing predictions at scale

## Data Preparation
- Data usually comes from [[S3 Data Lakes|S3]]
	- Ideal format varies with Algorithms - often it is RecordIO / [[Protocol Buffer (Protobuf)|protobuf]]
- Can also ingest from [[Athena]], [[EMR]], [[Redshift]]
- [[Apache Spark]] integrates with SageMaker
- scikit_learn, numpy, pandas

## Analyzing and Preprocessing Data
SageMaker provides the following components that helps with this phase
1. SageMaker notebook instance
	- Managed ML compute instance running the Jupyter Server (Like Colab)
2. SageMaker Studio
	- Monitor notebooks, models, training.
3. SageMaker Data Wrangler
	- import, transform and analyze data through a visual workflow, then export that workflow. Can import data form [[S3 Data Lakes|S3]], [[Athena]], and [[Redshift]].
	- Can add four different types of steps
		1. Transform
		2. Analysis
		3. Join
		4. Concatenate
4. SageMaker Processing
	- common data processing workloads such as preprocessing, feature engineering and model evaluation.
	- Take Python or PySpark script, copies data from [[S3 Data Lakes|S3]], processes the data, and writes back output data to another S3 locatoin.
5. SageMaker GroundTruth

## Training
- Creating a training job
	- URL of S3 bucket with training data
	- ML compute resources
	- URL of S3 bucket for output (model / logs)
	- ECR path to training code.
- Training options
	- Built-in training algorithms
	- Algorithms from AWS Marketplace
	- Spark MLLib
	- Custom Python Tensorflow / MXNet code
	- Own Docker image
- DataLoader (Stream to training)
	- File mode
	- Pipe mode (stream, useful for large size data)

SageMaker provides 17 build-in algorithms for typical use cases. These includes binary or multiclass classification, regression, time series forecasting, anomaly detection, IP address anomalizes, embedding generation, clustering, topic modeling, text classification and summarization, image classification, object detection and semantic segmentation.

## Inference
[[Sagemaker Inference]]

## Deploying
- Save trained model to S3
- Deploy in two ways
	- Persistent endpoint for making individual predictions on demand.
	- SageMaker Batch Transform to get predictions for an entire dataset
- Cool options
	- Inference Pipelines for more complex processing
	- SageMaker Neo for deploying to edge devices
	- Elastic Inference for accelerating DL Models.
	- Automative scaling (increase # of endpoints as needed)
 - Additional Features
	 - Endpoint Autoscaling
	 - Model Compilation
	 - Elastic Inference (EI)
	 - Inference Pipelines
	 - SageMaker Model Registry

## Built-in Algorithms 
- [[Linear Learner]], [[XGBoost]], [[DeepAR]], 
- [[Seq2Seq]], [[BlazingText]], [[Object2Vec]], 
- [[Object Detection]], [[Image Classification]],[[ Semantic Segmentation]], 
- [[Random Cut Forest]], [[Neural Topic Model]], [[LDA]], [[KNN]], [[K-Means]], [[PCA]] 
-[[ Factorization Machines]], [[IP Insights]], Reinforcement Learning

## Infrastructure Security
[[SageMaker Security]]

## Additional Features
- Distributed Training
- Managed Spot Training
- Automatic Model Tuning
- Monitoring Training Job
- SageMaker Debugger