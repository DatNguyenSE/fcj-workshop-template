---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# DISSECTING A HIGH-TRAFFIC E-COMMERCE WEBSITE ARCHITECTURE ON AWS

Every Flash Sale or Black Friday, the familiar question pops up in the minds of developers: *"How do massive e-commerce sites avoid crashing when millions of people log on simultaneously to hunt for deals?"*. If they just used a single server plugged directly into a database like we often do in school projects, the system would undoubtedly go up in smoke in the first second!

AWS provides a highly standardized Cloud-Native solution stack. By assembling Network, Compute, Cache, and Database services together, we can completely build a "monster" load-bearing e-commerce system. Let's dissect this architecture together!

### The Big Picture Architecture

The data flow entering the system passes through defense and distribution layers as follows:

**User → Amazon Route 53 → Amazon CloudFront → AWS WAF → Application Load Balancer → Amazon ECS (AWS Fargate) → Amazon ElastiCache / Amazon Aurora Serverless v2**

Every "link" in the chain has a vital mission:

- **Amazon Route 53 (The Gatekeeper)**
  - Resolves domain names blazingly fast and routes users to the optimal, nearest server.

- **Amazon CloudFront (The Cache Shield)**
  - Distributes product images and CSS/JS files from Edge Locations. Users fetch images from the cache before they even touch the main server.

- **AWS WAF (The Security Knight)**
  - Stands right at the door, instantly blocking common web attacks like SQL Injection or XSS that aim to sabotage the system.

- **Application Load Balancer (ALB - The Coordinator)**
  - Receives valid traffic and distributes it evenly across backend containers, ensuring no single server becomes a "bottleneck."

- **Amazon ECS with AWS Fargate (The Serverless Mercenary)**
  - Runs the backend using containers. It dynamically scales out to match the required load without spending time configuring physical servers.

- **Amazon ElastiCache (The Ultra-fast Short-term Memory)**
  - Instantly remembers hot sale items. Instead of querying straight into the resource-heavy database, it fetches data from RAM and returns it to the user in milliseconds.

- **Amazon Aurora Serverless v2 (The Elastic Storage)**
  - The repository for the most crucial user and order information. Automatically scales compute resources up and down precisely following the shopping rhythm.

### The Eyes and Ears of the System: Monitoring and Alerts

For a massive system to stay healthy, it cannot lack eyes and ears.
**Amazon CloudWatch** acts like a security camera continuously monitoring the heartbeat (CPU, RAM, Error rate) of ECS and Aurora. The moment it spots an anomaly (e.g., CPU spiking to 90%), it triggers a **CloudWatch Alarm**, notifying **Amazon SNS** to fire off an SMS or Email, waking up the operations team in the middle of the night to handle the incident.

### My Hard-Earned Practical Lessons

Looking at this massive E-commerce architecture diagram and cross-referencing it with the Snaptics project I just built during my internship, I truly see a completely different picture!

The biggest lesson I realized is: **"Building a large-scale application isn't about writing a giant monolithic block of code, but the art of orchestrating Managed Services logically!"**. Instead of forcing the Backend Server to do everything from security checks, serving images, to querying the database, the AWS architecture divides and conquers:
- Need Caching? Let CloudFront and ElastiCache handle it.
- Need to block Hacks? Hand it over to WAF.
- Need load balancing? Put an ALB in front.
- Need to process logic? Then it's ECS Fargate's turn to speak up.

This architecture helped me break free from the outdated monolithic mindset and taught me how to truly think "Cloud-Native": Decoupling components so that each service does exactly what it specializes in best.

### Illustration

<div style="text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.2-Blog2/blog2.jpg"
         alt="E-commerce website architecture"
         style="width: 900px; height: auto; border-radius: 8px;">
    <p>A scalable E-commerce website architecture on AWS.</p>
</div>

### References

For a deeper understanding, you can read the highly detailed original documentation from AWS:

- **Guidance for Web Store on AWS**
  https://docs.aws.amazon.com/solutions/web-store-on-aws/

- **Guidance for Building a Containerized and Scalable Web Application on AWS**
  https://docs.aws.amazon.com/solutions/building-a-containerized-and-scalable-web-application-on-aws/