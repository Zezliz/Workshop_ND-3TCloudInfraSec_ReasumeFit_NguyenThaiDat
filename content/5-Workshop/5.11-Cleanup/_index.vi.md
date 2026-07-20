---
title: "Dọn dẹp tài nguyên"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 5.11. </b> "
---

### 5.11.1. Trình Tự Dọn Dẹp (Cleanup Steps)

Sau khi hoàn tất quá trình workshop và kiểm thử, để tránh phát sinh chi phí lưu trữ và duy trì hạ tầng không cần thiết trên AWS, hãy tiến hành dọn dẹp theo thứ tự sau:

1. Xóa **Auto Scaling Group** để ngăn hệ thống tự khởi tạo lại máy chủ, sau đó Terminate các **EC2 Instances** thủ công còn sót lại.
2. Xóa **Application Load Balancer** và **Target Group**.
3. Xóa **Database RDS** (bỏ chọn tính năng tạo Snapshot cuối cùng nếu không cần giữ data) và **Subnet Group** của RDS.
4. Xóa **NAT Gateway**, đợi đến khi trạng thái là `Deleted` thì Release các **Elastic IPs**.
5. Giải phóng **VPC Endpoints**, **Route Tables**, **Internet Gateway**, **Subnets** và cuối cùng là xóa **VPC**.
6. Xóa rỗng toàn bộ object trong **S3 bucket**, sau đó tiến hành Delete Bucket.

### 5.11.2. Dự Toán Chi Phí Triển Khai Hệ Thống (Cost Breakdown)

Dựa trên cơ sở tính toán của AWS Pricing Calculator tại khu vực **US East (N. Virginia) – us-east-1** với mô hình giá **AWS On-Demand**, thời gian vận hành dự kiến **730 giờ/tháng (24/7)** và hệ thống chủ yếu phục vụ demo/chấm đồ án (lưu lượng thấp, không sử dụng Reserved Instances), bảng dưới đây trình bày dự toán chi phí hàng tháng cho kiến trúc đã triển khai.

#### Bảng Dự Tính Chi Phí Hàng Tháng

| STT | AWS Service | Configuration | Quantity | Estimated Monthly Cost (USD) | Notes | Total (USD) |
|---|---|---|---|---|---|---|
| 1 | Amazon VPC | Default | 01 | 0.00 | Dịch vụ cốt lõi miễn phí | 0.00 |
| 2 | Internet Gateway | Default | 01 | 0.00 | Dịch vụ mạng miễn phí | 0.00 |
| 3 | Public Subnet | Standard | 02 | 0.00 | Dịch vụ mạng miễn phí | 0.00 |
| 4 | Private Application Subnet | Standard | 02 | 0.00 | Dịch vụ mạng miễn phí | 0.00 |
| 5 | Private Database Subnet | Standard | 02 | 0.00 | Dịch vụ mạng miễn phí | 0.00 |
| 6 | NAT Gateway | 730 hrs, ~0 GB Data Processed | 02 | 32.85 | 0.045 USD/giờ cho mỗi NAT | 65.70 |
| 7 | Security Group | Default | 01 | 0.00 | Tường lửa ảo miễn phí | 0.00 |
| 8 | Amazon EC2 | t3.micro Linux (730 hrs) | 03 | 7.59 | 0.0104 USD/giờ (1 Backend, 2 ASG) | 22.77 |
| 9 | Amazon EBS | 30 GB gp3 | 03 | 2.40 | 0.08 USD/GB-tháng | 7.20 |
| 10 | Amazon Machine Image (AMI) | Custom AMI | 01 | 0.00 | Miễn phí theo tài khoản / rất nhỏ | 0.00 |
| 11 | Launch Template | Standard | 01 | 0.00 | Dịch vụ quản lý cấu hình miễn phí | 0.00 |
| 12 | Auto Scaling Group | Standard | 01 | 0.00 | Dịch vụ Auto Scaling miễn phí | 0.00 |
| 13 | Application Load Balancer | 730 hrs, ~0 LCU | 01 | 16.43 | 0.0225 USD/giờ cho mỗi ALB | 16.43 |
| 14 | Target Group | Standard | 01 | 0.00 | Dịch vụ cân bằng tải miễn phí | 0.00 |
| 15 | Amazon RDS Single-AZ | db.t3.micro (730 hrs) | 01 | 12.41 | 0.017 USD/giờ | 12.41 |
| 16 | Amazon RDS Storage | 20 GB gp3 | 01 | 2.30 | 0.115 USD/GB-tháng | 2.30 |
| 17 | Amazon S3 Standard | 5 GB Data | 01 | 0.12 | 0.023 USD/GB-tháng | 0.12 |
| 18 | Amazon SQS | Standard Queue & DLQ | 01 | 0.00 | Miễn phí 1 triệu request đầu tiên | 0.00 |
| 19 | AWS Secrets Manager | 01 Secret | 01 | 0.40 | 0.40 USD/Secret mỗi tháng | 0.40 |
| 20 | Amazon Cognito | < 50,000 MAU | 01 | 0.00 | Thuộc Free Tier | 0.00 |
| 21 | AWS Systems Manager | Session Manager | 01 | 0.00 | Dịch vụ quản lý miễn phí | 0.00 |
| 22 | Amazon CloudWatch | Basic Metrics & Logs | 01 | 0.00 | Gói cơ bản miễn phí | 0.00 |

