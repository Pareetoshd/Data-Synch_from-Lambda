![image](https://github.com/user-attachments/assets/8e5b5ed8-6ab5-41bf-a101-3ca2ab9c2574)



Project Documents

🚀 I completed Project of AWS Cloud on, How to Sync the Metadata of an Uploaded File in S3 to DyanamoDB using Lamda...

👨‍💻In the Project we basically Create an AWS Lambda, create a serverless application that automatically syncs file metadata from an S3 bucket into a DynamoDB database. This configuration is appropriate for applications that need real-time metadata tracking and storage in a scalable, cost-effective manner.

✨Get ready to enhance your AWS skills and boost your confidence in cloud technology☁️

Prerequisites - 
Before we start, make sure you have :-
An AWS account
Basic knowledge of AWS services (S3, DynamoDB, Lambda)
AWS CLI or AWS Management Console access

Step 1: Set Up AWS Environment - 

Step 1.1 - Create an S3 Bucket / Open the S3 console / Click on Create bucket / Enter a unique bucket name (ex. bucket-demo78) / Choose the AWS region and other settings as per your requirement / Click Create bucket 
 
[Fig 1: Successful Creation of Bucket {bucket-demo78}]

Step 1.2 - Create a DynamoDB Table / Open the DynamoDB console / Click on Create table / Enter the table name as (S3MetadataServerless) / Set the Partition key / primary key as Resource_id (String) / Configure additional settings as needed and click Create table .
[Fig 2: Successful Creation of Dynamo DB table {s3MetadataServerless}]

Step 1.3 - Create an IAM Role for Lambda / Open the IAM console / Click on Roles and then Create role / Select AWS service and choose Lambda / Attach the following policies : AmazonS3ReadOnlyAccess , AmazonDynamoDBFullAccess , AWSLambdaBasicExecutionRole / Give a name to the role (ex.RoleForMetadataSync) and a description / Review the selections and click Create role .
 
Fig 3: Successful Creation of IAM role (RoleForMetadataSync).

Step 2: Create the Lambda Function - 

Step2.1 - Create the Lambda Function / Open the Lambda console / Click on Create function  / Enter the function name as syncS3MetadataToDynamoDB / Choose Python 3.x as the runtime / Select the IAM role created earlier in Change default execution role option / Click Create function / Replace the default code with the Python code / After replacing the code press the Deploy button to update the lambda function . 
 
Fig 4: Successful Creation of Lambda function (syncS3MetadataToDynoDB).

Step 2.2 - Configure S3 Trigger - Go to the Lambda function configuration and click on Add trigger / Select S3 as the trigger source / Choose the S3 bucket created earlier (bucket-demo78) / Set the event type to All object create events (or any specific events such as s3:ObjectCreated:* ) / Click Add . 

Fig 5: Successful addition of S3 trigger.

Step 3 : Test the Setup - 

Step 3.1 - Upload a File to S3 / Open the S3 console and navigate to your bucket / Upload a test file to the bucket. 

Step 3.2 - Open the Dynamo DB console and navigate to your table / Click on the Explore table items button / If you see no items returned, then use Scan or query items option and select Scan and press Run / Now you see the data in the items returned section / Verify that a new item has been added with the correct metadata . 
 
Fig 6: Successful sync of Metadata of test image file to the DynamoDB table.

Conclusion – 
Following these instructions, you have successfully built a serverless application that uses AWS Lambda to sync file metadata from S3 to DynamoDB. This configuration not only simplifies metadata management, but it also leverages the power of AWS services to deliver a scalable and efficient solution.





