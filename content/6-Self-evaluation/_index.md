---
title: "Self-Assessment"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### SELF-ASSESSMENT

During my internship from **May 11, 2026 to August 07, 2026**, I worked mainly as a Backend Developer on an expense management project. I was still at an entry level with AWS, so my main goal was to understand the fundamentals, follow good practices and gradually connect backend development with cloud infrastructure.

I worked with a .NET 10 Web API, SQL Server and Entity Framework Core. Alongside the application work, I practiced AWS services and deployment concepts through guided labs and project tasks. This helped me understand that a backend feature also needs secure configuration, reliable storage, monitoring and a suitable deployment environment.

### Key Contributions & Technical Highlights

#### 1. Backend API and Database Development

* Created and updated .NET 10 APIs for users, categories, income sources, budgets and expense records.
* Used Entity Framework Core to model SQL Server data, define relationships and manage migrations.
* Implemented validation, authorization and basic error handling so each user could work with the correct data.
* Tested API flows with normal and invalid input instead of checking only the successful case.

#### 2. Authentication and Cloud Service Integration

* Built registration and login flows with JWT authentication and protected private endpoints.
* Integrated Amazon S3 for receipt and document images instead of keeping files only on local storage.
* Studied Azure Document Intelligence and Google Gemini for OCR and expense extraction, then mapped the results into backend entities.
* Used AWS SQS and a background worker to keep slow AI processing away from the main upload request, with SignalR for status updates.

#### 3. AWS Best Practices and Cloud Foundations

* Practiced least-privilege IAM access, secure handling of configuration and avoiding API keys in source code.
* Used AWS Systems Manager Parameter Store as an introduction to externalized application configuration.
* Learned the purpose of S3, SQS, VPC, subnets, NAT Gateway, ECS Fargate and Application Load Balancer in a simple cloud architecture.
* Built a Docker image for the backend and followed the basic flow of deploying a container to AWS.

### Self-Assessment

I evaluate myself honestly as a beginner who has made good progress but still needs more hands-on experience with production systems.

| No. | Criteria | Rating | Comments |
| :-: | :--- | :-: | :--- |
| 1 | **Professional Knowledge** | Developing | Have a good foundation in .NET backend development and basic knowledge of AWS services, but I am not yet confident with complex cloud architectures. |
| 2 | **Ability to Learn** | Good | Can follow documentation, ask focused questions and apply feedback to new backend or AWS tasks. |
| 3 | **Proactiveness** | Developing | Try to investigate errors before asking for help; I need to become more proactive in proposing complete technical solutions. |
| 4 | **Discipline** | Good | Followed the internship schedule, rules and weekly worklog requirements. |
| 5 | **Communication** | Good | Reported progress and problems to mentors, although I still need to explain technical details more concisely. |
| 6 | **Teamwork** | Good | Coordinated with team members on API contracts, testing and deployment tasks, and accepted review comments. |
| 7 | **Problem Solving** | Developing | Can debug common API, database and configuration issues; more production troubleshooting practice is needed. |
| 8 | **Project Contribution** | Good | Contributed backend APIs, cloud integrations and deployment preparation for the main expense management flow. |

### AREAS FOR IMPROVEMENT

* **Strengthening AWS foundations:** Continue practicing IAM, VPC, networking, monitoring, storage and cost control. I need to understand why a service is selected, not only remember the steps in a lab.

* **Improving production deployment skills:** Practice Docker, ECS, load balancing, DNS, HTTPS, CI/CD, logs and rollback in small complete environments.

* **Applying security and reliability practices:** Learn more about secret management, least privilege, backup, encryption, validation, retries and failure handling for backend services.

* **Growing as a Backend Developer:** Improve API design, automated testing, database performance and clean code, while continuing to communicate clearly with mentors and teammates.