#### Phân Tích Tổng Chi Phí:
- **Tổng chi phí triển khai mỗi tháng:** ~ **127.33 USD**.
- **Dịch vụ chiếm tỷ trọng cao nhất:** Hệ thống mạng, cụ thể là **NAT Gateway** (65.70 USD, chiếm khoảng 51.6% tổng chi phí). Nguyên nhân là NAT Gateway bị tính phí duy trì theo giờ (0.045 USD/giờ) bất kể lưu lượng sử dụng. Tiếp đến là phần Compute với **EC2 instances** (22.77 USD) và **Application Load Balancer** (16.43 USD).
- **Tính phù hợp với ngân sách AWS Credits 200 USD:** Kiến trúc hiện tại **hoàn toàn an toàn và phù hợp** để vận hành trong ngưỡng ngân sách được cấp (200 USD/tháng). Ngân sách dư (khoảng 72.67 USD) giúp hấp thụ các dao động lưu lượng truy cập nhẹ có thể phát sinh thêm tại các thời điểm nghiệm thu.

#### Đề Xuất Biện Pháp Tối Ưu Hóa Chi Phí:
Mặc dù hệ thống vẫn nằm trong ngưỡng giới hạn ngân sách, có thể áp dụng các giải pháp dưới đây để tiết kiệm chi phí nhưng không làm thay đổi kiến trúc tổng thể:
1. **Tinh giảm thiết kế NAT Gateway:** Thay vì triển khai 02 NAT Gateway trên cả 2 Availability Zones (nhằm đảm bảo tiêu chuẩn High Availability), có thể cắt giảm xuống chỉ chạy 01 NAT Gateway và định tuyến route của các AZ còn lại qua NAT duy nhất này. Việc này giúp tiết kiệm ngay lập tức **32.85 USD/tháng**.
2. **Cơ chế lập lịch tự động Bật/Tắt tài nguyên:** Vận dụng AWS Lambda hoặc AWS Instance Scheduler để cấu hình Tắt (Stop) các tài nguyên Compute (như EC2, RDS, thiết lập Desired Capacity của ASG bằng 0) vào ban đêm và ngoài giờ hành chính (ví dụ từ 22:00 đêm đến 08:00 sáng hôm sau). Phương án này có thể cắt giảm gần 40% chi phí điện toán hàng tháng.
3. **Thắt chặt dung lượng Storage (EBS):** Hệ thống demo không yêu cầu lưu trữ lớn. Giảm kích thước volume EBS mặc định từ 30 GB xuống 8 GB - 15 GB mỗi EC2 có thể làm giảm hóa đơn lưu trữ khối.
