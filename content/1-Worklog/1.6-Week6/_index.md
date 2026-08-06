---
title: "Week 6 Worklog"
date: 2026-06-15
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives

* Build the Backend CRUD APIs for the core business logic: Transactions.
* Design and code the Overview Dashboard UI to display total balances and preliminary charts.
* Integrate the Frontend to call APIs and display the transaction list with Pagination.
* Implement Route Guards on the Frontend (Angular AuthGuard) to restrict access to logged-in users only.
* Write an HttpInterceptor to automatically attach Tokens and handle 401 Unauthorized errors.
* Strictly handle data validation errors from the Frontend all the way down to the Backend.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Built Backend APIs (Create, Read, Update, Delete) for the Transactions table.<br>- **Afternoon:** Wrote optimized LINQ queries to fetch paginated Transaction lists filtered by Wallet, ensuring fast API response times with large datasets. | 15/06/2026 | 15/06/2026 | [EF Core LINQ](https://learn.microsoft.com/en-us/ef/core/querying/) |
| Tuesday | - **Morning:** Designed the Overview Dashboard UI (displaying Total Balance cards, monthly spending) in Angular.<br>- **Afternoon:** Integrated the Transaction list API call. Got a bug showing incorrect date and currency formats; fixed it completely using Angular Pipes (`DatePipe`, `CurrencyPipe`). | 16/06/2026 | 16/06/2026 | [Angular Pipes](https://angular.io/guide/pipes) |
| Wednesday | - **Morning:** Implemented the Route protection feature (`AuthGuard`) in Angular, blocking unauthenticated users from viewing the Dashboard.<br>- **Afternoon:** Wrote an `HttpInterceptor` to automatically inject the `Bearer Token` into HTTP Headers. Handled the logic to automatically kick users back to the Login page (Logout) when the API returns a `401 Unauthorized` error (Expired Token). | 17/06/2026 | 17/06/2026 | [Angular Interceptors](https://angular.io/api/common/http/HttpInterceptor) |
| Thursday | - **Morning:** Coded the UI for the Add/Edit/Delete Transaction Form. Caught validations for mandatory fields (Amount must be > 0, Category cannot be empty).<br>- **Afternoon:** Tested the Transaction creation flow from the Frontend all the way to the DB. Discovered users could bypass UI validation and send negative amounts via API; immediately added strict validation checks on the Backend. | 18/06/2026 | 18/06/2026 | [Angular Reactive Forms](https://angular.io/guide/reactive-forms) |
| Friday | - **Morning:** Created the Spending Category management UI (selecting Icons, choosing Hex colors).<br>- **Afternoon:** Ran device emulators to test UI, fixed bugs where the layout broke margins on phone screens (Mobile Responsive). Cleaned up commits and pushed to the `develop` branch. Closed Sprint 2. | 19/06/2026 | 19/06/2026 | [Tailwind Responsive](https://tailwindcss.com/docs/responsive-design) |

### Week 6 Achievements

* Built and finalized the project's most core API: Transaction Management.
* Fixed data display bugs (Date, Currency) on the Frontend.
* Successfully established an internal firewall for the Angular application using `AuthGuard` and `HttpInterceptor`.
* Synchronized Validation logic in both directions (Frontend Form and Backend API), blocking garbage data.
* Ensured the Dashboard and Transaction Forms are completely responsive on mobile device screens.
