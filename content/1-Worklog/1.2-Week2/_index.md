---
title: "Week 2 Worklog"
date: 2026-05-18
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives

* Master the core network components in Amazon VPC (IPv4 CIDR Block, Subnet, Route Table, Internet Gateway).
* Distinguish clearly between Public Subnet and Private Subnet based on routing tables and Internet connectivity permissions.
* Understand the operating principles and deploy a NAT Gateway for Private Subnet outbound Internet access.
* Compare security mechanisms between Security Group (Stateful, instance-level) and Network ACL (Stateless, subnet-level).
* Provision an Amazon EC2 instance within the VPC to test internal and external network connectivity.
* Get an overview of the **Workshop 5** lab regarding the AWS PrivateLink private connectivity solution and prepare the Prerequisite environment.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Explored the Amazon VPC service overview and IP addressing space planning principles (IPv4 CIDR Block).<br>- Analyzed the concepts of Public Subnet and Private Subnet in cloud network infrastructure design. | 18/05/2026 | 18/05/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)<br>[VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html) |
| Tuesday | - Provisioned a custom Amazon VPC with the CIDR block `10.0.0.0/16`.<br>- Created Public Subnets and Private Subnets across 2 different Availability Zones.<br>- Provisioned an Internet Gateway (IGW) and attached it to the custom VPC. | 19/05/2026 | 19/05/2026 | [VPC Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)<br>[Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| Wednesday | - Created a Route Table for the Public Subnet and added a route pointing `0.0.0.0/0` to the Internet Gateway.<br>- Provisioned a NAT Gateway in the Public Subnet and assigned a static Elastic IP.<br>- Configured the Route Table for the Private Subnet to route Internet traffic through the NAT Gateway. | 20/05/2026 | 20/05/2026 | [NAT Gateways Guide](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| Thursday | - Detailed comparison of Security Group (Stateful, server-level filtering) and Network ACL (Stateless, subnet-level filtering).<br>- Configured Inbound/Outbound rules for the Security Group (allowing HTTP/SSH) and Network ACL.<br>- Launched Amazon EC2 instances into the Public Subnet and Private Subnet for connectivity testing. | 21/05/2026 | 21/05/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)<br>[Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) |
| Friday | - **Practice Workshop 5 (Parts 1 & 2):**<br>&emsp; + Explored the overview of the "Secure Hybrid Access to S3 using VPC Endpoints" lab ([Workshop Overview](5-Workshop/5.1-Workshop-overview/)).<br>&emsp; + Prepared the Prerequisite environment (creating test VPC, Subnets, EC2 Server, and sample S3 Bucket) ([Workshop Prerequisite](5-Workshop/5.2-Prerequiste/)).<br>- Tested connectivity from the Public EC2 to the Private EC2 and captured evidence screenshots. | 22/05/2026 | 22/05/2026 | [AWS Site-to-Site VPN](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html)<br>[Workshop Overview](5-Workshop/5.1-Workshop-overview/) |

### Week 2 Achievements

* Understood Amazon VPC structure, how to calculate IP CIDR ranges, and subnetting best practices on AWS.
* Successfully provisioned a custom VPC fully integrated with Public and Private Subnets across multiple Availability Zones.
* Configured the Route Table connecting the Internet Gateway for the Public Subnet to operate stably.
* Successfully deployed a NAT Gateway with an Elastic IP, enabling Private resources to safely access the Internet outbound.
* Mastered multi-layer firewall configuration skills combining Security Groups and Network ACLs.
* Successfully tested and verified connectivity between the Public EC2 and Private EC2 instances.
* Grasped the overview knowledge of Workshop 5 and successfully prepared the Prerequisite infrastructure for the VPC Endpoint lab.
* Saved architecture diagram images and VPC network configurations for reporting purposes.
