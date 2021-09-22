# Introduction
The way AWS services are used largely depends on the way AWS organizes its hardware, networking, and security infrastructure.

# AWS Global Infrastructure: AWS Regions
https://aws.amazon.com/about-aws/global-infrastructure/

![image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Wed_Sep_22_2021_1632339709036.png)

![image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Wed_Sep_22_2021_1632339726023.png)

Not all of the regions are accessible from a regular AWS account. Deploying resources into the U.S. government GovCloud region requires special permission.

## Regionally Based Services
When you request an instance of an AWS service, the hardware of that instance will be given from one AWS Region. This is true for Elastic Compute Cloud (EC2), Elastic Block Store (EBS), a bucket within Simple Storage Service (S3), or a new Lambda serverless function.

Always be aware of the region that's active for any resource launch.

Checking your current region should become a second-nature reflex.

Dividing resources among regions allows you to do the following:
1. Locate your infrastructure geographically closer to your users to allow access with the lowest possible latency
2. Locate your infrastructure within national borders to meet regulatory compliance with legal and banking rules
3. Isolate groups of resources from each other and from larger networks to allow the greatest possible security

## Globally Based Services
Some AWS resources are not visibly tied to any one region.
1. AWS Identity and Access Management (IAM) - a service for managing the way access to your account resources is achieved by the way of users and groups, roles, and policies.
2. Amazon CloudFront - a content delivery network you can use to lower access latency for your application users by storing cached versions of frequently requested data at AWS edge locations.
3. While Amazon S3 buckets must exist within a single region, S3 is nevertheless considered a global service.

## Service Endpoints
To work with or access the resources within AWS Regions, you'll have to know how they are identified.

The endpoint for an EC2 instance in the us-east-1 (Northern Virginia) region would be: ec2.us-east-1.amazonaws.com.

The endpoint for the Amazon Relational Database Service (RDS) in the eu-west-3 (Paris) region would be: rds.eu-west-3.amazonaws.com.

https://docs.aws.amazon.com/general/latest/gr/rande.html

# AWS Global Infrastructure: Availability Zones
An AWS Region except for Osaka-Local region, encompasses at least two distinct Availability Zones connected to each other with low-latency network links.

Amazon zealously guards the street address of its data center. We do know that a single AZ is made up of at least one fully independent data center that's built on hardware and power resources used by no other AZ.

![image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Wed_Sep_22_2021_1632340488886.png)

The advantage of this level of separation is that if one AZ loses power or suffers an outage, the chances of it affecting a second AZ in the region are minimal.

No two AZs will ever share resources from a single physical data center.

## Availability Zone Designations
Need to specify a network subnet associated with an AZ.

AZs are not listed in order in the subnet drop-down menu to avoid users from underutilizing servers. The AZs are listed out of order to avoid all clients from using the top regions of the dropdown menu.

## Availability Zone Networking
You'll get the full value out of the resources you run within an AWS Region by properly organizing them into network segments or subnets.

Always isolate your production servers from your development and staging servers to ensure work conducted on dev or staging does not affect production.

Distributing production workloads among multiple subnets can also make your applications more highly available and fault tolerant.

AWS permits upto 200 subnets per AZ.

## Availability Zones and High Availability
A resource running without backup is known as a single point of failure.

The only effective protection against failure is redundancy which involes provisioning two or more instances of whatever your workload requires rather than one.

It is easier and sometimes cheaper to build resilience to your cloud infrastructure than on-premise data center.

AWS workloads can be requested and launched on-demand, the job of efficiently provisioning parallel resources is built into the platform's very DNA.

AWS provides autoscaling and load balancing:
1. Autoscaling can be configured to replace or replicate a resource to ensure that a predefined service level is maintained regardless of changes in user demand or the availability of existing resources.
2. Load balancing orchestrates the use of multiple parallel resources to direct user requests to the server resource that's best able to provide a successful experience. A common use case for load balancing is to coordinate the use of primary and remote backup resources to cover for a failure.

# AWS Global Infrastructure: Edge Locations
An edge location is a site where AWS deploys physical server infrastructure to provide low-latency user access to Amazon based data.

Edge locations are front-line resources for directing the kind of network traffic that can most benefit from speed.

## Edge Locations and CloudFront
CloudFront and Amazon's CDN service are best known tenant of edge locations.

They cache copies of the most popular files on servers located geographically close to your users.

Other AWS services that make use of edge locations:
1. Amazon Route 53 - Amazon's Domain Name System (DNS) administration tool for managing domain name registration and traffic routing
2. AWS Shield - A managed service for countering the threat of distributed denial-of-service (DDoS) attacks against your AWS-based infrastructure
3. AWS Web Application Firewall (WAF) - A managed service for protecting web applications from web-based threats
4. Lambda@Edge - A tool designed to use the serverless power of Lambda to customize CloudFront behavior.

## Regional Edge Cache Locations
Amazon has further enhanced CloudFront functionality by adding what it calls a regional edge cache.

Once the rate of new requests drops off, an object will be deleted from the cache. Regional edge cache locations allows objects rejeceted by edge locations to be moved to other nine regional edge caches.

By design, regional edge cache locations are more capable of handling less-popular content.

# The AWS Shared Responsibility Model
Amazon is responsible for the security and reliability of the cloud.

The customer is responsible for the security and reliability of what's in the cloud.

AWS is responsible for making sure that its locations are secure, reliably powered, and properly maintained. AWS is also responsible for patching, encrypting, and maintaining the operating systems and virtualization software running on physical servers and for the software running its managed services.

![image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Wed_Sep_22_2021_1632341901672.png)

## Managed Resources
A managed cloud service will hide all or some of the underlying configuration and administration work needed to keep things running.

If you install a database in your EC2 instance, you'd be responsible for patches, updates, and regular care. Alternatively, you can use a stand-alone database launched on Amazon's Relational Database Service (RDS). AWS will be responsible for patching, security and reliablity.

Elastic Beanstalk handles the instances, storage, databases and networking issues including ongoing patches and administration in the background.

## Unmanaged Resources
EC2 instances are unmanaged AWS service that is expected to care for the operating system and everything running on it.

If you can edit it, you own it. This will help during project's planning stages by being aware of your responsibilities and to always make security a critical priority.

## Service Health Status
AWS makes regular updated, region by region reports on the status of its services publicly available. Any service outages will appear on Amazon's Service Health Dashboard: https://status.aws.amazon.com/

## AWS Acceptable Use Policy
AWS AUP does not permit the use of illegal, harmful, or offensive actions. Amazon reserves the right to suspend or even terminate your use of its services if it breaches the policy. When conducting penetration testing against your own AWS infrastructure, you should gain explicit permission from Amazon in advance.

https://aws.amazon.com/aup/

# Summary
An AWS Region connects at least two AZs located within a single geographic area into a low latency network.

An Availability Zone is a group of one or more independent data centers located within a single geographic region.

The design structure of Amazon's global system of regions allow you to build your infrastructure in ways that provide the best user experience while meeting your security and regulatory needs.

AWS offers some global resources that is not restricted to any one region such as IAM, CloudFront, and S3.

EC2 instances are launched with an IP address issued from a network subnet that's associated with a single Availability Zone.

The principle of high availability can make your infrastructure more resilient and reliable by launching parallel redundant instances in multiple AZs.

AWS Edge locations are globally distributed data servers that store cached copies of AWS-based data on behalf of the CloudFront service. 