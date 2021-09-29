# Introduction
There are two common tools to interact with AWS services:
1. AWS Management Console
2. AWS Command Line Interface (AWS CLI)

AWS tools
1. Software Development Kits (SDKs) - Help developers write applications that integrate with AWS services.
2. CloudWatch - Monitors the performance of your resources, create alarms and notifies you when things are not working as expected, and collect, view, and search logs from your applications and AWS services.
3. CloudTrail - Works to keep a detailed log of every action that anyone or anything performs against your AWS resources.
4. Cost Explorer - Helps understand what your AWS services are costing you, spot usage and billing trends over time, and get recommendations to help you save money.

# The AWS Management Console
Also known as AWS Console or the AWS Web Console, is a web interface you can use to manage all of your AWS cloud resources through a web browser.

Most settings for your AWS resources can be configured using the console.

The AWS Management Console compatibility:
- Apple Safari
- Google Chrome
- Microsoft Edge
- Microsoft Internet Explorer
- Mozilla Firefox

## Accessing the AWS Management Console
URL: https://console.aws.amazon.com

There are two ways to sign in:
1. As a root user
2. As an IAM user

## Logging in as a Root User
Not recommended to use a root user to conduct administrative work. To login as root, you require:
1. Email address
2. Password

## Logging in as an IAM User
To login as an IAM user, you require:
1. Account ID or Account alias
2. IAM username
3. Password

Session login is active for 12 hours.

## Opening a Service Console
Each AWS service has its own service console where you can manage resources that are part of that service.

## Working with Shortcuts
Frequently used services can be pinned to the navigation bar.

## Selecting a Region
The EC2 service in the US East region is separate from the EC2 service in the US West region.

Some services such as IAM, Route 53, and S3 are global. These service consoles don't use region selector but global selector.

## The Account Name Menu
Displays the IAM user and account alias or ID.
- MyAccount - Takes your to the Billing service console page that displays your account information
- MyOrganization - Takes you to the AWS Organizations service console
- My Billing Dashboard - Takes you to the Billing and Cost Management Dashboard
- MySecurityCredentials - Takes you to the My Password page in the IAM service console where you can change your password
- Switch Role - Lets you assume an IAM role where you can perform tasks as a different principle with different permissions
- Sign Out - Signs you out of the AWS Management Console

## Resource Groups
Resource groups are one of the options readily available from the AWS Management Console. They let you view, manage, and automate tasks on multiple AWS resources at a time.
- Resource tags - A tag that you can assign to AWS resources. Must contain a label called a key and may optionally contain a value
- AWS CloudFormation stacks - Lets you programmatically deploy and manage multiple AWS resources as a single unit called a stack.

## Tag Editor
Prequisite is to have a tag created. At a minimum you must select at least one region and one or more resource types, such as EC2 instances, EC2 volumes, VPCs, or S3 buckets.

## Tagging Strategies
1. Technical
2. Automation
3. Business
4. Security

### Technical
Tag according to the technical properties of a resource. Example: an EC2 instance hosting a web server with a tag value of webserver01. Environment tag to specify whether the resource is part of your production, test, or development infrastructure. Application role tag to classify the type of role a resource performs: either a webserver or a database.

### Automation
Used to define resources that should be part of an automation process: Updating security patches, backups, deleting old snapshots, or turning off development servers after hours.

### Business
Business tag can be helpful to use for billing, management, and analysis.
- Owner - To identify the person or group responsible for the resource
- Business Unit or Cost Center - indicate who's responsible for paying for the resource
- Project - To identify the name of the program or project the resource is part of
- Customer - To identify resources that are dedicated to a particular customer

### Security
A tag to allow implicit permissions. Example: production web server should only be able to access production database if they have this tag. If this tag is not applied, then other instances should not have access to the prod database.
- Confidentiality - If your resources process or store data that has varying confidentiality requirements, resource tags should be created for that case. Example: application that processes protected health information (PHI).
- Compliance - If any resources must adhere to specific compliance requirements such as the Health Insurance Portability and Accountability Act (HIPAA) or the Payment Card Industry Data Security Standard (PCI DSS).

## The AWS Console Mobile Application
A smartphone application that lets you manage your AWS account and resources through your phone.
The application displays the following:
- Service Health - View any current health issues with AWS services across different regions.
- CloudWatch Alarms - View alarm graphs and current alarm status.
- Billing - View your current billing balance and a graph of usage charges.

The application allows limited changes to some AWS resources, including: CloudWatch Alarms, EC2 security groups, EC2 instances, and CloudFormation stacks.

