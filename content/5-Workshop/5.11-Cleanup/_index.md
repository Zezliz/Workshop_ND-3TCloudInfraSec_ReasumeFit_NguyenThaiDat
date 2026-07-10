---
title: "Clean up"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

After completing the workshop and testing process, to avoid incurring unnecessary storage and infrastructure maintenance costs on AWS, please proceed with the cleanup in the following order:

1. Delete the **Auto Scaling Group** to prevent the system from automatically launching new servers, then manually Terminate any remaining **EC2 Instances**.
2. Delete the **Application Load Balancer** and **Target Group**.
3. Delete the **RDS Database** (uncheck the final Snapshot creation feature if you do not need to keep the data) and the RDS **Subnet Group**.
4. Delete the **NAT Gateways**, wait until their status is `Deleted`, and then Release the **Elastic IPs**.
5. Release **VPC Endpoints**, **Route Tables**, **Internet Gateways**, **Subnets**, and finally delete the **VPC**.
6. Empty all objects within the **S3 bucket**, and then proceed to Delete the Bucket.
