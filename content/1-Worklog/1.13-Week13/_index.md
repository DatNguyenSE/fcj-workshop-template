---
title: "Week 13 Worklog"
date: 2026-08-03
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Week 13 Objectives

* Compile the application build (Build Production) for both Frontend and Backend.
* Deploy the static Frontend SPA onto the AWS Amplify platform.
* Package the Backend into a Docker Container and deploy it onto the Serverless Amazon ECS (Fargate) architecture behind a Load Balancer.
* Handle SSL/HTTPS security certificates using AWS Certificate Manager (ACM) to fix Mixed Content errors.
* Reconfigure network and WebSocket settings so the application runs stably on a real Domain.
* Practice **Workshop 5.6** lab: Clean up garbage resources and conclude the project.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Compiled the Frontend Production build using the `ng build --configuration production` command. Got hit with Strict Type Checking errors during build (ignored in dev but threw red errors in prod); spent time fixing all data types.<br>- **Afternoon:** Initialized the `Dockerfile` for the .NET Backend. Packaged it into a Docker Image and successfully pushed it to the Amazon ECR repository. | 03/08/2026 | 03/08/2026 | [Angular Deployment](https://angular.io/guide/deployment) |
| Tuesday | - **Morning:** Deployed the Frontend to the AWS Amplify service. Took quite a while to configure Rewrite/Redirect rules on Amplify for Angular routes (so hitting F5 wouldn't return a 404 error).<br>- **Afternoon:** Initialized the Cluster and Task Definition. Deployed the Backend to run on Amazon ECS (AWS Fargate) to avoid managing servers. | 04/08/2026 | 04/08/2026 | [Deploying Angular on AWS Amplify](https://aws.amazon.com/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/module-1/) |
| Wednesday | - **Morning:** Created an Application Load Balancer (ALB) as a request funnel for the Backend. Tested API calls from the Frontend (on Amplify) to the Backend (ALB).<br>- **Afternoon:** Web browser threw an HTTPS Mixed Content blocking error (Because the HTTPS Frontend tried calling the HTTP Backend). Registered a free SSL certificate from AWS Certificate Manager (ACM) and attached it to the ALB. Configured Route53 Domain routing to the ALB. | 05/08/2026 | 05/08/2026 | [ALB and HTTPS](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html) |
| Thursday | - **Morning:** Encountered an issue where Notifications weren't popping up. Debugged and found ALB wasn't routing WebSockets properly. Reconfigured Headers on the ALB, allowing `ws://` and `wss://` protocols to operate through the Custom Domain.<br>- **Afternoon:** Practiced Workshop 5.6 lab: Reviewed and cleaned up garbage resources (VPC Endpoints, Test EC2s, Test Buckets) on the AWS Console to avoid AWS charging money after the program ends. | 06/08/2026 | 06/08/2026 | [WebSockets on ALB](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html) |
| Friday | - **Morning:** The project went Live on the actual Domain. Took screenshots of the system UI. Finalized the Snaptics architecture internship report documentation.<br>- **Afternoon:** Final product demo with the team to review the flows. Officially submitted the project and successfully concluded the 13-week FCJ Workforce program. | 07/08/2026 | 07/08/2026 | [Project Submission Guidelines](#) |

### Week 13 Achievements

* Passed strict inspection rules during Production Build, properly packaging both Frontend and Backend.
* Completed deployment of a true Cloud-native system: Serverless Frontend (Amplify) and Containerized Backend (ECS Fargate).
* Definitively resolved specific errors upon migrating to a real environment: SPA 404 F5 errors, HTTPS Mixed Content errors, blocked WebSockets.
* Applied resource cleanup principles following the final lab to master cloud cost management.
* Excellently delivered and handed over the Snaptics project - the crystallization of Fullstack & AWS Cloud knowledge after 13 weeks of effort.
