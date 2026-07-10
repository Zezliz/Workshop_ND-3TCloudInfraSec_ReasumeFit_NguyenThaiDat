---
title: "Giám sát Hệ thống và Tính sẵn sàng cao"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

Việc giám sát là bắt buộc để đảm bảo luồng traffic được phân bổ chính xác và các quy tắc Scaling hoạt động đúng chuẩn.

### 5.9.1. Kiểm tra hoạt động của Auto Scaling Group

1. Truy cập dịch vụ **EC2**, điều hướng đến menu **Instances**.
2. Quan sát hệ thống tự động khởi tạo các EC2 mới có tên `ResumeMatching-ASG-Instance` phân bổ đều ở các Availability Zone khác nhau.
3. Một số máy chủ cũ có thể hiển thị trạng thái `Terminated`. Đây là minh chứng ASG đang hoạt động chính xác: tự động thu hồi máy chủ cũ và khởi chạy máy chủ mới khi có sự thay đổi cấu hình hoặc lỗi hệ thống.

### 5.9.2. Kiểm tra Health Check của Target Group

1. Tại mục **Load Balancing**, chọn **Target Groups**, nhấn chọn vào Target Group của hệ thống.
2. Chuyển sang tab **Targets** và quan sát bảng **Registered targets**.
3. Xác nhận cột `Health status` của các instance hiển thị trạng thái màu xanh `Healthy`, chứng minh máy chủ web đã khởi động và sẵn sàng nhận request từ Load Balancer.
![Target group healthy check](/images/5-Workshop/Target_group_healthy_check.jpg)

### 5.9.3. Giám sát hiệu suất qua CloudWatch

1. Truy cập **CloudWatch**, chọn menu **Metrics** để giám sát sâu các thông số.
2. **Đối với EC2**: Lọc Namespace EC2, chọn `CPUUtilization`. Quan sát biểu đồ để thấy các đỉnh gai xử lý (ví dụ `81.9%`) khi AI chạy tác vụ nặng, từ đó thiết lập Threshold mở rộng tự động cho ASG.
![CloudWatch monitor EC2](/images/5-Workshop/CloudWatch_dang_monitor_EC2.jpg)
![EC2 Metrics](/images/5-Workshop/EC2_Metrics.jpg)

3. **Đối với ALB**: Lọc metric `RequestCount` và `TargetResponseTime`. Sự tương quan giữa việc tăng vọt lượng Request và sự thay đổi của thời gian phản hồi (ví dụ `660.4 ms`) giúp đánh giá tính trơn tru của trải nghiệm người dùng.
![CloudWatch monitor ALB](/images/5-Workshop/CloudWatch_monitor_Load_Balancer.jpg)
![ALB Metrics](/images/5-Workshop/ALB_Metrics.jpg)
