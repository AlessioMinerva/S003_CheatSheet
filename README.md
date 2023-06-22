# S003_CheatSheet
S003_CheatSheet with key concepts for the AWS exam


# AWS Essentials Cheat Sheet

This cheat sheet provides a concise overview of key concepts and services covered in the AWS Essentials course. Use it as a quick reference to reinforce your understanding.

## Building Blocks of AWS

- **Region**: Physical location comprising 2 or more Availability Zones.
- **Availability Zone**: Discrete data center(s) with redundant power, networking, and connectivity.
- **Edge Locations**: Endpoints for caching content, closer to users. Includes CloudFront and more numerous than Regions.

## Shared Responsibility Model

- You're responsible for tasks you can perform in the AWS Management Console, such as security groups, user creation, and EC2 patching.
- AWS takes care of tasks you can't perform, including data center management, security cameras, cabling, and patching RDS or operating systems.

## Key AWS Services

### Compute
- EC2: Elastic Compute Cloud for scalable virtual servers.
- Lambda: Serverless compute service for executing code without managing infrastructure.
- Elastic Beanstalk: Platform as a Service (PaaS) for deploying and managing applications.

### Storage
- S3: Simple Storage Service for object storage in the cloud.
- EBS: Elastic Block Store for persistent block-level storage volumes.
- EFS: Elastic File System for scalable, fully managed file storage.
- FSx: Fully managed file systems for Windows-based workloads.
- Storage Gateway: Hybrid cloud storage integration service.

### Databases
- RDS: Relational Database Service for managed relational databases.
- DynamoDB: Fully managed NoSQL database for low-latency, scalable applications.
- Redshift: Fully managed data warehousing solution for analytics.

### Networking
- VPCs: Virtual Private Clouds for logically isolated network environments.
- Direct Connect: Dedicated network connection between on-premises and AWS.
- Route 53: Scalable domain name system (DNS) web service.
- API Gateway: Fully managed service for creating, deploying, and managing APIs.
- AWS Global Accelerator: Improves availability and performance of applications with automatic global routing.

## Well-Architected Framework

Read the Well-Architected Framework whitepaper before taking the exam, after completing the course. It provides valuable guidance on building and operating reliable, secure, efficient, and cost-effective systems on AWS.

# IAM Exam Tips Cheat Sheet

This README provides essential tips and key points to remember for the IAM (Identity Access Management) exam. Use this cheat sheet as a quick reference to enhance your exam preparation.

## 1. Securing the Root Account
- Enable multi-factor authentication for the root account.
- Create an administrator group with appropriate permissions.
- Generate user accounts for administrators and add them to the administrator group.

## 2. IAM Policy Documents
- Utilize JSON-based policy documents to assign permissions.
- Grant full admin access with "Effect: Allow" and wildcard actions.
- Interpret policy documents and consult documentation for better understanding.

## 3. Important IAM Points for the Exam
- IAM is universal and not specific to any region.
- The root account possesses complete administrator access; secure it promptly.
- New user accounts have no permissions initially; assign them to groups or use policy documents.
- Access keys and secret access keys are intended for programmatic access, not as username/password.
- Store access keys and passwords securely and implement password rotation policies.
- IAM federation enables integration of existing user accounts with AWS using SAML (e.g., Active Directory).

## 4. Next Section: S3 (Simple Storage Service)
- Dive into an in-depth exploration of S3 in the upcoming section.
- S3 is one of the oldest and frequently covered AWS services in the exam.
- Learning S3 is straightforward and enjoyable.

# S3 Cheat Sheet

![S3 Logo](s3-logo.png)

Welcome to the S3 Cheat Sheet! This guide provides a concise summary of essential information about Amazon S3 (Simple Storage Service). Whether you're studying for an exam or need a quick reference, this cheat sheet has got you covered. Let's dive in!

## 1. S3 Basics
- Object-based storage for cloud file uploads and storage.
- Not suitable for operating systems or databases.
- Supports files up to 5 terabytes in size.
- Unlimited storage capacity and objects within S3.
- Files are organized in buckets with a universal namespace.

## 2. Object Structure
- **Key**: Object name or file name.
- **Value**: Data content represented as bytes.
- **Version ID**: Enables multiple versions of an object.
- **Metadata**: Additional information about stored objects (e.g., content type, modification date).

## 3. Securing S3 Buckets
- S3 buckets are private by default.
- Use **object ACLs** for granular object-level access control.
- Apply **bucket policies** for broader bucket-wide access control.
- Host static websites with S3 using bucket policies.

## 4. Storage Tiers
- **S3 Standard**: Suitable for most workloads and applications.
- **S3 Standard Infrequent Access**: Long-term, infrequently accessed critical data.
- **S3 One Zone-Infrequent Access**: Long-term, infrequently accessed non-critical data (single availability zone).
- **Glacier and Glacier Deep Archive**: Long-term archival with varying retrieval times.
- **S3 Intelligent-Tiering**: Machine learning-based tiering for unpredictable access patterns.

## 5. Lifecycle Management
- Automate object movement between storage tiers.
- Works seamlessly with versioning and applies to current and previous object versions.

