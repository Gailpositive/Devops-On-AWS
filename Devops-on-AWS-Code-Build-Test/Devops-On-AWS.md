
# DEVOPS ON AWS..CODE, BUILD AND TEST.
## Introduction to DevOps cultural philosophies, practices, and tools to deliver applications and services faster and at a higher quality. 
<img width="495" alt="image 3" src="https://github.com/IwunzeGE/DevOps-Project/assets/111061512/eeb8e89f-f45a-4cf0-aa64-5d367586a7c4">


### AWS APPLICATION used:  
* AWS Cloud9 development environment for a sample application
* Amazon Simple Storage Service (Amazon S3) bucket
* Amazon API Gateway REST API
* Amazon DynamoDB table
* AWS Step Functions state machine
* AWS Lambda functions
* The final exercise includes instructions to delete all the resources created in the exercises.
<img width="483" alt="image8" src="https://github.com/IwunzeGE/DevOps-Project/assets/111061512/9a1fcdd2-2fb9-4774-b2be-bbfc9dbd0233">

### Learning Objectives
* Use AWS Cloud9 to set up my development environment
* Explore how I can use AWS CodeBuild to build and test code with continuous scaling
* Evaluate Git branching strategies

### Exercise: Setting Up Development Environment
In a production environment, I'd create a custom policy in AWS IAM for precise control. However, for this exercise, I skip that. I'm setting up a development space with AWS Cloud9, downloading code, and using AWS SAM CLI to build a serverless app. It includes backend elements like API Gateway, Lambda functions, DynamoDB, and a smart process. The frontend, a React web app, sits in an S3 bucket. Finally, I store my progress in AWS CodeCommit once the app is running.

### Step 1:
* Create cloud9 environment on AWS services 
<img width="960" alt="3" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/94bb4cee-947b-4599-ad34-9406632f69da">

* Give the app a name, brief description and create a new ec2 instance for the app to run on
<img width="814" alt="4" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/104723c9-e170-4abe-83c9-12413b1ff8c8">

* Trivial app created
<img width="914" alt="5" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/32029298-184d-4bed-bf1a-677cd890a62e">

* Cloud9 environment IDE terminal opened
<img width="958" alt="6" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/78008e02-0abd-4993-bdfa-3b47a1170e43">
