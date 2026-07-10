---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---
### Mục tiêu tuần 6:
* Tìm hiểu nguyên lý hoạt động của Application Load Balancer (ALB) trong việc phân phối lưu lượng HTTP/HTTPS (Layer 7).
* Khởi tạo Target Group và thiết lập cơ chế Health Check (kiểm tra sức khỏe đầu cuối) cho ứng dụng WordPress.
* Triển khai ALB công cộng, cấu hình Listener định tuyến traffic thông minh từ Internet về Target Group.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu về các loại Elastic Load Balancing (ALB, NLB, GLB) và mô hình định tuyến ứng dụng. <br> - Học các khái niệm Listener, Target Group và Rule định tuyến. | 25/05/2026 | 25/05/2026 | [Elastic Load Balancing Overview](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html) |
| 3 | - Thiết lập cấu hình Target Group cho giao thức HTTP (cổng 80). <br> - Cấu hình Health Check: Đường dẫn (Path `/`), khoảng thời gian (Interval), ngưỡng xác nhận (Thresholds). | 26/05/2026 | 26/05/2026 | [Target Groups for Application Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html) |
| 4 | - Khởi tạo một Security Group dành riêng cho Load Balancer cho phép nhận traffic HTTP/HTTPS (Port 80/443) từ bất kỳ đâu. <br> - Đăng ký thử nghiệm máy chủ WordPress EC2 vào Target Group. | 27/05/2026 | 27/05/2026 | [Security Groups for ALB](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-update-security-groups.html) |
| 5 | - Khởi tạo Application Load Balancer trên tối thiểu 2 Public Subnets khác Availability Zone để đảm bảo tính sẵn sàng cao. <br> - Áp dụng Security Group và cấu hình Listener cổng 80 cho ALB. | 28/05/2026 | 28/05/2026 | [Khởi tạo Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-application-load-balancer.html) |
| 6 | - Thiết lập định tuyến Listener chuyển hướng lưu lượng trực tiếp về Target Group chứa WordPress EC2. <br> - Truy cập ứng dụng thông qua tên miền DNS của ALB và kiểm tra trạng thái sức khỏe (Health status) của các máy chủ. | 29/05/2026 | 29/05/2026 | [Sửa lỗi Health Check trên ALB](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-troubleshooting.html) |

### Kết quả đạt được tuần 6:
* Hiểu sâu sắc cách thức phân tải ứng dụng ở tầng ứng dụng (Layer 7) bằng ALB.
* Thiết lập thành công Target Group với cơ chế giám sát sức khỏe Health Check chính xác.
* Triển khai hoàn thiện bộ cân bằng tải ALB hoạt động đa vùng sẵn sàng cao.
* Tối ưu bảo mật bằng cách cấu hình Security Group của EC2 chỉ chấp nhận HTTP từ ALB, chặn hoàn toàn các truy cập HTTP trực tiếp từ Internet vào máy chủ ảo.
* Truy cập và sử dụng trang WordPress bình thường qua địa chỉ DNS cung cấp bởi ALB.
