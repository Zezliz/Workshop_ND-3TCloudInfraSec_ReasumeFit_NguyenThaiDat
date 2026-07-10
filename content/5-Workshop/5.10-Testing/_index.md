---
title: "Testing the Resume Fit Application"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

1. **Backend API Test:** Test via the ALB API endpoint (e.g., `...elb.amazonaws.com/api/ready`) to receive a JSON `{"status": "ready"}` proving the entire Backend and Database have been successfully linked.
![Test ALB DNS](/images/5-Workshop/Test_hoat_dong_bang_DNS_cua_ALB.jpg)
![Check Connections](/images/5-Workshop/Tien_hanh_kiem_tra_cac_ket_noi.jpg)

2. **Frontend Access:** Access the Frontend Domain/IP. At the **Registration** and **System Login** interface, create an account and log into the workspace.
![Registration UI](/images/5-Workshop/giao_dien_dang_ky.jpg)
![Login UI](/images/5-Workshop/giao_dien_dang_nhap.jpg)

3. **Run the Main Workflow:**
* **Step 1: Create Job Title (Create JD Name)**
![Create Application Job Name](/images/5-Workshop/giao_dien_buoc_1_tao_ten_cong_viec_ung_tuyen.jpg)
* **Step 2: Upload Candidate CV and Job Description (JD)**
![Upload CV JD](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD.jpg)
![Upload CV JD Part 2](/images/5-Workshop/giao_dien_buoc_2_upload_CV_JD_Part-2.jpg)

4. **List Management:** The system allows management of the entire list of uploaded JDs and CVs.
![JD List](/images/5-Workshop/giao_dien_danh_sach_JD.jpg)
![CV List](/images/5-Workshop/giao_dien_danh_sach_CV.jpg)

5. **Candidate Ranking:** You can track the Evaluation History and the Ranking table of suitable candidates for each JD:
* **Evaluation History:**
![Evaluation History](/images/5-Workshop/giao_dien_lich_su_danh_gia_CV_JD.jpg)
* **Candidate Ranking:**
![Candidate Ranking](/images/5-Workshop/giao_dien_xep_hang_ung_vien_phu_hop.jpg)

6. **Detailed Candidate Report (Step 3):** The AI will analyze and return a highly detailed evaluation report including:
![View Candidate Results](/images/5-Workshop/giao_dien_buoc_3_xem_ket_qua_ung_vien.jpg)
* **Match Level and Overall Analysis:**
![Match Level](/images/5-Workshop/giao_dien_danh_gia_muc_do_phu_hop.jpg)
![Score Analysis](/images/5-Workshop/giao_dien_danh_gia_phan_tich_diem_so.jpg)
![Candidate Analysis](/images/5-Workshop/giao_dien_danh_gia_phan_tich_ung_vien.jpg)
* **Technical Skill Evaluation:** Analysis of missing technical skills.
![Skill Evaluation](/images/5-Workshop/giao_dien_danh_gia_ky_nang.jpg)
* **Recruitment Recommendations:**
![Recommendations](/images/5-Workshop/giao_dien_danh_gia_khuyen_nghi.jpg)
* **Interview Questions:** Automatically generated technical interview questions based directly on the project context found in the CV.
![Interview Questions](/images/5-Workshop/giao_dien_danh_gia_cau_hoi_phong_van.jpg)

7. **Extended Features:**
* **Extracted Text:** The OCR system extracts text from the original PDF/Word files.
![Extracted Text](/images/5-Workshop/giao_dien_danh_gia_van_ban_trich_xuat.jpg)
* **Debugger Information:** For admins to track the connection and responses from the OpenAI API.
![Debugger Info](/images/5-Workshop/giao_dien_thong_tin_go_loi_debugger.jpg)
