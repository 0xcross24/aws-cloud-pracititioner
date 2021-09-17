# What is Cloud Computing
There's no significant difference between running a software application on servers hosted in your own office versus locating it within Amazon's infrastructure

## Highly Available and Scalable Resources
- Design multiple layers of redundancy so that whenever one component fails, its workload is automatically and instantly moved to a healthy replacement
- Connect resources in geographically remote locations so that the failure of one complete region could trigger a predefined relocation. This relocation can be supported by a similarly automated rerouting of network requests
- Provide customers with access to as much compute power as they could possibly need, and delivery that power on-demand
- Because of the scale and efficiency of the platform, AWS can do all that at a price that's often far below what it would cost to run comparable workloads locally

## Professionally Secured Infrastructure
As a business, you are responsible for protecting the workstations and networking hardware running in your office along with securing your organization's data and code your developers put into your apps. The integrity of your underlying server infrastructure is just one more potential area of vulnerability for you to worry about.

AWS provides and takes responsibility for the security of its platform's underlying networking and compute infrastructure.

Cloud itself is managed by AWS

## Metered Payment Model
Defining characteristics of an cloud computing platform
1. Automatically allocates resources
2. The flexibility of the self-server system
    - Only billed for the time used per server.
    - This is good compared to a self-hosted baremetal. It allows lower cost, since you can delete an instance as soon as a testing environment is completed.

## Server virtualization: The Basics
Provides virtual hardware for the client's need on the spot. Doesn't require setting up a new hardware.

The virtualization model offers two benefits
1. Speed - Defining, purchasing, provisioning, testing, and launching a new physical server can take months
2. Efficiency - Resource constraint on hardware servers. Virtual servers can be divided into multiple instances onto a physical server running a hypervisor. This avoids having the server become overloaded or overused

# Cloud Platform Models
There are different types of cloud services.
1. Infrastructure as a Service (IaaS)
2. Platform as a Service (PaaS)
3. Software as a Service (SaaS)

## Infrastructure as a Service
Similar look and feel to managing physical resources. IaaS provides direct access to provider's compute, storage, and networking assets.

Responsible for the consequences of any bad configurations. You are provided with the resources but all management must be done by the company.

## Platform as a Service
You are not responsible for the complexity of the infrastructure like IaaS.

Given an interface through which you define the behavior and environment you want for your application.

## Software as a Service
Services that are meant to be accessed by end users like Gmail or outlook that runs locally.

[image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Fri_Sep_17_2021_1631912739147.png)