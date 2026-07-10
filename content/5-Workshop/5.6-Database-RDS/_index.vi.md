---
title: "Thiết lập Hệ Quản Trị Cơ Sở Dữ Liệu (RDS)"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

### 5.6.1. Cấu hình Secrets Manager

1. Truy cập **AWS Secrets Manager**, tạo secret tên `ResumeMatching-Secrets` để lưu trữ thông tin nhạy cảm.
![Tạo Secret](/images/5-Workshop/Tao_Secret.jpg)

2. Cấu hình phần **Secret value** với các trường Key/value như `HOST`, `PORT` (`5432`), `USERNAME`, `PASSWORD`, và `OPENAI_API_KEY` của ứng dụng.
![Cập nhật Secrets Manager](/images/5-Workshop/Cap_nhat_Secrets_manager.jpg)

### 5.6.2. Tạo RDS PostgreSQL

1. Truy cập giao diện **RDS**, chọn mục **Subnet groups** và tạo một subnet group tên `resumematching-dbsubnetgroup` trỏ vào VPC và gom 2 subnet `Private-DB-A`, `Private-DB-B` lại với nhau.
![Tạo DB Subnet Group](/images/5-Workshop/Tao_DB_Subnet_Group.jpg)

2. Tiến hành khởi tạo Database (DB identifier: `resume-matching-db`) với Engine là **PostgreSQL** và instance class là `db.t3.micro`.
![Tạo RDS Database](/images/5-Workshop/Tao_RDS_database.jpg)

3. Sau khi tạo thành công, copy Endpoint của Database và dán cập nhật vào khóa `HOST` trong Secrets Manager.
