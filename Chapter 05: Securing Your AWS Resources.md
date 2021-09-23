# Introduction
# AWS Identity and Access Management
IAM connects you to all the administration tools needed to manage the basics of account security

## Protecting the Root User
A root user is a superuser that has the highest level permission in the system.

The recommended best practice is to protect the root user by creating a complex password and implementing multifactor authentication and using IAM users with specific permissions instead.

## Authentication
In order to connect to any AWS resources, you'll require proper authentication with username and password. To access remotely to the command line of an EC2 instance, you'll require a valid key pair.

## Passwords
When choosing passwords for any users, choose a complex and long password including uppercase, lowercase, numbers and symbols.

First step in protecting your root user is giving it a high-quality password.

![image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Thu_Sep_23_2021_1632433216090.png)

Using multi-factor authentication (MFA) adds a second layer of security to your logins. Even if the password has been compromised, this step will deter or prevent users from accessing the account.

## Access Keys
A valid key pair is required to access programmatic and command line in AWS resources. Keys can be generated in the AWS Management Console under the Security Credentials page.

## Secure Shell Key Pairs
The industry standard tool for safely encrypting remote login sessions.

Encryption converts plain-text data packets to gibberish.

When launching a new EC2 Linux instance, you'll be prompted to either use an existing SSH key pair or to create a new one.

## Users, Groups, and Roles
Do not use root for regular administration duties. Instead, create users and assign permissions that is only needed to do their job. Also known as principle of lease privilege.

## IAM Users
A primary admin to replace a root user should have AdministratorAccess policy. This policy is enough to perform daily admin tasks without requiring to access root or expsoing to unnecessary risks.

## IAM Groups
Use groups to administrate permissions associated with multiple users in batch.

## IAM Roles
IAM roles define limits for what can be done within your AWS account. Roles are used by applications and services rather than people.

When creating a role, trusted entity needs to be defined that wil be used to trust that the role is valid.

## Providing Federated Access
Federation allows you to expand available tools for managing authentication beyond simple IAM options.

You can integrate Security Assertion Markup Language 2.0 (SAML) or Microsoft's Active Directory into your infrastructure.

This allows you to use single sign-on (SSO) accross your AWS infrastructure and enable access between your mobiel apps and backend resources like DynamoDB databases or S3-based objets.

For Active Directory integration with cloud-based MS SharePoint, .NET, and SQL server-based, you would use AWS Directory Service for Microsoft Active Directory. Also known as AWS Microsoft AD.

## Credential Report
A credential report allows you to download report in a CSV file format. Reports generates the state of your account security, listing all current IAM users and giving you key intelligence, such as when each of them logged in, whether they have MFA enabled, whether they have active access keys, and when those keys were laste rotated.

# Encryption
AWS provides a number of enterprise-strength encryption tools.

AWS Key Management Service (KMS) manages encryption keys that encrypts data in AWS.

KMS applies encryption using customer master key (CMK) that's been generated for your account. Key management can be done through either the KMS Dashboard or the Encryption Key page within IAM.

Any data managed by an AWS service can be encrypted.
- Relational Database Service (RDS)
- DynamoDB databases
- Elastic Block Store (EBS) volumes

Encryption for S3 works in the same manner but separately. S3 objects of a bucket are encrypted during or after bucket creation. S3 encryption can be managed in two ways:
1. Server side encryption keys (SSE-S3)
2. KMS managed keys (SSE-KMS)

Server-side encryption are objects that are encrypted within a server

Client-side encryption are objects that are encrypted while in transift from local infrastructure.

Client-side encryption needs to be encrypted before uploading it to S3 using either a KMS-managed customer master key or a client-side master key.

# Regulatory Compliance (AWS Artifact)
AWS Artifact is a set of links to documents describing various regulatory standard and how AWS meets them. Each documents is referred to as an artifact.

Artifacts that are available:
1. U.S. government's Federal Risk and Authorization Management Program (FedRAMP)
2. the Government of Canada (GC) Partner Package
3. Australian Prudential Regulation Authority (ARPA) "Management of Security Risk in Information and Information Technology" workbook.
4. PCI DSS Attestation of Compliance and Responsibility for handling credit card transaction.
5. Service Organization Controls (SOC) 1, 2, and 3 audits of AWS infrastructure
# Summary
Use strong passwords by following a password policy in IAM. Strongly recommended to use multi-factor authentication (MFA).

Programmatic and comman-line access to resources is authenticated using key ID and a secret access key. 

Using groups to efficiently control resource access for large number of users.

IAM roles are set of permissions permitting access to a beneficiary process to defined set of resources.