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
 Building knowing that failure can happen in anytime on our architecture.

 **Reliability on AWS**: 
 - **Fault Tolerance**: being able to support the failure of components within your architecture
-  **Hight Availability**: keeping our entire solution running in the expected manner despite issues that may occur.

Building Solutions on AWS: 
- Most managed AWS services provide high-availability out of the box 
- when building solutions directly on EC2 fault tolerance must be architectured. For solutions that are IaaS, this is where we have to consider fault tolerance and we will have to figure out how to built into our custom solutions
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


### Scenarios

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








 





