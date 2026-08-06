---
title: "Week 5 Worklog"
date: 2026-06-08
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives

* Coordinate with the team to build core components for the Snaptics system.
* Design the Database Schema, identifying tables, relationships, and data flows.
* Build the Backend Authentication APIs and standardize Request/Response structures.
* Initialize the Frontend SPA using Angular and configure Design System Tokens.
* Integrate and test the Login/Register APIs between the Frontend and Backend.
* Coordinate fixing integration bugs (CORS, Tokens, Validations).

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Detailed Database Schema design (Tables: Users, Wallets, Transactions, Categories).<br>- **Afternoon:** Setup DBContext using Entity Framework Core. Encountered a Migration conflict when the team created tables simultaneously; had to reset the local DB, consolidate code, and re-run the master Migration file. | 08/06/2026 | 08/06/2026 | [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/) |
| Tuesday | - **Morning:** Built a standard API Response structure (`ApiResponse<T>`) for the entire Backend system.<br>- **Afternoon:** Initialized the Angular SPA project. Installed Tailwind CSS. Structured directories (core, shared, features) and created basic Components (Header, Sidebar). | 09/06/2026 | 09/06/2026 | [Angular Folder Structure](https://angular.io/guide/styleguide) |
| Wednesday | - **Morning:** Coded Backend APIs for the Authentication flow (Login, Register) and JWT Token generation.<br>- **Afternoon:** Tested Auth APIs successfully with Postman. Integrated the Login form on Angular to call the API. The browser threw a glaring red CORS error; fixed it by reconfiguring `builder.Services.AddCors()` in the Backend. | 10/06/2026 | 10/06/2026 | [CORS in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/security/cors) |
| Thursday | - **Morning:** Designed the Main Layout page of the application and the Auth UI (polished Login/Register Forms).<br>- **Afternoon:** Handled storing JWTs in LocalStorage on the Frontend. Got an error extracting the wrong payload from the Token; debugged and rewrote the base64 JWT decoding logic in Angular. | 11/06/2026 | 11/06/2026 | [JWT Authentication](https://jwt.io/) |
| Friday | - **Morning:** Built basic APIs for CRUD operations on Categories and personal Wallets.<br>- **Afternoon:** End-of-week task handover. Finished the Forgot Password API. Updated the Auth API documentation on Swagger for cross-testing by the team. | 12/06/2026 | 12/06/2026 | [Swagger/OpenAPI](https://swagger.io/) |

### Week 5 Achievements

* Completed Database design and successfully deployed Entity Framework Core.
* Successfully initialized the Angular project, established standard folder architecture, and integrated Tailwind CSS.
* Finished building the JWT Authentication flow for the Backend.
* Overcame classic system integration bugs: CORS Policy errors, JWT parsing errors, and migration conflicts.
* Finalized the Auth UI and Main Layout, ensuring smooth API connectivity from the Client to the Server.
