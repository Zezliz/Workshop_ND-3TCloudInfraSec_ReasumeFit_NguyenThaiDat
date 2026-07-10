---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# 5. Workshop: Deploying AI Resume Matching & Interview Preparation Platform on AWS

This lab provides detailed instructions on how to comprehensively deploy the **Resume Fit** system on the AWS cloud platform. Resume Fit is an AI application that rapidly and transparently evaluates the matching compatibility between a Candidate's Resume (CV) and the Job Description (JD) to support recruitment decisions.

The system is designed following a standard AWS architecture, ensuring high scalability and availability. It encompasses core components: Isolated Network (VPC), Flexible Compute Servers (EC2, Auto Scaling Group), Relational Database (RDS PostgreSQL), Object Storage (S3), Asynchronous Processing Queue (SQS), Monitoring Service (CloudWatch), and Secrets Management Service (Secrets Manager).

#### Content

1. [Introduction](5.1-Introduction/)
2. [Prerequisites](5.2-Prerequisites/)
3. [Building Network Infrastructure](5.3-Networking/)
4. [Setting Up Security and Access Management](5.4-Security-IAM/)
5. [Setting Up Storage and Queue Services](5.5-Storage-Queue/)
6. [Setting Up Relational Database (RDS)](5.6-Database-RDS/)
7. [Deploying Compute and Configuring Servers](5.7-Compute-EC2/)
8. [Setting Up Auto Scaling and Load Balancing](5.8-AutoScaling-ALB/)
9. [System Monitoring and High Availability](5.9-Monitoring/)
10. [Testing the Resume Fit Application](5.10-Testing/)
11. [Clean Up](5.11-Cleanup/)