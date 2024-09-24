# Translation Application in AWS

- The application uses Amazon Translate  to translate a text into a different language.
- After translating the text, the application saves the result into an Amazon DynamoDB  table. The application uses the DynamoDB table before translating to make sure that the same text was not translated before. If it was, it uses the saved value. If it wasn't, it translates the text and saves it into the database.
- It exposes the translation component as a synchronous API using Amazon API Gateway .
- Finally, I provided a way to invoke the translation component asynchronously, by sending events to an SQS queue, using EventBridge Pipes .
- Lastly I created an AWS SAM template that can be used to build and deploy the entire application in an automated and repeatable way.
