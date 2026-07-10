---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# 5. Workshop: Triển khai AI Resume Matching & Interview Preparation Platform trên AWS

Bài lab này hướng dẫn chi tiết cách triển khai toàn diện hệ thống **Resume Fit** trên nền tảng đám mây AWS. Resume Fit là một ứng dụng AI giúp đánh giá độ phù hợp giữa Hồ sơ ứng viên (CV) và Yêu cầu công việc (JD) một cách nhanh chóng, minh bạch nhằm hỗ trợ ra quyết định tuyển dụng.

Hệ thống được thiết kế theo kiến trúc chuẩn trên AWS, đảm bảo tính mở rộng và sẵn sàng cao, bao gồm các thành phần cốt lõi: Mạng cô lập (VPC), Máy chủ tính toán linh hoạt (EC2, Auto Scaling Group), Cơ sở dữ liệu quan hệ (RDS PostgreSQL), Lưu trữ đối tượng (S3), Hàng đợi xử lý bất đồng bộ (SQS), Dịch vụ giám sát (CloudWatch) và Dịch vụ Quản lý Secret (Secrets Manager).

#### Nội dung

1. [Giới thiệu](5.1-Introduction/)
2. [Các bước chuẩn bị (Prerequisites)](5.2-Prerequisites/)
3. [Xây dựng Hạ tầng Mạng (Networking)](5.3-Networking/)
4. [Thiết lập Bảo mật và Quản lý Truy cập](5.4-Security-IAM/)
5. [Thiết lập Dịch vụ Lưu trữ và Hàng đợi](5.5-Storage-Queue/)
6. [Thiết lập Hệ Quản Trị Cơ Sở Dữ Liệu (RDS)](5.6-Database-RDS/)
7. [Triển khai Compute và Cấu hình Server](5.7-Compute-EC2/)
8. [Thiết lập Tự động mở rộng và Cân bằng tải](5.8-AutoScaling-ALB/)
9. [Giám sát Hệ thống và Đảm bảo Tính sẵn sàng cao](5.9-Monitoring/)
10. [Kiểm thử Ứng dụng Resume Fit](5.10-Testing/)
11. [Dọn dẹp tài nguyên (Clean up)](5.11-Cleanup/)