---
title: "Bản đề xuất"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Đề xuất dự án: AI Resume Matching & Interview Preparation Platform

### 1. Tổng quan dự án

*   **Mục tiêu:** Xây dựng ứng dụng Web đánh giá mức độ phù hợp giữa CV (hồ sơ ứng viên) và JD (yêu cầu tuyển dụng) dựa trên hạ tầng đám mây AWS chuẩn kiến trúc 3-Tier.
*   **Xử lý AI:** Cụm máy chủ EC2 (Backend + Worker) chịu trách nhiệm chính trong việc phân tích CV và JD bằng cách gọi các mô hình LLM thông qua API của OpenAI qua Internet, giúp tối ưu lượng token tiêu thụ và tiết kiệm chi phí tối đa.

### 2. Kiến trúc hạ tầng đám mây (AWS)

Hệ thống được thiết kế theo chuẩn kiến trúc 3 lớp (3-Tier Architecture) chạy trong VPC, đảm bảo tính sẵn sàng cao (High Availability), bảo mật và khả năng co giãn tự động:

![Sơ đồ kiến trúc giải pháp AI Resume Matching & Interview Preparation](/images/2-Proposal/proposal_architecture.png)

*   **Lớp Biên & Toàn Cầu (Global):**
    *   Mạng phân phối nội dung (Amazon CloudFront), tường lửa bảo mật AWS WAF và dịch vụ xác thực đang trong trạng thái dự kiến triển khai (Planned but not deployed - AWS account verification required), đây là các dịch vụ chờ xác minh tài khoản AWS và không phải là các dịch vụ đang hoạt động thực tế.
    *   Sử dụng Amazon S3 (Amazon Simple Storage Service) làm không gian lưu trữ chung.
    *   Người dùng (Users) tương tác với hệ thống qua Internet Gateway (1) hoặc thực hiện tải lên tệp tin trực tiếp thông qua cơ chế **Pre-signed URL** tới một phân vùng lưu trữ S3 riêng biệt (S3 CV/JD Storage) (5).

*   **Mạng & Cân Bằng Tải (Inbound):**
    *   Hạ tầng chạy trong dải mạng VPC `10.0.0.0/16` làm nền tảng cô lập.
    *   **Internet Gateway (IGW):** Làm cửa ngõ duy nhất kết nối với Internet cho toàn bộ lưu lượng Inbound (đi vào) và Outbound (đi ra ngoài qua NAT Gateway).
    *   **Application Load Balancer (ALB):** Nằm giữa các Vùng Sẵn Sàng (Availability Zones), tiếp nhận lưu lượng từ IGW và thực hiện phân phối tải thông minh đến cụm máy chủ Auto Scaling Group.

*   **Tầng Ứng Dụng (Application):**
    *   Cụm máy chủ EC2 (Backend + Worker) được đặt trong các phân vùng mạng con ứng dụng kín (**Private App Subnet A** & **Private App Subnet B**), trải dài qua 2 Vùng Sẵn Sàng (**Availability Zone A** & **Availability Zone B**) và được quản lý bởi một **Auto Scaling Group (ASG)** giúp tự động co giãn số lượng máy chủ dựa theo tải thực tế.
    *   **Giao tiếp nội bộ:** Các máy chủ EC2 ở AZ A kết nối trực tiếp với dịch vụ S3 storage và hàng đợi thông điệp Amazon SQS (6), có cấu hình Dead Letter Queue (DLQ) để xử lý các tác vụ lỗi.
    *   **Luồng xử lý API OpenAI:** Các máy chủ EC2 ở AZ B thực hiện đi ra ngoài Internet thông qua NAT Gateway đặt tại Public Subnet B để gọi tới API OpenAI thông qua Internet Gateway. (Lưu ý: Hệ thống triển khai dự phòng với 2 NAT Gateway đặt độc lập tại Public Subnet A và Public Subnet B).

*   **Mạng Outbound & Nội Bộ:**
    *   Triển khai **hai NAT Gateway** (một đặt tại Public Subnet A và một đặt tại Public Subnet B) giúp nâng cao khả năng dự phòng (High Availability) cho lưu lượng Outbound đi ra ngoài từ các mạng con Private Subnets.
    *   Mọi giao tiếp nội bộ đến SQS và S3 được truyền tải qua mạng VPC an toàn.

*   **Tầng Cơ Sở Dữ Liệu (Database):**
    *   Sử dụng dịch vụ cơ sở dữ liệu quan hệ **Amazon RDS PostgreSQL** cấu hình dự phòng đa vùng **Multi-AZ**.
    *   Đặt tại hai mạng con cơ sở dữ liệu kín (**Private DB Subnet A** & **Private DB Subnet B**) và được bảo vệ nghiêm ngặt bởi lớp tường lửa Security Group riêng biệt.
    *   RDS Primary (Master) đặt ở AZ A thực hiện ghi dữ liệu. RDS Standby Replica đặt ở AZ B nhận đồng bộ dữ liệu liên tục theo cơ chế đồng bộ (đường đứt nét).
    *   **Luồng kết nối:** Máy chủ EC2 ở AZ A kết nối trực tiếp đến RDS Primary (7). Máy chủ EC2 ở AZ B kết nối đến RDS Standby Replica thông qua RDS Endpoints (đường đứt nét) khi xảy ra sự cố chuyển vùng (Failover).

*   **Quản Lý & Giám Sát:**
    *   Phân vùng quản lý vùng khu vực bao gồm: **AWS Systems Manager** để quản trị máy chủ, **Amazon CloudWatch** để giám sát và lưu trữ log, và **AWS Secrets Manager** để quản lý và mã hóa các khóa bảo mật API Key của OpenAI.

*   **Triển Khai (Deployment):**
    *   Mã nguồn dự án được lưu trữ tại GitHub và thực hiện triển khai thủ công (**Manual Deployment**). Kiến trúc hiện tại không áp dụng các công cụ CI/CD tự động như AWS CodeBuild hay AWS CodePipeline.