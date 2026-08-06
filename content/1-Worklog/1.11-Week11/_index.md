---
title: "Week 11 Worklog"
date: 2026-07-20
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives

* Develop the Administration subsystem (Admin Panel) with an independent UI.
* Establish a strict Role-Based Access Control system.
* Integrate Background Jobs monitoring tools (Hangfire).
* Optimize system error screens.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
|------|-----------|-------------|----------------|---------------|
| Monday | **Admin UI:** <br> - Build a separate Layout for Admins <br> - Configure Angular CanActivate <br> - Build User Management page (Search, Status Filter) | 20/07/2026 | 20/07/2026 | |
| Tuesday | **Role-Based Access Control:** <br> - Configure Authorization `[Authorize(Roles)]` on .NET <br> - Differentiate Authentication and Authorization <br> - Test and block unauthorized access | 21/07/2026 | 21/07/2026 | |
| Wednesday | **Ticket Management (Admin):** <br> - Build Admin-side Ticket list UI <br> - Integrate user response APIs <br> - Handle user account lock/unlock flows | 22/07/2026 | 22/07/2026 | |
| Thursday | **Hangfire Background Jobs:** <br> - Install the Hangfire library <br> - Configure Dashboard for monitoring background Jobs <br> - Convert SQS Workers to the Hangfire model | 23/07/2026 | 23/07/2026 | |
| Friday | **Hangfire Security:** <br> - Write Authorization Filter for the Dashboard <br> - Restrict access strictly to Admins <br> - Design error notification pages (404, 403) | 24/07/2026 | 24/07/2026 | |

### Week 11 Achievements

* Successfully deployed the Admin subsystem with essential features.
* Multi-layered RBAC authorization system operating efficiently.
* Visually and securely managed Background Jobs via Hangfire.
* Perfected the Error Handling experience for users.
