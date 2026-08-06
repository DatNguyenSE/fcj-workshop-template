---
title: "Week 11 Worklog"
date: 2026-07-20
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives

* Design and build the Administrator Panel subsystem with a completely independent UI from the User side.
* Build a strict Role-Based Access Control (RBAC) flow on both the Frontend (Route Guards) and Backend (Attributes).
* Develop administrative features: User Management (Block/Unblock), Support Ticket Management.
* Integrate the Hangfire tool to visually manage Background Jobs (Background tasks) on a Dashboard.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Designed the specialized Admin Layout UI framework (Dark sidebar, separate Header). Installed `Angular CanActivate AdminGuard` to block normal Users from accessing `/admin`.<br>- **Afternoon:** Built the User Management feature. Paginated Users list API. UI features Search and Status filters (Active/Locked). | 20/07/2026 | 20/07/2026 | [Angular Route Guards](https://angular.io/guide/router-tutorial-toh#milestone-5-route-guards) |
| Tuesday | - **Morning:** Coded the Lock/Unlock user account feature from the Admin side. Tested by locking my own account; the result was the Session being invalidated and immediately kicked back to the login screen.<br>- **Afternoon:** Coded the Support Ticket Management feature on the Admin side. Supported viewing Ticket history and chatting back to Users directly on the dashboard. | 21/07/2026 | 21/07/2026 | [ASP.NET Core Authorization](https://learn.microsoft.com/en-us/aspnet/core/security/authorization/roles) |
| Wednesday | - **Morning:** Authorized Backend APIs by marking sensitive Controllers with the `[Authorize(Roles = "Admin")]` Attribute.<br>- **Afternoon:** Tested calling Admin APIs using a normal User's JWT Token. Got a `403 Forbidden` error instead of `401 Unauthorized`, thereby clearly understanding the practical difference between Authentication and Authorization. | 22/07/2026 | 22/07/2026 | [401 vs 403 Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/403) |
| Thursday | - **Morning:** Installed the Hangfire library on the Backend to manage Background Jobs (e.g., SQS invoice scanning Job, old DB garbage collection Job).<br>- **Afternoon:** Got a security flaw where the Hangfire Dashboard was exposed to the public. Researched and applied security (Hangfire Authorization Filter) allowing only Admin accounts to access. If not configured, anyone could access `/hangfire` and arbitrarily trigger Jobs. | 23/07/2026 | 23/07/2026 | [Hangfire Dashboard Security](https://docs.hangfire.io/en/latest/configuration/using-dashboard.html) |
| Friday | - **Morning:** Designed the 404 Not Found page and the System Maintenance Page as fallbacks for Server incidents.<br>- **Afternoon:** Reviewed all Roles/Permissions on the system. Fixed bugs regarding hiding/showing buttons based on UI Roles. Cleaned up code and prepared for the final integration phase. | 24/07/2026 | 24/07/2026 | [UX Error Pages](https://uxdesign.cc/how-to-design-404-page-12345) |

### Week 11 Achievements

* Successfully built an independent Admin Panel system, thoroughly managing Users and Tickets.
* Perfectly deployed a multi-layered RBAC mechanism: UI blocking via Angular Guards and Data access blocking via .NET Authorization.
* Successfully integrated Hangfire as a background Job monitor, ensuring the Dashboard is properly securely configured.
* Deeply understood and accurately handled 2 classic security error codes: 401 (Unauthenticated) and 403 (Unauthorized).
