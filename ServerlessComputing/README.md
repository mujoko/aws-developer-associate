# Serverless Architecture Model (SAM)
## Step to build and deploy SAM into AWS
Bear in mind, SAM is just an extention of Cloud Formation. So It will help you to define and provision of Lamnda and DynamoDB as core of the Serverless Architecture
![See the SAM](SAM.PNG)


###Make sure that the Region for this bucket aligns with where you deploy
aws s3 mb s3://sam-mujoko-bucket --region ap-southeast-1

###Step 1 - Download a sample application
sam init --runtime python3.6

###Step 2 - Build your application
cd sam-app
sam build

###Step 3 - Package your application
sam package --output-template packaged.yaml --s3-bucket sam-mujoko-bucket

###Step 4 - Deploy your application
sam deploy --template-file packaged.yaml --region ap-southeast-1
 --capabilities CAPABILITY_IAM --stack-name aws-sam-getting-started

###Step 4 - Get the details of the Service
aws cloudformation describe-stacks --stack-name aws-sam-getting-started --region ap-southeast-1 --query "Stacks[].Outputs"
[
    [
        {
            "OutputKey": "HelloWorldFunctionIamRole",
            "OutputValue": "arn:aws:iam::xxxxxxx:role/aws-sam-getting-started-HelloWorldFunctionRole-1AALAKPR3Z7OO",
            "Description": "Implicit IAM Role created for Hello World function"
        },
        {
            "OutputKey": "HelloWorldApi",
            "OutputValue": "https://xxxxxxxxxxxx.execute-api.ap-southeast-1.amazonaws.com/Prod/hello/",
            "Description": "API Gateway endpoint URL for Prod stage for Hello World function"
        },
        {
            "OutputKey": "HelloWorldFunction",
            "OutputValue": "arn:aws:lambda:ap-southeast-1:xxxxxxx:function:aws-sam-getting-started-HelloWorldFunction-xxxxxxxx",
            "Description": "Hello World Lambda Function ARN"
        }
    ]
]


https://bppx51xaw6.execute-api.ap-southeast-1.amazonaws.com/Prod/hello
