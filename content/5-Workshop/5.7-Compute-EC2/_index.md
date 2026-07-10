---
title: "Deploying Compute and Configuring Servers"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

### 5.7.1. Initialize EC2 Backend Instance

1. Create an RSA **Key Pair** named `ResumeMatching-Key`.
![Create Key Pair](/images/5-Workshop/Tao_Key_Pair.jpg)

2. From the EC2 Dashboard, launch an Instance named `ResumeMatching-Backend` with an Instance type of `t3.micro` placed within the application VPC.
![Create EC2 Backend](/images/5-Workshop/Tao_EC2_Backend.jpg)

3. Wait until the Instance state transitions to `Running` and the Status check displays `2/2 checks passed`.

### 5.7.2. Connect and Install Software

1. Securely access the EC2 instance remotely using **Systems Manager Fleet Manager**. Select the Running Managed node and click **Start terminal session**.
![Connect EC2 using Systems Manager](/images/5-Workshop/Connect_EC2_backend_bang_Systems_Manager.jpg)

2. Execute the **Git** installation command to pull the source code:
```bash
sudo dnf install git
```
![Install Git](/images/5-Workshop/Cai_GIT.jpg)

3. Proceed to install and start **Docker** to run the application as containers:
```bash
sudo dnf install -y docker
sudo systemctl enable docker
sudo systemctl start docker
```
![Install Docker](/images/5-Workshop/Cai_Docker.jpg)
![Check Docker Status](/images/5-Workshop/Kiem_tra_trang_thai_Docker.jpg)

4. Navigate to the `/opt` directory and clone the source code from GitHub:
```bash
cd /opt
sudo git clone http://github.com/thuanthien-tran/resume-fit.git
sudo chown -R ssm-user /opt/resume-fit
```
![Clone source code to EC2](/images/5-Workshop/Clone_source_len_EC2.jpg)
