# [Fundamental Cloud Concepts for AWS](https://app.pluralsight.com/library/courses/fundamental-cloud-concepts-aws/table-of-contents)
This course will provide an introduction to cloud computing on AWS as well covering cloud fundamentals, which is the first step toward the knowledge needed for the **AWS Certified Cloud Practitioner** exam.

Topics:
- The concept of cloud computing
- Organization of AWS global infrastructure
- Economics of cloud computing
- Tools and services that AWS provides to support infrastructures running in their cloud.

## 2. Understanding Cloud Computing
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