---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
### Mục tiêu tuần 8:
* Tìm hiểu dịch vụ giám sát hệ thống Amazon CloudWatch và các chỉ số hiệu năng (Metrics).
* Cấu hình CloudWatch Alarms (hệ thống cảnh báo) để giám sát ngưỡng CPU của máy chủ EC2.
* Tích hợp CloudWatch Alarms để kích hoạt tự động các chính sách tăng/giảm quy mô của Auto Scaling Group.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Học các khái niệm cơ bản trong CloudWatch: Metrics, Namespaces, Dimensions và Statistics. <br> - Tìm hiểu các chỉ số hiệu năng mặc định của EC2 (CPUUtilization, NetworkIn/Out). | 08/06/2026 | 08/06/2026 | [Amazon CloudWatch Concepts](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Concepts.html) |
| 3 | - Tìm hiểu logic hoạt động và thiết lập điều kiện kích hoạt cảnh báo (Alarms). <br> - Thiết kế các ngưỡng cảnh báo phù hợp với hiệu năng hệ thống để tối ưu co giãn. | 09/06/2026 | 09/06/2026 | [Cấu hình CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ConsoleAlarms.html) |
| 4 | - Khởi tạo CloudWatch Alarm cảnh báo CPU cao (High CPU). <br> - Đặt điều kiện: Kích hoạt khi chỉ số CPUUtilization trung bình vượt quá 70% trong 2 chu kỳ kiểm tra liên tiếp (mỗi chu kỳ 1 phút). | 10/06/2026 | 10/06/2026 | [Tạo Alarm giám sát EC2 CPU](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/create_alarms.html) |
| 5 | - Khởi tạo CloudWatch Alarm cảnh báo CPU thấp (Low CPU). <br> - Đặt điều kiện: Kích hoạt khi chỉ số CPU Utilization trung bình giảm xuống dưới 30% để thu hẹp tài nguyên dư thừa. | 11/06/2026 | 11/06/2026 | [Sử dụng Alarm làm điều kiện co giãn](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html#as-scaling-setup-alarms) |
| 6 | - Tích hợp High CPU Alarm với chính sách Scale Out của ASG (tự động thêm 1 máy chủ). <br> - Tích hợp Low CPU Alarm với chính sách Scale In của ASG (tự động giảm 1 máy chủ). Thiết lập thông báo qua dịch vụ SNS để gửi email cảnh báo cho quản trị viên. | 12/06/2026 | 12/06/2026 | [Cấu hình thông báo Email bằng Amazon SNS](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) |

### Kết quả đạt được tuần 8:
* Hiểu rõ tầm quan trọng của hệ thống giám sát và thu thập dữ liệu chỉ số hiệu năng trên đám mây qua CloudWatch.
* Xây dựng thành công bộ cảnh báo tự động giám sát mức tải CPU của cụm máy chủ.
* Đồng bộ hóa hoàn tất dữ liệu cảnh báo từ CloudWatch với các chính sách co giãn của Auto Scaling Group để tạo ra hệ thống tự động hoàn toàn.
* Cấu hình thành công dịch vụ Amazon SNS gửi email cảnh báo tự động về hòm thư khi hệ thống thay đổi trạng thái (Ok -> Alarm).
