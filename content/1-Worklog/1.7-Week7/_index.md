---
title: "Week 7 Worklog"
date: 2026-06-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives

* Database Environment Transition: Migrate all data from Local SQL Server to Amazon RDS.
* Apply security principles by placing Amazon RDS entirely within a Private Subnet network.
* Establish a static storage system: Move invoice image storage from local hard drives to Amazon S3.
* Write C# Backend code (.NET SDK for AWS) to interact with S3 to upload images and generate `Pre-signed URLs`.
* Test the integration flow: Frontend uploads images directly and securely to S3 without choking the Backend's bandwidth.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Re-evaluated the VPC architecture and provisioned a DB Subnet Group.<br>- **Afternoon:** Provisioned an Amazon RDS SQL Server in the Private Subnet. Configured the Security Group to only allow IPs from the Backend to access port 1433. | 22/06/2026 | 22/06/2026 | [Amazon RDS in a VPC](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html) |
| Tuesday | - **Morning:** Exported data from the Local SQL Server, generating a `.sql` script.<br>- **Afternoon:** Ran the script to migrate schema and data to RDS. Updated the Connection String in the Backend's `appsettings.json` to point to the RDS Endpoint. | 23/06/2026 | 23/06/2026 | [Migrating Data to Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.html) |
| Wednesday | - **Morning:** Tested the API connecting to RDS. Got an error: `"SSL Provider... connection was successfully established... error occurred during login process"`. Debugged and added `TrustServerCertificate=True` to the connection string to fix it.<br>- **Afternoon:** Created an Amazon S3 Bucket named `snaptics-invoices-dev`. Completely Blocked All Public Access. | 24/06/2026 | 24/06/2026 | [SQL Server SSL error](https://learn.microsoft.com/en-us/troubleshoot/sql/database-engine/connect/tls-ssl-issues) |
| Thursday | - **Morning:** Installed `AWSSDK.S3` for the Backend. Wrote a Service to upload images and generate a `Pre-signed URL` (living for 15 minutes) to return to the Frontend.<br>- **Afternoon:** Frontend used the Pre-signed URL to load the image. The browser threw a CORS Policy error blocking the image request. Accessed the AWS Console, rewrote the JSON CORS Policy on the S3 Bucket (allowed Origin `http://localhost:4200`), and fixed it successfully. | 25/06/2026 | 25/06/2026 | [S3 Pre-signed URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/ShareObjectPreSignedURL.html) |
| Friday | - **Morning:** Tested the E2E User image upload flow: Frontend calls Backend to get the upload URL -> Uploads the image file directly from the browser to S3 (saving Backend server bandwidth).<br>- **Afternoon:** Moved sensitive information (AWS Access Key, Secret Key) into local Environment Variables, strictly avoiding hard-coding them on Github. Weekly team sync meeting. | 26/06/2026 | 26/06/2026 | [Environment variables in .NET](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/environments) |

### Week 7 Achievements

* Successfully migrated the database from a local personal machine to the Cloud environment (Amazon RDS) safely inside a Private Subnet.
* Successfully fixed the common SSL Provider error when .NET connects to an RDS SQL Server.
* Finalized an extremely optimized and secure image storage flow using Amazon S3 combined with **Pre-signed URLs**.
* Thoroughly resolved the S3 CORS Policy issue blocking external domains.
* Practically applied credential security principles, storing keys safely in local environment variables instead of pushing to Git.
