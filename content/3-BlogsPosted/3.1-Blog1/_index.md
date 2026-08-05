---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# How Did AWS Upgrade Amazon Cognito With Near-Zero Downtime?

Authentication is always the "heart" of any application. Just imagine the authentication system going down for a few minutes; hordes of users would be kicked out, unable to log in, unable to reset passwords... a total disaster! That's why when reading the case study about how AWS upgraded the entire core infrastructure of Amazon Cognito for millions of users with almost zero downtime, I was truly blown away.

This article dissects how AWS migrated the system to a next-generation architecture, bringing a slew of massive features while maintaining perfect "backward compatibility."

### The "High-Value" New Features

Amazon Cognito's new infrastructure brings truly impressive numbers and features:

- **High-throughput Performance**
  - Supports tens of millions of users within a single User Pool.
  - Handles thousands of transactions per second (TPS) effortlessly.
  - Highly optimized, drastically reducing latency during user logins.

- **Customer-managed Encryption Keys (CMK)**
  - Integrates seamlessly with AWS KMS.
  - Enterprises can now hold their own data encryption "keys."
  - Solves strict enterprise-level security compliance requirements.

- **Multi-Region Replication**
  - Automatically synchronizes User Profiles, Passwords, and configurations across multiple AWS Regions.
  - The system becomes highly resilient with lightning-fast Disaster Recovery capabilities.

### Core Architectural Principles

Instead of just piling on more code, AWS redesigned it from the ground up based on very clever principles:

- **Identity-first Design**
  - No more trying to do everything! Cognito now focuses 100% of its power on the identity problem, rather than trying to be a multi-purpose storage system.
  - This makes scaling much smoother.

- **Backward Compatibility**
  - Server upgrades are the server's business; customers don't have to change a single line of code!
  - All legacy authentication API flows still operate flawlessly.

- **Avoid One-way Doors**
  - The "no dead ends" principle: The new architecture allows for easy future upgrades without getting trapped by deeply hard-coded decisions.

### Migration Strategy: The Pinnacle of Operations

Reading about how AWS migrated hundreds of millions of user profiles without anyone noticing really showed me how intense global-scale architecture can be:

- **Shadow Mode Validation**
  - Testing in the shadows! User requests are run in parallel on both the old and new systems.
  - AWS closely scrutinizes Responses and Status Codes to ensure they match before daring to switch real traffic over.

- **Dual-write Architecture**
  - Writing data to both places simultaneously.
  - If the new system "sneezes," the old system immediately carries the team.

- **Anti-entropy Validation**
  - Continuously scanning and cross-referencing data between the two sides.
  - If there's a discrepancy, the old system (Source of Truth) immediately overwrites and standardizes the new system.

- **Incremental Rollout & Rollback**
  - Rolling out in small, phased clusters.
  - If a bug occurs, they rollback immediately—there's no such thing as going "all-in."

### My Hard-Earned Lessons

Reading this case study and looking back at our team's Snaptics project, I realize the mindset of "make it work" versus "make it resilient" are worlds apart!

Previously, when modifying a database or updating an API, I often had a "deploy and pray" mentality. But through this article, I learned a massive lesson about **Shadow Mode** and **Dual-write**. When you design a large system, you cannot treat your customers as guinea pigs. Upgrades must be invisible to the user.

The **Backward Compatibility** mindset also changed how I write APIs. I realized that every time I change a data structure, I must always ask myself: *"Will the current Frontend app calling this new API crash?"* Truly, this article didn't just teach technology; it taught me the mindset of a true Cloud Engineer!

### Illustration

<div style="text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.1-Blog1/blog1.jpg"
         alt="Amazon Cognito Next-generation Infrastructure"
         style="width: 800px; height: auto; border-radius: 8px;">
    <p>Amazon Cognito's Next-generation Infrastructure Architecture</p>
</div>

### Reference Article

This article was studied and summarized from the AWS Security Blog:

- **Amazon Cognito unlocks advanced capabilities with next-generation infrastructure**
- https://aws.amazon.com/blogs/security/amazon-cognito-unlocks-advanced-capabilities-with-next-generation-infrastructure/