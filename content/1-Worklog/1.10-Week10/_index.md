---
title: "Week 10 Worklog"
date: 2026-07-13
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives

* Build the Fullstack Notification Center feature with a Realtime bell.
* Apply WebSockets (SignalR) to maintain a continuous, stable connection between Server and Client.
* Build the Support Ticket system allowing Users to send help requests to Admins.
* Practice **Workshop 5.5** lab: Detail IAM Policy configuration for VPC Endpoints to tighten S3 connectivity security.
* Build the User Account Settings UI (Change avatar, Update personal profile).

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Analyzed the Notification system business logic. Designed the `Notifications` table in the DB supporting multiple types (Budget warnings, AI, System, Invoice scanning).<br>- **Afternoon:** Built CRUD APIs for Notifications. Configured and extended the SignalR Hub so that whenever a new Notification event is created in the DB, the Server pushes the JSON data straight to online Users. | 13/07/2026 | 13/07/2026 | [Real-time apps with SignalR](https://learn.microsoft.com/en-us/aspnet/core/signalr/introduction) |
| Tuesday | - **Morning:** Coded the Notification Bell Dropdown Menu UI on the Angular Header. Implemented the unread notification badge counter effect.<br>- **Afternoon:** Tested the Realtime Notification flow. Got continuous WebSocket connection drop errors when the machine was idle for over 1 minute; debugged and added the `keepAliveIntervalInMilliseconds` config for the SignalR client to fix it. | 14/07/2026 | 14/07/2026 | [SignalR Configuration](https://learn.microsoft.com/en-us/aspnet/core/signalr/configuration) |
| Wednesday | - **Morning:** Designed the Support Ticket business flow. Initialized `Tickets` and `TicketMessages` tables (Storing support chat history). Wrote the API to create Tickets.<br>- **Afternoon:** Coded the Ticket creation Form UI on the Frontend and built the back-and-forth chat screen between User and Admin. Tested sending error attachments to S3 via the Pre-signed URL flow built in Week 7. | 15/07/2026 | 15/07/2026 | [Customer Support UX Patterns](https://uxdesign.cc/customer-support-ux-best-practices-28c0b561b369) |
| Thursday | - **Morning:** Practiced Workshop 5.5 lab: Tightened security for the S3 Gateway VPC Endpoint. It defaulted to Full Access, needed to change to a Custom Policy.<br>- **Afternoon:** Configured the Policy allowing Get/Put operations exactly on 1 Bucket `snaptics-invoices-dev`. Tried running the API and got thrown a "403 Access Denied" error. Checked AWS CloudTrail logs, found incorrect ARN syntax, fixed it to `arn:aws:s3:::snaptics-invoices-dev/*` and ran successfully. | 16/07/2026 | 16/07/2026 | [VPC Endpoint Policies](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) |
| Friday | - **Morning:** Built the Account Settings UI page (Account configuration interface, changing personal info).<br>- **Afternoon:** Integrated the profile update API. End-of-week team sync, Merged everyone's feature branches into the `develop` branch. Encountered a conflict in the `app.module.ts` file (since everyone declared new Components); the whole team sat together, resolved the conflict, and rebuilt successfully. | 17/07/2026 | 17/07/2026 | [Resolving Git Conflicts](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line) |

### Week 10 Achievements

* Perfected a top-notch Realtime Notification feature, thoroughly handling WebSocket drop errors using Ping/Pong (Keep-alive) mechanisms.
* Completed the core framework for the Support Ticket feature, ready for the Admin Panel next week.
* Enhanced AWS security skills (SecOps) by precisely configuring VPC Endpoint IAM Policies, preventing data leakage risks to out-of-project Buckets.
* Practiced real-world teamwork skills by resolving "tough" Git Conflicts during collaborative code merging.
