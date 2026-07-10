---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
### Week 6 Objectives:
* Understand Load Balancing concepts and the role of Application Load Balancers (ALB) in HTTP/HTTPS routing.
* Create a Target Group with appropriate HTTP Health Checks.
* Deploy an ALB and configure listener routing rules.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study Elastic Load Balancing (ELB) types (ALB, NLB, GLB) and HTTP routing mechanics. <br> - Review the concepts of Listeners, Target Groups, and routing rules. | 25/05/2026 | 25/05/2026 | [What is Elastic Load Balancing?](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html) |
| 3 | - Define Target Group configurations for HTTP (port 80). <br> - Configure Target Group health check attributes: interval, thresholds, and success response codes. | 26/05/2026 | 26/05/2026 | [Target Groups for Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) |
| 4 | - Define Security Group configurations for the Load Balancer, permitting HTTP/HTTPS traffic from any source. <br> - Register active WordPress EC2 instances into the Target Group. | 27/05/2026 | 27/05/2026 | [Security Groups for Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-update-security-groups.html) |
| 5 | - Provision an Application Load Balancer across multiple public Availability Zones. <br> - Bind the ALB to the custom web security group and establish HTTP listeners. | 28/05/2026 | 28/05/2026 | [Creating an Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-application-load-balancer.html) |
| 6 | - Configure routing logic to redirect HTTP listener traffic directly to the Target Group. <br> - Test the connection through the ALB DNS name and check target status. | 29/05/2026 | 29/05/2026 | [Troubleshooting ALB health checks](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-troubleshooting.html) |

### Week 6 Achievements:
* Gained solid theoretical knowledge of HTTP/HTTPS load distribution at Layer 7 using Application Load Balancers.
* Configured Target Groups and active HTTP Health Checks (`Path: /`) to dynamically determine instance health.
* Deployed a highly available Application Load Balancer spanning multiple public subnets.
* Configured inbound security group rules on EC2 to restrict direct public HTTP access and allow traffic ONLY routed through the ALB.
* Accessed the WordPress site successfully via the ALB DNS Endpoint.
