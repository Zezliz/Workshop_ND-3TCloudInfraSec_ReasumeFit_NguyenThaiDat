---
title: "Building Network Infrastructure"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

### 5.3.1. Create VPC and Internet Gateway

An isolated network infrastructure (VPC) provides a robust security foundation for the entire application, allowing full control over network traffic.

1. Access the VPC Console interface and select **Create VPC**.
![Create VPC](/images/5-Workshop/tao_VPC.jpg)

2. Initialize a VPC named `ResumeMatching-VPC` and set the `IPv4 CIDR` block to `10.0.0.0/16`.
3. Create an Internet Gateway named `ResumeMatching-IGW` to provide an outbound internet connection for public resources.
![Create Internet Gateway](/images/5-Workshop/Tao_Internet_Gateway.jpg)

4. Attach the newly created Internet Gateway to `ResumeMatching-VPC`.
![Attach to VPC](/images/5-Workshop/Attach_vao_VPC.jpg)

### 5.3.2. Configure Subnets and Route Tables

Divide the VPC network block into smaller subnets to separate application tiers (Public for Load Balancer, Private App for EC2, Private DB for RDS).

1. Navigate to **Subnets** and sequentially create subnets with appropriate CIDR blocks:
* Public Subnets: `Public-Subnet-A` (`10.0.1.0/24`), `Public-Subnet-B` (`10.0.2.0/24`).
* Private App Subnets: `Private-App-A` (`10.0.11.0/24`), `Private-App-B` (`10.0.12.0/24`).
* Private DB Subnets: `Private-DB-A` (`10.0.21.0/24`), `Private-DB-B` (`10.0.22.0/24`).
![Create Subnets](/images/5-Workshop/Tao_cac_Public_va_Private_subnet.jpg)

2. Create a public Route Table named `Public-RT` and assign it to the VPC.
![Create Public Route Table](/images/5-Workshop/Tao_Public_Route_Table.jpg)

3. Under the **Edit routes** section of `Public-RT`, add a route with `Destination` as `0.0.0.0/0` and point the `Target` to the Internet Gateway (`igw-...`).
4. Associate `Public-RT` with the 2 public subnets: `Public-Subnet-A` and `Public-Subnet-B`.
![Associate Public Route Table](/images/5-Workshop/Gan_Public_Route_Table.jpg)

5. Create additional private Route Tables named `Private-App-RT`, `ResumeMatching-Private-App-RT-B`, and `Private-DB-RT`, then associate them respectively with the corresponding App Subnets and DB Subnets to ensure these tiers are not exposed to the internet.
![Associate Private App Route Table](/images/5-Workshop/Tao_va_gan_Private_App_Route_Table.jpg)
![Associate Database Route Table](/images/5-Workshop/Tao_va_gan_Database_Route_Table.jpg)

### 5.3.3. Set up NAT Gateway for Private Subnets

This allows instances in Private Subnets to connect to the internet in a one-way outbound manner (for downloading packages or updating software) while denying any connections initiated from the internet.

1. Initialize two static **Elastic IPs** named `ResumeMatching-EIP` and `ResumeMatching-EIP-B`.
![Create Elastic IP](/images/5-Workshop/Tao_Elastic_IP.jpg)
![Create Elastic IP B](/images/5-Workshop/Tao_Elastic_IP_B.jpg)

2. Create a **NAT Gateway** named `ResumeMatching-NAT` located in `Public-Subnet-A` and attach the first Elastic IP.
![Create NAT Gateway](/images/5-Workshop/Tao_NAT.jpg)

3. Create another **NAT Gateway** named `ResumeMatching-NAT-B` in the remaining Availability Zone and attach the second Elastic IP to ensure High Availability.
![Create NAT Gateway B](/images/5-Workshop/Tao_NAT_B.jpg)

4. Open the configurations of the Private App Route Tables, add a route `0.0.0.0/0`, and set the `Target` to the corresponding newly initialized NAT Gateways.
