leverages the same technologies powering Amazon [[Alexa]] but is available as a transcription service that allows us to transcribe voice data without any prior machine learning knowledge.
- Stream and batch mode
	- For streaming, audio is directly streamed via the HTTP/2 protocol.
	- For batch audio files stored in [[S3 Data Lakes|S3]], `StartTranscriptJob` API can be used.
- Multiple Language Support
- Job Queuing
	- Send jobs to queue so that you don't have to build custom logic to prevent API throttling.
- Custom Vocabulary and Filtering
- Automatic Content Redaction
	- If audio includes personally identifiable information(PII), there is an option to redact it from the transcribed output or provide both unredacted and redacted scripts. eg. Credit Card Numbers. Note : This feature is only available in English.
- Language Identification
- Speaker Identification

## Transcribe Medical
The medical domain is highly specialized with a vast vocabulary. As a result, most common deep learning transcription models do not work well in this field. unless they have been specifically trained on medical data.
It is an ASR service that enables you to transcribe medical audio such as physician dictation, patient-to-physician conversations and telemedicine, available both in streaming and batch mode (only for Primary Care) and allows to build custom vocabularies

> Not all AI Services have a medical speciality. [[Comprehend]] and Transcribe does. There is no Translate Medical or Textract Medical.