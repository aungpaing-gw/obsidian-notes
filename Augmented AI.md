---
aliases : [A2I]
---
To get a secondary human review of a low-confidence prediciton form ML model.

Works out of the box with [[Rekognition]] and [[Textract]].
Can also use A2I with own custom ML model.

First, define a human review workflow
- define a work team that will review predictions
- Using a UI template for providing instructions and the interface for humans to provide feedback (worker task template)

## Real World Scenario
#### Detecting Loan Application Fraud
A financial services company has a machine learning model that predicts whether a loan application is fraudulent or not. A recent mandate states that this company must review predictions of fraudulent loan applications by humans before making a decision on the loan. The company uses A2I to support automated machine learning by first calling the machine learning model endpoint and analyzing the confidence score. If the confidence score is less than 90 percent, the client triggers a human review loop.
![[a2i.png]]