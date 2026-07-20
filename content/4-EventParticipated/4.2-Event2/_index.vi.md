---
title: "Event 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Bài thu hoạch: "FCAJ Community Day"

### Thông Tin Sự Kiện
*   **Tên Sự Kiện:** FCAJ Community Day.
*   **Thời gian tổ chức:** 23-05-2026.
*   **Địa điểm tổ chức:** Tầng 26, tòa nhà Bitexco, số 02 đường Hải Triều, phường Sài Gòn, thành phố Hồ Chí Minh.
*   **Đơn vị tổ chức:** Cộng đồng FCAJ phối hợp cùng nền tảng AWS Study Group.

### Mục Đích Của Sự Kiện
*   **Mục tiêu của chương trình:** Không chỉ để nghe hội thảo, sự kiện còn là nơi để người tham dự chủ động kết nối, bắt chuyện và truyền cảm hứng cho nhau.
*   **Nội dung chính muốn truyền tải:** Đi qua 6 phiên chia sẻ từ trí tuệ nhân tạo (AI), điện toán đám mây (Cloud) đến những câu chuyện thực chiến trong các môi trường doanh nghiệp khắt khe.
*   **Giá trị dành cho người tham dự:** Nhận thức được yêu cầu thực tế của thị trường tuyển dụng, biết cách cung cấp ngữ cảnh đúng cho AI, hiểu sâu về tối ưu hóa chi phí Cloud, và nắm bắt tư duy đưa AI vào ứng dụng thực tế của doanh nghiệp thay vì chỉ làm các demo nhỏ.

### Danh Sách Diễn Giả
*   **Tinh Truong** – Platform Engineer at GoTymeX
*   **Thinh Nguyen** – DevOps Engineer | FCAJ Ambassador
*   **Anh Pham** – Cloud Consultant at G-AsiaPacific Vietnam
*   **Uyen Le** – GenAI Engineer at VIB
*   **Thao Nguyen** – GenAI Engineer at VIB
*   **Mai Nguyen** – GenAI Engineer at VIB
*   **Duc Dao** – Solutions Architect at Cloud Kinetics
*   **Vy Lam** – Senior Business Systems Analyst at VPBank

### Nội Dung Nổi Bật
*   **Tổng quan vấn đề:** 
    *   Ngành IT đang trong thời kỳ giao thời, AI giúp phát triển phần mềm rẻ hơn nên nhu cầu thực tế tăng mạnh, nhưng lại đòi hỏi nhân sự phải có năng lực thực sự. 
    *   Việc copy code bừa bãi ("Internet Builder") hoặc prompt AI không rõ ngữ cảnh sẽ sinh ra "rác". 
    *   Chi phí CloudFront thường khó đoán (nguy cơ bill shock). 
    *   Đưa AI vào doanh nghiệp bị rào cản rất lớn về vấn đề rò rỉ dữ liệu và tuân thủ bảo mật. 
    *   AI luôn có tính bất định (probabilistic) ngay cả khi set thông số temperature = 0 do các kỹ thuật tối ưu hóa máy chủ.
*   **Giải pháp được giới thiệu:**
    *   Trang bị kiến thức nghiệp vụ thực tế, xây dựng sản phẩm hoàn chỉnh thay vì chỉ dừng ở mức demo.
    *   Áp dụng "Flat-rate pricing" cho CloudFront để kiểm soát và cố định chi phí hằng tháng.
    *   Thiết kế hệ thống Multi-Agent chia vai trò rõ ràng (VD: chuyên gia tài chính, chuyên gia rủi ro) thay vì dồn mọi công việc cho một AI duy nhất (Single Agent).
    *   Cần có màng lọc (Guardrail) bảo mật, chống Prompt Injection và lưu vết kiểm toán (Audit trail) trong mọi hệ thống AI doanh nghiệp.
*   **Công nghệ/Dịch vụ/Công cụ:** Amazon CloudFront (CDN, DDoS protection, VPC Origin, MTLS), Amazon Q (AI Agent cho BI), các hệ thống LLMs, giao thức MCP (Model Context Protocol), Terraform và CrewAI.
*   **Demo hoặc Case Study:**
    *   **Case study Data:** Dùng Amazon Q đọc file dữ liệu Excel để tự động tạo ra bảng phân tích dashboard (BI).
    *   **Case study Hackathon:** Dự án "UTM Morpo" - một hệ thống AI sinh ra mã HTML UI và cho phép người dùng kéo thả, chỉnh sửa giao diện trực tiếp, được hoàn thành trong 36 giờ thi.
    *   **Case study Doanh nghiệp:** Dùng hệ thống Multi-agent để phân tích khả năng cho vay tín dụng của một Startup không có tài sản thế chấp truyền thống tại ngân hàng.
*   **Các điểm đáng chú ý:** Bằng đại học và các kỹ năng cũ không hề mất đi giá trị, chúng càng trở thành bộ lọc khắt khe hơn khi thị trường cạnh tranh. Hệ thống Multi-Agent cần con người quyết định cuối cùng chứ không thể phó mặc "autopilot" hoàn toàn.

