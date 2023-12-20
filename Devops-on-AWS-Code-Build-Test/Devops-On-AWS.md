
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
* Successfully created/updated stack - trivia-app in us-west-2
* From the Outputs table in the terminal output, I copy and saved the Websocket Value
<img width="957" alt="5" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/54b3a124-27bf-480f-abab-661be43e12d3">


 ### Task 3: Testing the frontend on cloud9
*  SAM deployed
*  i cd into the path "trivia-app/front-end-react/src/config.js"
*  Cat the "config.js" file to view the websocketend point to update
*  To update the websocketend point, I Vi  "confif.js"
*  Update it with the websocket value copied and saved ealier
<img width="842" alt="6" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/5e72d96f-82ec-41a1-88e9-8bbf78814cce">

* To simplify Node.js version manager, I install nvm and set it to the v16 (codename: Gallium) 
<img width="753" alt="7" src="https://github.com/Gailpositive/Aws-Networking-Implementation-Projects/assets/111061512/5bee82e4-9768-44e9-ab31-cc628fbe8f30">

* I cd into the front-end-react directory and install the NPM dependencies
* NPM installation complied successful
* In the AWS Cloud9 menu bar, I click Preview and click Preview Running Application
<img width="947" alt="9b" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/da298254-6482-4804-9366-9399b01355fe">

### Task 4: Deploying the frontend to an S3 bucket
* Execute the AWS cli command to create the S3 bucket
* Gave it a name with the strings "trivia-app-bucket"
* Run the command to build my web application
* Application build successfully
<img width="882" alt="10" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/b5875f1f-60dc-44c3-b5a1-8a6df3dab0ed">

* Deploy the build artifacts to the S3 buckets
* There was an error issue,the bucket does not allow or support ACLs-Access Control List
<img width="960" alt="12" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/7b7e2516-e48d-421f-aa83-6e3470813567">

*To resolves this problem, I either update the sync command to exclude the "acl public-read" part which will use the defualt ACL settings for the bucket or update S3 policies
<img width="680" alt="15 removed ACLs" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/8794501c-e093-410e-ba39-12e76bfb9f64">

* Since my intent is to make the objects in the S3 bucket publicly readable, than I updated the S3 bucket policy to allow public read access
* To do this, in the S3 bucket, I navigate to the permisssion tab to update permissions and the bucket policy 
<img width="902" alt="13" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/c89727af-3d7e-49f5-af6d-5b62fc9de543">

* I turned off "block public access"
<img width="828" alt="14" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/688a22c1-d2a3-45aa-95bf-3697458431c1">

* Editing the bucket policy
<img width="693" alt="16" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/c8303e77-efbc-4512-ac2b-8e4df6098e2f">

* Json policy allowing public read to all object
* The Resource field in the policy specifies the bucket ARN (Amazon Resource Name), determiningthe precise scope of permissions and allowing detailed control
<img width="379" alt="18" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/632beaed-7f96-4280-9d6c-0a8bd539c18b">

* Object Ownership not transferable to another AWS account or entity. Ownership model is fundamental to S3's access control and security mechanisms.
  <img width="915" alt="19" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/02fb2f08-fbb1-4990-b07f-f5d13eaf83e8">

 * Enable ACLs (Access Control List) to grant only read access to this object and bucket
<img width="919" alt="20" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/605e737f-f8d6-4fa8-aa7e-8f6e827382bc">
<img width="921" alt="21" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/d26d33ee-1996-4333-adf9-7594d40e9922">

* View the application that’s hosted on my bucket on browser, by using the application URL
<img width="880" alt="22" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/dcd14175-8b02-4e1d-8887-f4c6daf1918e">

### Task 5: Putting the application under source control on AWS Codecomit
* On Codecomit, create a repo
<img width="914" alt="code comit1" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/f4ccfcda-f86f-405c-acbd-c9f6682628f7">

* Name the Repo and create
<img width="845" alt="code comit2" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/3053e3d2-bf41-440a-a33f-7cec4c027e80">

* Switch to cloud9 ternimal environment
* Config git with my name and email
  <img width="898" alt="git 1" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/1144ba13-08b8-4220-ba4d-846177e68c38">

  * cd trivia-app and
  * git initialize the repo
<img width="599" alt="git init 2" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/6ebc3b39-1383-4857-8c37-0a4bda7db1f3">

* Create a branch and switch into it
<img width="567" alt="git checkout main 3" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/adf4b441-0a92-4abb-a213-3811f39f6479">

* git add . to stage changes in pwd
<img width="806" alt="git add and commit 4" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/291ba742-4998-4049-85cf-d4e6af4c3487">

* git commit to save changes
<img width="769" alt="git commit 5" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/782f84be-a0f6-45da-bb82-ea78363313f1">

*  Git remote tracks the remote repository that is hosted in CodeCommit.
*  git push  Update the remote named origin with the main branch.
 <img width="898" alt="git 1" src="https://github.com/Gailpositive/Devops-On-AWS/assets/111061512/1144ba13-08b8-4220-ba4d-846177e68c38">
