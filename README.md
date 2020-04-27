AWS
# [Fundamental Cloud Concepts for AWS](https://app.pluralsight.com/library/courses/fundamental-cloud-concepts-aws/table-of-contents)
This course will provide an introduction to cloud computing on AWS as well covering cloud fundamentals, which is the first step toward the knowledge needed for the **AWS Certified Cloud Practitioner** exam.

Topics:
- The concept of cloud computing
- Organization of AWS global infrastructure
- Economics of cloud computing
- Tools and services that AWS provides to support infrastructures running in their cloud.

## Part 2: Understanding Cloud Computing
### 2.1 Creating a new personal AWS account and setting a budget alert.
I will be using the AWS educate connected with Unipd. In alternative a I can use a personal AWS account and choose the **Free Basic Plan**.

Setting a budget alert for the account is useful for avoiding unexpected charges on the AWS account.

    From the AWS Management Console > "My name" > My Billing Dashboard > Budgets > Create a budget > Cost budget > Set your budget > Name = "Monthly Budget", Budgeted amount = "10$" > Configure Alerts > Alert threshold = "80%" > email > confirm budget > create

### 2.2 Traditional Data Centers
Organization that have not shifted to the cloud. Case study: 
- Company launching a new social network 
- Focusing on the United States at launch
- Looking to expand into Europe and Asia if launch is successful
- Securing founding for the initial infrastructure

Creating the infrastructure:
- time to complete a data center in USA: time to finish work 5 months
- composed of different types of servers: webservers, fileservers, database servers,
- new data center in Europe, it will require the same time, effort and money to replicate the same data center
- hight request in Usa > scale the number of servers. Time to scale the infrastructure 1 month. During this time users will experience performance issues
- new data center in Asia, another 6 months to replicate the data center
- decline of users in Asia. Lost of resources in the data center because servers are not being used.

A traditional approach
- requires a **Large up-front investment** to sut up the initial data center.
- forecasting demand is difficult. User habits are difficult to predict and follow with static infrastructure.
- Slow to deploy new data centers and servers to respond to change in demand quickly.
- Maintaining data centers is expensive.
- Responsibility for security and compliance burden for each of the data centers.

## 2.3 Benefits of Cloud Computing
- Trading capital expense for variable expense. Not required a large initial capital investment to build up the data center. We have a variable expense depending on the amount of time and resources we are using from the cloud provider.
- Benefits from the massive economies of scale. Cloud providers buy a large amount of computing equipments so they can have then in an very concorrencial  price respect to other smaller companies. Also the cloud providers have "know how" to handle this huge infrastructures in scale. This means that this cost saving come down to the consumers also.
- Stop guessing capacity (Elasticity). The cloud provider  offers the possibility to grow or shrink the infrastructure based on demand. 
- Increase speed and agility. In the traditional approach, a company will require finding founding partners in the way to have an infrastructure and a product to for testing. With the cloud, it is require a small amount of investment for testing the hypothesis against real users before going out for the real investment.
- No costs in maintaining data centers. Personal to maintain the data centers.
- Go global in minutes. In traditional approaches is required months to create a data center in another country/city because of the bureaucratic and logistic requirements. With the cloud providers already present in this countries this job is done in hours.

Key terms:
- **Elasticity** : is the ability to acquire resources as you need them and release resources when you no longer deed them. In the cloud you want to do this automatically.
- **Reliability**: (fell over, data servers go down) A solution's ability to provide functionality for its users when it is needed. Amazon's global infrastructure is build to maximize reliability for the client's workloads.
- **Agility**
    - The cloud lowers the costs of trying new ideas of business processes offering frameworks for implementing them.
    - Reduces the time required to maintain infrastructures. This enables companies moving from **maintaining a service** to **services that create value to the business**
    - Reduce risk for the organizations around security and compliance.
    - Provides access to emerging technologies

## 2.4 Types of Cloud Computing
**Cloud computing** is the on-demand delivery of compute power, database storage, applications, and other IT resources through a cloud service platform via the internet with pay-as-you-go pricing.

Cloud Computing Models:
- from Maximum Control
    - Infrastructure as a Service (**IaaS**): is where we run servers in the cloud, virtual servers very similar to how we would run servers in our own data center. Meaning we have full access an control on the servers, we can change OS, configuration. We also have to perform maintenance on the servers, keeping up and running to do exactly what we want them to do.

    - Platform as a Service (**PaaS**): we are given a service configured for us where we simply need to deploy our customizations onto it. For example a WordPres host like WP Engine where we just need to drop our code and everything is already pre configured.

    - Software as a Service (**SaaS**): It as an application ready to use.
- to Minimum Maintenance


## 2.5 Cloud Deployment models
- Public cloud: Deployed onto a public cloud provider like AWS, Azure
- On-Premises (Private Cloud) : Cloud-like platforms ina a private data center
- Hybrid: Cloud applications connected to a private data center

## 2.6 Cloud Computing Scenarios:
Scenario 1:
- Company runs several production workloads in its data center. 
- They use VMWare to manage infrastructure in their data center.
- They want to use AWS and integrate it with their data center for new workloads

Which cloud deployment model would his company be following? Hybrid because of the integration of AWS

Scenario 2:
- Company is trying to decide whether to found a new line of business
- monetize a new emerging technology
- required a new infrastructure

What benefit of cloud computing would be most relevant to her company? Agility of Pay-as-you-go

Scenario 3:
- Insurance company
- they are considering moving to the cloud instead of colocating servers (renting space in another data center)
- maximum control of the cloud servers for security and compliance reasons

What kind of computing model would they need to leverage? IaaS


## Part 3: AWS Global Infrastructure 
The global infrastructure is how AWS deploys and makes accessible its resources globally to its clients. The three main component of the AWS infrastructure are:
- Regions
- Availability Zones
- Edge Locations

### 3.1 AWS Regions and Availability Zones

- Each region is located in a specific geographic location.
- Each geographic location has a cluster of data centers that work together
- AWS has currently launched 22 regions ( privat and publib )

The regions operate with smaller units called **Availability Zones**, which
- consist of one or more **Data Centers**
- multiple **availability zones** are included with each AWS Region. Each Region has at least two Availability Zones, and each Availability Zone has at leas one Data Center. As a the smallest number of Data Centers that can support a AWS Region is two
- These are located in the geographic area of the AWS Region
- The A.Z have redundant power, networking and connectivity to make sure there are no single points of failure that can compromise the QoS
- There are 69 Availability Zones globally

Now availability is the extent to which an application is fulfilling its intended business purpose. So if we have an application for our company that's mission critical, but it's down all the time, that would be a low‑availability application. But if we have a situation where we have an application that is mission critical, and it's up all the time, we could call that a highly available application. And that's done by making sure that no single point of failure will lessen the application's ability to be fully operational. So the concept of an availability zone is that if we deploy our applications and experiences across multiple availability zones within an AWS Region, we minimize any single point of failure in taking our application down. 

Region and Availability Zone Naming:

    us-east-2a
    -- Area (Usa, Europe, Asia)
    -- Sub-erea 
    -- Number (because could be multiple regions within the same area) 
       Letter (designating the availability zone )
   
Region name : us-east-2 (Usa east 2 which is located in Ohio)
Availability Zone: us-east-2**a** ( other a.z would be 2b or 2c)

### 3.2 AWS Edge Locations
- Are used a part of a global content delivery network (**CDN**)

Now there are two specific services within AWS that leverage these edge locations. So it's important to note when we're talking about **regions** and **availability zones**, those are connected to most every service that exists within AWS. However, when we're talking about **edge locations**, this really just supports two different services. The first of those is **Amazon CloudFront**, which is AWS's global content delivery network, and the second is **Amazon Route 53**, which is Amazon's **DNS** service.

- Utilized by Amazon **CloudFront** (CDN) and Amazon **Route 53** (DNS)
- Located globally at over 200 different locations (this is the most common and prevalent part of infrastructure within AWS)
- Allows AWS to serve content from locations closest to users

### 3.3 [Visualizing AWS Global Infrastructure](https://infrastructure.aws/)

### 3.4 Test Scenarios
Scenario 1: 
- Company is looking to transition to AWS
- They are starting gradually with few workloads
- It is requirement to store backup data in multiple geographic areas

Which element of AWS global infrastructure will best suit this need? Regions

Scenario 2:
- Company serves content through  their site to users around the globe
- They are looking to optimize performance to users around the world
- They want to leverage a Content Delivery Network to improve performance

