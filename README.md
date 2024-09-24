# Translation Application in AWS

- The application uses Amazon Translate  to translate a text into a different language.
- After translating the text, the application saves the result into an Amazon DynamoDB  table. The application uses the DynamoDB table before translating to make sure that the same text was not translated before. If it was, it uses the saved value. If it wasn't, it translates the text and saves it into the database.
- It exposes the translation component as a synchronous API using Amazon API Gateway .
- Finally, I provided a way to invoke the translation component asynchronously, by sending events to an SQS queue, using EventBridge Pipes.
- Lastly I created an AWS SAM template that can be used to build and deploy the entire application in an automated and repeatable way.

## Architecture

![image](https://github.com/user-attachments/assets/2745e546-b8e5-4269-91e8-b09ab1d4129e)

## Modules

1. Build Step Functions state machine to translate the text
2. Integrate with API Gateway to expose the functionality
3. Invoke the state machine from an SQS queue using EventBridge Pipes
4. Create a SAM template to deploy the application

I referred the following AWS Workshop to build this project [link](https://catalog.workshops.aws/svsmindsetapps/en-US)
