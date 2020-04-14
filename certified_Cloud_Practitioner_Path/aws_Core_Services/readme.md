# [Understanding AWS Core Services](https://app.pluralsight.com/library/courses/understanding-aws-core-services/table-of-contents)
from pluralsignt.com for AWS Certified Cloud Practitioner Path.

## 2. Interacting with AWS
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

### 3.1 Amazon EC2 Overview
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
-Pricing is based on the instance type
- Some Instance types have unique capabilities (specialized storage, gpu)

Example of EC2 Instance Type Pricing:
- t3.medium
- m5.large
- c5d.24xlarge
- p3.16xlarge
- i3.16xlarger

**Root Device Type**
- Instance Storage: ephemeral storage that is physically attached to the host the virtual server is running on. If we shutdown the instance then the data will be lost. 
- **Elastic Block Store** (EBS): persistent storage that exists separately from the host the virtual server is running on. The data wil be persistent during time and shutdowns.

**Amazon Machine Image (AMI)**: 
- Template for an EC" instance including configuration, operating system, and data
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
- When you request instances, if you bid is higher than Spot price they the instance is assigned to the highest bidder and the workload will be launched.
- If the Spot price grows to exceed your bid, the instances will be terminated
- Spot instances can be notified 2 minutes prior to termination.

Spot Instances are very good for workload that can start and stop. 

Amazon EC2 Purchase Options:
- If I have an instance that is **consistent** (run for at least 3 years, same requirements) and always needed, I should purchase a **Reserved Instance**
- If we have **batch** processing where the process can **start and stop** without affecting the job, i shot leverage **Spot Instances** 
- If I have an **inconsistent** need for instances that cannot be stopped without effecting the job, leverage **On-Demand Instances**.

### 3.3 Launching EC2 Instances with AWS Console
EC2 > scroll down and > Launch Instance > Choose AMI (Free Tier) > **t2.micro** (Free tier Instance Type) > Next: Configure Instance Details

Set the Auto-assign Public Ip to "Enable" so we can access our instance form the internet.
To the section Advance Details we can insert commands that the server will execute when it starts. In this case is installa web server and run it

    #!/bin/bash
    yum install httpd -y
    service httpd start

then we go > Next: Add Storage > Next: Add Tags in the way to control charges > Next: Configure Security Group changing the "Source ip" access to "My Ip" (curl ifconfig.me). In this case only my ip address can SSH this EC2 instance.
I will be adding a rule for allowing http traffic on port 80 > Review and Launch

We can check the state of our instance at EC2 Dashboard. Under Public DNS we can find the link to access our instance and check if the web server is working.

To destroy an instance we go Actions > Instance State > Terminate





