---
title: "Thiết lập Dịch vụ Lưu trữ và Hàng đợi"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

### 5.5.1. Khởi tạo S3 Bucket

1. Chuyển sang dịch vụ **S3**, nhấn **Create bucket** để tạo nơi lưu trữ CV và tài liệu của ứng viên.
![Tạo S3](/images/5-Workshop/Tao_S3.jpg)

2. Đặt tên bucket có dạng `resume-matching-storage-[AWS-ACCOUNT-ID]-us-east-1`. Có thể tạo thêm các folder bên trong để phân loại dữ liệu dễ dàng hơn.
![Tạo thư mục trong S3](/images/5-Workshop/Create_Folder_S3.jpg)

3. Tại tab **Permissions**, tiến hành chỉnh sửa **Cross-origin resource sharing (CORS)**. Thêm nội dung JSON để cấu hình `AllowedMethods` bao gồm: `GET`, `PUT`, `POST` nhằm cho phép ứng dụng web tải file lên bucket.
![Bổ sung CORS cho S3](/images/5-Workshop/Bo_sung_CORS_S3.jpg)

### 5.5.2. Khởi tạo SQS Queues

Sử dụng hàng đợi để tách biệt luồng xử lý AI nặng nề ra khỏi luồng phản hồi web chính.

1. Chuyển đến giao diện **SQS**. Tạo một hàng đợi Standard có tên `ResumeMatching-DLQ` (Dead Letter Queue) dùng để hứng các message bị lỗi trong quá trình xử lý.
![Tạo DLQ](/images/5-Workshop/Tao_queue.jpg)

2. Khởi tạo hàng đợi chính mang tên `ResumeMatching-Queue`.
3. Bật tính năng **Dead-letter queue** trên hàng đợi chính, trỏ đến ARN của `ResumeMatching-DLQ` và thiết lập `Maximum receives` = `3`.
![Tạo Main Queue](/images/5-Workshop/Tao_main_queue.jpg)
