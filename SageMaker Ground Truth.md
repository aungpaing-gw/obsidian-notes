- `Ground Truth`  creates its own modle as images are labeled by human labeler.
- As this model learns, only images the model isn't sure about are sent to labeler.
- Can reduce the cost of labeling jobs by 70%.

#### Other services to generate training labels
Using pre-trained models or unsupervised services from AWS
- Rekognition
	- AWS service for image recognition
	- Automatically classify images
- Comprehend
	- Text analysis and topic modeling
	- classify text by topics, sentiment