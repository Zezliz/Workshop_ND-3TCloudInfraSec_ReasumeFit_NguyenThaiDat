---
title: "Thiết lập Tự động mở rộng và Cân bằng tải"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

### 5.8.1. Cấu hình AMI và Launch Template

1. Chuẩn hóa môi trường EC2 vừa cài đặt bằng cách tạo ra một Amazon Machine Image (AMI) mang tên `ResumeMatching-Backend-AMI`.
![Tạo AMIs](/images/5-Workshop/Tao_AMIs.jpg)

2. Từ AMI này, tạo một **Launch Template** mang tên `ResumeMatching-LT` chứa các cấu hình phần cứng, mạng và bảo mật chuẩn.
![Tạo Launch Template](/images/5-Workshop/Tao_launch_template.jpg)

### 5.8.2. Auto Scaling Group (ASG)

1. Tạo Auto Scaling Group `ResumeMatching-ASG` và liên kết với Launch template `ResumeMatching-LT`.
![Tạo ASG](/images/5-Workshop/Tao_ASG.jpg)

2. Chỉnh sửa Desired capacity lên thành `2`. ASG sẽ tự động launch ra các EC2 instances mới ở trạng thái Initializing nhằm phục vụ dự phòng và mở rộng.
![ASG tạo thêm EC2](/images/5-Workshop/ASG_tao_them_EC2.jpg)
![ASG tạo EC2 mới sau khi cập nhật AMI](/images/5-Workshop/ASG_tao_EC2_moi_sau%20khi_cap_nhat_AMI.jpg)

### 5.8.3. Target Group và Application Load Balancer

1. Tạo một **Target Group** tên `ResumeMatching-TG`, dạng `Instance` giao thức HTTP trên cổng `8080` (hoặc `80` tùy cấu hình container nội bộ).
![Tạo Target Group](/images/5-Workshop/Tao_target_group.jpg)

2. Khởi tạo **Application Load Balancer (ALB)** tên `ResumeMatching-ALB`. Lựa chọn Scheme là `Internet-facing` để nhận traffic từ ngoài internet, lắng nghe tại 2 Availability Zones và định tuyến giao thông vào mạng thông qua Target Group trên.
![Tạo ALB](/images/5-Workshop/Tao_ALB.jpg)
