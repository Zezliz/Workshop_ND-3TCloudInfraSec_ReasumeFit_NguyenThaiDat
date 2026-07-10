---
title: "Kiểm thử Ứng dụng Resume Fit"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

1. **Kiểm tra API Backend:** Kiểm thử thông qua endpoint API của ALB (ví dụ: `...elb.amazonaws.com/api/ready`) để nhận về JSON `{"status": "ready"}` chứng minh toàn bộ Backend và Database đã được liên kết thành công.
![Test bằng DNS của ALB](/images/5-Workshop/Test_hoat_dong_bang_DNS_cua_ALB.jpg)
![Kiểm tra các kết nối](/images/5-Workshop/Tien_hanh_kiem_tra_cac_ket_noi.jpg)

2. **Truy cập Frontend:** Truy cập Domain/IP của Frontend. Tại giao diện **Đăng ký** và **Đăng nhập hệ thống**, tiến hành tạo tài khoản và đăng nhập vào không gian làm việc.
![Giao diện Đăng ký](/images/5-Workshop/giao_dien_dang_ky.jpg)
![Giao diện Đăng nhập](/images/5-Workshop/giao_dien_dang_nhap.jpg)

3. **Chạy luồng công việc chính:**
* **Bước 1: Tạo tên công việc ứng tuyển (Create JD Name)**
![Tạo tên công việc ứng tuyển](/images/5-Workshop/giao_dien_buoc_1_tao_ten_cong_viec_ung_tuyen.jpg)
* **Bước 2: Tải lên CV của ứng viên và nội dung JD (Job Description)**
![Upload CV JD](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD.jpg)
![Upload CV JD Part 2](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD_Part-2.jpg)

4. **Quản lý danh sách:** Hệ thống cho phép quản lý toàn bộ danh sách JD và CV đã tải lên.
![Danh sách JD](/images/5-Workshop/giao_dien_danh_sach_JD.jpg)
![Danh sách CV](/images/5-Workshop/giao_dien_danh_sach_CV.jpg)

5. **Xếp hạng ứng viên:** Bạn có thể theo dõi Lịch sử Đánh giá và bảng Xếp hạng các ứng viên phù hợp với từng JD:
* **Lịch sử đánh giá:**
![Lịch sử đánh giá](/images/5-Workshop/giao_dien_lich_su_danh_gia_CV_JD.jpg)
* **Xếp hạng ứng viên phù hợp:**
![Xếp hạng ứng viên phù hợp](/images/5-Workshop/giao_dien_xep_hang_ung_vien_phu_hop.jpg)

6. **Báo cáo chi tiết ứng viên (Bước 3):** AI sẽ phân tích và trả về báo cáo đánh giá cực kỳ chi tiết bao gồm:
![Xem kết quả ứng viên](/images/5-Workshop/giao_dien_buoc_3_xem_ket_qua_ung_vien.jpg)
* **Mức độ phù hợp và phân tích tổng quan:**
![Mức độ phù hợp](/images/5-Workshop/giao_dien_danh_gia_muc_do_phu_hop.jpg)
![Phân tích điểm số](/images/5-Workshop/giao_dien_danh_gia_phan_tich_diem_so.jpg)
![Phân tích ứng viên](/images/5-Workshop/giao_dien_danh_gia_phan_tich_ung_vien.jpg)
* **Đánh giá kỹ năng chuyên môn:** Phân tích các kỹ năng chuyên môn còn thiếu.
![Đánh giá kỹ năng](/images/5-Workshop/giao_dien_danh_gia_ky_nang.jpg)
* **Khuyến nghị tuyển dụng:**
![Khuyến nghị](/images/5-Workshop/giao_dien_danh_gia_khuyen_nghi.jpg)
* **Câu hỏi phỏng vấn:** Sinh tự động các câu hỏi phỏng vấn kỹ thuật dựa trên chính ngữ cảnh dự án trong CV.
![Câu hỏi phỏng vấn](/images/5-Workshop/giao_dien_danh_gia_cau_hoi_phong_van.jpg)

7. **Các tính năng mở rộng:**
* **Xem văn bản trích xuất (Extracted Text):** Hệ thống OCR trích xuất text từ file PDF/Word gốc.
![Văn bản trích xuất](/images/5-Workshop/giao_dien_danh_gia_van_ban_trich_xuat.jpg)
* **Thông tin gỡ lỗi (Debugger):** Dành cho admin theo dõi quá trình kết nối và phản hồi từ OpenAI API.
![Thông tin gỡ lỗi](/images/5-Workshop/giao_dien_thong_tin_go_loi_debugger.jpg)
