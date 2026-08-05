---
title: "Week 3 Worklog"
date: 2026-05-25
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives

* Deep dive into Amazon EC2 compute services (Instance Types, AMI, EBS Volume types).
* Practice connecting to EC2 instances via SSH protocol and running a sample web application (Nginx).
* Research Amazon RDS managed database services (PostgreSQL/SQL Server, Multi-AZ Deployment, Read Replicas).
* Deploy an Amazon RDS Instance completely within the Private Subnet of a VPC.
* Test secure connectivity from an EC2 instance to the Amazon RDS database via Security Groups.
* Practice **Workshop 5.3** lab: Create a Gateway VPC Endpoint connecting EC2 instances to Amazon S3 within the internal VPC environment without routing over the Internet.
* Practice the Database Backup (DB Snapshot) and Restore processes on Amazon RDS.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Learning Resources |
| --- | --- | --- | --- | --- |
| Monday | - In-depth research on Amazon EC2: categorizing Instance Types (t3.micro, c5, r5), Amazon Machine Image (AMI).<br>- Learned about Amazon EBS volume types (gp3, io2, st1) and their IOPS/Throughput characteristics. | 25/05/2026 | 25/05/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)<br>[Amazon EBS Volumes](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html) |
| Tuesday | - Provisioned an Amazon EC2 instance (Ubuntu/Amazon Linux 2023) and assigned a secure Key Pair.<br>- Connected to the server via SSH from a local machine.<br>- Installed Nginx/sample web server service and tested HTTP access via the Public IP address. | 26/05/2026 | 26/05/2026 | [Connect to Linux Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html) |
| Wednesday | - Researched Amazon RDS (Relational Database Service) managed database services.<br>- Differentiated between self-managed DBs on EC2 and managed RDS services.<br>- Learned about Multi-AZ replication (High Availability) and Read Replicas (read scaling). | 27/05/2026 | 27/05/2026 | [Amazon RDS User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)<br>[RDS Multi-AZ Deployments](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html) |
| Thursday | - **Practice Workshop 5 (Part 3 - S3 from VPC):**<br>&emsp; + Provisioned a Gateway VPC Endpoint for the Amazon S3 service ([Workshop S3 from VPC](5-Workshop/5.3-S3-vpc/)).<br>&emsp; + Updated the Private Subnet Route Table, routing `com.amazonaws.<region>.s3` traffic to the Gateway Endpoint.<br>&emsp; + Ran an AWS CLI command (`aws s3 ls`) from the Private EC2 instance to confirm successful internal connection to S3 without traversing the Public Internet. | 28/05/2026 | 28/05/2026 | [Workshop S3 from VPC](5-Workshop/5.3-S3-vpc/)<br>[VPC Gateway Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html) |
| Friday | - Provisioned a DB Subnet Group and deployed an Amazon RDS Instance into the Private Subnet.<br>- Practiced connecting a DB Client from the EC2 Server to the RDS Instance in the Private Subnet.<br>- Created a manual backup (DB Snapshot) on the Amazon RDS Console and performed a test Restore.<br>- Summarized AWS infrastructure knowledge in preparation for the project phase. | 29/05/2026 | 29/05/2026 | [RDS Backups & Restore](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html) |

### Week 3 Achievements

* Grasped the core technical specifications of Amazon EC2 and the criteria for selecting suitable Instance Types and EBS Volumes.
* Successfully provisioned, operated, and configured a sample Nginx web server on an EC2 instance.
* Deeply understood the benefits of Amazon RDS in automating backups, patching, and ensuring high availability.
* Successfully practiced the Workshop 5.3 lab: Created a Gateway VPC Endpoint for S3 and verified successful private connectivity from the Private EC2 to the S3 Bucket.
* Successfully provisioned an Amazon RDS Instance safely placed within the Private Subnet of a custom VPC.
* Accurately configured Security Group chaining rules between EC2 and RDS.
* Mastered the process of creating DB Snapshots and restoring databases during incidents.
* Systematized all core AWS infrastructure knowledge accumulated over the first 3 weeks.