Which element of the AWS global infrastructure will be used in this case? "Edge Locations"

Scenario 3: 
- Company transitioning one of their legacy applications to AWS
- This applications requires an uptime of at least 99.5%
- They want to be sure any issue at a single data center don't cause an outage. This need to be an **highly available application**.

Which element of the AWS global infrastructure will be used in this case? "Availability Zones"





## Part 4: Understanding Cloud Economics
Capitalized Expenditure (**CapEx**): When building a data center, an organization invests in upfront costs for the building, servers. and supporting equipment. This type of expense to attain a fixed asset is referred to as a **Capitalized Expenditure** or **CapEx**. 

For building a data center is required a large initial up-front-investment for the physical and hardware goods which is a capitalized expenditure.

Another type of expenditure si **Operating Expenditure** (**OpEx**) : The regular day to day expenses of a business are considered Operating Expenditures or OpEx. After building the initial data center, ongoing connectivity, utility, and maintenance costs would be considered OpEx.

Comparison between Data Cents and Cloud Computing:

Manage Your Own Data Center vs Leverage Cloud Infrastructure:
- Large Up-front costs (CapEx) | NO up-front investment
- Under-used Capacity or Unmet Demand | You Pay as You go for infrastructure (OpEx)
- scaling takes time and additional CapEx | Scales to meet users demand and can be provisioned immediately
- Monthly costs will map to **predicted** infrastructure needs | **Monthly costs** map directly to **User Demand**

### 4.1 Organizing and Optimizing AWS Cost

AWS Cost Explorer: this is a user interface where the user can explore the AWS costs. It provides breakdowns including:
- By service
- By cost tag
- provides predictions for the next three months of cost based on the current usage.
- recommendations for cost optimization
- accessible via console and API

AWS Budges: utilizes data from **AWS Cost Explorer** to plan and track your usage across AWS services. It can track cost 
- per service, 
- service usage, 
- reserved instance utilization and coverage,
- Savings Plans utilization and coverage.


AWS Cost Planing tools:
- **AWS TCO Calculator**: enables an organization to determine what could be saved by leveraging cloud infrastructure. This is for organizations that are considering migrating to the cloud. The TCO calculator will help make a case for transitioning to the cloud
- **AWS Simple Monthly Calculator**: enables an organization to calculate the costs of running a specific AWS infrastructure.

AWS Resource Tags: metadata assigned to a specific AWS resource. Common use cases include grouping by department, environment, project.
- Cost allocation report includes costs grouped by active tags.
- tags can be leveraged within the AWS Cost Explorer

Another way to organize cost is using the **AWS Organization**. It allows us to manage multiple accounts under a single **master** account. Different departaments or different projects can run inside completely different AWS accounts. AWS provides organizations with the ability to leverage **Consolidated Billing** for all accounts. Enables organizations to centralize logging and security standards across accounts.

### 4.3 Using the AWS TCO [Calculator](http://awstcocalculator.com/)
**TCO** stands for **Total Cost of Ownership**. This helps organizations understand what will cost them to move a workload in the cloud. Comparison the cost of using the cloud versus an organization that is leveraging their own data center. Calculations over 3 year period.

### 4.4 AWS Simple Monthly Calculator
Helps in calculating the costs of running a workload in AWS. (no comparison)

### 4.5 [Cost Explorer](https://console.aws.amazon.com/billing/home?region=us-east-1#/costexplorer)

## 5. Supporting AWS Infrastructure
Understanding the tools provided by AWS to supports workloads in the cloud.

### 5.1 Supporting tools
- AWS Support
- AWS Personal Health Dashboard : 
- AWS Trusted Advisor

**AWS Support**:
- Enables support form AWS resources for workloads running in the cloud
- Provided in different tiers based on need and scope
- Includes tools to provide automated answers and recommendations

**AWS Personal Health Dashboard**: provides alerts and remediation guidance when AWS is experimenting events that may impact you.

 **AWS Trusted Advisor**:
 - Automated tool to check your AWS usage against best practices
 - Access from AWS console
 - Different checks are provided based on the AWS Support plan tier
 - **All AWS customers get access to seven core checks**

The trusted Advisor checks are divided into five different categories:
- cost optimization
- performance 
- security
- fault tolerance 
- service limits

### 5.2 AWS Support Plan Differences
- Communication method
- Response time
- cost
- type of guidance offered


**AWS Basic support**:
- provided for all AWS customers
- access to Trusted Advisor (7 core checks)
- 24x7 access to customer service, documentation, forums & whitepapers. No access to AWS tech Engineers for tech implementation questions.
- access to AWS Personal Health Dashboard
- No monthly cost

**AWS Developer Support**: This is targeted at individual developer that's looking to get support for running their workloads in AWS.
- Includes all Basic Support
- Business hours email access to support engineers
- Limited to 1 primary contact
- Paid $29/month (tied to AWS usage)


**AWS Business Support**
- Includes all the features from the Developer Support
- Full set of Trusted Advisor checks
- 24/7 phone, email, and chat access to support engineers
- Unlimited contacts
- third-party software support
- $100/month (tied to AWS usage)

**AWS Enterprise Support**
- Includes all features from the Developer Support
- Includes designated Technical Account Manager (TAM)
- Includes concierge support team
- $15k / month (tied to AWS usage)

**Support Response time**:
- General Guidance
    - Dev: 24 business hours 
    - Business: 24 h
    - Enterprise: 24 h
- System Impaired
    - Dev: 12 bh 
    - Business: 12 h
    - Enterprise: 12 h
- Production System Impaired
    - Business: 4 h
    - Enterprise: 4 h
- Production System Down
    - Business: 1 h
    - Enterprise: 1 h
- Business-Critical System Down
    - Enterprise: 15 min

General Guidance when we have question we need to have answered.
System Impaired when something is not working as it should
Production S. I when a production system not performing at its desired capacity.
Production System Down when production system is non functional.
Business-Critical System Down when a core system is completely down.


## Preparing the Exam 

Items to Review:
- Cloud and Traditional Infrastructure. 
    - How traditional data centers work and what is the difference when we are leveraging the cloud. 
    - Concepts like Elasticity and how it is different in one versus the other.
- Elements of AWS Global Infrastructure:
    - Regions
    - Availability zones
    - Edge locations
    - how this effect the workloads that i choose to run on AWS
- Funding Cloud Infrastructure, how you found a cloud infrastructure as well as different economic considerations with the cloud.
    - CapEx vs OpEx
    - how the model is different
    - how cloud model fit to usage
- Forecasting and Managing AWS Costs
    - AWS Cost Explorer
    - TCO calculator
    - Simple Monthly calculator
    - How each of those can be beneficial to my workload on AWS
    - how to organize costs using features like tags.
- AWS Support Plans
    - different tires that are provided within AWS support plans and understand when you would choose one vs another
- Additional Support tools
    - AWS Trusted Advisor and knowing the categories provided for its recommendations
    - AWS Personal Health Dashboard and when I would use that when I am running workloads on AWS
# [Understanding AWS Core Services](https://app.pluralsight.com/library/courses/understanding-aws-core-services/table-of-contents)
from pluralsignt.com for AWS Certified Cloud Practitioner Path.

## 2. Interacting with AWS

Tools for interacting with AWS services:
- AWS Console. The users can leverage their browser to configure resource.
- AWS CLI: command line access for administration AWS resources.
- AWS SDK: Programmatic access to manage AWS resources.

**AWS Management Console**: A web and app based interface for interacting with most all of 150+ AWS services. All major browsers and mobile operating systems are supported.

**AWS Command Line Interface (CLI)**: Tool to manage the use of AWS services from the command line on Windows, Mac and Linux. Most every task that can be done in the console can be done with the CLI. Managing the services from the command line.

    aws --version
    aws iam list-users

    # using containers
    docker run --rm -it amazon/aws-cli --version

    # sharing credentials
    docker run --rm -it -v ~/.aws:/root/.aws amazon/aws-cli --version

**AWS Software Developer Kit (SDK)**: Programming language-specific resources that allows the user to interact with AWS services via code. This approach enables you to automate many aspects of how you interact with the platform. Language supported
- Java .Net Node.js JavaScript PHP Python Ruby Go C++

Interacting with AWS:
- The console is a great method for testing out AWS services
- Repeated tasks can be automated using the CLI or SDK
- SDK enables automation of AWS tasks within custom applications
- Most all services and actions can be performed in any of the three

### 2.2 AWS Console
Root user log in

