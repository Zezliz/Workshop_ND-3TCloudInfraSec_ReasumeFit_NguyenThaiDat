---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
# A VERY COOL FEATURE OF AWS LAKE FORMATION

Recently, while researching Data Lakes on AWS, I read a very interesting article from AWS about Lake Formation that I wanted to share with everyone.

Looking at the diagram, we can see:

* **EMR Spark** reads/writes data directly with S3 via IAM Permissions.
* **Lake Formation** manages permissions on data tables in the Glue Catalog.
* **Athena** queries data based on Lake Formation permissions.

This leads to a fairly common situation:
You can query data using Athena normally, but when using Spark to read files directly in S3, you get an **Access Denied** error.

The reason is that Athena and Spark use two different authorization mechanisms:
* Athena $\rightarrow$ Lake Formation
* Spark reading S3 files $\rightarrow$ IAM / S3 Policy

AWS recently introduced a new feature that solves this problem.
Lake Formation can now grant temporary credentials for Spark to access data directly in S3 based on permissions already granted in Lake Formation via the API:
`GetTemporaryDataLocationCredentials()`

In my opinion, the best parts of this feature are:
* **Reduces permission sprawl:** Reduces the need to manage permissions in multiple places.
* **Limits configuration mismatch:** Limits Access Denied errors caused by configuration misalignment between IAM and Lake Formation.
* **Streamlined workloads:** More convenient for Spark workloads, ETL, and Machine Learning.
* **Auditable access:** Easy to track data access activities through CloudTrail logs.

A few notes are that this feature currently requires:
* S3 Location must be registered with Lake Formation.
* Requires Amazon EMR 6.15.0+ or 7.1.0+.
* Does not support Apache Iceberg yet.
* Does not support Cross-Region yet.

I find this to be a very useful improvement for Data Lake systems on AWS, especially in environments that use both Athena and EMR Spark.

![AWS Lake Formation Architecture Diagram](/images/3-BlogsPosted/blog3_architecture.png)

* Link: [Facebook Post](https://www.facebook.com/groups/awsstudygroupfcj/posts/2191055074992786/?notif_id=1782041739635661&notif_t=group_post_approved&ref=notif)
* Guide: [AWS Big Data Blog](https://aws.amazon.com/vi/blogs/big-data/access-amazon-s3-data-files-directly-using-aws-lake-formation-permissions/?fbclid=IwY2xjawSu8LtleHRuA2FlbQIxMABicmlkETFDd1poRWJtcTNFMEw4bmJKc3J0YwZhcHBfaWQQMjIyMDM5MTc4ODIwMDg5MgABHlfRqurG5Rir4FRt1bIoRDfriCsPR9wuIOYoTnZdypKxZVcIBVgtWsk4A8C9_aem_pW5Px8mN6tGNyQOA7DJaXA)