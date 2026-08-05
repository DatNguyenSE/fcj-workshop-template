---
title: "Week 7 Worklog"
date: 2026-06-29
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives

* Migrate the system database from local storage to Amazon RDS.
* Create a DB Subnet Group and deploy RDS in Private Subnets across multiple Availability Zones.
* Configure the RDS Security Group to allow access only from the Backend and disable Public Access.
* Migrate the schema and data, then update the Backend connection string.
* Replace local image storage with Amazon S3 and configure the required permissions.
* Connect the Backend to RDS and S3 and test database and image operations.
* Document the AWS foundation for the remaining cloud deployment work in later weeks.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Learning Resources |
| --- | --- | --- | --- | --- |
| Monday | - Review the VPC architecture and identify Private Subnets for the database.<br>- Create a DB Subnet Group across multiple Availability Zones.<br>- Prepare Security Group rules for Backend-to-RDS connectivity. | 22/06/2026 | 22/06/2026 | [Amazon RDS in a VPC](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html) |
| Tuesday | - Create an Amazon RDS PostgreSQL instance with Public Access disabled.<br>- Configure the Security Group to allow database access only from the Backend Security Group.<br>- Test the Backend connection to RDS in the Private Subnet. | 23/06/2026 | 23/06/2026 | [RDS Security](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.html) |
| Wednesday | - Migrate the schema and data from the local database to RDS.<br>- Update Backend environment variables and the connection string.<br>- Test create, read, update, and delete operations on RDS. | 24/06/2026 | 24/06/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) |
| Thursday | - Create an S3 Bucket to replace local image storage.<br>- Configure the IAM permissions required by Backend to upload and retrieve images.<br>- Update Backend and test image upload, path storage, and image retrieval from S3. | 25/06/2026 | 25/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) |
| Friday | - Test the complete Backend flow with RDS and S3.<br>- Review access permissions, data integrity, and migration errors.<br>- Document the completed AWS foundation and summarize Week 7. | 26/06/2026 | 26/06/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)<br>[Amazon S3 Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) |

### Week 7 Achievements

* Deployed Amazon RDS PostgreSQL in Private Subnets with Public Access disabled.
* Created a DB Subnet Group and configured the Security Group to allow access only from Backend.
* Successfully migrated the schema and data from the local database to RDS.
* Updated the Backend to use RDS and tested database operations on the new instance.
* Replaced local image storage with S3 and configured Backend upload and retrieval permissions.
* Successfully tested the Backend connection to both RDS and S3.
* Documented the AWS foundation for deploying the remaining cloud components in later weeks.
