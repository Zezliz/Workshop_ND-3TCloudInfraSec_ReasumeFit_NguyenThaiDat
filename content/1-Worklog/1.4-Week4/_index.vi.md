---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
### Mục tiêu tuần 4:
* Cài đặt thành công môi trường web hosting LAMP (Linux, Apache, MySQL, PHP) trên máy chủ EC2.
* Tải xuống, phân quyền và cấu hình tệp mã nguồn ứng dụng WordPress.
* Chỉnh sửa tệp cấu hình `wp-config.php` để liên kết thành công WordPress với cơ sở dữ liệu RDS MySQL.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Kết nối SSH vào EC2, tiến hành cập nhật hệ thống. <br> - Cài đặt Apache2 Web Server và kiểm tra giao diện mặc định qua địa chỉ IP. | 11/05/2026 | 11/05/2026 | [Cài đặt Apache trên Ubuntu](https://ubuntu.com/tutorials/install-and-configure-apache) |
| 3 | - Cài đặt PHP cùng các thư viện liên kết quan trọng (php-mysql, php-gd, php-xml, v.v.). <br> - Tạo tệp `info.php` kiểm tra hoạt động biên dịch mã nguồn PHP của Apache. | 12/05/2026 | 12/05/2026 | [Hướng dẫn cài đặt LAMP trên AWS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-lamp-amazon-linux-2023.html) |
| 4 | - Tải gói mã nguồn WordPress từ trang chủ WordPress.org. <br> - Giải nén mã nguồn vào thư mục `/var/www/html/` và phân quyền sở hữu cho người dùng `www-data`. | 13/05/2026 | 13/05/2026 | [WordPress Download & Tar extraction](https://wordpress.org/download/) |
| 5 | - Đổi tên và chỉnh sửa tệp cấu hình `wp-config.php` của WordPress. <br> - Điền các thông tin `DB_NAME`, `DB_USER`, `DB_PASSWORD` và dán RDS Endpoint làm `DB_HOST`. | 14/05/2026 | 14/05/2026 | [Chỉnh sửa wp-config.php](https://developer.wordpress.org/advanced-administration/wordpress/wp-config/) |
| 6 | - Cấu hình Apache Virtual Host và kích hoạt Module Rewrite hỗ trợ đường dẫn WordPress. <br> - Truy cập IP công cộng, tiến hành cài đặt WordPress qua giao diện web và tạo bài viết thử nghiệm. | 15/05/2026 | 15/05/2026 | [Hướng dẫn cài đặt WordPress](https://developer.wordpress.org/advanced-administration/before-install/howto-install/) |

### Kết quả đạt được tuần 4:
* Cài đặt hoàn chỉnh ngăn xếp công nghệ LAMP Stack trên máy chủ Ubuntu ảo.
* Nắm vững các bước cấu hình máy chủ Web Apache cho phép xử lý động mã nguồn PHP.
* Cấu hình liên kết thành công cơ sở dữ liệu đám mây RDS với mã nguồn PHP WordPress thông qua tệp `wp-config.php`.
* Hoàn thành triển khai trang web WordPress hoạt động thực tế trên đám mây, có thể truy cập công khai và kết xuất dữ liệu ổn định từ RDS.
