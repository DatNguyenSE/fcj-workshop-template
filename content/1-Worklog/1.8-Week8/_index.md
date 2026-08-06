---
title: "Week 8 Worklog"
date: 2026-06-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

* Establish an asynchronous message queue system using Amazon SQS.
* Configure a Background Worker for hidden processing.
* Successfully integrate AI technology (Azure Document Intelligence) to read invoices.
* Push real-time notifications to users via WebSockets.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
|------|-----------|-------------|----------------|---------------|
| Monday | **Amazon SQS:** <br> - Learn about Amazon Simple Queue Service <br> - Provision a Standard Queue <br> - Understand and configure the Visibility Timeout mechanism | 29/06/2026 | 29/06/2026 | |
| Tuesday | **Background Processing:** <br> - Write an IHostedService on .NET <br> - Configure a Worker to pull messages from SQS <br> - Manage the message lifecycle within the Queue | 30/06/2026 | 30/06/2026 | |
| Wednesday | **Azure Document Intelligence:** <br> - Register for Azure OCR service <br> - Securely store the API Key using AWS Parameter Store <br> - Integrate API calls for invoice analysis into the Worker | 01/07/2026 | 01/07/2026 | |
| Thursday | **AI Data Processing:** <br> - Parse JSON result strings from Azure <br> - Map information to Database fields <br> - Add logic to handle missing/faulty data scenarios | 02/07/2026 | 02/07/2026 | |
| Friday | **Real-time SignalR:** <br> - Learn about WebSockets and SignalR technology <br> - Configure SignalR Hub on the Backend <br> - Integrate pushing invoice scan completion notifications to the Frontend | 03/07/2026 | 03/07/2026 | |

### Week 8 Achievements

* Integrated asynchronous architecture using SQS, enhancing performance for heavy tasks.
* Successfully leveraged artificial intelligence APIs to automate data extraction.
* Familiarized with application configuration security through AWS Parameter Store.
* Elevated user experience (UX) with smooth Real-time notifications.