### Supported Services
- AWS Billing and Cost Management
- AWS CloudFormation
- AWS CloudWatch
- Amazon DynamoDB
- Amazon EC2
- AWS Elastic Beanstalk
- Elastic Load Balancing
- AWS OpsWorks
- AWS Personal Health Dashboard
- Amazon Relational Database Service (RDS)
- Amazon Route 53
- Amazon Simple Storage Service (S3)
- Amazon Virtual Private Cloud (Amazon VPC)

### Requirements
Apple IOS 7.0+ and Android 4.0+
Authentication method:
- Root account credentials
- An IAM username and password
- An access key ID and secret key

# The AWS Command Line Interface
A unified command-line tool to manage your AWS resources. AWS gives access to the public application programming interfaces for all AWS services within 180 days of service launch.

The AWS CLI is useful for performing repetitive tasks, such as launching EC2 instances, taking EBS snapshots, or attaching policies to IAM users.

## Requirements
Requires IAM access key ID and secret key to authenticate to AWS using the CLI.

## Installation
Typically comes preinstalled on Amazon Linux AMIs. Other method of installing AWS CLI:
1. Python and Pip
2. Stand-alone installer for Linux, macOS, and Windows

https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html

# Software Development Kits
AWS SDK simplify the use of AWS services in custom applicatons. The SDKs are used for application developers to integrate their applications with AWS services easily and reliably.
AWS SDK supports the following languages:
- Java
- .NET
- Node.js
- PHP
- Python
- Ruby
- JavaScript
- Go
- C++

## Mobile Software Development Kits
Available mobile SDKs:
- AWS Mobile SDK for Android
- AWS SDK for iOS
- AWS Mobile SDK for Unity to create games that run on both iOS and Android
- AWS Mobile SDK for .NET and Xamarin, a cross-platform application development framework that can be used to develop applications for iOS and Android
- AWS Amplify - An open source framework to build mobile and web applications on AWS. Allows you to build an application backend on AWS and integrate it with your Android, iOS, and web applications.
AWS Amplify uses AWS serviecs to offer:
    - Cloud-based authentication
    - Notification
    - Offline data sync
    - Analytics


## Internet of Things Device Software Development Kits
AWS IoT is a collection of services that allow IoT devices to interact with AWS services, other applications, and even other devices. The platform lets you centrally onboard, manage, and monitor IoT devices.

AWS IoT can integrate with other AWS services:
- Amazon S3
- Amazon DynamoDB
- Amazon Kinesis
- AWS Lambda
- Amazon Simple Notification Service
- Amazon Simple Queue Service

IoT device SDKs are available for the following languages and platforms:
- Embedded C
- JavaScript
- Arduino Yun
- Python
- Java
- C++

# CloudWatch
A key service that helps you plan, monitor, and fine tune your AWS infrastructure and applications.

Common use cases:
1. Infrastructure monitoring and troubleshooting - Visualize performance metrics to discover trends over time and spot outliers that might indicate a problem.Use metrics and logs to understand the root cause of failures and performance issues.
2. Resource optimization - Save money and help with resource planning by identifying overused or underused resources. Ensure performance and availability by using AWS Auto Scaling to automatically provision new EC2 instances to meet demand.
3. Application monitoring - Creates CloudWatch alarms to alert and take corrective action when a resource utilization, performance, or health falls outside of a threshold that you define.
4. Log analytics - Search, visualize, and correlate logs from multiple sources to help with troubleshooting.

## CloudWatch Metrics
Collects numeric performance metrics from both AWS and non-AWS resources such as on-premises servers.

A metric is a variable that contains a time-ordered set of data points. Each data point contains a timestamp, a value and optionally a unit of measure.

All AWS resources automatically send their metrics to CloudWatch:
1. EC2 instance CPU utilization
2. S3 bucket sizes
3. DynamoDB consumed read and write capacity units

CloudWatch stores metrics for up to 15 months.

## CloudWatch Alarms
Watches over the value of a single metric. 

Simple Notification Service (SNS) - uses a publisher - subscriber model.
    - HTTP(S)
    - Simple Queue Service (SQS)
    - Lambda
    - Mobile push notification
    - Email
    - Email-JSON
    - Short Message Service (SMS) text messages

# CloudTrail
CloudTrail keeps detailed event logs of every action that occurs against your AWS resources.
- The service. Specifically, this is the address of the service's global endpoint, such as iam.amazonaws.com for IAM
- The name of the API action performed, such as RunInstances, CreateUser, or PutObject.
- The region the resource is located in. For global services, this is always us-east-1.
- Response elements. In the case of an API operation that changes or creates a resource, this contains information about the results of the action. 
- The principal that made the request. This may include the type of principal (IAM user or role), its Amazon resource name (ARN), and the name.
- The date and time of the request, given in coordinated universal time (UTC).
- The IP address of the requester.

