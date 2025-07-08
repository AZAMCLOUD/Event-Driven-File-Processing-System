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
 - **AWS CodePipeline** : Automate CI/CD stages
 - **Cloudformation** : Infrastructure as Code
 - **Amazon Lambda** : Event-driven processing logic
 - **AWS CodeBuild** : Build Lambda package and store in S3 
 - **Amazon S3** : Lambda code storage and event trigger
 - **SNS** : Notification service
 - **Amazon CloudWatch** : Logging and monitoring

---

## CI/CD

- Configured Infrastructure pipelines for the different infrastructures

- Configured Lambda function pipeline integrated Codebuild

- Configured CodeBuild to generate deployment artifacts and store lambda code versions.

- Used CodeBuild deployment artifacts for Lambda Code Deployments

- Configured Pipelines to trigger on GitHub commits.

---

## Pipeline Workflow

### Source Stage (GitHub)

- Monitors source repository for changes.

 ####  GitHub Structure

  event-driven-file-processing/

├── lambda/

│   └── lambda_function.py             # Lambda handler code

├── templates/                         # CloudFormation Templates

│   └── lambdaS3codeBucket.yaml        # S3 Bucket for Storing Lambda Code(Versions)

│   └── lambda.yaml                    # Lambda Function

│   └── s3.yaml                        # Trigger Bucket

│   └── sns.yaml                       # Simple Notification Service

├── buildspec.yml                      # Codebuild Spec

  


## Infrastucture Deployment 

The entire infrastructure for this project was provisioned using AWS Cloudformation with Templates stored on Git pulled using Codepipeline

This include:

### Lambda Function 

### Simple Notification Service

### S3 Trigger Bucket

### S3 Lambda Code Bucket







