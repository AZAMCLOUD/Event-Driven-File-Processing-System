# Event-Driven-File-Processing-System

This project implements a **serverless event-driven file processing system** using AWS Lambda, S3, and SNS, integrated with a fully automated **CI/CD pipeline** built with **GitHub**, **AWS CodePipeline**, **CodeBuild**, and **CloudFormation**.

---

## 🧭 Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [CI/CD Pipeline Workflow](#-cicd-pipeline-workflow)
- [IAM and Security](#-iam-and-security)
- [Key Files](#-key-files)
- [CloudWatch Logging](#-cloudwatch-logging)
- [Deployment Instructions](#-deployment-instructions)
- [Best Practices](#-best-practices)

---

## 📦 Overview

This project is designed to:

- Automatically deploy a Lambda function that processes files uploaded to S3.
- Trigger the function on S3 object creation events.
- Publish notifications to SNS.
- Automate code updates via GitHub commits using CodePipeline and CodeBuild.

---

## 🛠 Architecture

```text
GitHub Repo → CodePipeline → CodeBuild → S3 → CloudFormation → Lambda (triggered by S3 event)
                                                                 ↓
                                                           Publishes to SNS
