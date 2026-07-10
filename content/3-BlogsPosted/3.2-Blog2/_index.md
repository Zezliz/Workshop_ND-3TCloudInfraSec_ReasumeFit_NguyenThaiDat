---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# PRACTICAL EXPERIENCE: BUILDING AN AI GATEWAY TO MANAGE AMAZON BEDROCK USING API GATEWAY

Hello everyone. Recently, while working on AWS infrastructure labs—from configuring networks and debugging security with Secrets Manager in a Cloud9 environment to planning machine learning integration with Prometheus for system monitoring—I hit a pretty difficult problem: How to manage access permissions and control costs when teams start sharing Large Language Models (LLMs) on Amazon Bedrock?

In practice, when building Generative AI applications, you cannot simply hand out the Bedrock API key for everyone to call directly. Costs would skyrocket, and tenant isolation (managing data boundaries between users) would be virtually zero. After struggling for a while, I found an excellent reference pattern from Dynatrace and decided to test it out. Today, I'll share my experience of designing this "AI Gateway" from a practical standpoint.

### General Architecture - Compact Yet Powerful
Instead of letting the client talk directly to Bedrock, I set up a shield using Amazon API Gateway as the center. The entire request flow is broken down as follows:

* **Route 53 (Optional but recommended):** Instead of using the default long AWS endpoint, I used Route 53 to map a custom domain for a clean, corporate-standard format.
* **API Gateway (Main entry point):** Here, I set up rate-limiting rules to prevent spam and set quotas to avoid going over budget. The best part is that it supports response streaming, so when the application needs to stream text back from the LLM word-by-word in real time, everything runs extremely smoothly.
* **Lambda Authorizer (Security checkpoint):** Clients calling the API cannot come empty-handed. I configured a Lambda function to authenticate JWT tokens. They must have a valid token to proceed inside.
* **Lambda Integration (Heart of the system):** This is my favorite part. This Lambda function acts as a diligent courier. It captures the entire raw request from the user (headers, body, and parameters), automatically signs the call using AWS Signature Version 4 (SigV4), and forwards it to the correct Amazon Bedrock endpoint.

### Why Do I Highly Value This Pattern?
During actual deployment, this model solves two core problems that infrastructure engineers care about:

1. **Transparent to Client:** I regularly test code locally and use the Boto3 library extensively. The great thing about this gateway is that when calling the API, the client-side code requires almost no modification. External systems assume they are communicating directly with Bedrock, while in reality, everything is passing through a strict background filtering layer.
2. **Future-proof Design:** Anyone working on Cloud knows that AWS updates Bedrock features constantly. If the gateway had to hardcode every API endpoint, you'd have to edit the code every time a new model was released.

Thanks to the design of the Lambda Integration function, which only packages and signs the requests rather than deeply interfering with the API structure, if Bedrock launches a new model tomorrow or updates its Knowledge Bases, the system will keep running stably without needing a single line of maintenance code.

### Conclusion
Coming from a background in monitoring and data visualization systems (such as Grafana or Zabbix), routing all AI traffic through a single API Gateway makes it incredibly easy to connect monitoring tools to track system health and costs for each project.

Leveraging Serverless services as the management layer for AI not only enhances security but also significantly optimizes operations. If you are also building infrastructure for GenAI applications on AWS, this AI Gateway model is definitely a piece worth fitting into your system.

![AI Gateway Architecture Diagram](/images/3-BlogsPosted/blog2_architecture.png)

* Link: [Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179637596134534/?rdid=654DT9MyMTrqQ5kg#)
* Guide: [AWS Architecture Blog](https://aws.amazon.com/vi/blogs/architecture/building-an-ai-gateway-to-amazon-bedrock-with-amazon-api-gateway/)