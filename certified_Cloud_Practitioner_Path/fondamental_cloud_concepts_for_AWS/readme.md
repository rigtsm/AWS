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