### Những Gì Học Được
*   **Tư duy và phương pháp:** Cần có tư duy kinh doanh và thấu hiểu nghiệp vụ (business context): AI làm ra phục vụ cho ai, để làm gì và vào lúc nào.
*   **Kiến thức kỹ thuật:** Hiểu sâu về cách LLM chọn từ dựa trên điểm số Token (Logit/Soft max/Temperature). Nắm được các cơ chế bảo mật của CloudFront như giấu Origin bằng VPC Origin, và cơ chế Mutual TLS (MTLS) bắt buộc chứng thực cả 2 đầu máy chủ - client.
*   **Best practices:** Để AI không bị "lẫn" (hallucination), cần cung cấp bối cảnh (context) rất chi tiết, sát với tổ chức/dự án của bạn chứ không phải những kiến thức chung chung mạng nào cũng có.
*   **Kinh nghiệm thực tế:** Tuyệt đối không copy mã code lỗi lên AI sửa rồi paste thẳng vào môi trường làm việc chung mà không đọc kỹ (Ctrl C/Ctrl V), việc này có thể làm hỏng toàn bộ chuẩn lập trình của doanh nghiệp.

### Ứng Dụng Vào Công Việc
*   **Có thể áp dụng gì cho dự án hiện tại:** Áp dụng việc chia nhỏ Session và làm mới ngữ cảnh thường xuyên để tối ưu hóa đầu ra cho AI. Xây dựng "guardrails" để lọc dữ liệu đầu vào và đầu ra khi làm việc với LLMs.
*   **Công nghệ muốn thử nghiệm:** Triển khai hạ tầng dưới dạng mã (Infrastructure as Code) bằng Terraform thay vì thao tác tay. Thử nghiệm Amazon Q để hỗ trợ quản lý dữ liệu BI hoặc build các Multi-agent với framework CrewAI.
*   **Ý tưởng cải thiện quy trình làm việc:** Áp dụng hệ thống lưu vết (Audit) trong quy trình nội bộ: mọi quyết định dựa trên AI đều phải có con người xác nhận và lưu lại log chịu trách nhiệm.

### Trải Nghiệm Trong Event
*   **Học hỏi từ diễn giả:** Tiếp thu được tư duy làm việc nghiêm túc, cẩn trọng chuẩn "Enterprise" từ các kỹ sư đang làm việc ở ngân hàng và tập đoàn lớn.
*   **Trải nghiệm thực hành:** Quan sát cách các diễn giả giải phẫu một mô hình LLM từ kiến trúc bên trong ra đến cách nó sinh chữ bị biến thiên giữa local và cloud API.
*   **Giao lưu và kết nối:** Nắm bắt cơ hội để nói chuyện, trao đổi chéo giữa các lập trình viên nhằm tìm ra đối tác hay mở rộng góc nhìn.
*   **Điều ấn tượng nhất:** AI dù thông minh đến đâu thì trong môi trường doanh nghiệp có tính pháp lý (như ngân hàng), người đứng trước "vành móng ngựa" nếu có sai sót vẫn là con người, không phải là AI.

### Bài Học Rút Ra
*   **Kiến thức quan trọng nhất:** Kỹ thuật nền tảng của kỹ sư phần mềm (Software Engineering) cực kỳ quan trọng. Bạn phải hiểu cách mã hóa/giải mã hệ thống an toàn thì mới có thể tích hợp AI vào dự án doanh nghiệp.
*   **Kinh nghiệm thực tế:** Xây dựng hệ thống không chỉ cần chạy được, mà phải chạy an toàn, chạy đáng tin cậy và phục vụ đúng nghiệp vụ người dùng cuối.
*   **Định hướng học tập hoặc phát triển tiếp theo:** Đào sâu tìm hiểu khái niệm AI Mindset và AI adoption. Nâng cao kỹ năng về kiến trúc phân tán (Multi-agent), quản lý hạ tầng đám mây tự động (Terraform), và tìm hiểu thêm về các quy chuẩn tuân thủ bảo mật (Compliance/Security) để sẵn sàng làm việc tại các công ty lớn.

---
### Một số hình ảnh khi tham gia sự kiện
![FCAJ Community Day - Diễn giả Hưng chia sẻ về Tầm quan trọng của Ngữ cảnh](/images/4-EventParticipated/4.2-Event2/event2_1.png)
![FCAJ Community Day - Diễn giả Vy giới thiệu Multi-Agent trong ngân hàng](/images/4-EventParticipated/4.2-Event2/event2_2.png)
![FCAJ Community Day - Nhóm UTM chia sẻ hành trình từ Hackathon](/images/4-EventParticipated/4.2-Event2/event2_3.png)
![FCAJ Community Day - Toàn cảnh người tham dự sự kiện](/images/4-EventParticipated/4.2-Event2/event2_4.jpg)

> Tóm lại, sự kiện đã giúp tôi củng cố và thay đổi cách nhìn nhận về các giải pháp bảo mật CloudFront, kiểm soát chi phí thực tế và định hướng phát triển Multi-Agent chuyên sâu.
