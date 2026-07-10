---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
### Mục tiêu tuần 7:
* Tìm hiểu khái niệm và vai trò của Auto Scaling Group (ASG) trong việc đảm bảo tính sẵn sàng cao và tự phục hồi (Self-healing).
* Khởi tạo Auto Scaling Group liên kết với Launch Template và phân vùng mạng đã thiết kế ở tuần trước.
* Thiết lập các chính sách co giãn tự động để phản hồi lại thay đổi về tải (Scale Out và Scale In).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Học lý thuyết về Auto Scaling: Dung lượng mong muốn (Desired), dung lượng tối thiểu (Min) và dung lượng tối đa (Max). <br> - Tìm hiểu cơ chế tự phát hiện lỗi và thay thế máy chủ lỗi. | 01/06/2026 | 01/06/2026 | [Amazon EC2 Auto Scaling Concepts](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) |
| 3 | - Khởi tạo Auto Scaling Group thông qua trình thuật thuật trên AWS Console. <br> - Chọn Launch Template chứa ứng dụng WordPress và phân bổ ASG chạy trên nhiều subnets ở các Availability Zones khác nhau. | 02/06/2026 | 02/06/2026 | [Khởi tạo Auto Scaling Group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/create-asg-launch-template.html) |
| 4 | - Liên kết ASG trực tiếp với Target Group của Application Load Balancer (ALB). <br> - Cấu hình kiểm tra sức khỏe thông qua bộ Load Balancer và đặt thời gian chờ khởi chạy (Grace Period). | 03/06/2026 | 03/06/2026 | [Gắn Load Balancer vào Auto Scaling Group](https://docs.aws.amazon.com/autoscaling/ec2/userguide/attach-load-balancer-asg.html) |
| 5 | - Cấu hình chính sách co giãn động (Dynamic Scaling Policy) sử dụng thuật toán Target Tracking dựa trên chỉ số CPU sử dụng trung bình. <br> - Thiết lập ngưỡng mở rộng (Scale Out khi CPU > 70%) và thời gian cooldown để hệ thống ổn định trước khi co giãn tiếp. | 04/06/2026 | 04/06/2026 | [Chính sách co giãn cho Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html) |
| 6 | - Triển khai ASG và theo dõi hoạt động khởi tạo máy chủ ban đầu. <br> - Xác nhận các máy chủ mới được tự động sinh ra, đăng ký vào Target Group của ALB và vượt qua bài kiểm tra Health Check thành công. | 05/06/2026 | 05/06/2026 | [Theo dõi hoạt động của ASG](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-verify-scalling-activity.html) |

### Kết quả đạt được tuần 7:
* Nắm vững kỹ năng xây dựng kiến trúc có khả năng tự động đàn hồi theo tải thực tế.
* Tạo thành công Auto Scaling Group dựa trên khuôn mẫu Launch Template sẵn có.
* Tích hợp hoàn hảo ASG với bộ cân bằng tải ALB giúp phân tải tự động vào các máy chủ mới tạo.
* Thiết lập thành công chính sách co giãn tự động (Scale Out/Scale In) giúp hệ thống tự động tăng tài nguyên khi quá tải và giảm tài nguyên khi nhàn rỗi để tiết kiệm chi phí.
* Kiểm chứng hệ thống tự khởi chạy thành công số lượng máy chủ mong muốn ban đầu.
