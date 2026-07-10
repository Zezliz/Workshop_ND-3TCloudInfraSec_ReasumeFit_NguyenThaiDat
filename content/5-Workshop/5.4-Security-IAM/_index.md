---
title: "Setting Up Security and Access Management"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

### 5.4.1. Initialize Security Groups

Set up virtual firewalls to control inbound and outbound network traffic between resources at the protocol and port level.

1. **ALB Security Group** (`ResumeMatching-ALB-SG`): Open HTTP (`80`) and HTTPS (`443`) ports (TCP) with a Source of `0.0.0.0/0` to allow user web access.
![Create ALB Security Group](/images/5-Workshop/Tao_ALB_Security_Group.jpg)

2. **Backend Security Group** (`ResumeMatching-Backend-SG`): Configure Inbound rules to allow HTTP protocol on TCP ports. The Source is restricted to only receive traffic from `ResumeMatching-ALB-SG`.
![Create Backend Security Group](/images/5-Workshop/Tao_Backend_Security_Group.jpg)

3. **Worker Security Group** (`ResumeMatching-Worker-SG`): A firewall protecting the Worker Server that handles background tasks.
![Create Worker Security Group](/images/5-Workshop/Tao_Worker_Security_Group.jpg)

4. **Database Security Group** (`ResumeMatching-RDS-SG`): Open port `5432` (PostgreSQL). The Source only allows internal connections originating from the Backend and Worker Security Groups.
![Create Database Security Group](/images/5-Workshop/Tao_Database_Security_Group.jpg)

### 5.4.2. Configure IAM Roles

Securely grant delegated permissions to EC2 instances to interact with other AWS services without the need to store hard-coded Access Keys.

1. Access the **IAM** service, create a role named `ResumeMatching-Backend-Role` to assign to the backend servers running on EC2.
![Create Backend IAM Role](/images/5-Workshop/Tao_Backend_IAM_Role.jpg)

2. Create a second role named `ResumeMatching-Worker-Role` dedicated to the Worker server. Attach AWS Managed policies such as `AmazonSQSFullAccess` and grant permissions to interact with S3.
![Create Worker IAM Role](/images/5-Workshop/Tao_Worker_IAM_Role.jpg)
