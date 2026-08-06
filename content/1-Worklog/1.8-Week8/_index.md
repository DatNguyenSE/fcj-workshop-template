---
title: "Week 8 Worklog"
date: 2026-06-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

* Design an Asynchronous processing architecture using Amazon SQS message queues.
* Integrate AI Azure Document Intelligence (Azure OCR) to automatically extract invoice information (Merchant, Total, Date).
* Use AWS Systems Manager Parameter Store to securely store third-party API Keys.
* Build a Background Worker (Hosted Service) on the .NET Backend to continuously pull messages from SQS and process images.
* Integrate SignalR WebSockets to push real-time result notifications back to the user on the Frontend.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Provisioned an Amazon SQS queue (Standard Queue) on the AWS Console.<br>- **Afternoon:** Registered a Microsoft Azure account, provisioned the Document Intelligence (OCR) service, and grabbed the API Key and Endpoint. Stored these 2 Keys securely in the AWS Systems Manager Parameter Store instead of a config file. | 29/06/2026 | 29/06/2026 | [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) |
| Tuesday | - **Morning:** Coded the feature to Publish messages containing the S3 Image URI to SQS whenever a user finishes uploading an invoice.<br>- **Afternoon:** Coded a Background Worker (`IHostedService`) on .NET to pull messages from SQS. Encountered an issue where the worker pulled the same message multiple times; researched and increased the SQS `Visibility Timeout` to 30s because the AI image analysis process takes a long time. | 30/06/2026 | 30/06/2026 | [Amazon SQS Visibility Timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html) |
| Wednesday | - **Morning:** Wrote a Service calling the Azure OCR API within the Background Worker. Passed the S3 image URI to Azure for analysis.<br>- **Afternoon:** Parsed the JSON data returned from Azure, mapping Merchant Name, Total Amount, and Transaction Date fields to C# Objects and saving a draft into RDS. | 01/07/2026 | 01/07/2026 | [Azure Document Intelligence REST API](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/) |
| Thursday | - **Morning:** Got a worker crash Exception due to the JSON from Azure returning Null for some fields (due to testing with blurry/torn invoice images). Debugged and added safe Null checking statements (Null-conditional operators).<br>- **Afternoon:** Configured the SignalR library on the .NET Backend. Pushed real-time scan status notifications ("Success/Failed") to the Angular Frontend. | 02/07/2026 | 02/07/2026 | [SignalR in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/signalr/introduction) |
| Friday | - **Morning:** Coded the Frontend UI (Review Invoice Form) allowing Users to review and confirm (or edit) the information the AI just extracted.<br>- **Afternoon:** Light system load testing: pressed upload on 10 invoice images simultaneously. Monitored the AWS SQS Queue and observed the Worker pulling and processing each message sequentially without dropping any. Drew the SQS -> Azure data flow diagram on Draw.io. | 03/07/2026 | 03/07/2026 | [Design Patterns: Queue-Based Load Leveling](https://learn.microsoft.com/en-us/azure/architecture/patterns/queue-based-load-leveling) |

### Week 8 Achievements

* Successfully deployed an asynchronous processing architecture using Amazon SQS, preventing the Frontend from freezing while waiting for long image processing.
* Successfully integrated the Azure OCR AI solution, accurately extracting information from Vietnamese/English invoices.
* Gained a deep understanding of the message queue Visibility Timeout mechanism and handled duplicate processing errors.
* Absolutely secure API key management using AWS Parameter Store.
* Perfectly integrated SignalR WebSockets, providing a smooth Real-time experience for users (upload then do other tasks, the machine notifies when done).
