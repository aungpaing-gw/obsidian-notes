powered by natural language understanding (NLU) and automatic speech recognition ([[ASR]]), that allows users to build and deploy conversational interfaces for their applications.
With Lex, you can build a tailored and personalized experience for your customers to engage with your platform without any deep learning expertise.

## Lex Concepts
A bot is the entity that will perform the desired action. For an e-commerce application, this action would be fulfilling a customer order, connecting the customer to human representative.
An intent is the action you want the bot to perform.
An utterance is what the user actually asks for.
> samples of utterance would be required to paired with intent.

A slot is a set of parameters that define the user's ask and a slot type is a characterization of that slot.

If lex cannot understand utterance, there is 
Fallback intent : default call to lambda function
or, trigger a document search with `KendraSearchIntent` API to provide an answer.

With Lex, the backend actions can be performed by using an AWS [[Lambda]] function. For example, if your bot is designed to make an appointment at local doctor's office, have the Lambda function write to AWS [[RDS]] or [[DynamoDB]] appointment table.

![[lex_appointment.png]]