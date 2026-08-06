---
title: "Week 9 Worklog"
date: 2026-07-06
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives

* Integrate Generative AI using the Google Gemini API to analyze user financial data.
* Build a Backend flow to extract monthly transaction data, packaging it into a Prompt Context to send to the AI.
* Build the Spending Analysis & Reporting feature using the `ngx-charts` library on Angular.
* Optimize SQL queries on the Amazon RDS system to ensure fast loading of report data.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - **Morning:** Registered a Google Gemini API Key. Placed the key into the AWS Parameter Store for security, similar to the Azure approach.<br>- **Afternoon:** Installed the `Google.GenerativeAI` SDK for the Backend. Wrote basic Prompt Engineering to make the AI understand the user's transaction array data. | 06/07/2026 | 06/07/2026 | [Google Gemini API Docs](https://ai.google.dev/docs) |
| Tuesday | - **Morning:** The AI often returned verbose answers with messy markdown formatting. Refined the Prompt, using a force format technique to compel the AI to return strict JSON or concise bullet points.<br>- **Afternoon:** Finalized the `/api/ai/insights` API returning financial advice (e.g., warning about overspending on Dining). Integrated a simple Chatbot UI on Angular. | 07/07/2026 | 07/07/2026 | [Prompt Engineering Guide](https://www.promptingguide.ai/) |
| Wednesday | - **Morning:** Wrote SQL Queries (integrated via EF Core) using `GroupBy` to calculate total spending by Category for the month.<br>- **Afternoon:** Tested the Report API and found the response time quite slow when seeding 10,000 rows of test data. Researched and created Indexes on RDS for the `TransactionDate` and `CategoryId` columns; speed improved significantly. | 08/07/2026 | 08/07/2026 | [SQL Server Indexing](https://learn.microsoft.com/en-us/sql/relational-databases/indexes/sql-server-index-design-guide) |
| Thursday | - **Morning:** Installed the `ngx-charts` library for the Frontend. Coded the Pie Chart UI to display the monthly spending structure.<br>- **Afternoon:** Coded the Bar Chart comparing 6-month spending. Got a bug where the chart wasn't Responsive and overflowed the screen on mobile devices; debugged and wrapped it in CSS Flexbox/Grid containers to fix it. | 09/07/2026 | 09/07/2026 | [Ngx-charts Documentation](https://swimlane.gitbook.io/ngx-charts/) |
| Friday | - **Morning:** Completely assembled the Spending Analysis UI, combining visual Charts at the top and AI advisory Insights at the bottom.<br>- **Afternoon:** E2E combination flow testing: User changes month to view charts -> System reloads data -> Clicks "Ask AI for advice" -> Backend sends the new data to query the AI. The flow ran smoothly; committed and pushed to the Repo. | 10/07/2026 | 10/07/2026 | [Angular Component Interaction](https://angular.io/guide/component-interaction) |

### Week 9 Achievements

* Successfully integrated Generative AI (Gemini Flash), bringing a unique, smart feature to the system (AI Insights).
* Mastered basic Prompt Engineering skills, forcing the AI's output format for easy backend parsing.
* Successfully optimized Database (RDS) performance through Indexing techniques, well-serving the data-heavy Reporting features.
* Proficiently used the ngx-charts graphing library and completely resolved Responsive issues on mobile devices.
