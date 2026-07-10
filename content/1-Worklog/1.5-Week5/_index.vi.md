---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---
### Mục tiêu tuần 5:
* Tìm hiểu vai trò và lợi ích của Amazon Machine Image (AMI) trong việc sao lưu hệ thống và mở rộng máy chủ.
* Đóng gói máy chủ EC2 chứa ứng dụng WordPress đã hoàn thiện cấu hình thành một bản ghi AMI chuẩn hóa.
* Khởi tạo và thiết lập Launch Template (mẫu khởi chạy cấu hình) sử dụng AMI vừa đóng gói.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu lý thuyết về AMI (EBS-backed vs Instance-store). <br> - Nghiên cứu vòng đời của AMI và vai trò trong việc nhân bản máy chủ nhanh chóng. | 18/05/2026 | 18/05/2026 | [Amazon Machine Images (AMIs)](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html) |
| 3 | - Kết nối vào máy chủ EC2 dọn dẹp các tệp log tạm, lịch sử lệnh SSH và cache hệ thống. <br> - Tắt máy chủ EC2 một cách an toàn để đảm bảo tính nhất quán của dữ liệu ổ đĩa. | 19/05/2026 | 19/05/2026 | [Chuẩn bị máy chủ trước khi tạo AMI](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html#how-to-create-ebs-ami) |
| 4 | - Thực hiện thao tác tạo Image từ máy chủ EC2 trên bảng điều khiển AWS. <br> - Theo dõi trạng thái của AMI và kiểm tra cho đến khi chuyển sang trạng thái "available". | 20/05/2026 | 20/05/2026 | [Tạo AMI từ ổ đĩa EBS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/creating-an-ami-ebs.html) |
| 5 | - Học lý thuyết phân biệt Launch Template và Launch Configuration. <br> - Xác định các tham số cấu hình: Dòng máy chủ, ID của custom AMI, Key Pair và Security Group. | 21/05/2026 | 21/05/2026 | [Launch Templates Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html) |
| 6 | - Khởi tạo Launch Template trên bảng điều khiển AWS. <br> - Thử nghiệm tạo 1 máy chủ mới từ Launch Template để kiểm tra xem WordPress có hoạt động tự động mà không cần cài đặt lại hay không. | 22/05/2026 | 22/05/2026 | [Tạo máy chủ từ Launch Template](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html#launch-from-template) |

### Kết quả đạt được tuần 5:
* Hiểu rõ cơ chế đóng gói hệ điều hành và phần mềm trên nền tảng AWS thông qua AMI.
* Đóng gói thành công máy chủ WordPress thành bản mẫu AMI tái sử dụng linh hoạt.
* Thiết lập chuẩn hóa tài nguyên khởi tạo thông qua việc tạo Launch Template có hỗ trợ phiên bản.
* Kiểm tra và kiểm chứng tính năng nhân bản máy chủ hoạt động trơn tru: Máy chủ mới khởi chạy từ Launch Template tự động kích hoạt mã nguồn và chạy tốt WordPress mà không cần can thiệp cài đặt tay.
