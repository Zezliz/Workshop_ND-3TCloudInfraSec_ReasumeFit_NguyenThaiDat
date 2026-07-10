---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# SYSTEM MONITORING ON AWS: STREAMING CLOUDWATCH METRICS TO OPENTELEMETRY COLLECTOR IN VPC USING LAMBDA

Managing observability for large-scale cloud systems has always been a challenging problem, especially when businesses want to balance cost, flexibility, and security. Although OpenTelemetry is gradually becoming a common standard that helps organizations avoid vendor lock-in, they face a major technical hurdle: how to route metrics from AWS CloudWatch directly into strictly isolated internal collection systems within a VPC. To resolve this, a solution using AWS Lambda acting as a data transit station from CloudWatch Metric Streams to the internal network has proven highly effective, ensuring that the data stream is always transmitted securely and in real time.

### Key highlights of this push-based observability solution:

* **Shifting from Pull to Push model:** Using tools like Prometheus to constantly "pull" (poll) data causes API throttling, loss of metrics, and high costs. The "push" model with CloudWatch Metric Streams completely solves this issue, enabling event-driven data transmission with sub-minute latency for real-time alerting.
* **Overcoming Amazon Data Firehose limitations:** Although Firehose supports pushing data to HTTP endpoints, it requires those endpoints to be public. To route data into a private subnet, AWS uses a Lambda function (Lambda Transform Function) as a bridge. Firehose aggregates data and calls Lambda; Lambda then securely pushes the metrics through an NLB deep into the VPC.
* **OpenTelemetry Collector is the heart of the system:** Running on Amazon EC2 instances inside the VPC, the Collector acts as a processing hub with 3 flexible components: Receivers (accepting data), Processors (filtering, enriching data, masking sensitive data), and Exporters (exporting data to various destinations such as Grafana, AWS X-Ray, or Amazon OpenSearch).
* **Scalability and failover redundancy:** By using a Network Load Balancer to distribute TCP traffic to EC2 instances, the system can scale out horizontally with ease. Additionally, an Amazon S3 bucket is configured as a backup destination for Firehose (however, no storage cost is incurred if Lambda successfully pushes the data).
* **Cost optimization and eliminating Vendor Lock-in:** Using OpenTelemetry (completely free under Apache 2.0 license) helps businesses eliminate the burden of third-party software licensing fees. Its standardization allows operations teams to freely change backend monitoring platforms in the future without rebuilding the data collection pipeline.

Overall, the clever combination of AWS services like Lambda, Firehose, and Network Load Balancer has created a perfect bridge, bridging the gap between public cloud services and closed internal networks. This architecture not only completely handles the latency issues and limitations of traditional APIs but also empowers technical teams. By establishing an intelligent data transmission flow, businesses are free to build a powerful, independent, budget-optimized monitoring ecosystem that is always ready to scale in the future without vendor dependency risks.

Building a monitoring system is not hard; the challenge is making it secure, cost-effective, and vendor-neutral. What do you think about this Push-based architecture with Lambda and OpenTelemetry? If you are directly operating a system, is your biggest hurdle currently security (safe metric delivery into private VPC) or infrastructure cost optimization? Let's discuss!

![CloudWatch Metric Stream to OpenTelemetry Collector](/images/3-BlogsPosted/blog1_architecture.png)

* Link: [Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2173544653410495/?rdid=CUzsR7GSYpgaIwjW)
* Guide: [AWS Architecture Blog](https://aws.amazon.com/vi/blogs/architecture/streaming-cloudwatch-metrics-to-vpc-based-opentelemetry-collectors-using-lambda/)