### 2.3 Using the AWS CLI

## 3. Compute Services
A service that enables you to leverage **cloud-based virtual machines** for workloads. This could be serving web content to visitors, running a database, or calculating statistics form a data set.

Compute services on AWS:
- **Amazon EC2**: provides secure and resizable **virtual servers** on AWS
- **AWS Elastic Beanstalk**: platform for scaling and deploying web apps and services (PaaS)
- **AWS Lambda**: enables compute without managing servers

### 3.1 Amazon EC2 Overview (IaaS)
**Amazon Elastic Compute Cloud (Amazon EC2)** is a web service that provides **resizable compute capacity** in the cloud. It is designed to make web-scale computing easier for developers.

EC2 Use cases:
- hosting a web application in the cloud. we can spin up an EC2 instance and on that instance install a web server and save our files for the web application.
- batch processing. analyzing or pre processing huge amounts of data on en EC2 instance before analyzing it.
- web service endpoint
- desktop environment instance on the cloud (windows or linux)

Core concepts of EC2:
- Instance Types
- Root Device Types
- Amazon Machine Image (AMI)
- Purchase Options

**Amazon EC2 Instance Type**
- Defines the processor, memory, and storage type that are available to any server that are launched with that instance type.
- Cannot be changed without downtime
- Types if the following categories:
    - General purpose
    - compute, memory, and storage optimized
    - accelerated computing (ml with gpu)
- Pricing is based on the instance type
- Some Instance types have unique capabilities (specialized storage, gpu)

Example of EC2 Instance Type Pricing:
- t3.medium
- m5.large
- c5d.24xlarge
- p3.16xlarge
- i3.16xlarger

**Root Device Type**
- **Instance Storage**: ephemeral storage that is physically attached to the host the virtual server is running on. If we shutdown the instance then the data will be lost.
- **Elastic Block Store** (EBS): persistent storage that exists separately from the host the virtual server is running on. The data wil be persistent during time and shutdowns. **Each EBS is attached to a single EC2 instance.**

**Amazon Machine Image (AMI)**:
- Template for an EC2 instance including configuration, operating system, and data
- AWS provides many AMI's that can be leveraged easy to spin off.
- AMI's can be shared across AWS accounts

### 3.2 Amazon EC2 Purchase Types:
Amazon EC2 purchase options when we lunching instances on AWS:
- On-Demand: you pay by the second for the instances that are launched.
- Reserved: you purchase at a discount price instances in advance for 1-3 years
- Spot: you can leverage **unused** EC2 capacity in a region for a large discount

**Reserved Instance Cost Models**:
- All upfront: entire cost for the 1 or 3 year period is paid upfront. This can be done for services we know that will be for sure running for a certain period of time.
- Partial Upfront: Part of 1 or 3 year cost is paid upfront along with a reduced monthly cost
- No Upfront: no upfront payment is made, but there will be a reduced monthly cost


**Spot Instances**:
- Can provide up to 90% discount over on-demand pricing.
- There is a market price for instance types per availability zone called **Spot price**.
- When you request instances, if you bid is higher than Spot price then the instance is assigned to the highest bidder and the workload will be launched.
- If the Spot price grows to exceed your bid, the instances will be terminated
- Spot instances can be notified 2 minutes prior to termination.

**Spot Instances are very good for workload that can start and stop.**

Amazon EC2 Purchase Options:
- If I have an instance that is **consistent** (run for at least 3 years, same requirements) and always needed, I should purchase a **Reserved Instance**
- If we have **batch** processing where the process can **start and stop** without affecting the job, i shot leverage **Spot Instances**
- If I have an **inconsistent** need for instances that cannot be stopped without effecting the job, leverage **On-Demand Instances**.

### 3.3 Launching EC2 Instances with AWS Console
EC2 > scroll down and > Launch Instance > Choose AMI (Free Tier) > **t2.micro** (Free tier Instance Type) > Next: Configure Instance Details

Set the Auto-assign Public Ip to "Enable" so we can access our instance form the internet.
To the section Advance Details we can insert commands that the server will execute when it starts. In this case is install a web server and run it

    #!/bin/bash
    yum install httpd -y
    service httpd start

then we go > Next: Add Storage > Next: Add Tags in the way to control charges > Next: Configure Security Group changing the "Source ip" access to "My Ip" (curl ifconfig.me). In this case only my ip address can SSH this EC2 instance.
I will be adding a rule for allowing http traffic on port 80 > Review and Launch

We can check the state of our instance at EC2 Dashboard. Under Public DNS we can find the link to access our instance and check if the web server is working.

To destroy an instance we go Actions > Instance State > Terminate


### 3.4 AWS Elastic Beanstalk

- Automates the process of deploying and scaling workloads on EC2 (PaaS type approach).
At high level elastic beanstalk automates the process of deploying and scaling your workloads on EC2. But the difference is instead of dealing with those servers directly, which we would call infrastructure as a service (IaaS), this is more of a platform as a service type approach (PaaS).
- supports a specific set of technologies
- Leverage existing AWS services
- Only pay for the other services you leverage. Set of services that makes easier running other AWS services. We still are running all our workload on EC2, but the process of managing the servers and handling things like provisioning and load balancing, scaling and monitoring are all handled automatically through the work of Beanstalk by connecting other services into the overall platform.

Supported Application Platforms:
- java
- .Net
- PHP
- Node.js
- Python
- Ruby
- Go
- Docker


Features and Advantages of BeanStalk vs EC2:
- integrated monitoring tools
- managed deployment for multiple servers and load balancing in production environment
- Scaling
- EC2 Customizations


Use Cases:
- Deploy an application with minimal knowledge of other services like administrating EC2 servers, scaling, metrics
- Reduce the overall maintenance needed for the application. If our workload fits in one of the use cases the Beanstalk has, we can avoid dealing with many of the administrative tasks taken care of by the platform.
- Few environment customizations are required

**Launching an App on Elastic BeanStalk**
Using the [node.js tutorial](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/tutorials.html)

AWS Console > Beanstalk
Application Name
Platform depends on the tutorial
Upload your code
Configure More Options
Create App

Actions > Terminate Application

### 3.5 AWS Lambda Overview
**AWS Lambda** lets you **run code** without provisioning or managing servers. **You pay only for the compute time you consume**. You can run code for virtually any type of application or backend service - all with zero administration.

**AWS Lambda**:
- enables the running of code **without provisioning infrastructure**
- only charged for usage based on execution time
- charge depends on amount of memory requested for the function. Configurable memory from 128 to 3008 MB
- integrates with many AWS services as S3, DynamoDb
- enables event-driven workflows ( when i have a file upload, then trigger this function)
- primary service for **serverless** architecture approach


AWS Lambda Advantages:
- reduced maintenance requirements
- enables fault tolerance without addition work
- scales based on demand ( depends on the number of users that are using the lambda function)
- pricing is based on usage ( an EC2 server can be used by 10 or 100 users but the changing will be the same for maintaining the instance, instead fro lambda you are charged based on the number usage tha we have)

## Scenario Review
Silvia
- her company is moving workload to AWS
- one workload is an app that will be leveraged for at least 5 more years
- cost efficient as possible for its EC2 usage

What EC2 purchase options should be chosen? **All Upfront Reserved**

Edward:
- deploy PHP app to a virtual server
- no experience with EC2
- will need scaling

Best Compute options: **Elastic Beanstalk**

Cindy:
- transitioning to the cloud for the data processing
- daily routines that can start and stop without problems
- will be leveraged for at least one year

what EC2 purchase options would be the most cost efficient? Spot Instances

## 4. Content and Network Delivery Service
- Amazon Route 53
- Amazon VPC
- AWS Direct Connect
- Amazon API Gateway
- Amazon CloudFront
- Elastic Load Balancing

### 4.1 Amazon Virtual Private Cloud and Direct Connect

**Amazon Virtual Private Cloud (VPC)** is a logically isolate section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.
- enables virtual networks in AWS
- IP4 and IPv6
- allows for configuration of
    - ip address range
    - subnets
    - route tables
    - network gateways
- supports public & private subnets
- can utilize NAT for private subnets
- enables a connection to your data center
- can connect to other VPC's
- private connection to many AWS services

**AWS Direct Connect**: A cloud service solution that makes it easy to establish a dedicated high speed network connection from your data center to AWS.

### 4.2 Amazon Route 53 (Amazon's DNS service)

