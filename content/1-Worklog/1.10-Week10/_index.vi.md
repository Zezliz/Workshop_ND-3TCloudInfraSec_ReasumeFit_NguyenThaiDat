---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Mục tiêu tuần 10:
* Nghiên cứu giải pháp lưu trữ dùng chung có trạng thái (Stateful Filesystem) trong cụm máy chủ sử dụng Amazon Elastic File System (EFS).
* Tìm hiểu lý thuyết về mạng lưới phân phối nội dung Amazon CloudFront (CDN) giúp giảm độ trễ truy cập trang web.
* Phân tích và đánh giá lợi ích cốt lõi của mô hình Điện toán đám mây (Cloud) so với mô hình máy chủ vật lý truyền thống (On-Premises).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu về kiến trúc lưu trữ Amazon EFS, giao thức NFS và tính năng gắn kết đa máy chủ. <br> - So sánh EFS vs. Amazon EBS vs. Amazon S3 về mặt tính năng lưu trữ. | 22/06/2026 | 22/06/2026 | [Amazon EFS Overview](https://aws.amazon.com/efs/) |
| 3 | - Thực hành gắn ổ đĩa EFS vào thư mục tải lên của WordPress (`/var/www/html/wp-content/uploads/`). <br> - Kiểm tra đồng bộ dữ liệu hình ảnh tải lên giữa các máy chủ khác nhau trong ASG. | 23/06/2026 | 23/06/2026 | [Gắn ổ đĩa EFS vào EC2](https://docs.aws.amazon.com/efs/latest/ug/mounting-fs.html) |
| 4 | - Học lý thuyết về Mạng phân phối nội dung (CDN): Khái niệm Edge Location, Máy chủ gốc (Origin), Bộ nhớ đệm (Caching) và thời gian sống TTL. <br> - Tìm hiểu kiến trúc tổng quan của Amazon CloudFront. | 24/06/2026 | 24/06/2026 | [Amazon CloudFront Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 5 | - Khởi tạo CloudFront Distribution sử dụng bộ cân bằng tải ALB làm máy chủ gốc (Origin Server). <br> - Cấu hình định tuyến, tối ưu Cache Behavior và kiểm tra tốc độ tải tài nguyên tĩnh trước/sau khi chạy CDN. | 25/06/2026 | 25/06/2026 | [Khởi tạo CloudFront Distribution](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/distribution-web-creating-console.html) |
| 6 | - Nghiên cứu các mô hình cung cấp Cloud (IaaS, PaaS, SaaS) và cấu trúc chi phí linh hoạt. <br> - Viết báo cáo so sánh các điểm mạnh vượt trội của AWS Cloud (trả phí theo thực tế, mở rộng linh hoạt, độ tin cậy) so với hệ thống tự xây dựng On-Premises. | 26/06/2026 | 26/06/2026 | [So sánh Cloud vs On-Premises](https://aws.amazon.com/whitepapers/aws-overview/) |

### Kết quả đạt được tuần 10:
* Cấu hình thành công hệ thống tệp lưu trữ EFS dùng chung cho cụm Web Server chạy Auto Scaling, giải quyết bài toán mất dữ liệu ảnh khi có máy chủ mới tạo thêm hoặc xóa bớt.
* Nắm vững kiến thức tối ưu hóa website quy mô toàn cầu thông qua cấu hình hệ thống phân phối CloudFront CDN.
* Hiểu sâu sắc và viết báo cáo so sánh về lợi ích kinh tế (OpEx vs CapEx), tính linh hoạt và giảm thiểu rủi ro vận hành khi lựa chọn Cloud so với xây dựng phòng máy chủ vật lý On-Premises.
