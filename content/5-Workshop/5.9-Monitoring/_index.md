---
title: "System Monitoring and High Availability"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

Monitoring is mandatory to ensure traffic is correctly distributed and Scaling rules are operating properly.

### 5.9.1. Check Auto Scaling Group Operation

1. Access the **EC2** service and navigate to the **Instances** menu.
2. Observe the system automatically initializing new EC2 instances named `ResumeMatching-ASG-Instance` evenly distributed across different Availability Zones.
3. Some old servers might display a `Terminated` status. This is proof that the ASG is operating correctly: automatically retiring old instances and launching new ones upon configuration changes or system failures.

### 5.9.2. Check Target Group Health Check

1. Under the **Load Balancing** section, select **Target Groups**, and click on the system's Target Group.
2. Switch to the **Targets** tab and observe the **Registered targets** table.
3. Confirm that the `Health status` column for the instances displays a green `Healthy` status, proving the web servers have started and are ready to receive requests from the Load Balancer.
![Target group healthy check](/images/5-Workshop/Target_group_healthy_check.jpg)

### 5.9.3. Monitor Performance via CloudWatch

1. Access **CloudWatch** and select the **Metrics** menu to deeply monitor parameters.
2. **For EC2**: Filter the EC2 Namespace and select `CPUUtilization`. Observe the graph to see processing spikes (e.g., `81.9%`) when the AI runs heavy tasks, allowing you to set automatic scale-out Thresholds for the ASG.
![CloudWatch monitor EC2](/images/5-Workshop/CloudWatch_dang_monitor_EC2.jpg)
![EC2 Metrics](/images/5-Workshop/EC2_Metrics.jpg)

3. **For ALB**: Filter the `RequestCount` and `TargetResponseTime` metrics. The correlation between a spike in Requests and the change in response time (e.g., `660.4 ms`) helps evaluate the smoothness of the user experience.
![CloudWatch monitor ALB](/images/5-Workshop/CloudWatch_monitor_Load_Balancer.jpg)
![ALB Metrics](/images/5-Workshop/ALB_Metrics.jpg)
