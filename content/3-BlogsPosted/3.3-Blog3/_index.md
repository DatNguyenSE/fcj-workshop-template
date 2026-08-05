---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# HARD-EARNED AWS LESSONS AND THE CLOUD-NATIVE MINDSET FROM A REAL-WORLD PROJECT

13 weeks of interning and grinding on the Snaptics project has truly completely transformed my programming mindset. "Works on my machine" becomes utterly meaningless the moment you step into the Cloud environment!

Specifically, manually integrating Amazon S3 into the .NET Backend to build the Invoice Scanning flow provided me with some "hard-earned" but incredibly valuable lessons about the Cloud-Native mindset.

### The Most Memorable "Aha Moments"

- **Decoupling Compute and Storage**
  - Previously, whenever I built an image upload form, I would save the file straight into the `/wwwroot` folder of the server. Moving to the Cloud, I realized doing that is suicidal! The server bloats, and backups become difficult.
  - I learned how to push all invoice image files up to Amazon S3, and the Backend Database only saves a lightweight URL. The processing logic is separate, the storage repository is separate—it's incredibly unburdening!

- **Wrestling with AWS SDK for .NET**
  - The feeling of writing C# code to successfully call an API and push a file directly into an S3 bucket for the first time was truly fantastic. I started getting used to interacting with infrastructure via code instead of clicking around the Management Console.

- **The Magic of Pre-signed URLs**
  - This was my biggest "Aha Moment"! Initially, I had a huge headache: *"How do I keep my S3 Bucket completely Private (no public access), but still allow the user's Angular Frontend to load the invoice images to view?"*
  - The answer was **Pre-signed URLs**. My Backend code silently uses an Access/Secret key pair to generate a temporary link that lives for exactly 15 minutes, then tosses it to the Frontend. It's 100% secure and convenient—no need to download the image to the server and then stream it to the Frontend!

- **Learning IAM and "Least Privilege" the Hard Way**
  - At first, out of convenience, I just granted `S3FullAccess` permissions to the IAM User used in the code. As a result, the code review caught it and forced me to tear it down and redo it.
  - I had to sit down and tightly configure a JSON Policy: Only allowing `PutObject` and `GetObject` permissions specifically for the `snaptics-invoices-xyz` Bucket. It was a bit tedious initially, but I slept very soundly knowing the system was incredibly secure.

- **Stumbling over CORS (Cross-Origin Resource Sharing)**
  - After finishing the code, the Frontend called the image URL and got slapped in the face by the browser with a glaring red CORS error. I learned the hard way that Cloud security doesn't just reside in the Backend; you also have to set up CORS Policies right on the S3 Bucket so the browser "recognizes" the Frontend's domain name.

- **The Cost Optimization Problem**
  - Invoice data generates a lot of garbage (blurry images, failed upload images). If left alone, S3 will charge for permanent storage. I had to immediately set up S3 Lifecycle Policies to automatically "take out the trash," deleting temporary images after 7 days.

### Summarizing the Journey

This internship didn't just teach me how to use a few AWS services. It tore down and rebuilt my mindset.

I realized Cloud Computing isn't just about renting a virtual machine and dumping old code onto it to run. Cloud-Native is an art of design: security from its inception (IAM), cost optimization from the start (Lifecycle), decoupling functionalities (S3 + EC2 + SQS), and secure sharing (Pre-signed URLs).

These practical combat experiences are priceless baggage, creating massive momentum for me to continue pursuing the path to becoming a professional Fullstack / Cloud Engineer!

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

### References

The knowledge summarized in this article was learned from:

- Participation in a real-world project during the internship.
- AWS Official Documentation  
  https://docs.aws.amazon.com/