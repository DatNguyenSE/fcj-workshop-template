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
* Provision Amazon EC2 instances within the VPC to test internal and external network connectivity.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Weekly Sync meeting. Explored Amazon VPC service overview, IP addressing space planning principles (IPv4 CIDR Block), and subnetting.<br>- **Afternoon:** Drew VPC network architecture diagram using Draw.io. Calculated IP range allocation for `10.0.0.0/16` VPC and divided it into 2 Public Subnets and 2 Private Subnets. | 18/05/2026 | 18/05/2026 | [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| Tuesday | - **Morning:** Practiced creating a custom Amazon VPC on the AWS Console. Provisioned and attached an Internet Gateway (IGW) to the VPC.<br>- **Afternoon:** Got an Overlapping CIDR error when creating the 3rd Subnet due to calculation mistakes; re-read the subnetting guide and successfully fixed it. Configured the Route Table for the Public Subnet (routing `0.0.0.0/0` to IGW). | 19/05/2026 | 19/05/2026 | [VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/configure-subnets.html) |
| Wednesday | - **Morning:** Provisioned a NAT Gateway (placed in the Public Subnet) and assigned a static Elastic IP. Configured the Private Subnet Route Table to direct traffic out to the NAT Gateway.<br>- **Afternoon:** Analyzed the differences between Security Group (Stateful) and Network ACL (Stateless). Configured Inbound rules to allow HTTP/SSH access from trusted sources. | 20/05/2026 | 20/05/2026 | [NAT Gateways Guide](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html) |
| Thursday | - **Morning:** Launched 2 Amazon EC2 instances (1 in Public Subnet, 1 in Private Subnet) to test the network.<br>- **Afternoon:** SSH-ed into the Public EC2 and pinged the Private EC2. Encountered a ping Request Timeout error, debugged and found that the Security Group hadn't opened the ICMP IPv4 port; went to the Console and fixed it. Successfully tested outbound internet from the Private EC2 via NAT. | 21/05/2026 | 21/05/2026 | [Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html) |
| Friday | - **Morning:** Explored the theory of Workshop 5 regarding VPC Endpoints and the PrivateLink solution (accessing AWS Services without going over the Internet).<br>- **Afternoon:** Cleaned up resources (Deleted NAT Gateway, Terminated EC2 instances) to prevent billing charges. Wrote the Week 2 network summary document and saved the diagram to the team Notion. | 22/05/2026 | 22/05/2026 | [AWS Site-to-Site VPN](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html) |

### Week 2 Achievements

* Mastered the skills of calculating IP CIDR ranges and subnetting without overlapping.
* Successfully provisioned a custom VPC, configuring the Internet Gateway for stable Public Subnet operation.
* Successfully troubleshot real-world network errors: fixed overlapping CIDR bugs, opened ICMP ports on Security Groups for internal pinging.
* Successfully deployed a NAT Gateway with an Elastic IP, safely enabling Private EC2 instances to access the Internet.
* Built a cost-optimization habit: always cleaning up unused resources (especially NAT Gateways and Elastic IPs).
