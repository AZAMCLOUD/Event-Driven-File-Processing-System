# Event-Driven-File-Processing-System

---

## Project Overview

This project implements a **serverless event-driven file processing system** using AWS Lambda, S3, and SNS, integrated with a fully automated **CI/CD pipeline** built with **GitHub**, **AWS CodePipeline**, **CodeBuild**, and **CloudFormation**.

---

## 📦 Project Objective

This project is designed to:

- Automatically deploy a Lambda function that processes files uploaded to S3.
- Trigger the function on S3 object creation events.
- Publish notifications to SNS.
- Automate code updates via GitHub commits using CodePipeline and CodeBuild.

---

##  AWS Services Used

 - **GitHub** : Source control and CI/CD trigger
 - **Cloudformation** : Infrastructure as Code
 - **Amazon Lambda** : Event-driven processing logic
 - **AWS CodeBuild** : Build Lambda package and store in S3 
 - **AWS CodePipeline** : Automate CI/CD stages
 - **Amazon S3** : Lambda code storage and event trigger
 - **SNS** : Notification service
 - **Amazon CloudWatch** : Logging and monitoring

---

## Instance Deployment 

The entire infrastructure for this project was provisioned using AWS CloudFormation, ensuring repeatable, automated, and version-controlled deployments,templates stored in Git.

### Project Structure (GitHub)

event-driven-file-processing/

├── lambda/

│   └── lambda_function.py         # Lambda handler code

├── templates/                     # CloudFormation Templates

│   └── lambdaS3codeBucket.yaml    # S3 Bucket for Storing Lambda Code(Versions)

│   └── lambda.yaml                # Lambda Function

│   └── s3.yaml                    # Trigger Bucket

│   └── sns.yaml                   # Simple Notification Service

├── buildspec.yml                  # Codebuild Spec



