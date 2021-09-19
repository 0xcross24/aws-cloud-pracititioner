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
1. Light implementation of most AWS services are available through the first 12 months of a new AWS account.
2. Light usage of certain AWS services that are always available even after your initial 12 months.

https://aws.amazon.com/free/

## The 12-Month Free Tier
- 30 GB of either HDD or SSD memory from Elastic Block Storage (EBS).
- 500 MB/month of free storage on the Elastic Container Registry (ECR). ECR stores and manages Docker container images.
- 50 GB of outbound data transfers and 2 million HTTP or HTTPS requests for CloudFront distribution.
    - CloudFront is Amazon's content delivery network that can be used to cache copies of your content to remote users at low latency rates.
- One million API calls/month on Amazon API Gateway.
    - A tool for managing your organization's application programming interfaces (APIs).

## Permanently Free Services
1. 10 custom monitoring metrics and 10 alarms on CloudWatch active.
2. 10 GB of data retrievals from Glacier per month.
    - Glacier is a low cost storage service that's ideal for long term storage where you're not likely to require quick access to your data.
3. 62,000 outbound email messages per month using Simple Email Service (SES).
    - An enterprise scale email service geared to organizations that regularly send large volumes of emails.
4. One million requests and 3.2 million seconds of compute time using AWS Lambda functions.
    - Lambda lets you run code based on network triggers without provisioning any underlying server infrastructure.

# Product Pricing
How AWS bills for each of the services you're considering, and how to get an accurate pricing information.

## Finding AWS Pricing Documentation
Each AWS service has its own web page dedicated to pricing. Pricing can be found by adding /pricing at the end of an URL.

Example: https://aws.amazon.com/s3/pricing

Different AWS region can display different pricing across the global AWS infrastructure.

## Working with Online Calculators
1. Simple Monthly Calculator to help you understand what running any combination of AWS resources will cost you.
2. Total Cost of Ownership Calculator to closely compare what you're currently paying for on-premises servers with the same workload would cost on AWS.

## AWS Simple Monthly Calculator
https://calculator.s3.amazonaws.com/index.html

## AWS Total Cost of Ownership Calculator
https://calculator.aws/#/

# Billing and Cost Management
The dashboard is located through the account drop-down menu at the top of the AWS Management Console. It holds various tools to monitor the health of your organization's finances and operations.

## The AWS Billing Dashboard
Contains a helpful visual spend summary that displays your costs from the previous and current months. Also shows forecast of the costs you'll likely to receive through the end of the month.

Contains, month to date spend by service display that can itemized a breakdown of your current spending.

Contains billing payment method, records of your previous transactions and organization's tax information.

## AWS Budgets
A tool for tracking a specified set of events that triggers when a preset threshold is approached or passed. There are three budget types:
1. Cost budget to monitor costs being incurred against your account.
2. Usage budget to track particular categories of resource consumption.
3. Reservation budget to help you understand the status of any active EC2, RDS, Redshift, or Elasticache reserve instances you might have.

The budget setup process has two parts:
1. Set the terms of your budget - what it is you're tracking.
2. Define how and when you want alerts sent.

## Monitoring Your Costs
In depth deployment planning and properly configured budgets are important tools but not enough. Ongoing monitoring is a key part of that mix, using Amazon's Cost Explorer and its cost and usage reports.

## Cost Explorer
https://aws.amazon.com/aws-cost-management/aws-cost-explorer/

Cost Explorer lets you build graphs to  visualize your account's historical and current costs. There is a preconfigured views that includes spending over the most recent three months by a service.

Cost Explorer can open a heavily customizable view that lets you filter account cost events by date, region, Availability Zone, instance type, platform, and others. Uses CSV formatted files.

## Cost and Usage Reports
Can be accessed from Reports link on the Billing Dashboard.

Reports can be configured to create a full range of activity on your account, including what resources you have running and how much they're costing you.

You can control the level of details and enable support for Redshift and/or Amazon QuickSight (a managed, pay-per-user business intelligence tool) to handle the visualization and analysis of significant volumes of data.

The reports generated at preset intervals are compressed, saved using the CSV format, and sent to an S3 bucket you've already created. Then you have an option to configure Redshift or QuickSight to access and process the data as it's generated.

## Cost Allocation Tags
Tags are metadata indentification elements representing a resource and its action. Tags can be used to organize and track your resources, allowing you to visualize and better understand how resource are being used. There are two different types of tags:
1. Resource tags - Used to quickly identify the purpose and owner of a particular running resource.
2. Cost allocation tags - Interacts with billing tools and won't show up in the context of any other AWS resources or process. Cost allocation tags help efficiently identify your resources of tracking your account spending. There are two Cost Allocation Tags:
    1. AWS-generated cost allocation tags - automatically generates when resources are created.
    2. User-defined cost allocation tags.

## AWS Organizations
Allows you to centralize the administration of multiple AWS accounts owned or controlled by a single company.

Once accounts are linked, maintaining a secure profile and following best practices becomes even more critical than for stand-alone accounts.

# Summary
The Free Tier offers new accounts a full year of free access to light configurations. You can track your outspending your Free Tier allowance from the Billing Dashboard.

Pricing information can be found by adding /pricing to the URL of an AWS service: https://aws.amazon.com/s3/pricing/

The AWS Simple Monthly Calculator and AWS Cost of Ownership Calculator anticipate real-world usage costs for AWS deployment. TCO calculator compares your spending with its on-premises equivalent.

The AWS Billing Dashboard contains account administration, payment and tax status management, cost monitoring, and cost control.
