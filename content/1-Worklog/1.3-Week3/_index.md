---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
### Week 3 Objectives:
* Learn about Amazon RDS (Relational Database Service) managed database model.
* Setup multi-AZ DB Subnet Groups and provision a MySQL database inside the Private Subnet.
* Test private database endpoint connectivity using the EC2 instance.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study relational database architecture in AWS: Amazon RDS vs self-managed database on EC2. <br> - Compare database engines (MySQL, PostgreSQL, MariaDB). | 04/05/2026 | 04/05/2026 | [Amazon RDS Overview](https://aws.amazon.com/rds/) |
| 3 | - Learn the concept of DB Subnet Groups (multi-AZ requirements). <br> - Group Private Subnets from multiple Availability Zones to ensure database resilience. | 05/05/2026 | 05/05/2026 | [Working with DB Subnet Groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceandUTG.html) |
| 4 | - Create a database-specific Security Group. <br> - Add ingress rules allowing MySQL protocol (port 3306) traffic exclusively from the EC2 web server Security Group. | 06/05/2026 | 06/05/2026 | [RDS Security Group Ingress Rules](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html) |
| 5 | - Provision a MySQL database instance in the Private Subnet using the created DB Subnet Group. <br> - Disable Public Accessibility to prevent external internet access. | 07/05/2026 | 07/05/2026 | [Creating an RDS DB Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.CreatingConnecting.MySQL.html) |
| 6 | - Install MySQL Client CLI tools on the EC2 web server. <br> - Execute connection commands to the RDS endpoint and verify database availability. | 08/05/2026 | 08/05/2026 | [Connecting to a MySQL DB Instance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html) |

### Week 3 Achievements:
* Gained comprehension of cloud-native managed databases (RDS) and their advantages over self-managed options.
* Created a multi-AZ DB Subnet Group using private subnets to fulfill security compliance rules.
* Launched an RDS MySQL database instance completely isolated from the public internet.
* Restricted database network traffic by implementing security group chaining (limiting access to port 3306 exclusively from the web application server).
* Successfully validated connectivity from the EC2 instance to the RDS endpoint.
