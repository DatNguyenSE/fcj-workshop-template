---
title: "Week 9 Worklog"
date: 2026-07-06
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives

* Retrieve the Gemini API Key from AWS Parameter Store and securely integrate the Google Gemini 2.5 Flash SDK into the .NET Backend.
* Build the Backend AI Insight Assistant API flow to provide smart financial consultations based on user spending data.
* Build the Fullstack Spending Analysis & Reports feature.
* Develop Backend statistics APIs and integrate visual charts with **Ngx-charts / Chart.js** on the Frontend (Angular).
* Design a flexible time filter (day, week, month, quarter, year) and handle real-time data query logic from the SQL Server database.
* Design a modern Chatbot interface on Angular (Conversation history sidebar, main chat window, query input box).
* Implement real-time messaging flows, AI typing indicator animations, and suggested prompt chips.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Learning Resources |
| --- | --- | --- | --- | --- |
| Monday | - Securely fetched `GeminiApiKey` from AWS Systems Manager via `IConfiguration` in the .NET Backend.<br>- Integrated Gemini 2.5 Flash SDK to build the financial consultant AI Chatbot API.<br>- Built APIs to store user conversation histories in the database. | 06/07/2026 | 06/07/2026 | [Google Gemini API Docs](https://ai.google.dev/docs) |
| Tuesday | - Designed Database schema and wrote Backend APIs for general spending statistics analysis.<br>- Designed the layout of the Spending Analysis & Reports page on Angular.<br>- Integrated **Ngx-charts / Chart.js** to render budget allocation Pie Charts and overview Bar Charts. | 07/07/2026 | 07/07/2026 | [Ngx-charts Guide](https://swimlane.github.io/ngx-charts/) |
| Wednesday | - Built APIs for tracking spending trends over time.<br>- Developed Line Charts on the Frontend and a time filter toolbar (Week, Month, Quarter, Year).<br>- Optimized SQL queries to quickly calculate percentage increase/decrease compared to the previous period. | 08/07/2026 | 08/07/2026 | [Financial Chart Patterns](https://dribbble.com/) |
| Thursday | - Designed the AI Assistant Chat Component UI structure on Angular.<br>- Configured Frontend to call AI Insight APIs and display Message Bubbles distinguishing User and AI.<br>- Built visual AI typing indicator animations. | 09/07/2026 | 09/07/2026 | [Chat Interface UI Patterns](https://uicoach.io/) |
| Friday | - Designed a list of sample Prompt Chips on the Chatbot start screen.<br>- Configured a Dead Letter Queue (DLQ) flow for SQS as a fallback for AI API Timeout errors.<br>- Tested mobile responsiveness for reporting charts and the AI Chat interface. | 10/07/2026 | 10/07/2026 | [AI Chatbot UX Best Practices](https://uxplanet.org/) |

### Week 9 Achievements

* Successfully and securely integrated Gemini 2.5 Flash into the Backend system using the API Key fetched from AWS.
* Completed the AI Assistant integration flow and the modern Chat Interface.
* Built realistic typing animations providing a natural interaction feel with the AI.
* Completed the Spending Analysis feature from Backend APIs to Frontend with dynamic Ngx-charts.
* Developed a versatile report time filter and efficient data querying from the database.
* Visually displayed spending trend comparisons (increase/decrease) for financial periods.
* Integrated sample Prompt Chips to help users easily start conversations with the AI.
* Ensured financial charts and the AI chat interface are 100% responsive on mobile screens.
