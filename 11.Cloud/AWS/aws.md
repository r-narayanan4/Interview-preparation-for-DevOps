# AWS Cloud Practitioner CheatSheets - Questions and Answers

## 1. What is cloud computing?

**Question:** Define cloud computing.
**Answer:** Cloud computing refers to the delivery of computing services over the internet, including storage, databases, networking, software, analytics, and more. It offers faster innovation, flexible resources, and economies of scale, typically with pay-as-you-go pricing.

## 2. What are the three types of cloud computing mentioned in the cheat sheet, and what are their primary focuses?

**Question:** Name and describe the three types of cloud computing.
**Answer:**

- SaaS (Software as a Service) focuses on providing completed products managed by the service provider.
- PaaS (Platform as a Service) focuses on removing the need to manage underlying infrastructure for developers.
- IaaS (Infrastructure as a Service) focuses on providing basic building blocks for cloud IT for administrators.

## 3. Explain the six advantages and benefits of cloud computing outlined in the cheat sheet.

**Question:** List and briefly explain the six advantages of cloud computing.
**Answer:**

- Trade capital expense for variable expense
- Benefit from massive economies of scale
- Stop guessing capacity
- Increase speed and agility
- Stop spending money on running and maintaining data centers
- Go global in minutes

## 4. What is AWS Global Infrastructure, and what are its main components?

**Question:** Define AWS Global Infrastructure and list its main components.
**Answer:**

- Regions: Physical locations with multiple Availability Zones (AZs).
- Availability Zones (AZs): Discrete data centers within regions.
- Edge Locations: Datacenters owned by trusted partners for low-latency access.


## 5. What are the three main Cloud Computing Deployment Models mentioned in the cheat sheet?

**Question:** Name and describe the three main Cloud Computing Deployment Models.
**Answer:**

- Cloud: Fully utilizing cloud computing.
- Hybrid: Using both Cloud and On-Premise resources.
- On-Premise: Deploying resources on-premises, sometimes referred to as "private cloud."

## 6. Describe AWS Compliance Programs and provide examples mentioned in the cheat sheet.

**Question:** Explain AWS Compliance Programs and provide examples.
**Answer:**
AWS Compliance Programs are internal policies and procedures to comply with laws and regulations. Examples include HIPAA, PCI DSS, FIPS, and NIST 800-53.

## 7. What is the Shared Responsibility Model in AWS, and what are the responsibilities of customers and AWS?

**Question:** Explain the Shared Responsibility Model in AWS and the responsibilities of customers and AWS.
**Answer:**
The Shared Responsibility Model describes who is responsible for what:

- Customer Responsibility "In" the Cloud: Data, code, and configuration of services.
- AWS Responsibility "Of" the Cloud: Physical hardware, global infrastructure, and operation of managed services.

## 8. Name some of the security services provided by AWS, as mentioned in the cheat sheet.

**Question:** List some security services provided by AWS.
**Answer:**
Some security services provided by AWS include AWS Identity and Access Management (IAM), AWS Artifact, AWS Inspector, AWS Shield, and AWS Web Application Firewall (WAF).

## 9. What are some of the database services provided by AWS mentioned in the cheat sheet?

**Question:** Name some database services provided by AWS.
**Answer:**
Database services provided by AWS include DynamoDB, DocumentDB, RDS (Relational Database Service), Aurora, Neptune, and Redshift.


## 10. What are some of the networking services provided by AWS, as mentioned in the cheat sheet?

**Question:** List some of the networking services provided by AWS.
**Answer:**
Networking services provided by AWS include VPC (Virtual Private Cloud), Internet Gateway, Route Tables, NACLs (Network Access Control Lists), Security Groups (SGs), and Subnets.

## 11. What are the key organizational features mentioned in the cheat sheet for managing multiple AWS accounts?

**Question:** What are the key organizational features for managing multiple AWS accounts?
**Answer:**
Key organizational features include Organizations, Root Account User, Organization Units, and Service Control Policies (SCPs).

## 12. Name some provisioning services provided by AWS, as mentioned in the cheat sheet.

**Question:** Name some provisioning services provided by AWS.
**Answer:**
Provisioning services provided by AWS include Elastic Beanstalk, AWS OpsWorks, AWS CloudFormation, AWS QuickStart, and AWS Marketplace.

## 13. What are some of the storage services provided by AWS, as mentioned in the cheat sheet?

**Question:** List some storage services provided by AWS.
**Answer:**
Storage services provided by AWS include S3 (Simple Storage Service), S3 Glacier, Storage Gateway, EBS (Elastic Block Storage), EFS (Elastic File Storage), Snowball, and Snowmobile.

## 14. Name some logging services provided by AWS, as mentioned in the cheat sheet.

