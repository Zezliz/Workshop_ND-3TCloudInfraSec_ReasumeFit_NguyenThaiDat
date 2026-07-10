---
title: "Setting Up Relational Database (RDS)"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

### 5.6.1. Configure Secrets Manager

1. Access **AWS Secrets Manager**, create a secret named `ResumeMatching-Secrets` to store sensitive information.
![Create Secret](/images/5-Workshop/Tao_Secret.jpg)

2. Configure the **Secret value** section with Key/value pairs such as `HOST`, `PORT` (`5432`), `USERNAME`, `PASSWORD`, and the `OPENAI_API_KEY` for the application.
![Update Secrets Manager](/images/5-Workshop/Cap_nhat_Secrets_manager.jpg)

### 5.6.2. Create RDS PostgreSQL

1. Access the **RDS** interface, select **Subnet groups**, and create a subnet group named `resumematching-dbsubnetgroup` pointing to the VPC and grouping the 2 subnets `Private-DB-A` and `Private-DB-B` together.
![Create DB Subnet Group](/images/5-Workshop/Tao_DB_Subnet_Group.jpg)

2. Proceed to initialize the Database (DB identifier: `resume-matching-db`) with the Engine set to **PostgreSQL** and the instance class set to `db.t3.micro`.
![Create RDS Database](/images/5-Workshop/Tao_RDS_database.jpg)

3. Upon successful creation, copy the Database Endpoint and paste it into the `HOST` key in Secrets Manager.
