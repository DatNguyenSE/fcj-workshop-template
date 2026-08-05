---
title: "Week 8 Worklog"
date: 2026-06-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

* Provision and configure core AWS backend services: Amazon S3 (for receipt image storage), Amazon SQS (for asynchronous processing queues).
* Configure AWS Systems Manager Parameter Store to securely store API Keys (Azure, Gemini) and Database connection strings.
* Integrate Azure Document Intelligence into the .NET Backend to automatically extract information (Merchant, Total) from receipt images.
* Build the `scan-bill` API on the Backend, handling S3 pre-signed URL uploads, pushing messages to SQS, and invoking Azure OCR.
* Integrate the Invoice Scanning feature into the Angular Frontend, allowing users to upload images and receive extracted data in real-time.
* Set up the RDS SQL Server Database and adjust the Backend architecture for secure connections within the VPC.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Learning Resources |
| --- | --- | --- | --- | --- |
| Monday | - Provisioned Amazon S3 Bucket with Block Public Access for private receipt storage.<br>- Provisioned Amazon SQS Queue (along with a Dead Letter Queue) to handle asynchronous invoice analysis.<br>- Configured AWS Systems Manager Parameter Store to store AzureKey, GeminiKey, and ConnectionStrings. | 29/06/2026 | 29/06/2026 | [Snaptics Proposal](2-Proposal/)<br>[AWS S3 & SQS Guide](https://aws.amazon.com/s3/) |
| Tuesday | - Set up Amazon RDS for SQL Server in a Private Subnet and configured Security Groups.<br>- Wrote .NET Backend code to read security configurations from Parameter Store instead of `appsettings.json`.<br>- Installed AWS SDKs so the Backend can interact with S3 (create Pre-signed URLs) and SQS (send/receive messages). | 30/06/2026 | 30/06/2026 | [AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) |
| Wednesday | - Registered for Azure Document Intelligence, obtained the Endpoint and Key, and saved them to AWS Parameter Store.<br>- Integrated the Azure Document Analysis Client SDK into the .NET Backend.<br>- Built the `scan-bill` API: Receives scan requests, uploads images to S3, and passes the URI to Azure OCR to extract Merchant Name and Total Amount. | 01/07/2026 | 01/07/2026 | [Azure Document Intelligence](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/) |
| Thursday | - Integrated the Angular Frontend to call the `scan-bill` API.<br>- Designed the invoice upload UI (Drag & Drop box), displaying loading states while processing.<br>- Processed data returned from the API and auto-filled it into the new Transaction input form on the UI. | 02/07/2026 | 02/07/2026 | [Angular File Upload](https://angular.io/guide/file-uploads) |
| Friday | - Tested the end-to-end Invoice Scanning flow: Image Upload from Angular -> S3 -> SQS -> Worker invokes Azure OCR -> Result returned to Frontend.<br>- Handled edge cases for blurry images, incorrect formats, or failed OCR recognition.<br>- Documented APIs, fixed AWS misconfigurations, and conducted the Week 8 review. | 03/07/2026 | 03/07/2026 | [Postman API Testing](https://www.postman.com/) |

### Week 8 Achievements

* Successfully deployed core AWS infrastructure services (S3, SQS, RDS, Parameter Store) for the Snaptics system.
* Secured all sensitive information (API Keys, Database Passwords) using AWS Systems Manager Parameter Store.
* Successfully integrated Azure Document Intelligence into the .NET Backend for precise receipt data extraction.
* Completed the `scan-bill` API, handling complex business logic combining S3, SQS, and AI OCR.
* Finalized the Frontend UI, allowing users to upload receipt images and experience seamless automatic data extraction.
* Successfully tested end-to-end data flows from the Client to Cloud Services (AWS & Azure).
