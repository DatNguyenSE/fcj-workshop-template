---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# ANALYZING A HIGHLY SCALABLE E-COMMERCE WEBSITE ARCHITECTURE ON AWS

During Flash Sales or major shopping events, e-commerce platforms often face massive traffic pressure. If the system architecture is simply an application connecting directly to a monolithic database, the system will easily suffer from overload and service disruption.

To solve this problem, AWS provides a standard Cloud-Native solution suite. By flexibly combining Networking, Compute, Caching, and Database services, we can build an e-commerce system with outstanding load-bearing and scaling capabilities. Let's analyze the components within this architecture.

### The Big Picture Architecture

Data flow entering the system is distributed and protected through the following service layers:

**User → Amazon Route 53 → Amazon CloudFront → AWS WAF → Application Load Balancer → Amazon ECS (AWS Fargate) → Amazon ElastiCache / Amazon Aurora Serverless v2**

Each service performs a specialized role:

- **Amazon Route 53 (Network Routing)**
  - Provides high-speed Domain Name System (DNS) resolution and routes users to the most optimal access points.

- **Amazon CloudFront (Delivery Optimization)**
  - Distributes static content (product images, CSS/JS files) from a global network of Edge Locations, helping reduce the load on the main server and accelerating page load speeds.

- **AWS WAF (Application Security)**
  - A web application firewall that promptly blocks common attacks (like SQL Injection, XSS), protecting the system from malicious traffic.

- **Application Load Balancer (Load Balancing)**
  - Evenly distributes valid traffic to backend processing containers, preventing localized bottlenecks.

- **Amazon ECS with AWS Fargate (Elastic Compute)**
  - A containerized backend execution environment (Serverless). The system automatically scales compute resources based on actual demand without needing to manage physical server infrastructure.

- **Amazon ElastiCache (High-speed Caching)**
  - Temporarily stores frequently accessed data (e.g., hot products, shopping carts). Reading data from RAM provides extremely fast responses and relieves query pressure on the main database.

- **Amazon Aurora Serverless v2 (Elastic Database)**
  - Manages core data (users, orders). The ability to automatically scale compute resources in a fraction of a second helps the database gracefully handle sudden spikes in transaction volumes.

### Monitoring and Alert System

To maintain stability, the system integrates monitoring tools:
**Amazon CloudWatch** continuously collects performance metrics (CPU, RAM, error rates) of ECS and Aurora. When safety thresholds are breached, a **CloudWatch Alarm** is triggered, notifying the operations team via **Amazon SNS** for timely intervention.

### Practical Lessons Learned

When comparing this large-scale architectural diagram with the Snaptics project during my internship, I drew several lessons regarding system design thinking.

The biggest takeaway is: **The strength of a scalable system lies in the clever combination of Managed Services, rather than attempting to build a monolithic application to do everything.**
Decoupling components plays a crucial role:
- Caching is assigned to CloudFront and ElastiCache.
- Security and traffic filtering are assigned to WAF.
- Load balancing is handled by ALB.
- Business logic is completely centralized in ECS Fargate.

This mindset makes the system flexible, easier to maintain, and allows each component to scale independently based on actual operational needs.

### Illustration

<div style="text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.2-Blog2/blog2.jpg"
         alt="E-commerce website architecture"
         style="width: 900px; height: auto; border-radius: 8px;">
    <p>A scalable E-commerce website architecture on AWS.</p>
</div>

### References

To understand this architecture deeper, you can consult documentation from AWS:

- **Guidance for Web Store on AWS**
  https://docs.aws.amazon.com/solutions/web-store-on-aws/

- **Guidance for Building a Containerized and Scalable Web Application on AWS**
  https://docs.aws.amazon.com/solutions/building-a-containerized-and-scalable-web-application-on-aws/