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
 










