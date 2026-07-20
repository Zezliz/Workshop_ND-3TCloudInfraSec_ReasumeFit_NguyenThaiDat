---
title: "Clean up"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

### 5.11.1. Cleanup Steps

After completing the workshop and testing process, to avoid incurring unnecessary storage and infrastructure maintenance costs on AWS, please proceed with the cleanup in the following order:

1. Delete the **Auto Scaling Group** to prevent the system from automatically launching new servers, then manually Terminate any remaining **EC2 Instances**.
2. Delete the **Application Load Balancer** and **Target Group**.
3. Delete the **RDS Database** (uncheck the final Snapshot creation feature if you do not need to keep the data) and the RDS **Subnet Group**.
4. Delete the **NAT Gateways**, wait until their status is `Deleted`, and then Release the **Elastic IPs**.
5. Release **VPC Endpoints**, **Route Tables**, **Internet Gateways**, **Subnets**, and finally delete the **VPC**.
6. Empty all objects within the **S3 bucket**, and then proceed to Delete the Bucket.

### 5.11.2. Estimated System Deployment Cost (Cost Breakdown)

Based on calculations from the AWS Pricing Calculator in the **US East (N. Virginia) – us-east-1** region, utilizing **AWS On-Demand Pricing**, with an estimated operational time of **730 hours/month (24/7)**, and considering the system serves purely for demo and grading purposes (low traffic volume, no Reserved Instances), the table below illustrates the estimated monthly cost for the deployed architecture.

#### Estimated Monthly Cost Breakdown

| STT | AWS Service | Configuration | Quantity | Estimated Monthly Cost (USD) | Notes | Total (USD) |
|---|---|---|---|---|---|---|
| 1 | Amazon VPC | Default | 01 | 0.00 | Core networking is free | 0.00 |
| 2 | Internet Gateway | Default | 01 | 0.00 | Free service | 0.00 |
| 3 | Public Subnet | Standard | 02 | 0.00 | Free service | 0.00 |
| 4 | Private Application Subnet | Standard | 02 | 0.00 | Free service | 0.00 |
| 5 | Private Database Subnet | Standard | 02 | 0.00 | Free service | 0.00 |
| 6 | NAT Gateway | 730 hrs, ~0 GB Data Processed | 02 | 32.85 | 0.045 USD/hour per NAT | 65.70 |
| 7 | Security Group | Default | 01 | 0.00 | Free virtual firewall | 0.00 |
| 8 | Amazon EC2 | t3.micro Linux (730 hrs) | 03 | 7.59 | 0.0104 USD/hour (1 Backend, 2 ASG) | 22.77 |
| 9 | Amazon EBS | 30 GB gp3 | 03 | 2.40 | 0.08 USD/GB-month | 7.20 |
| 10 | Amazon Machine Image (AMI) | Custom AMI | 01 | 0.00 | Free tier / minimal cost | 0.00 |
| 11 | Launch Template | Standard | 01 | 0.00 | Free configuration management | 0.00 |
| 12 | Auto Scaling Group | Standard | 01 | 0.00 | Free scaling service | 0.00 |
| 13 | Application Load Balancer | 730 hrs, ~0 LCU | 01 | 16.43 | 0.0225 USD/hour per ALB | 16.43 |
| 14 | Target Group | Standard | 01 | 0.00 | Free load balancing component | 0.00 |
| 15 | Amazon RDS Single-AZ | db.t3.micro (730 hrs) | 01 | 12.41 | 0.017 USD/hour | 12.41 |
| 16 | Amazon RDS Storage | 20 GB gp3 | 01 | 2.30 | 0.115 USD/GB-month | 2.30 |
| 17 | Amazon S3 Standard | 5 GB Data | 01 | 0.12 | 0.023 USD/GB-month | 0.12 |
| 18 | Amazon SQS | Standard Queue & DLQ | 01 | 0.00 | First 1M requests are free | 0.00 |
| 19 | AWS Secrets Manager | 01 Secret | 01 | 0.40 | 0.40 USD/Secret/month | 0.40 |
| 20 | Amazon Cognito | < 50,000 MAU | 01 | 0.00 | Covered by Free Tier | 0.00 |
| 21 | AWS Systems Manager | Session Manager | 01 | 0.00 | Free management service | 0.00 |
| 22 | Amazon CloudWatch | Basic Metrics & Logs | 01 | 0.00 | Basic tier is free | 0.00 |

#### Total Cost Analysis:
- **Total Monthly Deployment Cost:** ~ **127.33 USD**.
- **Services with the Highest Cost Proportion:** The networking component, specifically the **NAT Gateway** (65.70 USD, accounting for roughly 51.6% of the total cost). This is due to the hourly maintenance charge (0.045 USD/hour) regardless of traffic volume. This is followed by Compute resources such as **EC2 instances** (22.77 USD) and the **Application Load Balancer** (16.43 USD).
- **Suitability against the AWS Credits 200 USD Budget:** The current architecture is **perfectly safe and well within** the allocated budget limit (200 USD/month). The remaining budget buffer (~72.67 USD) is sufficient to absorb any minor traffic fluctuations that may arise during demo presentations.

#### Proposed Cost Optimization Measures:
Although the system resides within the budget limits, the following measures can be adopted to further optimize costs for the project without altering the overall architectural design:
1. **Scale Down NAT Gateway Design:** Instead of deploying 02 NAT Gateways across 2 Availability Zones (for standard High Availability), it can be reduced to running just 01 NAT Gateway and routing the other AZ's traffic through this single node. This immediately yields a savings of **32.85 USD/month**.
2. **Automated Resource Start/Stop Scheduling:** Utilize AWS Lambda or AWS Instance Scheduler to configure automatic Shutdown (Stop) operations for Compute resources (e.g., EC2, RDS, setting ASG Desired Capacity to 0) during nighttime and non-business hours (e.g., from 10:00 PM to 08:00 AM). This approach can slash monthly compute costs by approximately 40%.
3. **Trim Redundant Storage (EBS):** A demo system does not demand extensive storage. Reducing the default EBS volume size from 30 GB to 8 GB - 15 GB per EC2 instance can slightly decrease block storage invoices.
