---
title: "Week 4 Worklog"
date: 2026-06-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives

* Hold a team meeting to agree on selecting the **Snaptics** project topic - A smart personal/family spending management and invoice scanning platform.
* Analyze real-world financial management problems and define the MVP feature scope for 2 user groups: User and Admin.
* Take on the **Fullstack Developer** role, taking responsibility for system design, Backend APIs, and UI/UX design.
* Research reference UI templates, build the system Sitemap, and draft the main User Flows.
* Design initial Wireframes for core screens and agree on a UI design style (Design System tokens).
* Learn about AWS services supporting project operations: Elastic Load Balancer (ALB), Auto Scaling, CloudWatch.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Team meeting to finalize the **Snaptics** project topic (Expense Mgmt & AI Invoice Scanning). Assumed the Fullstack Developer role.<br>- **Afternoon:** Analyzed problem scopes (User/Admin). Initialized the Github repository, agreed on the Git Flow workflow (main, develop, feature branches), and configured Collaborator permissions. | 01/06/2026 | 01/06/2026 | [Proposal Snaptics](2-Proposal/) |
| Tuesday | - **Morning:** Built a detailed Sitemap for screens (Dashboard, Transactions, AI Chat, Wallet, Admin Panel).<br>- **Afternoon:** Drew User Flows for the core feature: User uploads invoice image -> System sends to AI OCR for extraction -> Returns result to auto-fill the new Transaction form. | 02/06/2026 | 02/06/2026 | [UI/UX Design Patterns](https://refactoringui.com/) |
| Wednesday | - **Morning:** Drafted Wireframes on Figma for main pages. Finalized the Design System Tokens (Primary Dark Blue palette, Inter Typography, Component styles).<br>- **Afternoon:** Team meeting to finalize the Tech-stack (Frontend: Angular 17, Backend: .NET 8 Web API). Setup local coding environments, created project templates, and pushed the initial commits to Github. | 03/06/2026 | 03/06/2026 | [Modern Web Layouts](https://uxdesign.cc/) |
| Thursday | - **Morning:** Researched deployment architectures on AWS: Application Load Balancer (ALB) as a traffic filter and Auto Scaling Group (ASG) to stretch Servers.<br>- **Afternoon:** Drafted a Cloud-native architecture diagram for the project (Frontend hosted on AWS Amplify/S3, Backend running in containers behind an ALB, Database using RDS). | 04/06/2026 | 04/06/2026 | [AWS ALB Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html) |
| Friday | - **Morning:** Set up Trello/Jira Boards, listed the backlog of features to complete in the first Sprint.<br>- **Afternoon:** Divided tasks for the following week (Focusing on Database Schema design and Core API construction). Reviewed the entire project plan with the group to finalize the timeline. | 05/06/2026 | 05/06/2026 | [Agile Project Management](https://www.atlassian.com/agile) |

### Week 4 Achievements

* Officially locked in the Snaptics topic, clearly defining user personas (User & Admin) and MVP features.
* Successfully initialized the team workspace (Github Repo, Jira/Trello Board) and standardized the Git Flow process.
* Completed fundamental UI/UX system design documentation (Sitemap, User Flow, Wireframes, Design System).
* Determined the tech-stack (Angular, .NET) and drafted the expected Cloud-native architecture to be deployed on AWS.
