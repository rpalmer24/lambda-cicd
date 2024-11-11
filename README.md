# lambda-cicd

## Project Overview

### Push Request
Created a  **CI/CD** workflow that is triggered every time changes are pushed to the lambda function 
and updates using **GitHub Action**.

### Pull Request
Create a GitHub Action Workflow that will validate and test a Cloudformation template for an S3 bucket creation.
When a pull request is either open or updated 

## Steps

Push Request
1. initiate the process my pushing code to the GitHub repo
2. use GitHub Secrets to store **AWS** credentials. The reason for this is so GitHub action can access AWS resouces (**AWS Lambda**) to deploy lambda changes.
3. GitHub acction uses a Runner ( a server use to execute the workflow)
     - checks code from respository
     - setup Pythom environment
     - install any dependencies
     - and configure AWS credentials
     - package **Lambda**
4. The Runner deploy Lambda Function to AWS

Pull Request
1. initiate the process my pushing code to the GitHub repo
2. use GitHub Secrets to store **AWS** credentials
3. GitHub acction uses a Runner 
     - checks code from respository
     - setup AWS CLI
     - and configure AWS credentials
5. Validate Cloudformation template
6. Deploy a test bucket to AWS S3 and check that the S3 bucket was created.
7. Then it will comment on the **Pull Request** to confirm it passed (tell us the test result and the name of the pull request and name of the  cloudformation stack)
8. the chekc the console to confirm S3 bucket was created
9. Merge the pull request in main branch by doing this it will delete the test stask

## Technologies Used
- GitHub Actions
- AWS Lambda
- AWS S3
  

_Push Request_


<img width="346" alt="deploy_lambda" src="https://github.com/user-attachments/assets/cc0330c6-c707-40ca-90a3-3159a68164bc">


_Pull Request_


<img width="376" alt="pr_github_action" src="https://github.com/user-attachments/assets/a3696ea1-91d8-45c2-adb0-5d15e41d4250">
<img width="770" alt="awsconsole_github_acrtion" src="https://github.com/user-attachments/assets/3a728cc4-1b60-4413-a892-8abf24a3bf95">

