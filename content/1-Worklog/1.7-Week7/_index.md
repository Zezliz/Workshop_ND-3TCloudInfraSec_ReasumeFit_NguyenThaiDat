---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
### Week 7 Objectives:
* Understand the core concepts of Amazon EC2 Auto Scaling and its role in High Availability.
* Configure an Auto Scaling Group (ASG) integrated with the WordPress Launch Template.
* Define dynamic scaling policies (Scale Out and Scale In) to respond to load changes.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study Auto Scaling principles: desired capacity, minimum capacity, and maximum capacity. <br> - Understand self-healing mechanism and replacement logic. | 01/06/2026 | 01/06/2026 | [Amazon EC2 Auto Scaling Concepts](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) |
| 3 | - Configure Auto Scaling parameters. <br> - Select the WordPress Launch Template and designate subnets across different Availability Zones. | 02/06/2026 | 02/06/2026 | [Creating an Auto Scaling Group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/create-asg-launch-template.html) |
| 4 | - Link the ASG to the existing ALB Target Group. <br> - Configure load balancer connection checks and define grace periods for initialization. | 03/06/2026 | 03/06/2026 | [Attaching a Load Balancer to Your Auto Scaling Group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/attach-load-balancer-asg.html) |
| 5 | - Design dynamic scaling parameters: set Target Tracking scaling policies on Average CPU Utilization. <br> - Establish Scale Out threshold (e.g., CPU > 70%) and cooldown parameters. | 04/06/2026 | 04/06/2026 | [Dynamic Scaling for Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html) |
| 6 | - Deploy the ASG and monitor the initialization phase. <br> - Verify that instances automatically boot up, register with the Target Group, and pass health checks. | 05/06/2026 | 05/06/2026 | [Verifying ASG Status](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-verify-scalling-activity.html) |

### Week 7 Achievements:
* Gained hands-on proficiency in designing elastic, self-healing infrastructures.
* Successfully built an Auto Scaling Group using the WordPress Launch Template to span multiple AZ private subnets.
* Integrated the ASG with the ALB Target Group to automate the registration and deregistration of dynamic instances.
* Established threshold metrics and scaling cooldown rules to automatically scale capacity in response to traffic.
