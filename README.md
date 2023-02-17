## AWS Lambda Developer Guide

### sample-apps/java-basic

setup

1. install aws cli
2. create user with policies so that below screen can work

   a) 1-create-bucket.sh (create s3)
   
   b) 2-deploy.sh (deploy serverless app)
   
   <pre>
   AmazonS3FullAccess
   AWSCloudFormationFullAccess
   AWSLambda_FullAccess
   AWSLambdaBasicExecutionRole
   javaBasic (custom policy as below)
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Sid": "iamRole",
               "Effect": "Allow",
               "Action": [
                   "iam:GetRole",
                   "iam:GetRolePolicy",
                   "iam:PassRole",
                   "iam:DetachRolePolicy",
                   "iam:DeleteRolePolicy",
                   "iam:DeleteRole",
                   "iam:CreateRole",
                   "iam:AttachRolePolicy",
                   "iam:PutRolePolicy"
               ],
               "Resource": "arn:aws:iam::*:role/*"
           }
       ]
   }
   </pre>

run test

1. run '1-create-bucket.sh mvn', check s3 is created

2. run '2-deploy.sh', check stack is created in cloudFormation
