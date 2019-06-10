# Serverless-App

This application is designed to collect, process, and store the real-time datastreams without any servers. In order to improve the personal safety of the firefighters who are equipped with sensors, this application is designed to fetch the data like location, temperature and air quality from the sensors. The data can be processed, stored and visualized in real-time using AWS serverless architecture.

This architecture uses AWS services like: AWS Kinesis, AWS Cognito, AWS Lambda, AWS S3, AWS Dynamo DB. 

Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information. 

Amazon Cognito is used for authentication like user sign-up, sign-in, and access control. It also supports sign-in with social identity providers, such as Facebook, Google, and Amazon etc.

AWS Lambda is an event driven backend service that allows us to run code without using any server.

AWS Simple Storage Service is used for object storage purpose and AWS DynamoDB is used to store the records and it is the database for the applcation.

![Architecture](https://github.com/ramya206/Serverless-App/blob/master/Design/Architecture.png)
