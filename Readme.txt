Wild Rides :: 
Serverless Web-Application that enables users to request unicorn rides to get to their destination faster and hassle-free. 
Built using AWS Services such as  AWS Amplify, Amazon Cognito, AWS Lambda, Amazon API Gateway and Amazon DynamoDB

Amplify :: To Deploy the Web Application
Cognito :: User Management
Lambda :: Serverless backend
API Gateway :: Proxy between Web-Browser & Lambda Function 
DynamoDB :: To store the ride details

STEPS -->

1. Install AWS shell
pip install aws-shell

2. Configure AWS shell
aws configure

3. Create a repo on AWS CodeCommit
aws codecommit create-repository --repository-name wild-rydes

4. Clone the source code from Github
git clone https://github.com/aws-samples/aws-serverless-webapp-workshop

5. Split the WildRydes app into a branch
cd aws-serverless-webapp-workshop
git subtree split -P resources/code/WildRydesVue/ -b WildRydesVue

6. Create a git repo and populate it with source code of WildRydesVue
mkdir ../wild-rydes
cd ../wild-rydes
git init
git pull ../aws-serverless-webapp-workshop WildRydesVue

7. Create a repo and AWS CodeCommit and push this source code
git remote add origin codecommit::ap-south-1://wild-rydes
--Now Generate Git Credentials using AWS Code Commit User Guide
git push -u origin master

install Node.js

8. Install amplify cli
npm install -g @aws-amplify/cli
amplify init

9. Add user pool to amplify app
amplify add auth

10. Push changes to the codecommit
git add .
git commit -m "made changes"
git push