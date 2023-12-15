
# DEVOPS ON AWS..CODE, BUILD AND TEST.
## Introduction to DevOps cultural philosophies, practices, and tools to deliver applications and services faster and at a higher quality. 
### AWS APPLICATION used:  
* AWS Cloud9 development environment for a sample application
* Amazon Simple Storage Service (Amazon S3) bucket
* Amazon API Gateway REST API
* Amazon DynamoDB table
* AWS Step Functions state machine
* AWS Lambda functions
* The final exercise includes instructions to delete all the resources created in the exercises.

### Learning Objectives
* Describe how the DevOps model benefits development and operations teams
* Explain DevOps cultural philosophies, practices, and tools
* Use AWS Cloud9 to set up my development environment
* Explore how I can use AWS CodeBuild to build and test code with continuous scaling
* Evaluate Git branching strategies

### Exercise: Setting Up Your Development Environment
In a production environment, I  would normally create a customer managed policy in AWS Identity and Access Management (IAM). Customer managed policies provide more precise control over my policies than policies that AWS manages. This policy would then have permissions that are specific to the AWS resources I need. I would also attach this policy to a new user and log in to the AWS Management Console with that new user. However, because I am working in an exercise environment, those steps were omitted.

In this exercise, I will start by creating an AWS Cloud9 environment for your development environment. In this environment, I will download and extract the source code that I will use in this course. I will deploy the application’s backend infrastructure by using the AWS Serverless Application Model Command Line Interface (AWS SAM CLI). I will use AWS SAM to create all the resources that host the backend of the application: an Amazon API Gateway gateway, AWS Lambda functions, an Amazon DynamoDB table, and an AWS Step Functions state machine. I will also deploy the application frontend: a React web application that’s hosted on an S3 bucket, which acts as the web server. After the application is up and running, I will put the application under source control by using AWS CodeCommit.
