---
title: "Dọn dẹp tài nguyên"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

Sau khi hoàn tất quá trình workshop và kiểm thử, để tránh phát sinh chi phí lưu trữ và duy trì hạ tầng không cần thiết trên AWS, hãy tiến hành dọn dẹp theo thứ tự sau:

1. Xóa **Auto Scaling Group** để ngăn hệ thống tự khởi tạo lại máy chủ, sau đó Terminate các **EC2 Instances** thủ công còn sót lại.
2. Xóa **Application Load Balancer** và **Target Group**.
3. Xóa **Database RDS** (bỏ chọn tính năng tạo Snapshot cuối cùng nếu không cần giữ data) và **Subnet Group** của RDS.
4. Xóa **NAT Gateway**, đợi đến khi trạng thái là `Deleted` thì Release các **Elastic IPs**.
5. Giải phóng **VPC Endpoints**, **Route Tables**, **Internet Gateway**, **Subnets** và cuối cùng là xóa **VPC**.
6. Xóa rỗng toàn bộ object trong **S3 bucket**, sau đó tiến hành Delete Bucket.
