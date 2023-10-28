Reference
[YouTube](https://www.youtube.com/watch?v=bRUNpuRGeZc&t=1s)
## Key concepts
- Model
- Production variant
- Endpoint configuration
- Endpoint

---
## Real-Time Inference
- Performance
	- Optimized for sub-second latency use cases
	- Configurable auto-scaling capabilities
	- CPU and GPU available
- Operationally efficient & Reliable
	- Fully managed
	- Built in support for advanced deployment strategies ( A/B, Linear, Canary )
	- Multi-AZ Support
	- Multi-model / container deployment options
- Secure
	- HTTPS endpoint
	- VPC Support
	- Encrypted storage volumes with option to use AWS KMS
	- Configurable network isolation option
- Constraints
	- The model must return result within **60s.** If not, error.
	- Payload must be less than **6MB.**
 
### Updating and Endpoint
- Multi-model Endpoints

---
## Asynchronous Inference
- Performance
	- Auto-scaling with down to 0 instances.
- Constraints
	- Timeout for 50 mins.
	- Payload can be 1GB.
	- Model size can be large.

---
## Batch Transform Inference
Data and model must be in S3.
Make predictions on very large datasets. Run Inference when you don't need a persistent endpoint.
Do not have Load Balancer, REST Endpoint?

---
## Serverless Endpoint
- Automatically spins up and manage compute resouces
- Automatic scaling based on demand
- Managed logging and monitoring
- Constraints
	- Do not support GPU currently.


---
## Inference Optimizer
- Use Inference recommender for selecting the right instance.
- Delete endpoints that aren't in use
- Host multiple models with multi-model endpoints
- Use the right automatic scaling policy based on your traffic patterns
- Use caching features to reduce the latency.
- Optimizer model using SageMaker Neo
- use Amazon SageMaker savings plans