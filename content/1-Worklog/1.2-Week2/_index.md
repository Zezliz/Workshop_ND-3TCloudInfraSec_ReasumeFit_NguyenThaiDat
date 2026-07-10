---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---
### Week 2 Objectives:
* Learn about Amazon EC2 (Elastic Compute Cloud) instance concepts.
* Understand Security Groups and firewall filtering rules.
* Provision an EC2 instance, configure SSH credentials, and test remote access.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study Amazon EC2 instance families (t-type, m-type, c-type) and scaling concepts. <br> - Review AMI, EBS volumes, and Key Pair options. | 27/04/2026 | 27/04/2026 | [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/) |
| 3 | - Learn about virtual firewalls in AWS (Security Groups). <br> - Design inbound/outbound rules to block/permit web traffic. | 28/04/2026 | 28/04/2026 | [Amazon EC2 Security Groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html) |
| 4 | - Launch a t2.micro EC2 Instance using Ubuntu Server AMI in the public subnet. <br> - Configure Security Group to permit SSH (port 22) from your IP only, and HTTP (port 80). | 29/04/2026 | 29/04/2026 | [Launching an Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html) |
| 5 | - Setup SSH private keys (.pem format) on local terminal. <br> - Learn to use Windows PowerShell, WSL, or Git Bash to configure key permissions. | 30/04/2026 | 30/04/2026 | [SSH connection troubleshooting](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstances.html) |
| 6 | - Successfully execute remote SSH connections to the EC2 instance. <br> - Verify network properties, assign Elastic IP, and test public web availability. | 01/05/2026 | 01/05/2026 | [Elastic IP Addresses](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) |

### Week 2 Achievements:
* Gained a solid understanding of compute virtualization in AWS using Amazon EC2.
* Learned how to secure instances using stateful firewalls (Security Groups) by enforcing least-privilege ingress configurations.
* Deployed an active Ubuntu Linux EC2 server inside the public subnet of the custom VPC.
* Established secure SSH connection keys and set up an Elastic IP to maintain a persistent public address for the instance.
