provides a set of natural language processing based APIs to pretrained and custom models that can extract insights from text.

Can analyze a document for the following characteristics:
- Entities
	- Date, Location, Organization, Persons, Quantity
- Key phrases
- Personally Identificable Information (PII)
- Language
- Sentiment
- Syntax

## Custom Models
There are three types of custom models that can be trained
- Custom Document Classification
- Custom Entity Detection
- Document Topic Modeling

> Notes:
> 	All Text are UTF-8 encoded and the size of each document must be less than 5,000 bytes.
> 	If plan to send more than 25 documents per second : use Batch Detect operation.
> 	`DetectDominatnLanguage` for less than 25 document, use `BatchRequestDominantLanguage` for 25 up to 250 documents per second.

### Real World Scenario

#### Email Parsing Model
A customer collects incoming email in a JSON document and wants to use the subject line to redirect emails to the right department. The customer first organizes their data into a set of two-column CSV files; the first column is the department label, and the second column is the subject line. They can then use the console or the `CreateDocumentClassifier` API to start a custom training job.
Comprehend uses between 10 and 20 percent of the training data for testing the final trained model and provides a classifier performance metric to help determine if the model is trained well enough.
The customer can then analyze incoming emails by passing in the subject line to the hosted model end point and routing the email using the results obtained from this API call.
