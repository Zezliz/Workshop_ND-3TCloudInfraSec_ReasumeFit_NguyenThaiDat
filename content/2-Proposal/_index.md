---
title: "Proposal"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Project Proposal: AI Resume Matching & Interview Preparation Platform

### 1. Project Overview

*   **Goal:** Build a web application that evaluates the matching compatibility between CVs (resumes) and JDs (job descriptions) based on a 3-Tier AWS cloud infrastructure.
*   **AI Processing:** The EC2 cluster (Backend + Worker) is responsible for analyzing CVs and JDs by calling LLM models via the OpenAI API over the Internet to optimize token consumption and minimize costs.

### 2. Cloud Infrastructure Architecture (AWS)

The system is designed following the standard 3-Tier Architecture within a VPC, ensuring High Availability, robust security, and auto-scaling capabilities:

![AI Resume Matching & Interview Preparation Architecture Diagram](/images/2-Proposal/proposal_architecture.png)

*   **Edge & Global Tier:**
    *   The content delivery network (Amazon CloudFront), AWS WAF firewall, and authentication service are currently planned but not deployed (AWS account verification required). These services are pending verification and are not active in the current environment.
    *   Amazon S3 (Amazon Simple Storage Service) is used for shared storage.
    *   Users interact with the system via the Internet Gateway (1) or upload files directly using **Pre-signed URLs** to a dedicated S3 bucket (S3 CV/JD Storage) (5).

*   **Networking & Load Balancing (Inbound):**
    *   The infrastructure runs inside a VPC with a CIDR block of `10.0.0.0/16` for network isolation.
    *   **Internet Gateway (IGW):** Acts as the single entry point connecting to the Internet for both Inbound traffic and Outbound traffic (routed via NAT Gateways).
    *   **Application Load Balancer (ALB):** Positioned across Availability Zones, receives traffic from the IGW and distributes it intelligently to the Auto Scaling Group.

*   **Application Tier:**
    *   The EC2 cluster (Backend + Worker) is placed in private application subnets (**Private App Subnet A** and **Private App Subnet B**), spanning two Availability Zones (**Availability Zone A** and **Availability Zone B**). This is managed by an **Auto Scaling Group (ASG)** to automatically scale instances based on system load.
    *   **Internal Communication:** EC2 instances in AZ A connect directly to the S3 storage and Amazon SQS queues (6), backed by a Dead Letter Queue (DLQ) to handle failed messages.
    *   **OpenAI API Flow:** EC2 instances in AZ B route outbound traffic through the NAT Gateway located in Public Subnet B to call the OpenAI API via the Internet Gateway. (Note: The architecture deploys two independent NAT Gateways in Public Subnet A and Public Subnet B for redundancy).

*   **Outbound & Internal Network:**
    *   **Two NAT Gateways** are deployed (one in Public Subnet A and another in Public Subnet B) to ensure High Availability for outbound traffic originating from the Private Subnets.
    *   All internal communications to SQS and S3 are securely routed within the VPC network.

*   **Database Tier:**
    *   **Amazon RDS PostgreSQL** is utilized with a **Multi-AZ** deployment configuration for database redundancy.
    *   It is located in two private database subnets (**Private DB Subnet A** and **Private DB Subnet B**), strictly protected by database Security Groups.
    *   The RDS Primary (Master) in AZ A handles write operations. The RDS Standby Replica in AZ B continuously synchronizes data from the primary instance (represented by the dashed line).
    *   **Connection Flow:** The EC2 instance in AZ A connects directly to the RDS Primary (7). The EC2 instance in AZ B connects to the RDS Standby Replica via RDS Endpoints (dashed line) during a failover scenario.

*   **Management & Monitoring:**
    *   The regional management and security zone includes: **AWS Systems Manager** for instance administration, **Amazon CloudWatch** for system monitoring and log storage, and **AWS Secrets Manager** to securely manage and encrypt OpenAI API Keys.

*   **Deployment:**
    *   The codebase is hosted on GitHub and deployed manually (**Manual Deployment**). The current architecture does not incorporate automated CI/CD services such as AWS CodeBuild or AWS CodePipeline.