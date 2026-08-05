---
title: "Week 10 Worklog"
date: 2026-07-13
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives

* Build the Fullstack Notification Center and Header Dropdown Menu feature.
* Integrate SignalR to push real-time notifications from the .NET Backend to the Angular Frontend.
* Set up APIs and classify notifications: Invoice Scans, Budget Alerts, AI Suggestions, Family Wallet Invitations.
* Build the Fullstack Support Ticket feature including Ticket management APIs, Ticket creation form UI, and discussion threads.
* Practice **Workshop 5.5** lab: Configure VPC Endpoint IAM Policies to tighten security and restrict Amazon S3 resource access.
* Build the User Account Settings UI and integrate profile update APIs.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Learning Resources |
| --- | --- | --- | --- | --- |
| Monday | - Designed Database schema for Notifications and Support Tickets.<br>- Wrote APIs to fetch notification lists and mark them as read.<br>- Designed Notification Dropdown Menu UI on the Top Header and the Notification Bell icon with an unread badge. | 13/07/2026 | 13/07/2026 | [Notification System UX](https://uxdesign.cc/) |
| Tuesday | - Integrated SignalR WebSockets into the .NET Backend and Angular Frontend for real-time notifications.<br>- Classified UI designs for notification types: Invoice Scans, Budget Alerts, Financial AI Insights, Wallet Invitations.<br>- Tested notification flows upon new transactions. | 14/07/2026 | 14/07/2026 | [SignalR with Angular](https://learn.microsoft.com/en-us/aspnet/core/signalr/javascript-client) |
| Wednesday | - Built CRUD APIs for Support Tickets and message discussion threads.<br>- Designed the Support Ticket Page layout on Angular.<br>- Built the Submitted Tickets Data Table and the New Support Ticket Form with validation. | 15/07/2026 | 15/07/2026 | [Helpdesk UI Patterns](https://dribbble.com/) |
| Thursday | - **Practice Workshop 5 (Part 5 - VPC Endpoint Policies):**<br>&emsp; + Learned about layered security using VPC Endpoint IAM Policies ([Workshop VPC Endpoint Policies](5-Workshop/5.5-Policy/)).<br>&emsp; + Drafted a JSON Endpoint Policy attached to the VPC Endpoint to exclusively allow access to the Snaptics project S3 Bucket.<br>&emsp; + Executed Access Denied tests by querying S3 Buckets outside the permitted list. | 16/07/2026 | 16/07/2026 | [Workshop VPC Endpoint Policies](5-Workshop/5.5-Policy/)<br>[VPC Endpoint Policy Reference](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) |
| Friday | - Integrated APIs and designed the Ticket Detail & Discussion Thread UI.<br>- Built the User Account Settings Page and integrated APIs for updating personal info and changing passwords.<br>- Checked form validation errors and optimized responsiveness for Week 10. | 17/07/2026 | 17/07/2026 | [Account Settings Layout](https://refactoringui.com/) |

### Week 10 Achievements

* Completed the Fullstack Notification Center, successfully integrating SignalR for smooth real-time notification pushes.
* Classified and visually designed 4+ core notification groups, ensuring data synchronization with the Backend.
* Completed the professional Support Ticket Management feature from API to User Interface.
* Successfully practiced Workshop 5.5: Drafted and attached VPC Endpoint Policies, blocking unauthorized access to non-project S3 Buckets.
* Successfully integrated detailed discussion flows in Tickets between Users and the Support Team.
* Completed a clean, secure User Account Settings page and successfully invoked password change APIs.
* Ensured aesthetic consistency and smooth responsiveness across all screen sizes.
