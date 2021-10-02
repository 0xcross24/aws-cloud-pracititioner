# Introduction
Three core networking services:
1. Virtual Private Cloud
2. Route 53
3. CloudFront
# Virtual Private Cloud
A virtual network in AWS cloud that's logically isolated from other networks. Amazon automatically creates a default VPC in each region. The default VPC is configured to allow instances within the VPC to access the internet.

Nondefault VPCs are fully isolated from every other network and AWS resources including other VPCs. An explicit configuration is required to have them access other networks and AWS resources outside of the VPC.

## VPC CIDR Blocks
Each VPC requires a Classless Inter-Domain Routing (CIDR) block to define the range of IP version 4 addresses. By default they have 172.31.0.0/16 which includes addresses from 172.31.0.0 to 172.31.255.255.

## Subnets
Each VPC requires further division into one or more subnets. A subnet is a logical separation and isolation of resources within the same VPC.

Each EC2 instance exists within a subnet and within each default VPC, Amazon creates a default subnet in each Availability Zone.

## Internet Access
Internet gateway - a VPC resource that allows EC2 instances to obtain a public IP address

A subnet with a default route to an internet gateway is called a public subnet.

Each instance must also have a public IP address. Elastic IP addresses can be reassigned to different instances and don't change until you deallocate them.

## Security Groups
Security group - a firewall that determines what network traffic can pass into and out of an instance. Each instance must have at least one security group attached.

Security groups consist of inbound and outbound rules that permits network traffic according to IP address and protocol.

## Network Access Control Lists
Network access control list - a firewall that operates at a subnet level. Consists of inbound and outbound rules that allow all traffic by default.

An NACL can't restrict traffic between instances in the same subnet, but it can prevent traffic from entering or leaving a subnet.

Each VPC has a default NACL that can be associated with one or more subnets.

## VPC Peering
VPC peering connection - a private, point-to-point connection between only two VPCs. Allows resources in different VPCs to communicate with each other over the private AWS network instead of the internet.

## Virtual Private Networks
VPN - allows you to connect a VPC to an external network, such as a ddata center or office via secure connection.

To setup a VPN, a virtual private gateway needs to be created and attached to a VPC.

## Direct Connect
Direct Connect - A private network connectivity between your VPC and public services such as Amazon S3 and Glacier.

Offered through AWS Partner Network (APN) partners. And operates through a dedicated link at 1 or 10 Gbps.

# Route 53
Route 53 - Amazon's global Domain Name System (DNS) service. The primary purpose of DNS is to translate human-readable domain names into IP addresses.

## Resource Records
DNS can store mappings for different types of data, including IPv6 addresses, mail servers, and arbitrary text.

DNS must first define some resource records for a domain.

![image](https://github.com/dannymoon-dev/aws-cloud-pracititioner/raw/master/images/Sat_Oct_02_2021_1633197392256.png)

## Domain Name Registration
A public domain must be register with a domain registrar to avoid having duplicate public domains.

Route 53 is a domain registrar for hundreds of TLDs.

Registration and DNS hosting are two different functions

Registering a domain name gives you control over it for the duration of the lease, including the right to specify the service you want to provide DNS hosting for the domain.

Route 53 is both a registrar and a DNS hosting provider.

## Hosted Zones
To have Route 53 host the DNS for a public domain name, you created a public hosted zone and specify the domain name. You can then define the resource records for that domain.

If you use Route 53 to register a domain name, it automatically takes care of creating a public hosted zone for the domain.

Route 53 provides name resolution for private domain. Private domain names are used on a network other than the internet.

Route 53 private hosted zones provide DNS resolution for a single domain name within multiple VPCs. 

## Routing Policies
Variety of routing policies:
1. Simple - the default for new resource records. Allows you to map a domain name to a single static value. It does not check whether the resource record points to is available.
2. Weighted - distributes traffic across multiple resources according to a ratio. 
3. Latency - sends users to resources in the AWS Region that's closest to them.
4. Failover - route traffic to a primary resource unless it's unavailable.
5. Geolocation - route users based on their specific continent, country or state.
6. Multivalue Answer - evenly distribute traffic across multiple resources. Returns all records, sorted in a random order.

## Health Checks
All routing policies except for Simple can use health checks to determine whether they should route users to a given resource.

Can use one of three things:
1. An endpoint
2. a CloudWatch alarm
3. another health check

All health checks occur every 10 seconds or 30 seconds.

1. Endpoint - Connects to the endpoint via HTTP, HTTPS, or TCP. Ensures that an endpoing is reachable from various locations around the world
2. CloudWatch alarm - A Route 53 health check can monitor the status of a CloudWatch alarm.
3. Calculated - Monitors the status of other health checks. Example, checking the status of both an Endpoint and CloudWatch alarm.

## Traffic Flow and Traffic Policies
Route 53 Traffic Flow visual editor to create a diagram to represent the desired routing.

Can use the same routing policies that are available with normal resource records with addition to Geoproximity.

Geoproximity - directs users to a resource based on how close they are to a geographic location. Differs from Geolocation which is based on the user's specific continent, country or state.

# CloudFront
Amazon's content delivery network that helps deliver static and dynamic web content to users faster that serving it out of an AWS Region.

CloudFront caches your content in number of data centers called edge locations to allow lesser latency for users far away from that region.

CloudFront sends users to the edge location that will give them the best performance.

Edge locations must be chosen from three options:
1. United States, Canada, and Europe.
2. United States, Canada Europse Asia, and Africa.
3. All edge locations

A distribution must be created to make your content available via CloudFront.

A distribution defines the type of content you want CloudFront to cache. content's origin, and where CloudFront should retrieve the content from.

Two types of distributions:
1. Web
2. Real Time Messaging Protocol (RTMP)

Web - Used for static and dynamic content such as web pages, graphic files, and live or on-demand streaming video. Can be accessed through HTTP or HTTPS. Must specify an origin to act as the authoritative source for your content. An origin can be a web server, or a public S3 bucket.

RTMP - Delivers streaming video or audio content to end users. Must provide both a media player and media files to stream, and must be stored in S3 buckets.

# Summary
Virtual Private Cloud provides the virtual network for many AWS resources. Can connect to:
1. Internet via an internet gateway
2. External, private networks via Direct Connect, or a Virtuan Private Network (VPN)
3. Other VPCs using VPC peering

Route 53 provides two distinct but related Domain Name System services. Functions as a registrar and DNS hosting services. 
- To use a public domain, a public hosted zone must be created.
- To use a name resolution within a VPC, a private hosted zone must be created.

CloudFront is Amazon's content delivery network (CDN).
- Improves delivery of data to end users by storing content in edge locations.
- Retrieves contents from edge location that will give them the best performance.