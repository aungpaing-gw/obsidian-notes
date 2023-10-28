References
- [Youtube](https://www.youtube.com/watch?v=zTJTzKcNzMk)
- [Secure Machine Learning on AWS](https://www.youtube.com/watch?v=4chQZJL7Qz8)
- [Blog Post](https://docs.aws.amazon.com/sagemaker/latest/dg/security.html)

## General Security Features
- Security Features
	- Security
		All traffic transfer is over private and secure network links
	- Authentication
		Ensure compliance with corporate authentication standards
	- Authorization
		limit access to data, code and training resources by role and job function
	- Data Protection
		Encrypt data in transit and data at rest with customer managed keys ( CMK )
- Model Governance Features
	- Auditability
		Provide end-to-end auditability at the user and object level
	- Artifact Management
		Securely persist and protect code and model artifacts
	- Model Explainability
		Provide interpretability  on model training results
	- Model monitor
		monitors for data drift and model drift
	

SageMaker Studio and notebook instances allow direct internet access by default. This allow users to download popular packages and notebooks. However, this could provide an additional avenue for unauthorized access to the data. eg. if user install malicious code on the instance in the form of a publicly available source code library, it could access user data.

User can choose to restrict which traffic can access the internet by launching Studio and notebook instances in [[AWS VPC]] of user choosing. User can disable internet access to add an additional layer of security.


## Security Tenets
- AWS do not retain customer data ( dataset, model artifacts )
- Always encrypt in transit
- Always encrypt at rest
- Compute isolation
- Network isolation
- Secure, fully-managed infrastructure
- Audit-ability
- Compliance
- 