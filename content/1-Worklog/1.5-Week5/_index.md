---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---
### Week 5 Objectives:
* Understand the role and benefits of Amazon Machine Images (AMIs) in system backup and scalability.
* Create a custom, pre-configured WordPress AMI based on the active EC2 instance.
* Create and configure an EC2 Launch Template utilizing the custom AMI.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Study AMI architecture (EBS-backed vs instance-store). <br> - Research the lifecycle of custom AMIs and how they enable rapid compute provisioning. | 18/05/2026 | 18/05/2026 | [Amazon Machine Images (AMIs)](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html) |
| 3 | - Connect to EC2 and clean up temporary logs, SSH histories, and cached data. <br> - Shut down the instance gracefully to guarantee file system consistency. | 19/05/2026 | 19/05/2026 | [Preparing an Instance for AMI Creation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html#how-to-create-ebs-ami) |
| 4 | - Execute the "Create Image" operation on the EC2 instance via AWS Management Console. <br> - Track progress status and verify that the AMI transitions to the "available" state. | 20/05/2026 | 20/05/2026 | [Creating an EBS-backed Linux AMI](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html) |
| 5 | - Understand Launch Templates vs Launch Configurations. <br> - Define launch configurations including Instance Type, custom AMI ID, Security Groups, and IAM roles. | 21/05/2026 | 21/05/2026 | [Launch Templates Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html) |
| 6 | - Create the Launch Template with version control. <br> - Launch a test EC2 instance from the template to verify WordPress serves content automatically. | 22/05/2026 | 22/05/2026 | [Launching an Instance from a Launch Template](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html#launch-from-template) |

### Week 5 Achievements:
* Mastered server packaging, backup patterns, and gold-image deployment techniques using Amazon Machine Images.
* Packaged the fully-configured WordPress LAMP server into a reusable private AMI.
* Standardized instance parameters by creating an AWS Launch Template with versioning support.
* Successfully validated the Launch Template by bootstrapping a secondary server that served WordPress immediately with no manual setup.
