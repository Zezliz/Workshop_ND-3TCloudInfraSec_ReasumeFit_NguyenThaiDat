---
title: "Setting Up Auto Scaling and Load Balancing"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

### 5.8.1. Configure AMI and Launch Template

1. Standardize the newly installed EC2 environment by creating an Amazon Machine Image (AMI) named `ResumeMatching-Backend-AMI`.
![Create AMIs](/images/5-Workshop/Tao_AMIs.jpg)

2. From this AMI, create a **Launch Template** named `ResumeMatching-LT` containing standard hardware, network, and security configurations.
![Create Launch Template](/images/5-Workshop/Tao_launch_template.jpg)

### 5.8.2. Auto Scaling Group (ASG)

1. Create an Auto Scaling Group `ResumeMatching-ASG` and link it to the Launch template `ResumeMatching-LT`.
![Create ASG](/images/5-Workshop/Tao_ASG.jpg)

2. Edit the Desired capacity to `2`. The ASG will automatically launch new EC2 instances in an Initializing state for redundancy and scaling purposes.
![ASG creating more EC2s](/images/5-Workshop/ASG_tao_them_EC2.jpg)
![ASG creating new EC2 after AMI update](/images/5-Workshop/ASG_tao_EC2_moi_sau%20khi_cap_nhat_AMI.jpg)

### 5.8.3. Target Group and Application Load Balancer

1. Create a **Target Group** named `ResumeMatching-TG`, of type `Instance` for the HTTP protocol on port `8080` (or `80` depending on your internal container configuration).
![Create Target Group](/images/5-Workshop/Tao_target_group.jpg)

2. Initialize an **Application Load Balancer (ALB)** named `ResumeMatching-ALB`. Select the Scheme as `Internet-facing` to receive traffic from the internet, listening across 2 Availability Zones and routing traffic into the network via the above Target Group.
![Create ALB](/images/5-Workshop/Tao_ALB.jpg)
