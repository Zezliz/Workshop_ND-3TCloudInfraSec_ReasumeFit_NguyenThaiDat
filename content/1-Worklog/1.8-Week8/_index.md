---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
### Week 8 Objectives:
* Learn about Amazon CloudWatch monitoring services, namespaces, and performance metrics.
* Configure CloudWatch Alarms for system monitoring based on CPU utilization metrics.
* Integrate CloudWatch Alarms to automatically trigger ASG scale-out and scale-in policies.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study CloudWatch core components: metrics, dimensions, statistics, and resolution. <br> - Review standard EC2 performance metrics. | 08/06/2026 | 08/06/2026 | [Amazon CloudWatch Concepts](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Concepts.html) |
| 3 | - Learn the configuration logic of CloudWatch Alarms. <br> - Design threshold parameters for CPU utilization to identify system bottlenecks. | 09/06/2026 | 09/06/2026 | [Create a CloudWatch Alarm Based on a Static Threshold](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ConsoleAlarms.html) |
| 4 | - Create a High-CPU CloudWatch Alarm. <br> - Set rule to trigger when average CPU utilization exceeds 70% for two consecutive 1-minute evaluation periods. | 10/06/2026 | 10/06/2026 | [Creating CloudWatch Alarms for EC2 Metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_alarms.html) |
| 5 | - Create a Low-CPU CloudWatch Alarm. <br> - Set rule to trigger when average CPU utilization falls below 30% to clean up idle resources. | 11/06/2026 | 11/06/2026 | [CloudWatch Alarms for Scaling Policies](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html#as-scaling-setup-alarms) |
| 6 | - Integrate the High-CPU Alarm with the ASG Scale Out policy (adds 1 instance). <br> - Integrate the Low-CPU Alarm with the ASG Scale In policy (removes 1 instance). Test alert notifications using SNS. | 12/06/2026 | 12/06/2026 | [Using Amazon CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) |

### Week 8 Achievements:
* Gained comprehensive understanding of cloud observability and system metrics monitoring using Amazon CloudWatch.
* Successfully built CloudWatch Alarms for monitoring cluster CPU utilization.
* Bound CloudWatch Alarms directly to Auto Scaling Group policies to form a closed-loop automated scaling system.
* Configured Amazon Simple Notification Service (SNS) to automatically alert the administrator via email whenever an alarm state transition occurs.
