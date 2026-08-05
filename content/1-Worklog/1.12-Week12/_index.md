---
title: "Week 12 Worklog"
date: 2026-07-27
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives

* Review Swagger API documentation, ensuring complete synchronization of Endpoints, Request Bodies, and Response Formats between the Backend and Frontend.
* Build and update the Frontend API Service layer using **Angular HttpClient** and **Angular HttpInterceptor** to automatically attach Bearer Access Tokens (JWT) and centrally handle expired token errors.
* Completely remove mock data services and ensure all features fetch real data from the Backend API.
* Comprehensively integration test APIs: Auth (Login/Register), Transactions, Wallets, Budgets, Invoice Scanning, Notifications, AI Insight, Support Tickets, and Admin APIs.
* Smoothly handle UI states: Skeleton Loading Components, Toast notifications for errors/success, Network Errors, and Empty States.
* Fine-tune Angular Reactive Form Validation and fix mobile scrolling glitches/misaligned Navigation bars.
* Fix responsive bugs on the Settings page and resolve issues with the account dropdown menu being obscured or frozen.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Learning Resources |
| --- | --- | --- | --- | --- |
| Monday | - Detailed review of the .NET Backend Swagger UI documentation.<br>- Cross-checked the entire list of Endpoints, HTTP methods (GET, POST, PUT, DELETE), JSON data structures, and Error Codes.<br>- Built Angular `AuthInterceptor` (`HTTP_INTERCEPTORS`) to attach JWT Bearer Tokens to Request Headers and centrally handle 401 Unauthorized, 403 Forbidden, and 500 Server Errors via RxJS `catchError`. | 27/07/2026 | 27/07/2026 | [Angular HttpClient Guide](https://angular.io/guide/http)<br>[Angular Interceptors](https://angular.io/guide/http-intercept-requests-and-responses) |
| Tuesday | - Completely removed mock data and connected real APIs via Angular Services for Auth, overall Dashboard, Transaction List, and Spending Category Management.<br>- Updated CORS policies on the Backend to allow Frontend API calls.<br>- Built Skeleton Loading effects for smooth UI rendering while waiting for API data responses via RxJS Observables. | 28/07/2026 | 28/07/2026 | [RxJS Observables Guide](https://rxjs.dev/guide/observable) |
| Wednesday | - Integrated and tested API flows for complex features: Invoice Scanning (sending files via S3 Gateway Endpoint and receiving OCR), Personal/Family Wallet Management, Budgets, AI Insight Chatbot, and Support Tickets.<br>- Integrated Toast notification service (`Ngx-Toastr`) to show instant alerts for successful or failed user actions. | 29/07/2026 | 29/07/2026 | [Ngx-Toastr Guide](https://ngx-toastr.vercel.app/) |
| Thursday | - Integrated APIs for the Admin Panel area (User Management, Ticket Management, System Notifications, and Hangfire Jobs).<br>- Fixed layout breaking responsive bugs on the Account Settings Page when resizing browser windows.<br>- Resolved issues with the Account Dropdown Menu being cut off or not closing when clicking outside. | 30/07/2026 | 30/07/2026 | [UI Bug Fixing Techniques](https://developer.mozilla.org/) |
| Friday | - Fixed mobile Navigation bar alignment/jittering issues during page scrolling (locked navigation bar using `position: sticky/fixed` and handled CSS overflow).<br>- Re-tested Form Validation on both Frontend and Backend, ensuring transparent error displays for invalid data inputs.<br>- Reviewed UI/UX consistency and tested overall system API connection stability. | 31/07/2026 | 31/07/2026 | [Mobile Navigation CSS Fixes](https://css-tricks.com/) |

### Week 12 Achievements

* Completed Swagger API review and ensured 100% synchronization of integrated endpoints between Backend and Frontend.
* Successfully developed Angular API Services & HttpInterceptors to manage HTTP connections, automatically handle JWT Access Tokens, and centrally process network errors via RxJS.
* Completely eliminated Mock Data and successfully replaced it with real Backend API data across the entire Snaptics application.
* Delivered a highly responsive UI with Skeleton Loading states, transparent Toast Notifications, and thoughtful empty data handling.
* Permanently resolved mobile Navigation bar scrolling and layout jittering issues.
* Fully fixed responsive display bugs on the Settings page and Account Dropdown Menu.
* Ensured Form Validation error-checking systems operate accurately and securely on both Frontend and Backend layers.
* The entire Snaptics system reached a high level of completion, operates smoothly, and is ready for the Production packaging phase.
