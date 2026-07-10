---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Week 9 Objectives:
* Test the High Availability and self-healing behaviors of the Auto Scaling Group.
* Perform synthetic CPU stress testing on dynamic servers using benchmarking tools.
* Evaluate the automated lifecycle activity (Scale Out and Scale In) under simulated load.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Formulate a step-by-step verification plan for High Availability (HA) and dynamic resource provisioning. | 15/06/2026 | 15/06/2026 | [Testing Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-verify-scalling-activity.html) |
| 3 | - Manually terminate a running WordPress EC2 instance from the AWS console. <br> - Observe and log ASG detection latency and the launch of a replacement server. | 16/06/2026 | 16/06/2026 | [Auto Scaling Instance Lifecycle](https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroupLifecycle.html) |
| 4 | - Log in to a WordPress instance via SSH. <br> - Install the Linux benchmark utility `stress` or `stress-ng` from system packages. | 17/06/2026 | 17/06/2026 | [Installing stress on Ubuntu](https://manpages.ubuntu.com/manpages/noble/man1/stress.1.html) |
| 5 | - Run the command `stress --cpu 4 --timeout 600` to simulate 100% CPU load on the instance. <br> - Monitor CloudWatch metric graphs to observe the CPUUtilization trend. | 18/06/2026 | 18/06/2026 | [Monitoring EC2 CPU Utilization](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html) |
| 6 | - Observe the CloudWatch Alarm transitioning into the `ALARM` state. <br> - Verify that the ASG launches a new instance, integrates it into the Target Group, and returns the cluster to `OK` state after the stress test ends. | 19/06/2026 | 19/06/2026 | [Observing Scaling Activities](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-verify-scalling-activity.html) |

### Week 9 Achievements:
* Verified the system's High Availability and self-healing properties: the ASG automatically replaced a manually terminated instance without user intervention.
* Successfully generated high CPU workloads on active servers using the Linux `stress` utility.
* Validated the dynamic scale-out mechanism: the ASG successfully launched and configured new servers to share the load within minutes of CPU utilization breaching the threshold.
* Verified the scale-in mechanism: the ASG correctly terminated the additional instances once the stress timeout completed and average CPU fell below the scale-in threshold.
