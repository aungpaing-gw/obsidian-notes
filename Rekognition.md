AI services that makes it easy for users to implement image or video analysis workflows into their applications.
With Amazon Rekognition, developers can simply leverage **pretrained models or train custom machine learning models** without having to worry about writing the algorithm code or about setting up or managing the infrastructure to **train and deploy** a deep learning model.

Amazon Rekognition can be used in following key use cases:
- Image Labeling
- Custom Image labeling
- Face detection and search
- People Paths (only Video)
- Text detection
- Celebrity Detection
- Personal Protective Equipment (only image)

> Key Phrases : 
> "Without any prior machine learning knowledge" or "Cost effective", "Custom model"

Static Image => Synchronous
Videos => Asynchronous => Once the job is finished, will be notified with Amazon SNS by publishing to an SNS topic.

> The quality of Rekognition output strongly depends on the quality of input image.

## Inputs
- S3
- Ingest from [[Kinesis]] Video Streams, process videos and publish the outputs to Amazon [[Kinesis]] Data streams for stream processing.


---
## Real World Scenario
`Facial Recognition in Video`

Imagine you are a solutions architect at a media company who wants to ingest streaming
video content as it is aired and detect faces of known people in the videos. However, your
executives are concerned that building, training, and maintaining these ML models could
be time intensive and challenging given the deep learning expertise required. They want
you to design an architecture that can address this use case but also keep costs low.

The key to a scenario like this is to understand that the executives are concerned about the lack of deep learning expertise in their organization being a barrier to developing this use case. Amazon Rekognition Video is ideally suited for this.

![[facial_recognition.png]]
