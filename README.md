# Event-Driven File Processing System

## Overview

This project implements a fully automated, event-driven file processing system using AWS services and DevOps best practices. Designed with scalability, automation, and observability in mind, it enables efficient file ingestion and processing triggered by object uploads in Amazon S3.

## Architecture

- **GitHub**: Source code repository for Lambda function and CloudFormation templates.
- **AWS CodePipeline**: Automates the entire CI/CD process.
- **AWS CodeBuild**: Builds and packages the Lambda function code as artifacts, updating Lambda, and uploading artifacts to S3.
- **Amazon S3**: An S3 bucket to store Codebuild artifacts, another(source) for trigger functions when files are uploaded.
- **AWS Lambda**: Executes custom logic when new files are added to the source S3 bucket.
- **Amazon CloudWatch**: Monitors logs and provides insights into Lambda executions.
- **AWS CloudFormation**: Provisions all resources in a repeatable and scalable manner.

## Features

- Automated infrastructure provisioning via CloudFormation
- CI/CD deployment using AWS CodePipeline and CodeBuild
- Event-driven Lambda function execution on S3 upload
- Seamless source integration with GitHub
- Full observability via CloudWatch logs

## Infrastructure Deployment

Infrastructure is defined using modular CloudFormation templates and deployed automatically via AWS CodePipeline. The build and deploy process is initiated by changes pushed to the GitHub repository.

### CI/CD Flow

1. **Source**: GitHub push triggers CodePipeline
2. **Build**: CodeBuild compiles and uploads Lambda code to S3 
3. **Deploy**: CloudFormation stacks are created/updated to reflect changes
4. **Execution**: Lambda is triggered on new S3 object events

## File Structure

```
├── lambda/
│   └── lambda_function.py       # Lambda Code
├── templates/
│   ├── lambda.yaml              # Lambda + IAM definition
|   |── lambdaS3codeBucket.yaml  # Bucket for artifacts
│   ├── s3.yaml                  # Buckets for triggers 
│   └── sns.yaml                 # Simple Notification Service
└── buildspec.yml                # Build instructions for CodeBuild
```

## Monitoring

All Lambda invocations and pipeline activities are logged in **Amazon CloudWatch**. CloudWatch dashboards can be used to track performance, errors, and request counts.

## Technologies Used

- AWS Lambda
- Amazon S3
- AWS CloudFormation
- AWS CodePipeline
- AWS CodeBuild
- Amazon CloudWatch
- GitHub




