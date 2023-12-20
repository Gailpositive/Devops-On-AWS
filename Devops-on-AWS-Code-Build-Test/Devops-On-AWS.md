
# CREATING A REACT GAME WEB APP ON AWS DEVOPS
## Introduction to AWS DevOps  practices, and tools to deliver applications and services faster and at a higher quality. 
### Exercise: Setting Up Development Environment
In a production environment, I'd create a custom policy in AWS IAM for precise control. However, for this exercise, I skip that. I'm setting up a development space with AWS Cloud9, downloading code, and using AWS SAM CLI to build a serverless app. It includes backend elements like API Gateway, Lambda functions, DynamoDB, and a smart process. The frontend, a React web app, sits in an S3 bucket. Finally, I store my progress in AWS CodeCommit once the app is running.

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
* Setting up  my development environment on AWS Cloud9
* Explore how I can use AWS CodeBuild to build and test code with continuous scaling
* Evaluate Git branching strategies


### Task 1: Create cloud9 environment and downloading the application
<img width="960" alt="3" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/94bb4cee-947b-4599-ad34-9406632f69da">

* Give the app a name, brief description and create a new ec2 instance for the app to run on
<img width="814" alt="4" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/104723c9-e170-4abe-83c9-12413b1ff8c8">

* Trivial-app created
<img width="914" alt="5" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/32029298-184d-4bed-bf1a-677cd890a62e">

* Cloud9 environment IDE terminal opened
<img width="958" alt="6" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/78008e02-0abd-4993-bdfa-3b47a1170e43">

* Download the application and unzip the file
<img width="960" alt="4" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/50b7a130-7d7e-424f-89a3-50c900425487">

### Task 2: In deploying AWS serverless application model (SAM) & AWS command line interface (CLI) to create the back-end infrastracture, 
* I cd into the app folder and  use SAM to build the template.yaml file.
* From the Outputs table in the terminal output, I copy and saved the Websocket Value
<img width="957" alt="5" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/54b3a124-27bf-480f-abab-661be43e12d3">


 ### Task 3: Testing the frontend on cloud9
*  SAM deployed
*  i cd into the path "trivia-app/front-end-react/src/config.js"
*  Cat the "config.js" file to view the websocketend point to update
*  To update the websocketend point, I Vi  "confif.js"
*  Update it with the websocket value copied and saved ealier
<img width="842" alt="6" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/5e72d96f-82ec-41a1-88e9-8bbf78814cce">

* Install "Node version manager" nvm and set it to the v16 (codename: Gallium)
<img width="753" alt="7" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/5bee82e4-9768-44e9-ab31-cc628fbe8f30">
