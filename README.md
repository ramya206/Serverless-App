# Serverless-App

This application is designed to collect, process, and store the real-time datastreams without any servers. In order to improve the personal safety of the firefighters who are equipped with sensors, this application is designed to fetch the data like location, temperature and air quality from the sensors. The data can be processed, stored and visualized in real-time using AWS serverless architecture.

This architecture uses AWS services like: AWS Kinesis, AWS Cognito, AWS Lambda, AWS S3, AWS Dynamo DB. 

Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information. 

Amazon Cognito is used for authentication like user sign-up, sign-in, and access control. It also supports sign-in with social identity providers, such as Facebook, Google, and Amazon etc.

AWS Lambda is an event driven backend service that allows us to run code without using any server.

AWS Simple Storage Service is used for object storage purpose and AWS DynamoDB is used to store the records and it is the database for the applcation.

![Architecture](https://github.com/ramya206/Serverless-App/blob/master/Design/Architecture.png)

For processing the real time data we require Kinesis stream, a producer and consumer.

1. Our producer is the sensor attached to the firefighter personnel. This sensor emits data regularly including the person’s current location, distance traveled in the previous second etc.

2. AWS Cognito user pool is created and necessary IAM roles should be assigned to access and view the data from streams. In this project for now, since Sign-up/Sign-in is not yet configured, unauthenticated identities are supported by providing a unique identifier and AWS credentials for users who do not authenticate with an identity provider

3. The Kinesis stream is setup to collect data every few seconds. Since IOT sensors send raw data, it becomes unmanageble, so AWS Kinesis analytics is used to aggregate and process the data, it is helpful in calculating total distance travelled, maximum temperature in air layer, maximum concentration of pollutants etc. The processed data is stored in AWS Kinesis destination stream 

4. AWS Lambda to process data from the wildrydes Amazon Kinesis stream created earlier. In this step, Lambda function is created and configured to read from the destination stream and write records to an Amazon DynamoDB table as they arrive.
