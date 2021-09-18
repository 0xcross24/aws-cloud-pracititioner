# Introduction

Two account-level things to clear
1. Cost: Virtually no limit to how much you can purchase or to how much they can host you.
2. Authority: Who makes the decision for launching and shutting down account resources.

# The Free Tier
AWS provides free tier for the first 12 months after opening a new account to work with before migrating the infrastructure to cloud.

## How Does the Free Tier Work?
1. Allows you to run t2.micro Elastic Cloud Compute (EC2) instances.
    - 750 hours per month
2. Allows you to run lightweight relational database workloads under Amazon's Relational Database Service (RDS).
    - 750 hours per month
    - Store up to 5 GB of data within Simple Storage Service (S3) buckets.

## Tracking Your Free Tier Usage
1. Free Tier-related email alerts
2. A tracking tool that is located toward the bottom of the Billing Dashboard.

![image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Fri_Sep_17_2021_1631914591755.png)

## What's Available Under the Free Tier?
1. Light implementation of most AWS services are available through the first 12 months of a new AWS account
2. Light usage of certain AWS services that are always available even after your initial 12 months

https://aws.amazon.com/free/

## The 12-Month Free Tier
- 30 GB of disk memory from Elastic Block Storage (EBS)
- 500 MB/month of free storage on the Elastic Container Registry (ECR). ECR stores and manages Docker container images.
- 50 GB of outbound data transfers and 2 million HTTP or HTTPS requests for CloudFront distribution.
    - CloudFront is Amazon's content delivery network that can be used to cache copies of your content to remote users at low latency rates.
- One million API calls/month on Amazon API Gateway.
    - A tool for managing your organization's application programming interfaces (APIs).

## Permanently Free Services
1. 10 custom monitoring metrics and 10 alarms on CloudWatch active.
2. 10 GB of data retrievals from Glacier per month
    - Glacier is a low cost storage service that's ideal for long term storage where you're not likely to require quick access to your data
3. 62,000 outbound email messages per month using Simple Email Service (SES).
    - An enterprise scale email service geared to organizations that regularly send large volumes of emails
4. One million requests and 3.2 million seconds of compute time using AWS Lambda functions.
    - Lambda lets you run code based on network triggers without provisioning any underlying server infrastructure.

# Product Pricing
How AWS bills for each of the services you're considering, and how to get an accurate pricing information

## Finding AWS Pricing Documentation
Each AWS service has its own web page dedicated to pricing. Pricing can be found by adding /pricing at the end of an URL

Example: https://aws.amazon.com/s3/pricing

Different AWS region can display different pricing across the global AWS infrastructure.

## Working with Online Calculators
1. Simple Monthly Calculator to help you understand what running any combination of AWS resources will cost you
2. Total Cost of Ownership Calculator to closely compare what you're currently paying for on-premises servers with the same workload would cost on AWS

## AWS Simple Monthly Calculator
https://calculator.s3.amazonaws.com/index.html

## AWS Total Cost of Ownership Calculator
https://calculator.aws/#/