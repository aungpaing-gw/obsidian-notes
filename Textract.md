an AI services that allows us to quickly extract intelligence from documents such as financial reports, medical records, tax forms, and university application forms beyond simple optical character recognition (OCR). you don't have to build models to extract text, forms or tables from PDF documents; Textract will do that for us.

> Textract is used for extracting forms, tables, and text from PDFs or images. It **does not do document classification, sentiment analysis, or entity recognition**. 

## Usages
- create search index by storing the outputs of Textract document analysis in a Key-Value store like [[DynamoDB]].
- Mining text from documents for NLP: can extract words, lines, and tables.
- Automating data capture from forms: can extract information from structured documents such as tax forms or application forms.
- Cost effective: Pay for what you use.

## Inputs
- Byte array or [[S3 Data Lakes|S3]] object.

Output a **key-value** pair, allowing the user to ingest these outputs into a key-value database store.

sync API : `DetectDocumentText` or `AnalyzeDocument`
async API : Large document : `StartDocumentAnalysis` or `StartDocumentTextDetection`

## Other notes
- HIPAA eligible
- Pay-as-you-go
- Can integrate with [[Augmented AI|A2I]]


![[human_review.png]]
Fig: Document analysis with human review flow