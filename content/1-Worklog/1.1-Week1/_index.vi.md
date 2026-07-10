---
title: "Worklog Tuần 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---
### Mục tiêu tuần 1:
* Tìm hiểu tổng quan về hạ tầng toàn cầu của AWS (Regions, Availability Zones, Edge Locations).
* Đăng ký thành công tài khoản AWS Free Tier và thiết lập bảo mật cơ bản.
* Khởi tạo và cấu hình mạng VPC tùy chỉnh bao gồm phân vùng Subnet (Public/Private), Route Table và Internet Gateway (IGW).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu về AWS Regions, Availability Zones (AZs) và Edge Locations. <br> - Đọc hiểu mô hình chia sẻ trách nhiệm (Shared Responsibility Model). | 20/04/2026 | 20/04/2026 | [AWS Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/) |
| 3 | - Đăng ký tài khoản AWS Free Tier. <br> - Cấu hình tài khoản IAM Admin, kích hoạt xác thực đa nhân tố (MFA). <br> - Cấu hình Billing Alarm cảnh báo chi phí. | 21/04/2026 | 21/04/2026 | [AWS Free Tier Registration Guide](https://aws.amazon.com/free/) |
| 4 | - Học lý thuyết Amazon VPC: Dải CIDR, Subnet, Route Table và Gateway. <br> - Thiết kế sơ đồ phân hoạch mạng cho ứng dụng WordPress. | 22/04/2026 | 22/04/2026 | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| 5 | - Khởi tạo VPC tùy chọn với dải CIDR 10.0.0.0/16. <br> - Thiết lập Public Subnet (10.0.1.0/24) và Private Subnet (10.0.2.0/24). <br> - Tạo và đính kèm Internet Gateway (IGW) vào VPC. | 23/04/2026 | 23/04/2026 | [Khởi tạo VPC trên AWS](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html) |
| 6 | - Tạo Route Table cho Public Subnet và Private Subnet. <br> - Định tuyến dải 0.0.0.0/0 trỏ về Internet Gateway cho Public Route Table. <br> - Gán Subnet tương ứng và kiểm tra luồng định tuyến mạng. | 24/04/2026 | 24/04/2026 | [VPC Route Tables Guide](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) |

### Kết quả đạt được tuần 1:
* Nắm vững kiến thức nền tảng về hạ tầng toàn cầu của AWS.
* Thiết lập thành công tài khoản thực hành cá nhân đảm bảo các yếu tố bảo mật cơ bản như MFA và quản lý phân quyền qua IAM.
* Xây dựng hoàn chỉnh hạ tầng mạng VPC tùy chỉnh dải `10.0.0.0/16` làm nền móng vững chắc cho các tài nguyên sẽ triển khai.
* Phân chia mạng con thành Public Subnet (`10.0.1.0/24`) phục vụ Web server và Private Subnet (`10.0.2.0/24`) phục vụ database.
* Cấu hình định tuyến giúp các tài nguyên thuộc Public Subnet có thể kết nối Internet thông qua Internet Gateway (IGW).
