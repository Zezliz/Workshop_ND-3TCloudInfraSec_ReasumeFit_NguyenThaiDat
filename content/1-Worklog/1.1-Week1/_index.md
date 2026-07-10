---
title: "Week 1 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---
### Week 1 Objectives:
* Gain an overview of AWS Global Infrastructure (Regions, AZs, Edge Locations).
* Successfully register and configure an AWS Free Tier account.
* Launch and configure a Custom VPC with associated Subnets (Public/Private), Route Tables, and an Internet Gateway (IGW).

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn about AWS Regions, Availability Zones, and local Edge Locations. <br> - Understand the shared responsibility model. | 20/04/2026 | 20/04/2026 | [AWS Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/) |
| 3 | - Register for AWS Free Tier account. <br> - Configure IAM Admin user, enable Multi-Factor Authentication (MFA). <br> - Setup Billing Alarms. | 21/04/2026 | 21/04/2026 | [AWS Free Tier Registration Guide](https://aws.amazon.com/free/) |
| 4 | - Study Amazon VPC concepts: CIDR block sizing, IP addresses, Subnets, and Gateways. <br> - Design VPC network topology. | 22/04/2026 | 22/04/2026 | [What is VPC?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| 5 | - Create custom VPC with 10.0.0.0/16 CIDR. <br> - Designate Public Subnet (10.0.1.0/24) and Private Subnet (10.0.2.0/24). <br> - Provision and attach an Internet Gateway (IGW). | 23/04/2026 | 23/04/2026 | [AWS VPC Creation Console](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html) |
| 6 | - Define Route Tables for Public and Private networks. <br> - Route all 0.0.0.0/0 traffic from Public Route Table to the IGW. <br> - Perform subnet associations and verify logic. | 24/04/2026 | 24/04/2026 | [VPC Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) |

### Week 1 Achievements:
* Acquired foundational knowledge on AWS Global Infrastructure (Regions, AZs, and Edge Locations) and Cloud core concepts.
* Configured a secure root AWS account with IAM users, MFA enforced, and budget alerts active.
* Successfully built a custom VPC (CIDR `10.0.0.0/16`) from scratch, segmenting it into logical public (`10.0.1.0/24`) and private (`10.0.2.0/24`) subnets.
* Enabled public internet routing using an Internet Gateway (IGW) connected via Route Table configuration for the public subnet.
