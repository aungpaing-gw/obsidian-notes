a text translation service that uses advanced state-of-the-art deep learning to provide high-quality translations to customers without any deep learning experience, with a pay-for-what-you-use pricing structure.
- Sync and Async APIs: 
	- Asynchronously process large numbers of documents using a batch job (in 5GB batches) with the `StartTextTranslationJob` API.
	- Synchronously process smaller documents in real time with `TranslateText` API.
- Custom terminology and parallel data

Translate does not let you build your own custom translation models; it uses models trained by Amazon. As a result, Amazon may use customer data to improve the quality of its algorithms and models.

![[customer_service.png]]