## 6. S3 Object Lock
- **Write once, read many (WORM) model** for secure object storage.
- Available in **governance mode** and **compliance mode**.
- Provides added security and prevents unauthorized modifications.

## 7. Encryption with S3
- **Encryption in Transit**: Use SSL or HTTPS when sending data to S3.
- **Server-Side Encryption (SSE)**: AES 256-bit encryption handled by S3 or Key Management Service (KMS).
- **Client-Side Encryption**: Encrypt files before uploading to S3.
- Encryption enforcement possible with bucket policies.

## 8. Performance Optimization
- Use **prefixes** (folders/subfolders) to improve performance.
- SSE with KMS has built-in limits for requests per second.
- **Multipart uploads** for large files (over 100 MB) or files over 5 GB.
- **S3 byte-range fetches** for faster file downloads.

## 9. S3 Replication
- Replicate objects between buckets (same or different regions).
- Objects in existing buckets aren't replicated automatically.
- **Replicate delete markers** with an option for comprehensive replication.

Congratulations on mastering the S3 section! Get ready for the next exciting topic on EC2, where you'll learn about provisioning virtual machines in the AWS Cloud. Good luck!

For more detailed information, check out the [official Amazon S3 documentation](https://docs.aws.amazon.com/s3/).

# EC2 Exam Tips Cheat Sheet

Welcome to the EC2 Exam Tips Cheat Sheet! This guide provides a concise overview of key concepts and tips to help you prepare for your EC2 exam.

## Overview

1. EC2 Basics:
   - EC2 is a virtual machine hosted on AWS.
   - Offers flexible capacity provisioning and pay-as-you-go pricing.
   - Provisioning instances is quick and cost-effective.

2. Pricing Options:
   - On-Demand: Pay by the second or hour for flexible usage.
   - Spot: Purchase unused capacity at discounted rates.
   - Reserved: Reserve capacity for 1-3 years with upfront payment and significant discounts.
   - Dedicated: Physical EC2 server for exclusive use, ideal for compliance or license requirements.

3. AWS CLI:
   - Grant users least privilege access.
   - Utilize IAM groups for permission management.
   - Protect secret access keys and prefer role-based access.
   - Control permissions with policies.

4. Security Groups:
   - Immediate application of changes to security groups.
   - Manage multiple EC2 instances within a security group.
   - Default inbound traffic block, outbound traffic allowed.

5. Bootstrap Scripts and User Data:
   - Bootstrap scripts run at instance startup with administrative privileges.
   - User data supports metadata retrieval.
   
6. Networking with EC2:
   - ENI (Elastic Network Interface): Basic networking for separate networks at low cost.
   - Enhanced Networking: High-speed, reliable throughput.
   - EFAs (Elastic Fabric Adapter): High-performance computing and machine learning applications.

7. Placement Groups:
   - Cluster Placement Group: Low latency, high throughput for high-performance computing.
   - Spread Placement Group: Critical instances distributed across different hardware.
   - Partition Placement Group: Multiple instances for HDFS, HBase, and Cassandra.

8. Dedicated Hosts:
   - Dedicated physical servers for exclusive use.
   - Suitable for special licensing or compliance requirements.

9. Spot Instances and Spot Fleets:
   - Spot Instances offer significant cost savings compared to On-Demand Instances.
   - Use Spot block to prevent Spot Instances from terminating.
   - Spot Fleets combine Spot Instances and On-Demand Instances.

10. vCenter on AWS and AWS Outposts:
   - Deploy vCenter on AWS for private VMware cloud extension.
   - AWS Outposts bring AWS services to your data center.

Remember these key points as you prepare for your EC2 exam. Best of luck!

*[EC2]: Elastic Compute Cloud
*[CLI]: Command Line Interface
*[IAM]: Identity and Access Management
*[ENI]: Elastic Network Interface
*[EFA]: Elastic Fabric Adapter
*[HDFS]: Hadoop Distributed File System
*[HBase]: Hadoop Database
*[AWS]: Amazon Web Services

## EBS Cheat Sheet

This cheat sheet provides an overview of Amazon Elastic Block Store (EBS) and its key features and options. Use it as a quick reference guide for your EBS exam preparation.

### EBS Volume Types

1. SSD Volumes:
   - **gp2**: General purpose SSD for boot disks and general applications.
   - **gp3**: High-performance SSD with predictable baseline performance.
   - **io1**: Provisioned IOPS SSD for online transaction processing.
   - **io2**: Latest generation provisioned IOPS SSD with best durability.

2. Magnetic Storage:
   - **Throughput optimized HDD**: Suitable for big data and data warehouses.
   - **sc1**: Lowest-cost volume for less frequently accessed data.

### Volume and Snapshot Tips

- Volumes exist on EBS, snapshots exist on S3.
- Snapshots are incremental, shareable between accounts and regions.
- EBS volumes can be resized and changed to different types.

### EBS vs. Instance Store

- EBS volumes retain data on reboot, while instance store volumes don't.
- EBS-backed instances can be stopped without data loss.
- AMIs are blueprints for EC2 instances.

### Encrypted Volumes

- Data-at-rest and data-in-flight are encrypted.
- Unencrypted root device volumes can be encrypted using snapshots and AMIs.

### EC2 Hibernation

- Preserves in-memory RAM on persistent storage for faster boot-up.
- Available for specific instance families and operating systems.
- Instances cannot be hibernated for more than 60 days.

### EFS (Elastic File System)

- Network file system for highly distributed and resistant storage for Linux instances.
- Automatically adjusts storage capacity as files are added.

### Storage Options

- **S3**: Serverless object storage.
- **Glacier**: Archive storage.
- **FSx for Windows**: Centralized storage for Windows-based applications.
- **FSx for Lustre**: High-speed, high-capacity distributed storage.
- **EBS Volumes**: Persistent storage for EC2 instances.
- **Instance Store**: Ephemeral storage for EC2 instances.

### AWS Backup

- Centralized control for backing up AWS services.
- Supports EC2, EBS, EFS, FSx, Storage Gateway.
- Offers automation, lifecycle policies, encryption, and compliance.

For more details, refer to the full documentation of AWS Elastic Block Store.

# Database Exam Tips Cheat Sheet

Welcome to the Database Exam Tips Cheat Sheet!

This cheat sheet provides essential information for your database exam preparation. Whether you're reviewing for an exam or refreshing your knowledge, these key points will help you navigate the world of databases.

## RDS (Relational Database Service)

- RDS supports a wide range of database types, including SQL Server, Oracle, MySQL, PostgreSQL, MariaDB, and Amazon Aurora.
- Use RDS for online transaction processing workloads, such as customer orders, banking transactions, payments, and booking systems.
- For online analytics processing and data warehousing, consider leveraging Redshift.

## Read Replicas and Multi-AZ

- Read Replicas are ideal for scaling read performance and reducing load on the primary database.
- Multiple read replicas are supported (up to 5 for various database engines).
- Multi-AZ provides disaster recovery capabilities by maintaining an exact copy of the production database in a separate Availability Zone.
- Read replicas are suitable for read-heavy workloads, while Multi-AZ ensures high availability during a disaster.

## Amazon Aurora

- Aurora is Amazon's proprietary database, offering compatibility with MySQL and PostgreSQL.
- Aurora ensures data redundancy with two copies of data in each Availability Zone (minimum of 3 AZs).
- It supports different replica types: Aurora replicas, MySQL replicas, and PostgreSQL replicas.
- Automated failover is available exclusively with Aurora replicas.
- Aurora has automated backups enabled by default and allows snapshot sharing with other AWS accounts.
- Consider Aurora Serverless for cost-effective solutions with intermittent or unpredictable workloads.

## DynamoDB

- DynamoDB utilizes SSD storage and is distributed across three geographically distinct data centers.
- It offers both eventually consistent and strongly consistent reads, providing flexibility based on your application's needs.
- DynamoDB transactions ensure atomicity, consistency, isolation, and durability (ACID) across one or more tables.
- Back up and restore your DynamoDB database at any time without impacting table performance.
- Leverage point-in-time recovery to restore your database to any specific point within the last 35 days.
- DynamoDB Streams provides time-ordered sequences of item-level changes, offering valuable insights into data modifications.
- Global tables enable multi-master, multi-region replication for disaster recovery and improved availability.

## Amazon DocumentDB and Other Databases

- Migrating MongoDB workloads to AWS? Amazon DocumentDB is the solution you're looking for.
- AWS Keyspaces facilitates the migration of big data Cassandra clusters.
- Neptune is a powerful graph database primarily designed for graph-related scenarios.
- QLDB (Quantum Ledger Database) is an immutable database technology that ensures data integrity.
- Timestream is specifically designed for storing and analyzing time-series data.


# VPC Networking Exam Tips Cheat Sheet

Congratulations on completing the VPC section of the course! This cheat sheet provides a concise summary of key points to help you prepare for your exam.

## Key Topics Covered:

- **VPC**: Visualize it as a logical data center within AWS, comprising internet gateways, virtual private gateways, route tables, network access control lists (ACLs), subnets, and security groups.

- **Subnets**: Each subnet is tied to a specific Availability Zone and cannot span multiple zones.

- **NAT Gateways**: Redundant within Availability Zones, offering 5Gb/s to 45Gb/s throughput. No need for OS patching or security group association. NAT gateways receive automatic public IP assignment.

- **High Availability for NAT Gateways**: Ensure availability across multiple Availability Zones by creating NAT gateways in each zone and configuring routing.

- **Security Groups**: Stateful groups that allow response traffic regardless of inbound rules. Responses to permitted inbound traffic can flow out regardless of outbound rules.

- **Network ACLs**: Default VPCs have an all-traffic-allowed default ACL. Custom ACLs require explicit rule configuration, are stateless, and have separate inbound and outbound rules.

- **Direct Connect**: Establishes a direct, stable, and high-throughput connection between your data center and AWS.

- **VPC Endpoints**: Enable connectivity to AWS services without leaving the Amazon internal network. Two types available: interface endpoints and gateway endpoints.

- **Peering**: Connects VPCs using private IP addresses in a hub-and-spoke model. No transitive peering allowed. Peering works within the same account or between different accounts and regions.

- **AWS PrivateLink**: Connects multiple customer VPCs without VPC peering. Requires a network load balancer on the service VPC and an Elastic Network Interface (ENI) on the customer VPC.

- **Transit Gateway**: Simplifies network topology by facilitating communication between VPCs, Direct Connect, and VPN connections. Supports IP multicast.

- **VPN Hub**: Simplifies VPN network topology by establishing communication between offices or locations through a central VPN hub.

- **AWS Wavelength**: Enables mobile edge computing and enhances application speed at the edge, particularly for 5G scenarios.

## Exam Preparation Tip:

Challenge yourself to build a VPC from memory before the exam to reinforce your knowledge.

Great job on completing this section! If you have any questions, feel free to ask or proceed to the next section. Good luck!

# Route 53 Cheat Sheet

A concise summary of Route 53 concepts for quick reference.

## Alias Record vs. CNAME

- **Alias Record**: Translates naked or sub domain names to AWS resources (e.g., Elastic Load Balancer, S3 bucket).
- **CNAME**: Translates sub domain names only.

## Common DNS Record Types

- **SOA**: Defines the authoritative DNS server for a domain.
- **CNAME**: Translates sub domain names.
- **NS Records**: Specifies name servers for a domain.
- **A Records**: Translates web addresses into IP addresses.

## Routing Policies

- **Simple Routing**: Returns multiple IP addresses randomly. No health checks.
- **Weighted Routing**: Directs traffic based on weightings for different regions or availability zones.
- **Latency Based Routing**: Routes users to the region with the lowest latency.
- **Failover Routing**: Automatically switches traffic based on health checks.
- **Geolocation Routing**: Routes users to specific web servers based on geographic location.
- **Geoproximity Routing**: Routes traffic based on users' and resources' geographic location, with optional biases.
- **Multivalue Answer Routing**: Routes traffic to healthy instances if one record fails the health check.

## Domain Registration

- Domain names can be purchased directly from AWS and may take up to 3 days to register.

## Health Checks

- Set health checks on individual record sets.
- Failed health checks result in the temporary removal of the record set.
- SNS notifications can be configured for failed health checks.

# ELB Exam Tips Cheat Sheet

A concise and visually appealing cheat sheet for studying Elastic Load Balancer (ELB) concepts:

## Elastic Load Balancer Types

- **Application Load Balancers (ALB)**: Operate at Layer 7, supporting HTTP and HTTPS. Utilize listeners, rules, and target groups.
- **Network Load Balancers (NLB)**: High-performance Layer 4 balancers for non-supported protocols. Require certificate installation.
- **Classic Load Balancers (CLB)**: Operate between Layer 4 and Layer 7, troubleshoot 504 errors.

## Application Load Balancers (ALB)

- Listeners handle connection requests on ports 80 or 443.
- Rules prioritize, act, and conditionally route requests.
- Target groups direct requests to registered targets using protocols and ports.
- Limited to HTTP and HTTPS, SSL/TLS certificates are necessary for HTTPS.
- Sticky sessions available at target group level.

## Network Load Balancers (NLB)

- Layer 4 balancers for high-performance needs.
- Support non-supported protocols, require SSL/TLS certificate installation.
- Decrypt traffic for inspection.

## Classic Load Balancers (CLB)

- Troubleshoot 504 errors for gateway timeouts.
- X-Forwarded-For header provides end user's IPv4 address.
- Sticky sessions maintain user connection to EC2 instances.
- Disable sticky sessions to prevent directing traffic to removed instances.
- Deregistration delay/connection draining maintains existing connections for unhealthy instances.

# Monitoring Exam Tips Cheat Sheet

A concise and organized cheat sheet for studying monitoring concepts for exams:

## Exam Preparation Tips

1. **Best Monitoring Tool**: Determine whether an AWS service or a third-party tool is the optimal choice based on your use case and specific keywords.
2. **Custom Metrics**: Identify metrics that are not available by default and learn how to create custom metrics.
3. **Log Management**: Understand where to find logs, whether stored in log streams and groups or centralized in S3 buckets (e.g., CloudTrail logs).
4. **Alarm Threshold**: Consider adjusting alarm thresholds for scenarios like improper auto-scaling of EC2 instances.

## CloudWatch Overview

- **Alarm Management**: CloudWatch is the primary tool for managing alarms, allowing you to trigger actions or alerts using services like SNS.
- **AWS Standards**: AWS Config is recommended for monitoring AWS resource changes, while CloudWatch focuses on alarms.
- **Monitoring Intervals**: Standard metrics are delivered every 5 minutes, while detailed monitoring provides data every 1 minute (non-standard).

## Application Monitoring with CloudWatch Logs

- **Logging Service**: CloudWatch Logs is the go-to service for logging, supporting integration with EC2, on-premise, RDS, Lambda, and CloudTrail.
- **CloudWatch Logs Insights**: Consider CloudWatch Logs Insights for SQL-related logs and queries.
- **Real-Time Logging**: For real-time logging, prefer Amazon Kinesis over CloudWatch Logs.
- **Kinesis for Real-Time**: Kinesis is ideal for real-time data and will be covered in the big data section.

## Visualizing Data and Monitoring Containers at Scale

- **Grafana**: Use Grafana for visualizing container metrics effectively, especially in scenarios involving AWS Managed Services for container/IoT metric correlation and visualization.
- **Amazon Managed Service for Prometheus**: Leverage this service for large-scale monitoring of Kubernetes-based metrics, whether using Amazon EKS or self-managed clusters.
- **Managed Services**: Both Grafana and Amazon Managed Service for Prometheus are fully managed by AWS, providing scalability and high availability.

# High Availability and Scaling Exam Tips

Welcome to the High Availability and Scaling Exam Tips README page! This guide aims to provide you with valuable insights to excel in your AWS exams. Let's dive right in:

## Four Important Questions

When faced with scaling and high availability questions, ask yourself these four crucial questions:

1. Is the solution highly available? Prioritize high availability unless stated otherwise explicitly.
2. Should the scaling be horizontal or vertical? Horizontal scaling is generally preferred for increased availability.
3. Is the scaling solution cost-effective? Evaluate the cost and suitability of the solution.
4. Can switching the database solve the problem? Consider database migration as a simple option in the AWS exam context.

## Auto Scaling Tips

Here are some tips to master auto scaling concepts:

- Auto scaling is specifically designed for EC2 instances, not other services.
- Opt for answers that proactively handle the workload, anticipating predictable patterns.
- Accelerate provisioning by baking dependencies and code into AMIs.
- Enhance high availability by distributing resources across multiple availability zones.
- For legacy instances that can't have more than one online simultaneously, utilize a steady state group with a capacity of 1.
- Leverage load balancers in conjunction with auto scaling groups for efficient traffic distribution and health checks.

## Database Scaling Tips

Take note of these scaling tips specifically for databases:

- RDS: Scaling options encompass vertical scaling (resizing the instance), scaling out with additional storage, and horizontal scaling via read replicas.
- DynamoDB: Use auto scaling for consistent access patterns and on-demand provisioning for unpredictable workloads.

# Decoupling Workflows Exam Tips Cheat Sheet

Welcome to the Decoupling Workflows Exam Tips Cheat Sheet! This concise guide will help you reinforce important concepts for the exam.

## Key Questions to Ask Yourself

1. Workload Type:
   - Determine if the workloads are synchronous or asynchronous.
   - Choose the appropriate decoupling method: Pub/Sub or step functions.
   - Consider the order of messages and use FIFO SQS queues when necessary.
   - Assess the type of application load that will be encountered.

## Tips for Amazon SQS

- Beware of message duplication in SQS standard queues.
- Note that queues are unidirectional, requiring a second queue for producer communication.
- Familiarize yourself with default settings like visibility timeout and message persistence limit.
- Utilize SQS FIFO queues for strict message ordering.

## Insights for Amazon SNS and API Gateway

- Leverage SNS for proactive notifications, including email and push-based notifications.
- Combine SNS with CloudWatch for efficient alarm notifications.
- Utilize API Gateway as a secure front door for external communication.

## Recommendations for AWS Batch

- Opt for AWS Batch when dealing with long-running batched workloads (exceeding 15 minutes).
- Consider AWS Batch for batch workload queues and as an alternative to Lambda.

## Key Points about Amazon MQ

- Amazon MQ is a managed messaging broker service supporting RabbitMQ or ActiveMQ.
- Look for mentions of specific messaging protocols like JMS.
- Amazon MQ is an excellent choice when SNS/SQS cannot handle the required messaging protocols.

## Insights for Step Functions

- Step Functions provide serverless orchestration of AWS services.
- Use Step Functions for workflow decision requirements, conditional checks, failure handling, and wait periods.

## Recommendations for Amazon AppFlow

- Amazon AppFlow facilitates simplified data ingestion between third-party SaaS applications and AWS services.
- It supports bi-directional data flow and often involves Amazon S3 for storing data.


## Big Data Exam Tips Cheat Sheet

Congratulations on completing the Big Data section! Here are some key exam tips to reinforce your knowledge:

### Key Questions to Ask

1. Database Selection:
   - Determine if a transactional or non-relational database is needed (e.g., RDS or DynamoDB).
   - Consider the data size limits for services like Kinesis and Amazon S3.

2. Serverless Requirement:
   - Identify if serverless services, EC2 instances, or on-premises VMs are required based on the scenario.

3. Cost Optimization:
   - Explore ways to implement AWS services in a cost-optimized manner.

### Redshift and EMR

- Redshift is a relational database but not a replacement for RDS in traditional applications.
- Redshift only supports single availability zone deployments.
- EMR is composed of EC2 instances, allowing the use of cost-saving measures like savings plans.

### Kinesis, Athena, and Glue

- Kinesis is the only service with real-time response for processing or moving data.
- Both SQS and Kinesis can act as queues, each with its pros and cons.
- Consider Amazon Athena for serverless SQL querying of data stored in S3.
- AWS Glue is a serverless ETL service that creates a schema for data when paired with Amazon Athena.

### Visualization: QuickSight and OpenSearch/ElasticSearch

- QuickSight is used for visualizing data and creating dashboards.
- OpenSearch/ElasticSearch analyze log files and integrate with CloudWatch logs.
- OpenSearch and ElasticSearch have similar functions and uses.

### Data Pipeline

- Data Pipeline is a managed ETL service for movement and transformation of data.
- It integrates with storage services like RDS and S3, and compute services like EC2 and EMR.
- Tasks in Data Pipeline can be dependent on previous successful tasks.

### Amazon MSK (Managed Streaming for Apache Kafka)

- MSK is a managed service for building and running Apache Kafka streaming applications.
- It handles control plane operations while allowing you to manage data plane operations.
- Broker logs can be pushed to CloudWatch, S3, or Kinesis Data Firehose.
- API calls are logged to AWS CloudTrail.


## Serverless Architecture Exam Tips Cheat Sheet

Congratulations on completing the Serverless Architecture section! Here are key exam tips to help you prepare:

### Key Questions to Ask

1. Application Fit:
   - Determine if the application is better suited for containers (e.g., Kubernetes) or serverless options like AWS Lambda or AWS ECS/EKS.

2. AWS Specificity:
   - Assess if the application is AWS-specific, which may allow leveraging services like ECS or Lambda.

3. Code Runtime:
   - Consider the required code execution time to select the appropriate AWS service.

### AWS Lambda

- IAM roles must be attached to Lambda functions for credential management.
- Understand Lambda triggers, including Amazon S3 events, Kinesis, and EventBridge (formerly CloudWatch Events).
- Be aware of Lambda's limitations, such as function length and runtime window.
- Any AWS API call can trigger an EventBridge rule, which can, in turn, invoke a Lambda function.

### Containers and Images

- For open-source solutions, think Kubernetes.
- Amazon EKS and EKS Anywhere are options for container management in AWS and on-premises.
- Fargate requires Amazon ECS or Amazon EKS to work.
- Containers offer flexibility and can handle various workloads.
- Familiarize yourself with Dockerfile basics and using Amazon ECR as an AWS-managed image registry.

### Amazon Aurora Serverless

- Aurora Serverless is an on-demand and auto-scaling database suitable for variable traffic and workloads.
- It is a good choice for scenarios involving capacity planning and unknown workload patterns.

### AWS X-Ray

- AWS X-Ray provides application insights by tracing requests and responses across different services.
- It integrates tightly with AWS Lambda and Amazon API Gateway, offering deep insights into workloads.

### AWS AppSync

- AppSync is a managed GraphQL interface for front-end applications.
- Questions regarding managed GraphQL interfaces or architectures may involve AppSync.

# Security Exam Tips Cheat Sheet

This cheat sheet provides a concise overview of important security exam tips. Use it as a quick reference to review key concepts for your exam preparation.

## DDoS
- Distributed Denial of Service attack
- Layer 4 attacks: SYN floods, NTP amplification attacks
- Layer 7 attacks: floods of GET or POST requests

## CloudTrail
- Logs all API calls made to AWS account
- Provides incident investigation, intrusion detection, compliance

## Shield
- Protects against Layer 3 and Layer 4 DDoS attacks
- Free version available, Advanced version costs $3,000/month

## AWS WAF
- Operates at Layer 7
- Blocks Layer 7 DDoS attacks, SQL injections, cross-site scripting
- Can block access to specific countries or IP addresses

## AWS Firewall Manager
- Centrally secures multiple AWS accounts and resources

## GuardDuty
- Uses AI to detect abnormal or malicious behavior
- Monitors CloudTrail logs, VPC Flow logs, DNS logs

## Macie
- Analyzes data in S3 to identify sensitive information
- Assists with compliance and preventing identity theft

## Inspector
- Performs vulnerability scans on EC2 instances and VPCs

## KMS and CloudHSM
- KMS: Managed service for encryption key control
- CloudHSM: Dedicated physical hardware for key control

## Secrets Manager
- Stores application secrets securely
- Enables easy rotation of credentials

## Presigned URLs
- Used to share private files in S3 buckets

## Advanced IAM policies
- Explicit deny trumps allow
- Only attached policies have an effect

## AWS Certificate Manager
- Manages SSL certificates for integration with services

## AWS Audit Manager
- Automates auditing reports for compliance

## Cognito
- User pools for sign up and sign in options
- Identity pools for accessing AWS services

## Detective
- Analyzes root cause of events across AWS services

## Network Firewall
- Filters network traffic and provides intrusion prevention

## AWS Security Hub
- Centralized view of security alerts across AWS services and accounts

Use this cheat sheet to quickly review and reinforce your knowledge of these important security topics. Good luck with your exam!

# Automation Exam Tips Cheat Sheet

Welcome to the Automation Exam Tips Cheat Sheet! Whether you're preparing for an exam or looking to enhance your knowledge of automation tools, this guide has you covered. Below, you'll find concise tips to help you navigate the key concepts and considerations of various automation tools covered in the previous lessons.

## Exam Tips Overview

1. **Can you automate?**
   - Identify manual steps and leverage appropriate automation tools.
   - Consider CloudFormation, Elastic Beanstalk, and Systems Manager for different automation scenarios.

2. **Is the automation repeatable?**
   - Opt for AWS-provided frameworks over custom scripts.
   - Ensure your automation is built on reliable and repeatable foundations.

3. **Will the automation work cross-region or cross-account?**
   - Avoid hard-coding IDs or values in templates to ensure flexibility.
   - Leverage mappings or Parameter Store for storing IDs and values.

4. **CloudFormation-specific tips:**
   - Understand the purpose of CloudFormation sections: parameters, mappings, and resources.
   - Prioritize an immutable architecture that allows for easy reprovisioning.
   - Store IDs in mappings or Parameter Store, avoiding direct hard-coding.

## Additional Tips

Here are specific tips for Elastic Beanstalk and Systems Manager:

- **Elastic Beanstalk:**
  - Ideal for quick migrations and simplified web server setups.
  - Choose Elastic Beanstalk when dealing with straightforward scenarios.
  - Consider it as your one-stop shop for AWS web server deployments.

- **CloudFormation:**
  - Best suited for complex scenarios involving multiple AWS services.
  - Provides granular control over automation, allowing for detailed customization.
  - Focus on building an immutable architecture for robust and disposable solutions.

- **Systems Manager:**
  - Leverage automation documents to configure EC2 instances and manage the AWS environment.
  - Useful for various automation tasks across your AWS account.
  - Explore the benefits of Parameter Store and familiarize yourself with session manager functionality.

These exam tips are designed to streamline your preparation and help you excel in your automation journey. Remember to apply these concepts to real-world scenarios and stay up-to-date with the latest AWS developments.

Good luck with your exam, and happy automating!

# Caching Exam Tips Cheat Sheet

Welcome to the Caching Exam Tips Cheat Sheet! This guide will help you master the key concepts of caching for your exams. Let's dive right in:

## Can it be cached?
- Evaluate if caching can enhance your architecture:
  - Boost performance, reduce costs, tackle technical issues.
- Select the appropriate cache based on the scenario:
  - Redis, Memcached, or Dax for caching databases.
  - CloudFront for efficient content distribution.

## Managing cache content:
- Control cache data expiration with Time-to-Live (TTL) settings.
- CloudFront allows purging or waiting for TTL to expire.

## Caching benefits beyond speed:
- Enhance security with CloudFront's web application firewall.
- Leverage Global Accelerator for IP caching and improved speed.

## CloudFront and Global Accelerator:
- Secure static S3 websites using CloudFront for HTTPS connections.
- Prioritize caching when comparing solutions without caches.

## In-memory database caching:
- Redis and DynamoDB are powerful in-memory database options.
- Redis can serve as a cache or standalone database.
- DynamoDB is ideal for database solutions.

## Choosing between Redis and DynamoDB:
- In the exam, favor DynamoDB over Redis.
- Both offer speed and flexibility as non-relational databases.

## Comparing ElastiCache options:
- Redis provides extensive features and can be used as a persistent data storage.
- Memcached serves as a cache without backup support.
- Neither Memcached nor Dax are reliable data sources.

# Governance Exam Tips Cheat Sheet

Welcome to the Governance Exam Tips Cheat Sheet! This concise guide will provide you with essential tips to ace your governance exam. Let's dive in:

## Key Questions:
- Can it be centralized? (e.g., AWS RAM or Control Tower)
- How can we standardize it? (e.g., leverage guardrails)
- How can we enforce standards? (e.g., service control policies, AWS Config rules)
- Are users internal or external? How to grant them access?

## AWS Organizations:
- Use Service Control Policies (SCPs) to control API calls.
- Centralize logs with CloudTrail.
- Isolate workloads in separate accounts for enhanced security.

## AWS Config:
- Utilize Config for account rule setup and compliance checks.
- Automate responses using automation documents or Lambda functions.
- Track changes in your account with AWS Config.

## Authentication:
- Manage internal user access with AWS Single Sign-On (Identity Center).
- Consider Cognito for external users.
- For Active Directory scenarios, leverage AWS Directory Service.

## Cross-account Roles:
- Enhance authentication by utilizing cross-account roles instead of IAM users.

## Cost Management:
- Track costs using tags, Cost Explorer, and AWS Budgets.
- Create proactive alerts for cost thresholds.
- Automate responses to minimize manual intervention.
- Optimize costs with AWS Compute Optimizer for accurately-sized compute instances.

## Trusted Advisor:
- Leverage Trusted Advisor for auditing and reporting purposes.
- Automate processes using EventBridge and Lambda.

## Accounts and Licenses:
- Ensure compliance and account governance with AWS Control Tower.
- Implement preventative and detective guardrails.
- Simplify license management with AWS License Manager.

## Infrastructure and Deployments:
- Provision pre-approved products using AWS Service Catalog.
- Automate provisioning of application stacks with AWS Proton.
- Document architectural decisions against best practices using the Well-Architected Tool.

## AWS Health:
- Receive notifications for public and account-specific events.
- Automate event handling using EventBridge and Lambda.


# Migration Exam Tips Cheat Sheet

Congrats on completing the migration section! Here's a concise cheat sheet of important tips for your migration exam preparation:

## Four Key Questions:
1. Where are we going? Determine the source and destination of the migration (on-premises to AWS, AWS to on-premises, cloud vendors, third-party SaaS).
2. How do we get there? Choose the appropriate migration method (Snowball, AWS DMS, replication) based on the use case.
3. Is it all at once? Decide between a bulk move (Snowball) or incremental migration using replication for AWS servers.
4. Is it a partial migration? Consider options like basic S3 upload, multi-part upload, server replication, or lift and shift.

## AWS Snow Family:
- Snowball devices are ideal for moving large amounts of data, especially in scenarios with limited or slow internet.
- Snowcone and Snowmobile have fewer exam questions but understanding their basic overview is beneficial.

## Storage Gateway Exam Tips:
1. Hybrid: Choose the appropriate Storage Gateway version based on on-premises storage needs and the requirement for quick on-premises access to data stored in S3.
2. Out of space: File Gateway is suitable when local network-attached storage is full, allowing easy utilization of AWS storage.
3. Virtual Machine: Storage Gateway runs locally as a VM on-premises, connecting to storage solutions like S3 and enabling access from virtual machines.

## DataSync and Transfer Family:
- DataSync is an agent-based solution for one-time migration of file shares into AWS.
- EFS and FSx are viable destinations for DataSync transfers, depending on the operating system.
- The Transfer Family enables legacy file transfer protocols (e.g., SFTP) for older applications to read and write from S3 buckets.

## Migration Hub and Database Migration Service (DMS):
- Migration Hub organizes migration steps but requires additional tools for completing the migration.
- DMS is the go-to tool for database migration, whether on-premises to the cloud or between different RDS databases. It includes the AWS Schema Conversion Tool.

## Server Migration Service:
- Use Server Migration Service to migrate VMs out of the data center and into AWS.

## Application Discovery Service:
- Use agentless or agent-based discovery methods in the Application Discovery Service to collect detailed information on VMs for migrating entire applications to the cloud.

## Application Migration Service (AWS MGN):
- AWS MGN (Automated Lift and Shift Service) replicates source servers (VMs, physical servers, Azure VMs) into AWS for non-disruptive cutover, with fast recovery time objectives (RTO) and recovery point objectives (RPO).


# Front-end and Mobile Exam Tips Cheat Sheet

Congratulations on completing the front-end web and mobile section! This cheat sheet provides important exam tips to help you prepare:

## AWS Amplify
- Simplifies front-end web and mobile development.
- Supports frameworks like React, Vue.js, and Angular, and static generator tools like Gatsby and Hugo.
- Key feature: Supports server-side rendering, particularly with Next.js.

## Device Farm
- Ideal for automated or manual testing on physical Android, iOS devices, or tablets.
- Can also test simple web applications on mobile devices.

## Pinpoint
- Enables customer engagement at scale.
- Provides flexibility for marketing teams, business users, and sometimes developers.
- Allows creation of segments for targeted messaging to specific audiences.
- Key feature: Leverage machine learning models for predicting future engagements.

Remember to consult the detailed AWS documentation for further information and references.

Take a break, and get ready for the next section of the course!

# Machine Learning Exam Tips Cheat Sheet

Congratulations on completing the machine learning section! This cheat sheet provides essential exam tips to help you succeed:

## Services Covered:
- Rekognition: Detects inappropriate content in social media using AI/ML.
- Amazon SageMaker: Develop, train, and deploy models with Jupyter Notebooks. SageMaker Neo optimizes for specific hardware, and Elastic Inference reduces costs.

## Other Key Services:
- Comprehend: Perform sentiment analysis, e.g., for product reviews and social media.
- Kendra: Build intelligent search services for unstructured text, ideal for research papers.
- Textract: Extract text, handwriting, and data from scanned documents using OCR.
- Forecast: Analyze time-series data and make predictions, e.g., weather temperatures.
- Fraud Detector: Customize fraud detection models to your data and requirements.
- Transcribe: Convert audio and video to text, useful for closed captioning and chatbots.
- Lex: Power conversational chatbots like Alexa or build conversational interfaces.
- Polly: Convert text to natural speech in multiple languages, as used by Alexa.
- Translate: Use deep learning for language translation tasks.

Remember, focus on Rekognition and Amazon SageMaker for the exam. For more details, refer to the AWS documentation.

Feel free to ask any questions. Good luck with your exam preparation!

# Media Exam Tips Cheat Sheet

Congratulations on completing the media section! Here's a handy cheat sheet to help you prepare for your exam:

## Elastic Transcoder

- Converts video files into optimized formats for specific devices.
- Ensures compatibility across different platforms and devices.

## Amazon Kinesis Video Streams

- Enables scalable video streaming from millions of devices.
- Useful for scenarios like Ring doorbell systems.

Remember, the media section covers two key services: Elastic Transcoder and Amazon Kinesis Video Streams.

If you have any questions, feel free to ask. Good luck with your exam preparation!