- is a Domain Name Service (DNS)
- global AWS service
- highly available
- enables global resource routing ( sending users to a specific server based on what county they are coming from.)

**DNS**: translates more readily memorized domain names to the numerical IP addresses needed for the locating and identifying computer services and devices with the underlying network protocols.

### 4.3 Elastic Load Balancer

**Elasticity**: the ability for the infrastructure supporting an application to grow and contract based on how much it is used at a point in time.

**Elastic Load Balancing**:
- distribute traffic across multiple targets
- integrates with EC2, ECS, and Lambda
- supports one or more Availability Zones in a region.
- three types of load balancers
    - Application Load Balancer (ALB)
    - Network Load Balancer (NLB)
    - Classic Load Balancer

Scaling on Amazon EC2
- **Vertical scaling**: you **"scale up"** your instance type to a larger instance type with **additional resources**. So we scale our instance type to a **larger instance** type with **additional resources**. (small to larger server)
- **Horizontal scaling**: you **scale out** and add **additional instances** to handle the demand of the application (increasing the number of servers)

### 4.3 Amazon CloudFront and API Gateway

Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment.
- it is a Content Delivery Network (CDN)
- enables users to get content from server closest to them to increase performance
- supports static and dynamic content
- utilizes AWS edge locations
- includes advanced security features
    - AWS Shield for DDoS
    - AWS WAF (wep app firewall)


**API Gateway**
- fully managed API management service ( creating APIs which are web application that other applications can call and make them available and distribute them through **CloudFront**)
- directly integrates with multiple AWS services
- provides monitoring and metrics on API calls
- supports VPC and on-premise private applications


### Scenarios
Jane
- company maintains two corporate data centers
- they want the data centers to work alongside AWS for specific workloads
- persistent connection to AWS

What service AWS would you recommend? **Direct Connect**

Tim
- serve content around the globe
- optimize performance
- CDN

Which service to optimize performance globally? **CloudFront**

Elen
- internal application on EC2
- downtime for capacity
- scaling up (vertical) or scaling out (horizontal)

Horizontal scaling (scaling out) using Elastic Load Balancing

## 5. File Storage Services
AWS File Storage and Data Transfer Services
- Amazon S3 (core services)
- Amazon S3 Glacier
- Amazon Elastic Block Store
- Amazon Elastic File System
- AWS Snowball
- AWS Snowmobile


### 5.1 Amazon Simple Storage Service S3 ( Core Service )

**Amazon Simple Storage Service (S3)**:
- stores file as objects in buckets. Buckets are unit of organization on S3. We have to create a bucket which will have a set of settings and any file that we drop in can have those settings applied to it.
- provides different storage classes for different use cases
- stores data _**automatically across multiple available zones**_, which gives us durability and resiliency for the data.
- enables URL access to files (sharing a file through a URL)
- offers configurable rules for data lifecycle
- can serve as a static website host

**Amazon S3 Non-archival Storage Classes**:
- **S3 Standard** is the default storage class and is for _**frequently**_ accessed data.
- **S3 Intelligent-Tiering** will move your data to the correct storage class based on usage.
- **S3 Standard-IA** is for _**infrequently**_ accessed data with the standard **resilience** (multiple A.Z.)
- **S3 One Zone-IA** is for **infrequently** accessed data tha is only stored in on Availability Zone.

**S3 Intelligent Tiering Storage Class**:
- Automatically moves files based on access classes
- moves between this two classes
    - frequent
    - infrequent
- same performance as S3-Standard
- cost saving if we have data to be moved between the two classes 

**S3 Lifecycle Policies**:
- Objects in a bucket can transition or expire based on the settings criteria
- transitions can enable objects to move to another storage class based on **time**. Moving based on usage is available on the **Intelligent** class.
- Expiration can delete object based on age
- Policies can also factor in **versions** of a special object in the bucket

**S3 Transfer Acceleration**: Feature that can be enabled per bucket that allows for optimized uploading of data using the AWS Edge Locations as a part of Amazon **CloudFront**. Feature for uploading data into the bucket much faster.


### 5.2 Hosting a static Website on S3
- Creating a new S3 bucket
- Uploading objects to an S3 bucket
- Accessing objects on S3 bucket from URL
- Configuring a bucket for website hosting


### 5.3 Glacier and Glacier Deep Archive:

Amazon S3 Glacier: Archiving data that will be accessed for rare circumstances.
- Designed for archiving of data within S3 as separate storage classes. ( holding payment information from customers for 1 year or three years, i will not access them only in rare cases when required)
- Offers configurable retrieval times (**quick or slow** retrieval and we will be charged based on the choice )
- can send files directly or through lifecycle rules in S3 to transition data into S3 Glacier.
- provides two different storage classes
    - S3 Glacier
    - S3 Glacier Deep Archive

**S3 Glacier vs Deep Archive**: 
- Designed for Archival data
- 90 days minimum storage duration change | 180 days (saving data for at leas 6 months)
- can be retrieved in either min or hours (different charges for every speeds) | can be retrieved in hours 
- you pay a retrieval fee per GB retrieved
- over 5 times less expensive then S3 Standard Storage Class | 23 times

The AWS Management console can be used to quickly set up Amazon S3 Glacier. Data can then be uploaded and retrieved programmatically (CLI or SDK).


### 5.4 Elastic File System (EFS)

- is a fully managed NFS (Network File System)
- designed specifically for Linux workloads
- supports up to petabyte 10^15
- data stored across multiple AZs, (data durability and resilience )
- provides two different storage classes
    - Standard
    - infrequent access
- configurable lifecycle data rules for transitioning between the two storage classes

_**The difference with the EBS is that EBS are attached to a single EC2 instance, instead EFS has the ability to be a network file system that we can attach to multiple instances at the same time**_


Amazon FSX for **Windows File Server**:
- fully managed native windows file system
- includes native windows features including 
    - SMB support
    - Active Directory integration
    - Windows NTFS
- utilizes SSD drives for low latency   


### 5.5 Data transfer with **AWS Snowball**
How to transfer large amount of data into AWS cloud without _**passing**_ through the **public internet** ?

AWS Large Scale Data Transfer Service:
- **AWS Snowball**: service to physically migrate petabyte scale data to AWS
- **AWS Snowmobile**: service to physically migrate exabyte scale data onto AWS

Large-scale Data transfer into AWS: Snowball vs Snowmobile:
- Designed for large-scale data transfers
- petabyte scale transfer || exabyte
- physical device is delivered by AWS to the our office || shipping container (huge/large)
- we upload the data on the device | AWS sets up a connection for uploading the data
- the device is returned by local carrier back to AWS
- AWS loads the data from the device to S3 


### Scenarios

Elaine:
- elearing website
- uses s3 to store the assets needed per tutorial
- hight demand during the first week
- after the first week this assets  are rarely accessed

how to reduce the S3 costs maintaining durability (multiple copies)?
Solution: S3 lifecycle rules with **S3-standard IA** storage class



Esteban:
- company moving to AWS
- have 2 PB of data to migrate
- which is the fastest approach to migrate the data (internet maybe takes too long)

Is there a fastest way to do it? Snowball


Emily:
- messaging app
- she is looking for a shared File System between 8 Linux EC2 instances
- the file system would need to support 1 PB of data

What approach is ok for Emily? EFS (NFS)


## 6. Databases Services and Utilities

AWS Databases & Related Services:
- Amazon RDS (PaaS)
- Amazon Aurora (PaaS)
- Amazon DynamoDB (SaaS)
- Amazon Redshift
- Amazon Elasticache
- AWS Database Migration Service

Different approaches:
- **IaaS** (Maximum Control over everything)
    - we would instal a Database on a EC2 instance
- **PaaS** Relation Database Service (RDS)
    - control on the database but not on the infrastructure
- **SaaS** (Minimum maintenance)
    - DynamoDB, Elasticache, Redshift


### 6.1 Amazon Relational Database Service (PaaS RDS)

It uses the **PaaS** approach for running databases that we can leverage within our applications that are running on the platform. First it is important to note that **it is a fully managed service** for relation databases.

**RDS**:
- Fully managed service for relational databases
- handles provisioning, patching, backups, and recovery of the database
- supports deployments across multiple availability zones (mylti-AZ)
- some platforms support read replicas ( helps scaling out the database)
- launches into a VPC
- provides both general purpose SSD and provisioned IOPS SSD drive options

Amazon **RDS Platforms**:
- MySQL
- PostgreSQL
- MariaDB
- Oracle Database
- SQL Server
- Amazon Aurora

