Overview:
This project is a serverless web application built using AWS services. It demonstrates how to perform Create, Read, Update, and Delete (CRUD) operations in a scalable and cost-effective manner without managing traditional servers. The application tracks and updates a view count while allowing user interaction through a web interface.

Features:
1)Serverless Architecture: No need to manage servers; AWS handles the infrastructure.
2)CRUD Operations: Users can interact with data stored in DynamoDB.
3)Scalable and Reliable: Uses AWS services like Lambda, DynamoDB, S3, and CloudFront.
4)Responsive Frontend: A visually appealing interface built with HTML and CSS.

Technologies Used:
1)Backend: AWS Lambda (Python), DynamoDB
2)Frontend: HTML, CSS, JavaScript
3)Static File Hosting: Amazon S3
4)Content Delivery: AWS CloudFront

Architecture:

(A)Frontend:
Hosted on Amazon S3.
Delivered globally via AWS CloudFront.

(B)Backend:
AWS Lambda handles logic for CRUD operations.
DynamoDB stores the application data (view counts).

Setup Instructions:

Prerequisites:
1) An AWS account.
2) Basic knowledge of AWS services like S3, Lambda, DynamoDB, and CloudFront.
3) Python 3.8 installed locally for testing Lambda functions.

Steps:
1) Create DynamoDB Table
Table Name: serverless-web-application-on-aws
Primary Key: id (String)

Add an initial item:

{
  "id": "0",
  "views": 0
}

2) Develop Lambda Function

Write a Python Lambda function (provided in lambda-function.py).
Install AWS SDK for Python (boto3) if testing locally: pip install boto3
Deploy the Lambda function to AWS and attach a policy to allow DynamoDB access.

3) Host Frontend Files on S3
Upload index.html and style.css to an S3 bucket.
Enable static website hosting for the bucket.

4) Set Up CloudFront
Create a CloudFront distribution pointing to the S3 bucket.
Enable SSL for secure access.

5) Test the Application
Access the application through the CloudFront URL.
Interact with the frontend, and verify view count updates.

How It Works:
1) Frontend Interaction: Users access the application and submit data.
2) Backend Processing: The Lambda function updates the DynamoDB table based on user actions.
3) View Count Display: The updated count is retrieved and displayed on the frontend.

