---
title: "Setting Up Storage and Queue Services"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

### 5.5.1. Initialize S3 Bucket

1. Navigate to the **S3** service and click **Create bucket** to create a storage location for candidate CVs and documents.
![Create S3](/images/5-Workshop/Tao_S3.jpg)

2. Name the bucket in the format `resume-matching-storage-[AWS-ACCOUNT-ID]-us-east-1`. You can create folders inside to organize the data more easily.
![Create S3 Folder](/images/5-Workshop/Create_Folder_S3.jpg)

3. Under the **Permissions** tab, edit the **Cross-origin resource sharing (CORS)** configuration. Add JSON content to configure `AllowedMethods` including: `GET`, `PUT`, `POST` to allow the web application to upload files to the bucket.
![Add CORS to S3](/images/5-Workshop/Bo_sung_CORS_S3.jpg)

### 5.5.2. Initialize SQS Queues

Use queues to decouple the heavy AI processing flow from the main web response flow.

1. Go to the **SQS** interface. Create a Standard queue named `ResumeMatching-DLQ` (Dead Letter Queue) to catch messages that fail during processing.
![Create DLQ](/images/5-Workshop/Tao_queue.jpg)

2. Initialize the main queue named `ResumeMatching-Queue`.
3. Enable the **Dead-letter queue** feature on the main queue, point it to the ARN of `ResumeMatching-DLQ`, and set `Maximum receives` = `3`.
![Create Main Queue](/images/5-Workshop/Tao_main_queue.jpg)