**Amazon Aurora** is a MySQL and PostgreSQL-compatible relational database built for the **cloud**, that combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases

**Amazon Database Migration Service (DMS)**:
- Enables you to move data into AWS from existing databases
- supports both one time and continual migration of data
- supports many popular commercial and open source databases
- only pay the compute leverage in the migration process

### 6.2 Amazon DynamoDB Overview (SaaS)
 - **fully managed NoSQL service (SaaS)**
 - provides both key-value and document database
 - enables extremely low latency at virtually any scale
 - supports automated scaling based on configuration
 - offers in-memory cache with the DynamoDB Accelerator (DAX)

 **DynamoDB** can handle more than 10^12 requests per day and can support peaks of more than 20 million requests per second.

 **DynamoDB use Cases**: 
 - scale without excessive maintenance
 - serverless applications
 - implementations where low latency is key
 - data models without BLOB storage

 ### 6.3 Amazon Elasticache & Reshift

 **Elasticache**:
 - is a fully managed in-memory data store
 - supports both **Memcached** and **Redis**
 - provides low latency in response times
 - enables scaling and replicas to meet application demand
 - handles common use cases including:
    - database layer caching
    - session storage 

**Redshift**:
- Scalable data **warehouse** service
- supports petabyte 10^15 scale warehousing of data
- leverages high performance disks and columnar storage
- offers the ability to fully encrypt the contents
- provides isolation with a VPC
- enables querying of exabytes of data in S3 using Redshift Spectrum 

### 6.4 Scenarios

Jennifer:
- transitioning the data warehouse to AWS for analysis and ML
- 2 PB
What approach would you recommend? **Redshift**


Sam:
- launch a MySQL for a new app
- direct access to the MySql server

What approach would you recommend? **EC2 + MySQL** IaaS


Frank:
- how to store real time user analytics
- low latency and scale for 10^6 players
- low maintenance work

What approach would you recommend? DynamoDB




## 7. App Integration Services

- **Amazon SNS** (simple notification service): Managed pub/sub messaging service
- **Amazon SQS** (simple queue service): Managed message queue service
- **AWS Step Function**: Serverless workflow management service

### 7.1 AWS Messaging Services

**SNS (Simple Notification Service  )**
- fully managed pub/sub messaging service
- enables you to create decoupled applications
- organized according to topics
- integrates with multiple AWS services
- provides end user notifications across SMS, email, and push notifications.
- messages are not saved, they trigger actions and after disappear


**Simple Queue Service (SQS)**
- fully managed message queue service
- enables to build decoupled and fault tolerant applications (we can have an aspect of our system going down and it can still work according to its purpose)
- supports up to 256 kb data payload
- allows messages to be stored up to 14 days
- provides two types of queues
    - standard queue
    - FIFO queue

Example of SNS & SQS Architecture:
![picture](./img/sns_sqs.png)

### 7.3 AWS Step Functions
- enables orchestration of **workflows** through a fully managed service
- supports serverless architectures
- can support complex workflows including error handling
- charged per state transaction along with the other AWS services leveraged
- Workflows are defined using Amazon States Language

Example of Workflow Architecture:
![picture](./img/workflow.png)


AWS Step Function Integrations:
- compute services (integrate with lanbda)
- database services
- messaging services (SQS, SNS)
- data processing services
- ML services

This is a powerful tool that can be used to build out very complex work flows and have Amazon manage the state for us of the different steps within that workflow.

### 7.4 Scenarios

Ruth:
- database server went down and uses were unable to signup
- there is no guarantee for no downtime
- AWS service to prevent lost of your signups

Fault tolerant problem.
What AWS service would you recommend? SQS

Jessi:
- complex workflow

What AWS service would you recommend? Step Function


Roger:
- ecommerce platform
- platform listening for key events

SNS

## 8. Management & Governance Services

- AWS CloudTrail
- AWS CloudFormation
- AWS CloudWatch
- AWS Config
- AWS System Manager
- AWS Control Tower


### 8.1 AWS CloudTrail

With **CloudTrail**, you can log, continuously monitor, and retain **account activity** related to actions across your AWS infrastructure. CloudTrail provides event history of your **AWS account** activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services.

- Inserts audit trail in an **S3** bucket or into **CloudWatch Logs**
- Logs events in the regions in which they occur
- meets many compliance requirements for infrastructure auditing
- as a best practice, it should be enabled on every AWS account
- can be consolidated into an Organizational trail using AWS Organizations

AWS CloudTrail Use Cases:
- compliance requirements
- forensic analysis
- operational analysis
- troubleshooting

### 8.2 Amazon CloudWatch and AWS Config

- **CloudWatch** which provides metrics, logs, and alarms for our infrastructure
- **AWS Config** which continually evaluates infrastructure against a predefined set of rules
- **AWS Systems Manager** Provides operational data and automation across the infrastructure

**CloudWatch**:
- monitoring and management service
- collects logs, metrics, and events from most AWS services
- enables alarms based on metrics
- provides visualization capabilities for metrics
- allows for custom dashboards based on collected metrics

**AWS Config** continuously monitors and records your AWS resources configurations and allows you to automate the evaluation of recorded configurations against desired state
- provides configuration history for infrastructure
- works against rules that you can customize or even create custom validations
- includes conformance packets for compliance standards including PCI-DSS (payments)
- can work with AWS Organizations for both cross-region and cross-account


### 8.3 AWS Systems Manager

**AWS Systems Manager**  provides a unified user interface so you can view operational data from multiple AWS services and allows you to automate operational tasks across your AWS resources.
- provides multiple tools that make it easier to manage your AWS infrastructure
- enables automation tasks for common maintenance
- gives a secure way to access servers using only AWS credentials
- stores commonly used parameters securely for operational use (like password databases)

### 8.4 AWS CloudFormation
- managed service for provisioning infrastructure based on templates
- no additional charges
- templates can be YAML or JSON
- enables infrastructure as code
- manages dependencies between resource
- provides drift detection to find changes in the infrastructure

### 8.5 AWS Organizations & Control Tower

**AWS Organizations**:
- allows organizations to manage **multiple** accounts under a **single master** account
- provides organizations with the ability to leverage Consolidated Billing for **all accounts**
- enables organizations to centralize logging and security standards across accounts


AWS Organizations shows what we can do with it, but not what we should do with it. So Amazon collected a lot of the best practices for a multi account set up under a service called
**AWS Control Tower**: is a service to create a multi-account environment on AWS that follows the recommended best practices in operational efficiency, security, and governance.

**AWS Control Tower**:
- centralizes users across all AWS accounts. this allows us to minimize effort to creating users across multiple accounts.
- provides a way to create new AWS accounts based on templates ( specific settings for each different account category)
- integrated guardrails for accounts. this helps makes sure that there are specific protections for accounts underneath the master account. setting rules to accounts
- includes a dashboard to gain operation insights from a single view across all accounts.

### 8.6 Scenarios

Elliot is Ops engineer
- someone had disabled a security setting on a server
- how to track such activities

Which service would allow the organization to continually track configuration of infrastructure?
**AWS Config**

James
- launching a new app with multiple components
- minimize manual work required when creating infrastructure

What service would enable James to automate much of this effort? **CloudFormation**

Candace:
- cloud server was deleted
- follow up wit the person who deleted this instance. they wanna figure out who this individual is

Which service could show the individual that deleted this specific server? **CloudTrail**










# [Introduction to Security and Architecture on AWS](   https://app.pluralsight.com/course-player?clipId=b2d82afd-e122-45fc-b203-7350fae19fdc)
# 2. AWS Core Concepts

**Acceptable Use Policy** : AWS's policy for acceptable and unacceptable uses of their cloud platform. All users must agree with this policy to have an account on the platform.
- Sending unsolicited mass email is prohibited
- hosting or distributing harmful content is prohibited
- **Penetration test are allowed for a list of specific services**

**Least Privilege Access**: when granting permission for a user to access AWS resources, we should grant them the minimum permissions needed to complete their tasks and no more. AWS recommends tha we don't use our root account as the day to day account. They recommend to create and use an **IAM** account for a daily basis use. So everyone should have access only to what they need to do the job that is given. 

### 2.3 AWS Shared Responsibility Model
**"Security and Compliance is a shared responsibility between AWS and the customer"**
- AWS Responsibility:
    - AWS is responsible for the security **of** the cloud. So AWS has responsibility for the core system that is running the entire platform.
