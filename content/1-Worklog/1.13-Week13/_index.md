---
title: "Week 13 Worklog"
date: 2026-08-03
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Week 13 Objectives

* Package and compile the entire system (Build Production).
* Deploy the system onto a Cloud-native infrastructure (Amplify & ECS).
* Configure Custom Domains and SSL/HTTPS security.
* Handover the project and clean up resources.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
|------|-----------|-------------|----------------|---------------|
| Monday | **Build Production:** <br> - Compile Angular Frontend for Production <br> - Package Backend into a Docker Image <br> - Push Image to Amazon ECR repository | 03/08/2026 | 03/08/2026 | |
| Tuesday | **Frontend Deployment:** <br> - Push Frontend build to AWS Amplify <br> - Configure Rewrite/Redirect Rules for the SPA <br> - Test access via the default domain | 04/08/2026 | 04/08/2026 | |
| Wednesday | **Backend Deployment (ECS):** <br> - Initialize Cluster and Task Definition <br> - Deploy ECS Fargate to run containers <br> - Set up the Application Load Balancer (ALB) | 05/08/2026 | 05/08/2026 | |
| Thursday | **SSL/HTTPS Security:** <br> - Create certificates via AWS Certificate Manager (ACM) <br> - Attach SSL to ALB for HTTPS protocol <br> - Configure Route53 to route Custom Domain to ALB | 06/08/2026 | 06/08/2026 | |
| Friday | **Optimization and Handover:** <br> - Configure Headers allowing WebSockets to run through ALB <br> - Practice lab cleaning up garbage resources (VPC Endpoints, Test EC2s) <br> - Demo and officially submit the Snaptics project | 07/08/2026 | 07/08/2026 | |

### Week 13 Achievements

* Successfully deployed the project to an enterprise-standard AWS environment.
* Smoothly operated a true Cloud-native architecture (Serverless & Containers).
* Definitively resolved issues related to networking, security certificates, and Domains.
* Concluded the 13-week FCJ Workforce journey successfully with a complete product.
