---
title: "Week 12 Worklog"
date: 2026-07-27
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives

* Begin the "Code Freeze" phase, focusing on system cleanup and not adding new features.
* Completely synchronize API documentation (Swagger) between Backend and Frontend, removing all Mock Data.
* Perform UX Polishing like Skeleton Loaders, Empty States, and Toast Notifications.
* Thoroughly fix Responsive bugs (broken layouts) on mobile devices (Mobile/Tablet).
* Finalize the Authenticated Email sending feature using the Amazon SES service.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Began the system cleanup phase. Reviewed Swagger API documentation, ensuring complete synchronization of Endpoints and Request Bodies between Backend and Frontend.<br>- **Afternoon:** Deleted all simulated data (Mock Data Service) on the Frontend. Rewrote all Components to bind data directly from real Http Service APIs. | 27/07/2026 | 27/07/2026 | [Swagger API Documentation](https://swagger.io/) |
| Tuesday | - **Morning:** E2E tested feature flows. Got a blank Angular screen crash because the API returned a null data array (when the user had no transactions) and the Frontend didn't check for it.<br>- **Afternoon:** Added the Optional Chaining operator `?.` to HTML templates and designed Empty State screens (e.g., "You have no transactions, click Add") to guide users. | 28/07/2026 | 28/07/2026 | [Angular Optional Chaining](https://angular.io/guide/template-syntax) |
| Wednesday | - **Morning:** UX Polishing. Added shimmering Skeleton Loading Components to the UI instead of a blank white screen while waiting for slow APIs to load.<br>- **Afternoon:** Standardized the error notification system (Toast notifications). Caught Network Error or Server 500 crash scenarios to display friendly error messages instead of failing silently. | 29/07/2026 | 29/07/2026 | [UI Skeleton Screens](https://uxdesign.cc/what-you-should-know-about-skeleton-screens-a820c45a571a) |
| Thursday | - **Morning:** Fixed a series of Responsive UI bugs on Mobile: Navigation bar being covered, dropdown menus half-hidden.<br>- **Afternoon:** Fixed scrolling stutter bugs on iOS/Safari devices (added the `-webkit-overflow-scrolling: touch;` CSS property). Handled modal popups overflowing content. | 30/07/2026 | 30/07/2026 | [CSS Responsive Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design) |
| Friday | - **Morning:** Finalized the Set/Forgot Password features. Configured Amazon SES (Simple Email Service) to automatically send Emails containing OTP codes.<br>- **Afternoon:** Code Freeze. Reran basic test flows. Planned the Production deployment steps for the final week. | 31/07/2026 | 31/07/2026 | [Amazon SES Guide](https://docs.aws.amazon.com/ses/latest/dg/Welcome.html) |

### Week 12 Achievements

* Completed 100% real API wiring, completely eliminating temporary (Mock Data) code.
* Smoothly and safely handled Edge cases like Empty States, Network Errors, and Null Data.
* Elevated the application UX to a new level, making it friendly with Loading Skeletons and Toasts.
* Ensured excellent UI display without Responsive layout bugs on all mobile screen sizes.
* Readied a complete, "mature" Source Code base ready for Deployment in the final week.