**Question:** Name some logging services provided by AWS.
**Answer:**
Logging services provided by AWS include CloudTrail and CloudWatch, which includes CloudWatch Logs, CloudWatch Metrics, CloudWatch Events, CloudWatch Alarms, and CloudWatch Dashboard.


## 15. What are some of the computing services provided by AWS, as mentioned in the cheat sheet?

**Question:** List some computing services provided by AWS.
**Answer:**
Computing services provided by AWS include EC2 (Elastic Compute Cloud), ECS (Elastic Container Service), Fargate, EKS (Elastic Kubernetes Service), Lambda, Elastic Beanstalk, and AWS Batch.

## 16. What are some of the enterprise integration services provided by AWS, as mentioned in the cheat sheet?

**Question:** Name some enterprise integration services provided by AWS.
**Answer:**
Enterprise integration services provided by AWS include Direct Connect, AWS VPN, Storage Gateway, and Active Directory.

## 17. Name some business-centric services provided by AWS, as mentioned in the cheat sheet.

**Question:** Name some business-centric services provided by AWS.
**Answer:**
Business-centric services provided by AWS include Amazon Connect, WorkSpaces, WorkDocs, Chime, WorkMail, Pinpoint, and SES (Simple Email Service).

## 18. What are some application integration services provided by AWS, as mentioned in the cheat sheet?

**Question:** List some application integration services provided by AWS.
**Answer:**
Application integration services provided by AWS include Simple Notification Service (SNS), Simple Queue Service (SQS), Step Functions, EventBridge, Kinesis, Amazon MQ, and Managed Kafka Service (MKS).

## 19. What do the initialisms ELB, ALB, and NLB stand for in AWS, as mentioned in the cheat sheet?

**Question:** Expand the initialisms ELB, ALB, and NLB as used in AWS.
**Answer:**

- ELB stands for Elastic Load Balancer.
- ALB stands for Application Load Balancer.
- NLB stands for Network Load Balancer.

## 20. What are some of the key features of AWS billing and pricing, as mentioned in the cheat sheet?

**Question:** List some key features of AWS billing and pricing.
**Answer:**
Key features of AWS billing and pricing include AWS Marketplace, Savings Plans, Consolidated Billing, AWS Cost Explorer, AWS Budgets, TCO Calculator, Resource Groups and Tagging, AWS Cost and Usage Reports, and Free Tier for certain services.


## 21. What is the difference between horizontal and vertical scaling? Explain the concepts of scale in, scale out, scale up, and scale down.

**Question:** Explain the difference between horizontal and vertical scaling. Define the concepts of scale in, scale out, scale up, and scale down.
**Answer:** 

- Horizontal scaling, also known as scaling out, involves adding more machines or instances to your pool of resources to handle increased load. It distributes the workload across multiple machines, which can help improve performance and redundancy.
- Vertical scaling, also known as scaling up, involves increasing the resources (such as CPU, memory, or storage) of a single machine or instance to handle increased load. This typically involves upgrading the hardware specifications of the machine.
- Scale in refers to the process of reducing the number of machines or instances in your pool of resources. It is typically done to optimize resource usage and reduce costs during periods of low demand.
- Scale out refers to the process of adding more machines or instances to your pool of resources. It is done to accommodate increased demand and distribute the workload across multiple machines for better performance and redundancy.
- Scale up refers to the process of increasing the resources (such as CPU, memory, or storage) of a single machine or instance. It is done to handle increased load and improve the performance of individual instances.
- Scale down refers to the process of reducing the resources (such as CPU, memory, or storage) of a single machine or instance. It is typically done to optimize resource usage and reduce costs during periods of low demand.


## 22. What is the difference between Security Groups (SGs) and Network Access Control Lists (NACLs)?

**Question:** Explain the difference between Security Groups (SGs) and Network Access Control Lists (NACLs).
**Answer:** 

- Security Groups (SGs) act as a firewall at the instance level. They control traffic based on security rules associated with individual instances. SGs are stateful, meaning they keep track of the state of a connection.
- Network Access Control Lists (NACLs) act as a firewall at the subnet level. They control traffic in and out of subnets based on specified rules. NACLs are stateless, meaning they do not keep track of the state of a connection.

## 23. What is the difference between stateless and stateful?

**Question:** Define the terms stateless and stateful.
**Answer:** 

- Stateless: In a stateless system, each transaction is independent and self-contained. The system does not retain any information or state about past transactions. Each request is processed as if it were the first one. Stateless systems are often more scalable and fault-tolerant.
- Stateful: In a stateful system, the system retains information or state about past interactions or transactions. It remembers the context or history of interactions with a user or client. Stateful systems can provide more personalized experiences but may be less scalable and more complex to manage.


Click below for remaining questions

[Remaining Questions](https://github.com/iam-veeramalla/aws-devops-zero-to-hero/tree/main/interview-questions)
