---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---
### Mục tiêu tuần 3:
* Tìm hiểu mô hình cơ sở dữ liệu quan hệ được quản lý (Managed Database) qua dịch vụ Amazon RDS.
* Khởi tạo DB Subnet Group đa vùng (Multi-AZ) và cài đặt một cơ sở dữ liệu RDS MySQL nằm trong phân vùng Private Subnet.
* Sử dụng máy chủ EC2 để kiểm tra kết nối mạng và xác thực Endpoint của cơ sở dữ liệu RDS.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu về cơ chế quản lý tự động của Amazon RDS so với việc tự dựng Database trên EC2. <br> - So sánh các Engine phổ biến như MySQL, PostgreSQL. | 04/05/2026 | 04/05/2026 | [Amazon RDS Overview](https://aws.amazon.com/rds/) |
| 3 | - Tìm hiểu định nghĩa DB Subnet Group (yêu cầu cấu hình Multi-AZ). <br> - Nhóm các Private Subnets ở nhiều Availability Zones khác nhau để làm hạ tầng cho RDS. | 05/05/2026 | 05/05/2026 | [Cấu hình DB Subnet Groups](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceandUTG.html) |
| 4 | - Khởi tạo một Security Group dành riêng cho cơ sở dữ liệu RDS. <br> - Định nghĩa luật Inbound: Chỉ cho phép traffic cổng 3306 (MySQL) đi từ Security Group của máy chủ Web EC2. | 06/05/2026 | 06/05/2026 | [Phân quyền Security Group cho RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html) |
| 5 | - Triển khai cơ sở dữ liệu MySQL thông qua bảng điều khiển Amazon RDS. <br> - Tắt tùy chọn Public Accessibility để đảm bảo database không bị truy cập trực tiếp từ Internet. | 07/05/2026 | 07/05/2026 | [Khởi tạo RDS MySQL](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.CreatingConnecting.MySQL.html) |
| 6 | - Truy cập SSH vào máy chủ EC2 và cài đặt công cụ dòng lệnh MySQL Client. <br> - Dùng MySQL Client kiểm tra kết nối từ EC2 tới endpoint của RDS thành công. | 08/05/2026 | 08/05/2026 | [Kết nối cơ sở dữ liệu MySQL trên RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html) |

### Kết quả đạt được tuần 3:
* Hiểu rõ cơ chế và lợi ích khi sử dụng dịch vụ cơ sở dữ liệu được quản lý hoàn toàn trên đám mây.
* Xây dựng thành công DB Subnet Group liên kết các Private Subnets bảo mật.
* Triển khai hoạt động ổn định cơ sở dữ liệu RDS MySQL nằm ẩn hoàn toàn trong mạng Private.
* Thiết lập phân quyền truy cập thông minh cho database bằng cách chỉ chấp nhận kết nối từ đúng Security Group của Web Server.
* Kết nối và tương tác thành công với database thông qua client từ máy chủ trung gian EC2.
