---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Mục tiêu tuần 9:
* Kiểm thử tính sẵn sàng cao (High Availability) và khả năng tự phục hồi của Auto Scaling Group.
* Tiến hành stress test (giả lập tải CPU 100%) lên các máy chủ ảo bằng công cụ kiểm thử hiệu năng.
* Đánh giá quá trình tự động tăng quy mô (Scale Out) và giảm quy mô (Scale In) thực tế dựa trên tải giả lập.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Lập kế hoạch chi tiết các bước kiểm thử khả năng chịu tải và khôi phục sự cố của hệ thống. | 15/06/2026 | 15/06/2026 | [Kiểm thử Auto Scaling trên AWS](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-verify-scalling-activity.html) |
| 3 | - Tiến hành dừng thủ công (Terminate) một máy chủ WordPress đang hoạt động từ bảng điều khiển EC2. <br> - Theo dõi thời gian phát hiện lỗi của ASG và kiểm chứng việc khởi tạo tự động một máy chủ thay thế. | 16/06/2026 | 16/06/2026 | [Vòng đời của máy chủ trong ASG](https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroupLifecycle.html) |
| 4 | - Kết nối SSH vào máy chủ EC2. <br> - Cài đặt công cụ giả lập stress hệ thống Linux `stress` hoặc `stress-ng` từ kho ứng dụng Ubuntu. | 17/06/2026 | 17/06/2026 | [Tài liệu hướng dẫn công cụ stress Linux](https://manpages.ubuntu.com/manpages/noble/man1/stress.1.html) |
| 5 | - Thực hiện chạy lệnh `stress --cpu 4 --timeout 600` để bắt CPU chạy hết công suất 100% trong vòng 10 phút. <br> - Theo dõi biểu đồ chỉ số CPUUtilization trên bảng điều khiển CloudWatch để quan sát sự thay đổi. | 18/06/2026 | 18/06/2026 | [Giám sát chỉ số CPU của EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_metrics_with_cloudwatch.html) |
| 6 | - Đợi CloudWatch Alarm kích hoạt trạng thái báo động `ALARM` do CPU vượt ngưỡng 70%. <br> - Kiểm tra việc ASG tự động tạo thêm máy chủ mới để chia sẻ tải, và tự động thu hồi (Scale In) máy chủ khi quá trình stress test kết thúc. | 19/06/2026 | 19/06/2026 | [Theo dõi hoạt động co giãn trong ASG](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-verify-scalling-activity.html) |

### Kết quả đạt được tuần 9:
* Kiểm chứng thực tế tính năng sẵn sàng cao: ASG tự phát hiện một máy chủ bị mất và khởi tạo thành công máy chủ mới thay thế tức thì để duy trì số lượng máy chủ mong muốn.
* Sử dụng thành thạo công cụ stress test trên Linux để tạo tải giả lập CPU cho máy chủ ảo.
* Đánh giá và ghi nhận quy trình Scale Out diễn ra chính xác: Khi CPU đạt ngưỡng 100%, CloudWatch Alarm kích hoạt ASG bổ sung thêm máy chủ và đăng ký vào Target Group để san sẻ traffic.
* Đánh giá quy trình Scale In thành công: Hệ thống tự động xóa bớt các máy chủ dư thừa khi tải hạ nhiệt nhằm tối ưu chi phí.
