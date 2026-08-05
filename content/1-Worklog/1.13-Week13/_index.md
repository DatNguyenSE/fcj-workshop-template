---
title: "Week 13 Worklog"
date: 2026-08-03
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Week 13 Objectives

* Conduct comprehensive End-to-End User Flow testing across the entire system, from Frontend to Backend and Database.
* Fix all minor UI/UX bugs and optimize overall system performance (Angular & .NET API).
* Configure AWS infrastructure deployment (Amplify for Frontend, CloudFront & ALB for Backend API) combined with SSL/HTTPS certificates.
* Successfully compile the static Frontend Production build using Angular CLI and configure automated CI/CD from GitHub.
* Ensure the CloudFront to ALB architecture operates smoothly via Custom Domains, accurately handling Headers and WebSockets (SignalR).
* Practice **Workshop 5.6** lab: Thoroughly clean up experimental resources (VPC Endpoints, EC2 test instances, IAM policies, S3 test buckets) to avoid unnecessary AWS costs.
* Capture real application screenshots, finalize internship report documentation, prepare the product demo script, and officially submit the Snaptics project on **07/08/2026**.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Learning Resources |
| --- | --- | --- | --- | --- |
| Monday | - Conducted End-to-End Testing on the Fullstack system:<br>&emsp; + Login, Register, JWT Auth flows.<br>&emsp; + Dashboard, Transactions, Wallets, Budgets saving to SQL Server.<br>&emsp; + Invoice Scanning (S3 + SQS + Azure OCR), SignalR Notifications, Gemini AI Chatbot, Support Tickets.<br>&emsp; + Admin Management and Hangfire Background Jobs.<br>- Reviewed and refined UI/UX bugs, optimized API response times. | 03/08/2026 | 03/08/2026 | [Software Testing Best Practices](https://developer.mozilla.org/) |
| Tuesday | - Accurately checked Production environment variables (`src/environments/environment.prod.ts` pointing to CloudFront API URL).<br>- Ran `ng build --configuration production` to compile the static Production build and confirmed 100% success.<br>- Optimized Parameter Store configurations on AWS Systems Manager for the Backend. | 04/08/2026 | 04/08/2026 | [Angular Deployment Guide](https://angular.io/guide/deployment) |
| Wednesday | - Deployed the system to Production AWS:<br>&emsp; + Hosted Frontend on **AWS Amplify** with GitHub CI/CD.<br>&emsp; + Configured **CloudFront** in front of the Backend API ALB, setting Cache Policy to `CachingDisabled` and Origin Request Policy to `AllViewer`.<br>&emsp; + Routed Custom Domains via Route 53 and configured ACM SSL security certificates. | 05/08/2026 | 05/08/2026 | [AWS Amplify Hosting](https://docs.aws.amazon.com/amplify/latest/userguide/welcome.html)<br>[CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Thursday | - **Practice Workshop 5 (Part 6 - Resource Cleanup):**<br>&emsp; + Cleaned up all Workshop lab resources following the guide ([Workshop Clean-up](5-Workshop/5.6-Cleanup/)).<br>&emsp; + Deleted Gateway VPC Endpoints, Interface VPC Endpoints, EC2 test instances, S3 test buckets, and released Elastic IPs.<br>&emsp; + Reviewed AWS Cost Explorer to ensure no background junk resources cause extra charges. | 06/08/2026 | 06/08/2026 | [Workshop Clean-up](5-Workshop/5.6-Cleanup/)<br>[AWS Cost Management](https://aws.amazon.com/aws-cost-management/) |
| Friday | - **Finalize & Submit Internship Report:**<br>- Gathered application screenshots and prepared the product Demo script for the final review.<br>- Summarized all Fullstack knowledge (.NET, Angular) and AWS cloud services integrated into the Snaptics architecture over 13 weeks.<br>- Finalized internship report documentation and **officially submitted the Snaptics Project**, concluding the FCJ Workforce internship program on **07/08/2026**. | 07/08/2026 | 07/08/2026 | [FCJ Workforce Regulations](https://hcm-rules.awsfcaj.com/1-regulations/) |

### Week 13 Achievements

* Successfully performed End-to-End testing, ensuring the entire Fullstack system operates smoothly from Frontend to Database.
* Optimized Angular app size and Backend API performance, enhancing system response speed.
* Successfully compiled the Angular Production Build with 100% success and no syntax errors.
* Successfully deployed Production AWS infrastructure: Frontend running blazingly fast on Amplify, Backend API secured behind CloudFront & ALB.
* Completed domain configuration via Route 53 with HTTPS security certificates for both Frontend and Backend APIs.
* Successfully practiced 100% resource cleanup in Workshop 5 (Clean-up), optimizing AWS costs.
* Fully prepared high-quality product Demo scripts and final defense presentation content.
* Gained highly valuable practical experience in Fullstack Web Development, Serverless/Container architecture, and AWS services.
* Completed and officially submitted the Internship Report & Snaptics Project on time by **07/08/2026**.