- Customer Responsibility:
    - Customer is responsible for the security **in** the cloud. It has control on the things it is putting in the platform and how it is using it.


**AWS Responsibility**
- Access control & training for their AWS employees. They have control on what employees can access, and the training to know what they are doing. 
- Global data centers and underlying network. responsible for the connectivity to exists between the AZ and all the infrastructure.
- Hardware for the global infrastructure
- Configuration management for the infrastructure, this means responsibility for how bits of data get from one location to another. 
- Patching of cloud infrastructure and services. 

**Customer Responsibility**
- Individual access to cloud resources and user training.
- Data security and encryption (both in transit and at REST)
- Operation system, network, and firewall configuration. In case of IaaS with EC2 instances then we are responsible for the OS and all the other server configurations.
- All code deployed onto cloud infrastructure
- Patching guest operations systems and custom applications

### 2.4 [AWS Well-architected Framework](https://aws.amazon.com/architecture/well-architected/?nc1=h_ls)


AWS offers best practices to follow for creating well configured Architectures and they gathered this information on the 
**"AWS Well-architected Framework"**: The well-architected Framework is a collection of best practices across five key pillars for how to best create systems that create business value on AWS.

- **Operational Excellence**: running and monitoring systems for business value. Checking that we are being efficient with the time to build and deploy our solutions on the cloud 
- **Security**: Protecting information and business assets. Monitoring to ensure that we are following the same standards of security through the life of those assets.
- **Reliability**: Enabling infrastructure to recover from disruptions. Our system up and running as often as possible. (Reliability is the degree of consistency of a measure. A test will be reliable when it gives the same repeated result under the same conditions.)
- **Performance Efficiency**: using resources efficiently to achieve business value. Leveraging the resources on AWS and using only the amount that are needed to perform the tasks that we have for them.
- **Cost Optimization**: Achieving minimal costs for the desired value. We have to be sure we are not paying any more than we need to to achieve the level of business value that we need. ( concepts as Reserved Instances, Spot Instances, different S3 storage classes)

