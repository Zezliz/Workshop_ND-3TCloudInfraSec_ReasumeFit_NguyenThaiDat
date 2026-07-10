---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Week 10 Objectives:
* Research and understand stateful filesystems in AWS using Amazon Elastic File System (EFS).
* Study the theory of Amazon CloudFront Content Delivery Network (CDN) for low-latency web distribution.
* Evaluate the benefits and business value of Cloud Computing models compared to physical On-Premises datacenters.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Learn about Amazon EFS architecture, mounting options, and multi-instance attachment. <br> - Compare EFS vs. Amazon EBS vs. Amazon S3 storage characteristics. | 22/06/2026 | 22/06/2026 | [Amazon EFS Overview](https://aws.amazon.com/efs/) |
| 3 | - Mount EFS to the WordPress upload directory (`/var/www/html/wp-content/uploads/`). <br> - Verify that media files uploaded on one EC2 instance are synchronized across all instances in the ASG. | 23/06/2026 | 23/06/2026 | [Mounting EFS to EC2](https://docs.aws.amazon.com/efs/latest/ug/mounting-fs.html) |
| 4 | - Study Content Delivery Network (CDN) concepts: Edge Locations, Origin Servers, Caching, and TTL. <br> - Learn the architecture of Amazon CloudFront. | 24/06/2026 | 24/06/2026 | [Amazon CloudFront Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 5 | - Create a CloudFront Distribution with the ALB as its Origin Server. <br> - Configure routing rules, SSL certificates, and check latency improvement for static assets. | 25/06/2026 | 25/06/2026 | [Creating a CloudFront Distribution](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/distribution-web-creating-console.html) |
| 6 | - Analyze Cloud Computing models (IaaS, PaaS, SaaS) and cost structures. <br> - Write a comparison report evaluating the advantages of AWS Cloud (pay-as-you-go, scalability, reliability) vs. physical On-Premises datacenters. | 26/06/2026 | 26/06/2026 | [AWS Cloud vs On-Premises Comparison](https://aws.amazon.com/whitepapers/aws-overview/) |

### Week 10 Achievements:
* Configured a shared, stateful filesystem using Amazon EFS to enable synchronized storage of media assets across dynamic auto-scaled instances.
* Mastered website caching and global acceleration principles by deploying an Amazon CloudFront CDN distribution in front of the Application Load Balancer.
* Gained strong theoretical knowledge of Cloud Economics (CapEx vs OpEx), high availability architectures, and security compliance advantages over traditional physical on-premises servers.
