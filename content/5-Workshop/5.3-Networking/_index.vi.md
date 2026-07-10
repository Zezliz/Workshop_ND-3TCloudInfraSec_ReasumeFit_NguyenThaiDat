---
title: "Xây dựng Hạ tầng Mạng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

### 5.3.1. Tạo VPC và Internet Gateway

Hạ tầng mạng cô lập (VPC) là nền tảng bảo mật vững chắc cho toàn bộ ứng dụng, giúp kiểm soát hoàn toàn luồng giao thông mạng.

1. Truy cập vào giao diện VPC Console, chọn **Create VPC**.
![Tạo VPC](/images/5-Workshop/tao_VPC.jpg)

2. Khởi tạo một VPC với tên `ResumeMatching-VPC` và thiết lập dải IP `IPv4 CIDR` là `10.0.0.0/16`.
3. Tạo một Internet Gateway có tên `ResumeMatching-IGW` để cung cấp đường truyền kết nối ra internet cho các tài nguyên công khai.
![Tạo Internet Gateway](/images/5-Workshop/Tao_Internet_Gateway.jpg)

4. Thực hiện Attach Internet Gateway vừa tạo vào `ResumeMatching-VPC`.
![Attach vào VPC](/images/5-Workshop/Attach_vao_VPC.jpg)

### 5.3.2. Cấu hình Subnet và Route Table

Chia nhỏ dải mạng VPC thành các mạng con để phân tách các tầng ứng dụng (Public cho Load Balancer, Private App cho EC2, Private DB cho RDS).

1. Truy cập mục **Subnets** và tạo lần lượt các subnet với các dải CIDR phù hợp:
* Public Subnets: `Public-Subnet-A` (`10.0.1.0/24`), `Public-Subnet-B` (`10.0.2.0/24`).
* Private App Subnets: `Private-App-A` (`10.0.11.0/24`), `Private-App-B` (`10.0.12.0/24`).
* Private DB Subnets: `Private-DB-A` (`10.0.21.0/24`), `Private-DB-B` (`10.0.22.0/24`).
![Tạo Subnet](/images/5-Workshop/Tao_cac_Public_va_Private_subnet.jpg)

2. Tạo một Route Table công khai với tên `Public-RT` và gán vào VPC.
![Tạo Public Route Table](/images/5-Workshop/Tao_Public_Route_Table.jpg)

3. Trong phần **Edit routes** của `Public-RT`, thêm route có `Destination` là `0.0.0.0/0` và trỏ `Target` đến Internet Gateway (`igw-...`).
4. Gán (Associate) `Public-RT` vào 2 subnets: `Public-Subnet-A` và `Public-Subnet-B`.
![Gán Public Route Table](/images/5-Workshop/Gan_Public_Route_Table.jpg)

5. Tạo thêm các Route Table riêng tư là `Private-App-RT`, `ResumeMatching-Private-App-RT-B` và `Private-DB-RT`, sau đó lần lượt gán chúng cho các App Subnet và DB Subnet tương ứng để đảm bảo các tầng này không lộ ra internet.
![Gán Private App Route Table](/images/5-Workshop/Tao_va_gan_Private_App_Route_Table.jpg)
![Gán Database Route Table](/images/5-Workshop/Tao_va_gan_Database_Route_Table.jpg)

### 5.3.3. Thiết lập NAT Gateway cho Private Subnets

Giúp các instance ở Private Subnet kết nối ra internet một chiều (để tải package, cập nhật phần mềm) nhưng từ chối các kết nối khởi tạo từ internet đi vào.

1. Khởi tạo hai **Elastic IP** tĩnh là `ResumeMatching-EIP` và `ResumeMatching-EIP-B`.
![Tạo Elastic IP](/images/5-Workshop/Tao_Elastic_IP.jpg)
![Tạo Elastic IP B](/images/5-Workshop/Tao_Elastic_IP_B.jpg)

2. Tạo **NAT Gateway** tên `ResumeMatching-NAT` đặt tại `Public-Subnet-A` và gắn Elastic IP thứ nhất.
![Tạo NAT Gateway](/images/5-Workshop/Tao_NAT.jpg)

3. Tạo thêm **NAT Gateway** tên `ResumeMatching-NAT-B` đặt tại Availability Zone còn lại và gắn Elastic IP thứ hai nhằm đảm bảo tính sẵn sàng cao (High Availability).
![Tạo NAT Gateway B](/images/5-Workshop/Tao_NAT_B.jpg)

4. Mở cấu hình của các Route Table Private App, thêm route `0.0.0.0/0` và trỏ `Target` về các NAT Gateway tương ứng vừa khởi tạo.
