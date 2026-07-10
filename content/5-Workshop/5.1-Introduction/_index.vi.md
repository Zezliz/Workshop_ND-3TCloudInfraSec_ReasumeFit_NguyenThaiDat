---
title: "Giới thiệu"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

Bài lab này hướng dẫn chi tiết cách triển khai toàn diện hệ thống **Resume Fit** trên nền tảng đám mây AWS. Resume Fit là một ứng dụng AI giúp đánh giá độ phù hợp giữa Hồ sơ ứng viên (CV) và Yêu cầu công việc (JD) một cách nhanh chóng, minh bạch nhằm hỗ trợ ra quyết định tuyển dụng.

Hệ thống được thiết kế theo kiến trúc chuẩn trên AWS, đảm bảo tính mở rộng và sẵn sàng cao, bao gồm các thành phần cốt lõi: Mạng cô lập (VPC), Máy chủ tính toán linh hoạt (EC2, Auto Scaling Group), Cơ sở dữ liệu quan hệ (RDS PostgreSQL), Lưu trữ đối tượng (S3), Hàng đợi xử lý bất đồng bộ (SQS), Dịch vụ giám sát (CloudWatch) và Dịch vụ Quản lý Secret (Secrets Manager).