AWS has collected this information on a [website](https://aws.amazon.com/architecture/well-architected/?nc1=h_ls)

### 2.5 Hight-availability and Fault Tolerance 
Both of this concepts fall under the **Reliability** pillar of the Well-Architectured Framework.

**"Everything fails all the time"** CTO, Amazon
 We should build knowing that failure can happen in anytime on our architecture.

 **Reliability on AWS**: 
 - **Fault Tolerance**: being able to support the failure of components within your architecture
-  **Hight Availability**: keeping our entire solution running in the expected manner despite issues that may occur.

Building Solutions on AWS: 
- Most managed AWS services provide high-availability out of the box 
- when building solutions directly on EC2 fault tolerance must be architectured. For solutions that are **IaaS**, this is where we have to consider fault tolerance and we will have to figure out how to built into our custom solutions
- Multiple Availability zones should be leveraged so that we can deal with potential failure of a complete zone within a region.
- Some services can enable fault tolerance in our custom applications (SQS, Routo 53 to detect of there end point non available and route the users to an available server)

### 2.6 Compliance
IT Compliance is the process of meeting a third party's requirements for digital security with the aim of enabling business operations in a particular market or with a particular customer.

Common Compliance Standards:
- PCI-DSS: Compliance standard for processing credit cards
- HIPAA: Compliance standard for healthcare data
- SOC 1, 2, 3 : third-party reviews of operational processes related to the datacenters
- FedRAMP: US government data handling
- ISO 27018: handling Personally Identifiable Info

There are services on AWS that can help you know how to navigate these compliance standards

**Compliance Services**:
- AWS Config: provides conformance packs for standards
- AWS Artifact: provides self-service access to AWS compliance reports
- AWS GuardDuty: provides intelligent threat detection. detects scenarios that are happening that unusual, that could lead to you being out of compliance.

Demo:
- Examining compliance reports in **AWS Artifact**
- Exploring conformance packs in **AWS Config**


### 2.7 Scenarios

Jane:
- app for processing Credit Cards
- directly not through a third party service
- the bank needs a PCI DSS compliance report for AWS

Where should Jane go to get the information?? **AWS Artifact**

Tim:
- transitioning to the cloud
- store personal information securely in their system
- what is the company's responsibility is for security once they migrated in AWS

What is the responsibility ? 

Ellen:
- solutions architect at a startup
- building new app
- how to best leverage the best capabilities of AWS in this app

What resource should they review before planing? **AWS Well-architectured Framework**.


## 3 AWS Identities and User Management

**"Least Privilege Access"**: When granting permission access to a user on AWS resources, we should grant them the minimum permissions needed to complete their task and no more. 

### 3.1 AWS Identity & Access Management (**IAM**)
- This is the service that controls access to AWS resources. This is the service where we can create a user and configure what are their permissions.
- IAM is a free services
- Manges both authentication (verifies users) and authorization (what the user can do ) 
- Supports identity federation through **SAML** providers including Active Directory. This allows us to use an external identity provider to handle the authentication.

**IAM Identity types**
- **User**: Account for a single individual to access AWS resources. New employ > new account and assign permission to access specific resources.
- **Group**:  allows you to manage permissions for a group of IAM users. We create IAM for each user, we create group and set all the permissions for specific resources and after we add users to this group. which users will inherit the permissions of the group. 
- **Roles**: enables a user or AWS service to assume permissions for a task. Is like a sudo command for a user or when we give permissions to a service to run with root privileges on linux. Or we can consider an EC2 instance that needs to write data to an S3 bucker, but by default it can't do it, se we can assign to the EC2 instance a Role with permission to write data to S3 bucket.

How do we assign permissions? This leads to the concept of Policies which is just a Json document that defines permissions for an IAM identity.

**Policies in AWS IAM**:
- A JSON document that defines permissions for an AWS **IAM** identity ( user, group, role)
- Defines both the AWS services that the identity can access and what actions can be taken on that service.
    - EC2 server with permission for read and write to a specific S3 bucket, but not permission for deleting the bucket 
- Can be either customer managed or managed by AWS   
    - AWS managed policies are already created and can be used without the need to create custom policies, like:
        - Read access to an AWS account
        - Full access to S3

![Policy example](./img/policy.png)

**AWS IAM Best Practices**:
- **Multi-Factor Authentication**: provides additional security with either physical or virtual device that generates a token for a login.
- **Least Privilege Access**: users should only be granted access to AWS resources that are required for their current tasks.

### 3.2 Creating an Managing IAM Users
Demo
- Creating a new IAM user
- Configuring permissions for the IAM users
- Creating an IAM Group
- Attaching permissions to an IAM Group

### 3.3 Enabling Multi-factor Authentication
Demo:
- Enabling MFA for the root user
- Enabling MFA for an IAM user


### 3.4 Amazon Cognito

**Amazon Cognito**: A managed service that enables you to handle authentication and aspects of authorization for your custom web and mobile applications through AWS 

**Amazon Cognito**:
- is a fully managed user directory service for custom applications. IAM deals with permissions for AWS resources, but what happen if we basically want to implement something similar for our custom application. Then Cognito fill that role.
- Provides UI components to be integrated for many platforms.
    - sign in
    - sign up 
- Provides security capabilities to control account access
- Enables controlled access to AWS resources (intersection with IAM). Example
    - web app that lets users upload foto, we have to be sure that users have access to a specific part of the S3 bucket that is just for them. There is a way with **Cognito** to configure access to specific pieces of AWS infrastructure that you would want a user to have access to, but **without having them to sign up for an IAM account** 
- Can work with social and enterprise identity providers. Letting users to log in with a Google account and have that correspond to a Cognito identity.

**Cognito Identity Providers**:
- Google
- Amazon 
- Facebook 
- Microsoft Active Directory
- SAML 2.0 Providers

Cognito gives us the possibility to use this level of authentication/authorization and tie it into our custom application. 

### 3.5 Scenarios
Sylvia:
- team of DevOps
- each member needs to have the same access to the cloud system

What approach would help Sylvia manage the team's permissions? Create IAM and assign to a Group

Edward:
- the EC2 servers need to access data stored within S3 buckers
- created a user in IAM for these servers and uploaded keys to the server

Is he following best practice for this approach? Use Roles for EC2 instances

William:
- migrating to the cloud
- concerns for securing access with password to AWS resources

Additional level os Security? Two factor Authentication

## 4. Data Architectures on AWS

### 4.1 Integrating On-premise Data

- **AWS Storage Gateway**: Hybrid-cloud storage service.
    - Integrates cloud storage into the local network
    - Deployed as a VM or a specif hardware  appliance to running the Storage Gateway software on it onto our network.
    - Integrates with S3 and EBS
    - Supports three different gateways types:
        - Tape gateway:
            - Tape backup virtual experience
        - Volume gateway:
            - provides cloud based iSCSi volumes to local applications for the data actually stored in the cloud
        - File gateway
            - Stores files in S3 while providing cached low-latency local access (stores files in S3 but keeping certain files on the storage gateway device so we can have low latency access, also using local **cash** pulling certain files or the one that are most recently accessed )
- **AWS DataSync**: Automated data transfer service. Setting up a system network to send data from the local data center to AWS.
    - Leverages a **DataSync** agent deployed as a VM on our network.
    - Integrates with S3, EFS, and FSx for Windows File Server on AWS 
    - Greatly improved speed of transfer due to custom AWS protocol and optimization
    - Charged for GB of data transferred 

### 4.2 Processing Data on AWS

- **AWS Glue**: Manged Extract, Transform, and Load **ETL** Service. ETL means that we have data stored somewhere, we need to pull it out from where it is stored (Extract), then we have to transform so will have to do things like normalizing the data. Then we have the Load step, this means that we have to put the data in a different location where it will be analyzed. And this is the ELT process.
- **Amazon EMR**: Elastic Map Reduce is a big data cloud processing service
- **AWS Data Pipeline**: data workflow orchestration service across AWS services. This a service for managing how the data get from point A to point B, especially if it needs to go through a specific type of AWS service in the middle, this is where **Data Pipeline** can be very helpful.

**AWS Glue**:
- fully managed ETL (extract, transform and load) service on AWS 
- supports data in Amazon RDS, DynamoDB, Redshift, and S3
- supports a serverless model of execution ( we just use the service which handles everything)

**Amazon EMR (Elastic Map Reduce)**:
- Enables big-data processing on Amazon EC2 and S3
- Supports open-source frameworks and tools
    - Apache Spark, Flink, Hive, Hudi, HBase, Presto
- operates in a **cluster** environment without additional configuration

**AWS Data Pipeline**:
- managed ETL service on AWS
- manages data workflow through AWS services
- supports S3, EMR, Redshift, DynamoDB, and RDS
- can integrate on-premise data stores within our data pipelines.

### 4.3 Analyzing Data

**Data Analysis Services**:
- Amazon Athena: Service that enables querying of data stored in Amazon S3
- Amazon Quicksignt: Business intelligence service enabling data dashboards
- Amazon CloudSearch: managed search service for custom applications

**Amazon Athena**:d
-  Fully managed serverless service ( we don't have to configure any of the underlying infrastructure, we have just lo leverage the service )
- enables querying of large-scale data stored in Amazon S3 (Data lakes approach)
- queries are written in SQL
- charged based on the data scanned for the query


**Amazon Quicksignt**:
- fully managed business intelligence service
- enables dynamic data dashboards based on data stored in AWS
- charged on a per-user and per-session pricing model
- multiple versions provided based on needs

**Amazon CloudSearch**
- fully-managed search service on AWS
- support scaling of search infrastructure to meet demand
- charged per hour and instance type of search infrastructure
- enables developers to integrate search into custom applications


### 4.4 Integrating AI and Machine Learning

- **Amazon Rekognition**: Computer vision service powered by ML. We can get insights out of images that we have stored on the platform.
    - Fully managed image and video recognition depp learning service 
    - identifies objects in images
    - identifies objects and actions in videos
    - can detect specific people using facial analysis
    - supports custom labels for our business objects
- **Amazon Translate**: text translation service powered by ML
    - fully managed service for translation of tex
    - currently supports 54 languages
    - can perform language identification
    - works both in batch and real-time
- **Amazon Transcribe**: speech to text solution using ML
    - fully manages speech recognition service
    - recorded speech is converted into text in custom applications
    - includes a specific sub-service for medical use ( medical terms )
    - batch and real time transcription
    - 31 languages supported

### Scenarios:

Ruth:
- process large scale data set needs to be processed before analysis
- just want to define the processing

What service would be useful for her??? **AWS Glue**

Jessi:
- working to identify an approach for controlled lab access with facial recognition

Is there an AWS service that can help with this approach? **Amazon Rekognition**


Roger:
- ways to visualize the data sales
- is currently stored in Redshift(data warehouse)

What AWS service would allow this access to the data by non-technical resources? **Amazon Quicksignt**

### 5. Disaster Recovery:

**Disaster recovery**(DR) is about preparing for and recovering from a disaster. Aby event that has a negative impact on a company's business continuity or finances could be termed a disaster.This includes hardware or software failure, a network outage, a power outage, physical damage to a building like fire of flooding, human error, or some other significant event.

### 5.1 Disaster Recovery Architecture:

**Disaster Recovery Scenarios** listed in increasing Cost&Complexity and decreasing Recovery Time
- Backup and Restore
- Pilot Light
- Warm Standby
- Multi Site

![dc](./img/dr.png)

**Backup and Restore**:
- Production data is backed up into Amazon S3
- Data can be stored in either standard or archival storage classes
- EBS data can be stored as snapshots in Amazon S3 also
- In a Disaster Recovery event. a process is started to launch new environment instances 
- This approach has the longest recovery time (the time needed for being up and running another time), and has the least cost.

**Pilot Light**:
- Key infrastructure components are kept running in the cloud
- Designed to reduce the recovery time over the Backup&Restore approach
- Does incur cost of this infrastructure continually running in the cloud.
- AMIs are prepared for additional systems and can be launched quickly.

The **pilot light** method gives you a quicker recovery time then the backup-&-restore method because the **core pieces** of the system are already running and are continually kept up to date. 


**Warm Standby**: 
- A scaled-down version of the full environment is running in the cloud
- Critical systems can be running on less capable instance types
- Instance types and other systems can be up for disaster recovery event
- Does incur cost of this infrastructure continually running in the cloud

**Multi Site** (on-premise + cloud infrastructure up and running,or running in more then one region):
- full environment is running in the cloud
- utilizes instances types needed for the production not just recovery
- provides a near seamless recovery process
- incurs the most cost over the other approaches

### 5.2 Selecting a Disaster Recovery Architecture for an Organization
Values that we have to take in consideration for the decision
- **Recovery Time Objective (RTO)**
- **Recovery Point Objective (RPO)**


**Recovery Time Objective (RTO)**: the time it takes to get your system back up and running to the ideal business state after a disaster recovery event.

**Recovery Point Objective (RPO)**: the amount of data loss (in terms of time) for a production system during a disaster recovery event. Loosing data of 1 hour, after it i have to be up and running.


### Scenario:

Roger:
- several workload on AWS
- architecting the disaster recovering approach
- wants a **seamless** transition during an event

Multi Site approach


Jennifer:
- they don't have an approach
- they need to minimize cost is  more critical than minimizing RTO 

Backup&Restore


Eliza:
- they keep **few key servers** up and running in AWS in case of an event
- these servers have smaller instance types what production would need

Which disaster approach most closely matches this scenario? Pilot Light

## 6. Architecting Application on EC2

Scaling on AWS:
- **Vertical scaling**: "scaling up" our instance type to a larger instance type with additional resources
- **Horizontal scaling**: "scaling out" add additional instances to handle the demand of our application 

In the cloud Horizontal scaling is more sustainable approach than vertical scaling. In the vertical scaling we will need to to restart out instance for creating a new one with more resources. In horizontal scaling we create new copies of our original instance.

**Amazon EC2 Horizontal Scaling Service**
- **Auto Scaling Group**: set of EC2 instances with rules for scaling & management
- **Elastic Load Balancer**: distributes traffic across multiple targets

**Amazon EC2 Auto Scaling Group**
This is like one of the deployment types of kubernetes (StatefullSet, Deployment, )
- Launch template defines the instance configuration for the group (deployment yaml file)
- defines the minimum, maximum, and desired number of instances
- performs health checks on each instance
- exist within 1 ore more availability zones in a single region. We span it in multiple available zones because this adds a level of fault tolerance in case of an AZ going down. 
- works with "on-demand" and "spot" instances

**EC2 Horizontal scaling example**:
- First we have a region, and in this case this will be **"us-east-1"** 
- inside of our region we have configured a **VPC** with an **Internet gateway**. This VPC will house our custom application. 
- we have supported that across two different **Availability Zones** A and B 
- we created our **auto scaling group**, and it exists within both availability zones, and we chose to have a desire **capacity of two**. So it's going to try to keep it balanced between the different availability zones. **So it will launch one instance in Availability Zone A and one instance in Availability Zone B**.

![EC2 Horizontal Scaling example](./img/hs.png)

- Now we wanna have users be able to be routed to a server, the server that has the most room to handle their request, and so we're going to have a specific type of **ELB** called an application load balancer. That's going to be between our users and the specific servers that they're going to be accessing. Now it knows how to work effectively with the **Auto scaling group**, so it knows what instances are healthy and which ones are not. So in the beginning, all of these instances air healthy, so the **application load balancer** can route the user traffic to either of the servers. 
- However, let's say that something changes and the server that we have an availability zone A is no longer healthy. Well, the auto scaling group will note that it will let the application load balance or know that, and it will stop sending traffic to that particular server while the auto scaling group terminates that server and then goes in and actually starts a new server. Once that startup process is complete, it can communicate with the application load balancer and let it know that it is now safe to send traffic back to availability Zone A.


**AWS Secrets Manager**: 
- we need a way when scaling out to multiple servers to securely integrate things like credentials, API keys, tokens, and other secret content in a way that cant be compromised. Example are the credentials for the database, we can't store them in our public repositories.
- Secrets Manager Integrates natively with RDS, DocumentDB, and Redshift
- can auto-rotate credentials with integrated services
- enables fine-grained access control to secrets, this means that we know exactly which servers adn what applications have access to which secret values that are stored within the **Secrets Manager**


### 6.2 Controlling Access to EC2 Instances
- **Security Groups**: enables firewall-like controls for resources within the VPC
- **Network ACLs**: controls inbound and outbound traffic for subnets within the VPC
- **AWS VPN**: secure access to an entire VPC using an encrypted tunnel

**Security Groups**:
- Serve as firewall for our EC2 instances
- Control inbound and outbound traffic
- this work at the instance level, associating an EC2 group with a specific instance
- EC2 instances can belong to multiple security groups
- VPCs have a default security group
- must be explicitly associated with an EC2 instance
- ** by default all outbound traffic is allowed**, our server can send any information out to the internet.


What are **Access Control Lists**?
ACLs are a network filter utilized by routers and some switches to permit and restrict data flows into and out of network interfaces. When an ACL is configured on an interface, the network device analyzes data passing through the interface, compares it to the criteria described in the ACL, and either permits the data to flow or prohibits it.


**Network ACL**:
 - works at the subnet level within an VPC, when we define a network configuration, every server that get spun up within a sub net will adopt the ACL for that subnet
 - enables us to allow and deny traffic
 - **each VPC has a default ACL that allows all inbound and outbound traffic**
 - by default a new created custom ACLs denies all traffic until rules are added

 **AWS VPN**
 - creates an encrypted tunnel into our VPC. If we don't want our VPC to be accessed by the internet but we still want to have a way to get access to manage the servers tha are withing that VPC 
 - can be used to connect our data center or even individual client machines to our VPC
 - supports two services:
    - Site-to-site VPN
    - Client VPN

**AWS Site-to-site VPN Example**:
- So let's say that we have our own corporate data center and we have several servers 
- need to interact with some EC2 instances that we have "spun up" within our VPC on AWS. 
- we could utilize the AWS VPN service. We would create a customer gateway, and we would need to enter that information into the service. And then we would have a VPN gateway that would exist within our VPC on AWS. And once these things are in place and once they know how to communicate with one another, we then would be able to have encrypted traffic traveling back and forth between our corporate data center and eight of us. 

![VPN example](./img/vpn.png)


Now you may be asking, How is this different from **AWS Direct connect**? And that's a great question. With AWS Direct connect, you have a direct connection to the **AWS global infrastructure** that doesn't have to go over the **public Internet**. However, when you're using AWS VPN, that traffic does go over the Internet, it is just encrypted the entire way.

### 6.3 Protecting Infrastructure from Attacks

Security Services:
- **AWS Shield**: managed DDoS protection service for apps on AWS
- **Amazon Macie**: data protection service powered by machine learning
- **Amazon Inspector**: automated security assessment service for EC2 instances

**"Distributed Denial of Service (DDoS)"** is a type of attach where a server or group of servers are flooded with more traffic that they can handle in a coordinated effort to bring the system down.

**AWS Shield**:
- provides protection against DDoS attacks for apps running on AWS
- enables on-going threat detection and mitigation
- has tow different service levels:
    - standard
    - advanced

**Amazon Macie**:
- utilizes machine learning to analyze data stored in Amazon S3
- it can detect personal information and intellectual property on S3
- provides a dashboard that show how the data is being stored and accessed
- enables alerts if it detects anything unusual about data access. if will search for anomaly detection on how our data is accessed.

**Amazon Inspector**:
- enables scanning of Amazon EC2 instances for security vulnerabilities. if we wanna be sure that our EC2 instance is ready and save for the internet then we use the Inspector to check for possible vulnerabilities in our configuration
- charged by instance per assessment run
- tow types of rules packages:
    - **Network Reachability Assessment**. what is available to the internet from to our servers
    - **Host Assessment** checks the state of configuration

### 6.4 Deploying Pre-defined Solutions

Deploying Pre-defined Solutions on AWS:
- **AWS Service Catalog**: managed catalog of IT services on AWS for an organization
    -  targeted to serve as an organizational service catalog for the cloud.
    - can include single server image to multi-tier custom applications. can handle a wide variety of infrastructures needs on AWS
    - enables organizations to leverage services that meet compliance. 
    - supports a lifecycle for services released in the catalog
- **AWS Marketplace**: catalog of software to run on AWS from third-party providers
    - curated catalog of third-party solutions for customers to run AWS
    - provides AMIs, CloudFromation stacks, and SaaS based solutions
    - enables different pricing options to overcome licensing in the cloud
    - charges appear on AWS bill

### 6.5 Developer Tools

AWS Developer Services:
- **AWS CodeCommit**: manage source code repository deeply integrated with AWS
- **AWS CodeBuild**: this is a build service or a CI/CD
- **AWS CodeDeploy**: service that takes care of the deployment to different AWS services
- **AWS CodePipeline**: this service knows how to work with all of the service previously mentioned to create to create a pipeline so we can go through and look at the entire process of building testing and ultimately deploying our applications.
- **AWS CodeStar**: which gives a great way bootstrap this entire process for our custom application.


**AWS CodeCommit**:
- is a manages source control service on AWS
- utilizes git for repositories
- control access with IAM policies
- serve as an alternative to Github and Bitbucket
 

**AWS CodeBuild**:
- fully managed build and continuous integration service on AWS CI/CD 
- don't have to worry about maintaining infrastructure
- charged per minute for compute resources we utilize 
- takes care of building the application and creating the output artifacts

**AWS CodeDeploy**:
- managed deployment service for deploying our custom applications
- deploys to EC2, Fargate(container service), Lambda, and on-premise servers
- provides a dashboard for deployments in the AWS Console

**AWS CodePipeline**: 
- creates a fully managed continuous delivery service on AWS. knows how to integrate with the previous services that we mentioned above
- provides capabilities to automate building, testing, and deploying
- integrates with other developer tools as well as Github

**AWS CodeStar**: this in not like a different service, but it is like a tool to make easier the use of the other services.
- Workflow tool that automates the use of the other developer services
- Can create a complete continuos delivery toolchain for a custom application 
- Provides custom dashboards and configurations int the AWS Console
- We are charged only for the other services you leverage


### Scenarios:

Ellen: 
- made a transition to AWS
- they want to be sure each department is following best practice
- they want to create compliant IT services that other departments can use

What service would you recommend? AWS Service Catalog, services for use in the organization. Instead MarketPlace would be for third party services that can be launch in AWS

Tim: 
- AWS for multiple workloads
- they had downtime due to one of their application failing on EC2
- Tim has to avoid downtime if an instance stop responding

What approach would you recommend to Tim? Horizontal Scaling this means EC2 auto scaling Group alongside an Elastic Load Balancer 

Jane:
- sensitive information from the users
- reasonable policies in place for data stored in S3
- Jane is worried if some of those policies accidentally get changed could lead to a potential data breach
- she is worried of a breach going unnoticed

Macie in the way to use ML to classify the data, find the sensitive ones and monitor that data and its access patterns and can proactively alert them if it sees any anomaly happening within any of these patterns


## Exam Part #########################################