## API and Non-API Events
The events CloudTrail logs consist of two different actions:
1. API
2. Non-API

### API
Actions include:
- Launching an instance
- Creating an S3 bucket
- Creating a new IAM user
- Taking an EBS snapshot

### Non-API
Actions that include everything else, such as logging into the management console.

## Management and Data Events
CloudTrail also classifies events along two other dimensions:
1. Management events
2. Data events

### Management events
Also known as control plan operations are operations that a principal (such as a user or service) attempts to execute against an AWS resource.

Includes:
- write only events: API operations that modify or might modify resources
- read only events: Read resource information but don't make any changes.

### Data events
Data events consists of S3 object-level activity and Lambda function execution, both which tend to be high volume. CloudTrail treats data events as separate from management events. CloudTrail draws a distinction between read-only events like GetObject and write-only events such as PutObject and DeleteObject.

## Event History
Stores 90 days of management events in the event history. The event history log doesn't record data events.

For each region, CloudTrail maintains a separate event history log containing the events that occurred in that region. But events generated by global services including IAM and Route 53 are included in the event history for every region.

### Trails
A trail is a configuration that directs CloudTrail to record specified events in log files and deliver them to an S3 bucket. You can choose to log management events, data events, or both.

CloudTrail doesn't provide a way to search trail logs, which are written in JavaScript Object Notation (JSON) format. You can also configure CloudTrail to send a trail log to CloudWatch logs, making them available for storage, searching, and metric filtering.

### Log File Integrity Validation
Calculates and stores cryptographic has of the file. Log files can be encrypted using server-side encryption with Amazon S3-managed encryption keys (SSE-S3) or server-side encryption with AWS KMS-managed keys (SSE-KMS).

# Cost Explorer
AWS Cost Explorer offers the following three categories of reports:
1. Cost and usage reports
2. Reservation reports
3. Reserved instance recommendations

## Cost and Usage
Gives you a graphical view of your daily and monthly costs and usage over time. Cost Explorer can also show you the forecast for the current month, 3 months and 12 months out.

You can go back as far as one year and filter or group by several parameters including but not limited to the following:
- Service
- Availability Zone
- Region
- Instance type
- Usage type
- Tag
- API operation
- Charge type
- Platform

Provides five default cost and usage reports
1. Monthly costs by service - Displays your top five most expensive services over the past six months. Services are graphed individually, while other services are aggregated and graphed as a single bar.
2. Monthly costs by linked account - Shows your costs for your top five linked accounts over the past six months. The top five linked accounts are grouped individually, and the rest are aggregated and graphed as one bar.
3. Monthly EC2 running hours costs and usage - Displays two monthly graphs showing the costs and running hours for your EC2 instances.
4. Daily costs - Shows your monthly sped for the last six months and a forecast for the current month.
5. AWS marketplace - Allows vendors to make their products and services available to you via AWS. License, subscription and usage costs are bundled together and billed through AWS. This report shows you how much you've spent on AWS Marketplace solutions.

## Reservation Reports
Two built-in reservation reports to give you insight on how much you are saving or could have saved with instance reservation

### Reserved Instances Utilization
Provides the percentage of your reserved instances you've used and how much money you've saved or overspent by using reserved instances. Shows you net saving from reserved instances, provides insight whether you've had too ffew or too many reserved instances.

### Reserved Instances Coverage
Tells you how many of your running instance hours are covered by instance reservation, how much you've spent for on-demand instances, and how much you could have saved by purchasing reserved instances.

## Reserved Instance Recommendations
Cost Explorer provide reserved instance recommendations to help reduce your costs.

Analyzes your on-demand instance usage over the past 7, 30, or 60 days. Searches for all available reserved instances that would cover that usage and selects the most cost-effective reserved instances and recommends them.

Cost Explorer makes separate recommendations for each service such as EC2 or RDS.

# Summary
Two ways to interact with AWS:
1. AWS Command Line Interface (CLI)
2. AWS Management Console

CloudWatch - collects metrics from AWS services. You can create alarms to take action, such as notification. Receives and stores logs from AWS and non-AWS services .

CloudTrail - records events that occur against your AWS account. By default, captures the last 90 days of management events in each region. If required more than 90 days, you need to create a trail to cause CloudTrail to store events in an S3 bucket.
