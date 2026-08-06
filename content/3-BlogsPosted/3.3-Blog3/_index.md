---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# LESSONS ON CLOUD-NATIVE MINDSET FROM A REAL-WORLD PROJECT

The 13-week journey of interning and working on the Snaptics project has brought me valuable practical experience. Integrating infrastructure services in a Cloud environment requires a significant shift in software development mindset, moving beyond the limits of conventional programming on a personal machine.

Specifically, the process of integrating the Amazon S3 storage service into the .NET Backend for the Invoice Scanning feature flow noticeably strengthened my grasp of Cloud-Native design principles.

### Key Technical Highlights

- **Decoupling Compute and Storage**
  - In legacy models, uploaded files are often stored locally right on the application server (e.g., the `/wwwroot` folder). When the system scales, this makes capacity management and backups difficult.
  - Applying a Cloud-Native mindset, I used Amazon S3 to store invoice files, while the Backend Database only saves the mapped URL. Separating the processing logic from the storage repository makes the application lightweight, easily scalable, and optimizes resources.

- **Interacting with Infrastructure via AWS SDK for .NET**
  - This process familiarized me with configuring and controlling AWS services entirely through source code instead of manual operations on the Management Console, serving as an initial step into system administration automation.

- **Ensuring Security with Pre-signed URLs**
  - A requirement arose: How to keep the S3 Bucket completely Private for security, yet allow the Angular Frontend to download and display invoice images to the user?
  - The optimal solution was using **Pre-signed URLs**. The Backend application uses an Access/Secret key pair to generate a time-limited access link (e.g., 15 minutes). As a result, images are distributed safely, ensuring absolute data security, and eliminating the need to download data to the Server before transmitting it to the Frontend.

- **Applying the Least Privilege Principle with IAM**
  - Initially, I tended to grant broad permissions (e.g., `S3FullAccess`) to the IAM User for programming convenience. The cross-review process revealed this as a major security risk.
  - I practiced tightening the JSON Policy, granting `PutObject` and `GetObject` permissions strictly for a specific S3 Bucket (`snaptics-invoices-xyz`). This operation keeps the system secure and minimizes the risk of data leakage.

- **Resolving CORS Security Issues**
  - During deployment, the image retrieval flow using Pre-signed URLs was blocked by the browser due to a CORS error. I realized that Cloud security requires synchronized configuration across all layers. Properly setting up the CORS Policy on the S3 Bucket resolved the issue, allowing secure communication between independent domains.

- **Data Lifecycle Management and Cost Optimization**
  - Garbage data (blurry images, upload errors) is continuously generated. If unmanaged, S3 will incur wasteful storage costs. I configured S3 Lifecycle Policies to automatically delete temporary image files after 7 days, a small operation that brings long-term operational value.

### Summarizing the Journey

The internship not only helped me improve my skills in using AWS tools but, more importantly, reshaped my system design thinking.

Cloud-Native is a comprehensive approach: prioritizing security by design (IAM), cost optimization (Lifecycle), decoupled modular design (S3 + EC2 + SQS), and secure resource sharing (Pre-signed URLs). These practical knowledge and experiences will form a solid foundation for me to continue developing on the path to becoming a professional Cloud / Fullstack Engineer.

### Illustration

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 24px; margin-top: 20px;">

  <div style="width: 420px; text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.3-Blog3/blog3.jpg"
         alt="Amazon S3 Architecture"
         style="width:100%; height:260px; object-fit:contain; background:#fafafa; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Cloud-Native architecture integrating Amazon S3 into the Backend app.</p>
  </div>

  <div style="width: 420px; text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.3-Blog3/blog3.1.jpg"
         alt="Amazon S3 Pre-signed URL"
         style="width:100%; height:260px; object-fit:contain; background:#fafafa; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.15);">
    <p>Implementing Amazon S3 Pre-signed URLs using AWS SDK for .NET.</p>
  </div>

</div>