---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---
### Mục tiêu tuần 2:
* Tìm hiểu các khái niệm cốt lõi của máy chủ ảo Amazon EC2 (Elastic Compute Cloud).
* Hiểu cách cấu hình Security Group hoạt động như một tường lửa lọc dữ liệu mạng.
* Khởi tạo máy chủ EC2, cấu hình khóa SSH bảo mật và kiểm tra truy cập từ xa thành công.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu về các dòng máy chủ EC2 (t-family, m-family) và các loại cấu hình tài nguyên. <br> - Xem các khái niệm về AMI, EBS volume và Key Pair. | 27/04/2026 | 27/04/2026 | [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/) |
| 3 | - Tìm hiểu cơ chế hoạt động của Security Group (tường lửa ảo cấp máy chủ). <br> - Thiết lập sơ đồ lọc traffic Inbound/Outbound. | 28/04/2026 | 28/04/2026 | [Amazon EC2 Security Groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html) |
| 4 | - Khởi tạo 1 máy chủ EC2 (chọn t2.micro và hệ điều hành Ubuntu Server) nằm trong Public Subnet của VPC đã tạo tuần 1. <br> - Cấu hình Security Group cho phép SSH (Port 22) từ IP của bạn và HTTP (Port 80) từ mọi nơi. | 29/04/2026 | 29/04/2026 | [Khởi tạo EC2 trên AWS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html) |
| 5 | - Cấu hình file Private Key (.pem) trên máy cá nhân để kết nối SSH. <br> - Tìm hiểu cách thiết lập quyền hạn file khóa bảo mật (chmod 400 hoặc cấu hình Security trên Windows). | 30/04/2026 | 30/04/2026 | [Sửa lỗi SSH vào máy chủ EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstances.html) |
| 6 | - Thực hiện kết nối SSH từ máy cá nhân vào EC2 thành công. <br> - Gán Elastic IP (IP tĩnh công cộng) vào EC2 để cố định địa chỉ truy cập từ Internet. | 01/05/2026 | 01/05/2026 | [Elastic IP Addresses Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) |

### Kết quả đạt được tuần 2:
* Hiểu rõ cơ chế cung cấp tài nguyên tính toán của dịch vụ Amazon EC2.
* Thành thạo việc cấu hình các chính sách bảo mật cho máy chủ thông qua Security Group.
* Khởi tạo thành công máy chủ Ubuntu Linux hoạt động ổn định trong Public Subnet.
* Kết nối SSH điều khiển máy chủ từ xa an toàn qua Key Pair.
* Liên kết thành công Elastic IP với máy chủ để đảm bảo IP không bị thay đổi mỗi khi khởi động lại máy chủ ảo.
