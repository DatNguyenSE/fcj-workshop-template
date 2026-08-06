---
title: "Week 1 Worklog"
date: 2026-05-11
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Week 1 Objectives

* Become familiar with the First Cloud Journey (FCJ Workforce) program.
* Understand the regulations, roadmap, and evaluation requirements of the internship program.
* Gain an overview of Cloud Computing and AWS global infrastructure (Regions, Availability Zones, Edge Locations).
* Create an AWS Free Tier account and set up security with Multi-Factor Authentication (MFA).
* Research AWS IAM services (Users, Groups, Policies, Roles) and apply the Least Privilege principle.
* Install and configure AWS CLI on a personal computer and verify basic administrative commands.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Attended the FCJ Workforce orientation session, got acquainted with the intern team. Read the rules and 13-week roadmap.<br>- **Afternoon:** Setup personal workspace (Installed Visual Studio, VS Code, Git, Docker). Held a team meeting to discuss working conventions (Daily Standup at 9 AM). | 11/05/2026 | 11/05/2026 | [FCJ Regulations](https://hcm-rules.awsfcaj.com/1-regulations/) |
| Tuesday | - **Morning:** Read AWS Cloud Overview, IaaS/PaaS/SaaS models, and Global Infrastructure (Regions, AZs).<br>- **Afternoon:** Explored the AWS Shared Responsibility Model. Group discussion on real-world AWS use cases in Vietnam. | 12/05/2026 | 12/05/2026 | [AWS Cloud Overview](https://aws.amazon.com/what-is-aws/) |
| Wednesday | - **Morning:** Provisioned an AWS Free Tier account. Added payment card and enabled Multi-Factor Authentication (MFA) for the Root account.<br>- **Afternoon:** Configured initial AWS Budgets cost alerts. Handled an issue where the payment card was rejected because international payments were not enabled. | 13/05/2026 | 13/05/2026 | [AWS Free Tier](https://aws.amazon.com/free/) |
| Thursday | - **Morning:** Researched AWS IAM (Users, Groups, Policies, Roles) and the Least Privilege principle.<br>- **Afternoon:** Practiced creating a dedicated IAM User for daily tasks. Encountered a permission denied error when trying to create an S3 bucket; successfully debugged the JSON Policy and attached the appropriate permissions. | 14/05/2026 | 14/05/2026 | [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| Friday | - **Morning:** Downloaded, installed, and configured the AWS CLI v2 tool on the local machine. Initialized the default profile.<br>- **Afternoon:** Tested basic CLI commands (`aws sts get-caller-identity`). Got an "Access Denied" error, found out it was due to a missing character while copying the Secret Key, fixed the error, and configured successfully. Wrote the weekly report on Notion. | 15/05/2026 | 15/05/2026 | [Configuring AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) |

### Week 1 Achievements

* Completely set up the team workspace, programming tools, and familiarized with the 13-week internship roadmap.
* Successfully provisioned an AWS Free Tier account and enabled MFA security for the Root Account.
* Mastered core knowledge about AWS IAM and created a daily administrative IAM User adhering to the Least Privilege principle, learned how to read and fix JSON Policies.
* Successfully installed and configured AWS CLI v2 locally, and successfully troubleshot Credentials authentication errors.