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

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Deep dive into Amazon EC2: categorizing Instance Types (t3, c5, r5), choosing Amazon Machine Images (AMI) and EBS Volumes.<br>- **Afternoon:** Provisioned an Ubuntu EC2, downloaded the Key Pair (`.pem`). Encountered an `SSH Permission Denied` error because the `.pem` file was too open (public permissions); researched and ran `chmod 400 key.pem` to fix it. Installed Nginx on EC2 and successfully tested the default page. | 25/05/2026 | 25/05/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| Tuesday | - **Morning:** Read Amazon RDS documentation, differentiating between self-managed DBs on EC2 and managed RDS services. Explored the Multi-AZ (High Availability) mechanism.<br>- **Afternoon:** Provisioned a DB Subnet Group and deployed an Amazon RDS SQL Server Instance completely within the Private Subnet. | 26/05/2026 | 26/05/2026 | [Amazon RDS User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) |
| Wednesday | - **Morning:** Connected from the EC2 (Public) to the RDS (Private) to test. Got a `Connection Timeout` error. Debugged and found the RDS Security Group was completely locked; added an Inbound rule from the EC2 Security Group and successfully connected to SQL Server via port 1433.<br>- **Afternoon:** Practiced RDS backups: manually created a DB Snapshot, deleted the current RDS, and restored it from the newly created Snapshot. | 27/05/2026 | 27/05/2026 | [RDS Backups & Restore](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html) |
| Thursday | - **Morning:** Practice Workshop 5.3: Provisioned a Gateway VPC Endpoint for the Amazon S3 service. Updated the Private Subnet Route Table, routing `com.amazonaws.<region>.s3` traffic to the Endpoint.<br>- **Afternoon:** Used the AWS CLI on the Private EC2 to run `aws s3 ls`. Confirmed successful API calls to S3 purely via the AWS internal network, bypassing the Public Internet entirely (thanks to the VPC Endpoint). | 28/05/2026 | 28/05/2026 | [VPC Gateway Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html) |
| Friday | - **Morning:** Reviewed the entire VPC, EC2, and RDS architectures learned and practiced over the first 3 weeks.<br>- **Afternoon:** Cleaned up lab resources (Terminated EC2, Deleted RDS Snapshot & Database) to optimize costs. Completely drew the current network architecture diagram on Draw.io and updated the team documentation file. | 29/05/2026 | 29/05/2026 | [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) |

### Week 3 Achievements

* Mastered how to select appropriate compute resources (Instance Types, EBS) for EC2. Overcame basic SSH security errors.
* Successfully provisioned an Amazon RDS SQL Server safely placed in the Private Subnet.
* Clearly understood cross-connection mechanisms between Security Groups (Security Group chaining), successfully configuring EC2 access to RDS.
* Successfully practiced Snapshot & Restore on the DB system.
* Understood and smoothly implemented VPC Endpoints to enhance security when internal servers need to communicate with S3.
