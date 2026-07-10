---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Bài thu hoạch: "FCAJ Community Day"

### Thông Tin Sự Kiện
*   **Tên Sự Kiện:** FCAJ Community Day.
*   **Thời gian tổ chức:** 09-05-2026.
*   **Địa điểm tổ chức:** Tầng 26, tòa nhà Bitexco, số 02 đường Hải Triều, phường Sài Gòn, thành phố Hồ Chí Minh.
*   **Đơn vị tổ chức:** AWS Study Group / Cộng đồng FCAJ.

### Mục Đích Của Sự Kiện
*   **Mục tiêu của chương trình:** Tạo ra môi trường để các thành viên trong cộng đồng có cơ hội rèn luyện kỹ năng thuyết trình, sự tự tin khi đứng trước đám đông và mạnh dạn chia sẻ kiến thức.
*   **Nội dung chính muốn truyền tải:** Các phương pháp "hack não" để duy trì động lực học tập, kỹ năng tối ưu hóa câu lệnh cho AI (Prompt Engineering), định hướng tư duy cốt lõi khi đi làm cho sinh viên/Fresher, và phương pháp sử dụng AI bài bản trong phát triển phần mềm.
*   **Giá trị dành cho người tham dự:** Cung cấp những bài học thực tế từ các chuyên gia, giúp người tham dự không bị "ngợp" trước lượng kiến thức lớn, biết cách biến AI thành đòn bẩy công việc, và xây dựng nền tảng vững chắc để phát triển dài hạn.

### Danh Sách Diễn Giả
*   **Diễn giả 1 (Long - Ban tổ chức):** Trình bày về chủ đề "Hack não" tạo động lực học tập bằng Dopamine.
*   **Diễn giả 2 (Thịnh):** Trình bày về kỹ thuật "Ultimate Prompt Engineering" và kiến trúc AWS.
*   **Diễn giả 3 (Khang):** Chức vụ: Solution Architect. Đơn vị công tác: Cloud Kinetics. (Chia sẻ về tư duy đi làm và nền tảng cốt lõi).
*   **Diễn giả 4 (Thảo):** Chức vụ: Software Development Developer. Đơn vị công tác: Ngân hàng Quốc tế Việt Nam - VIB. (Chia sẻ về phương pháp BMX trong phát triển phần mềm).

### Nội Dung Nổi Bật
*   **Tổng quan vấn đề:** 
    *   Sinh viên thường lười học do não bộ ưu tiên các hoạt động có phần thưởng nhanh như mạng xã hội, game. 
    *   Khi dùng AI, nếu cung cấp câu lệnh mơ hồ sẽ dẫn đến tình trạng AI "ảo giác" (hallucination) và trả lời sai. 
    *   Sinh viên mới ra trường thường hoang mang, lạm dụng AI để giải quyết bài tập nhưng thiếu tư duy cốt lõi. 
    *   Việc giao toàn bộ dự án cho AI viết code mà không có kiến trúc rõ ràng sẽ tạo ra "code rác".
*   **Giải pháp được giới thiệu:** 
    *   Dùng "canh bạc dopamine": chia nhỏ việc học, tự tạo các phần thưởng ngẫu nhiên để kích thích sự tò mò của não bộ.
    *   Tối ưu prompt bằng cách cung cấp đủ vai trò (Role), bối cảnh (Context), hướng dẫn (Instruction) và ràng buộc (Constraint).
    *   Tập trung xây dựng kiến thức nền tảng (Foundation) thay vì chạy theo số lượng dịch vụ hay công nghệ.
    *   Áp dụng phương pháp BMX (Through Method for AI Development) để biến các yêu cầu thành tài liệu kỹ thuật chi tiết (VD: PRD, Architecture) trước khi cho AI viết code.
*   **Công nghệ/Dịch vụ/Công cụ:** AI LLMs (Gemini, Claude 4.0), AWS (CloudFront, S3, Cognito, API Gateway, Lambda, Bedrock, DynamoDB), Prompt Optimizer, và BMX framework.
*   **Demo hoặc Case Study:** 
    *   **Case study AWS & AI:** Demo kiến trúc ứng dụng Serverless sử dụng các dịch vụ của AWS kết hợp AI để tạo công cụ tối ưu prompt.
    *   **Case study tuyển dụng:** Một bài test kỹ năng có 20 người nộp thì khoảng 15 người dùng AI. Những người này tuy hoàn thành yêu cầu bề nổi nhưng lại thất bại khi nhà tuyển dụng thay đổi một chi tiết nhỏ, vì họ không hiểu bản chất thực sự của vấn đề.
*   **Các điểm đáng chú ý:** **AI chỉ là công cụ khuếch đại (Amplify)**. Nếu bạn kém, AI sẽ làm bạn tệ đi (lười suy nghĩ); nếu bạn giỏi, AI sẽ giúp năng suất của bạn tăng gấp nhiều lần.

### Những Gì Học Được
*   **Tư duy và phương pháp:** Quy tắc 2 phút (việc giải quyết được trong 2 phút thì làm ngay). Liên tục đặt câu hỏi "Tại sao" (Why) để hiểu rõ quyết định kỹ thuật của mình. 
*   **Kiến thức kỹ thuật:** Khái niệm về Token trong AI (đầu vào/đầu ra) và các kỹ thuật suy luận như Chain of Thought, Tree of Thought. Sự khác biệt giữa lưu trữ Serverless linh hoạt như Lambda so với quản lý máy chủ EC2.
*   **Best practices:** Để AI không bị lẫn lộn context (hallucination), cần chia nhỏ các tác vụ lớn và cấp cho mỗi AI agent một context/story riêng biệt.
*   **Kinh nghiệm thực tế:** Đi làm cần có **sự liêm chính (Integrity)** - hoàn thành công việc một cách trách nhiệm nhất ngay cả khi không ai giám sát. Đừng ngại mắc sai lầm ở giai đoạn Fresher/Junior.

### Ứng Dụng Vào Công Việc
*   **Có thể áp dụng gì cho dự án hiện tại:** Áp dụng phương pháp chia nhỏ tác vụ và tự lập "chuỗi" thói quen (như tính năng streak) để giữ động lực học các công nghệ mới cho dự án.
*   **Công nghệ muốn thử nghiệm:** Các dịch vụ quản lý người dùng không máy chủ như Amazon Cognito, Amazon Bedrock cho các dự án tích hợp AI, hoặc mô hình NoSQL với DynamoDB. Thử nghiệm framework BMX để cấu trúc lại dự án.
*   **Ý tưởng cải thiện quy trình làm việc:** Thay vì để AI trực tiếp viết code bừa bãi, nên dùng AI để brainstorm ý tưởng -> tạo tài liệu yêu cầu (PRD) -> phân rã thành Epic/Story -> rồi mới đưa cho AI Agent code từng phần nhỏ nhằm kiểm soát chất lượng.

### Trải Nghiệm Trong Event
*   **Học hỏi từ diễn giả:** Tiếp thu được mindset đúng đắn khi làm nghề từ góc nhìn của các nhà tuyển dụng và kỹ sư trưởng. 
*   **Trải nghiệm thực hành:** Tận mắt xem các demo kiến trúc thực tế và cách một extension "Prompt Optimizer" tinh chỉnh câu lệnh để ra kết quả chất lượng cao từ AI.
*   **Giao lưu và kết nối:** Là cơ hội để sinh viên và người đi làm kết nối, học hỏi từ kinh nghiệm thực chiến của người khác, mở rộng "Network" - một trong những lợi ích cốt lõi khi đi làm.
*   **Điều ấn tượng nhất:** Quan điểm "Outsource thinking" - bạn có thể nhờ AI nghĩ hộ ý tưởng, nhưng bạn **không thể outsource sự thấu hiểu của bản thân**. Nếu không tự hiểu kiến thức nền tảng, AI sẽ khiến bạn mất năng lực tư duy.

### Bài Học Rút Ra
*   **Kiến thức quan trọng nhất:** Việc sở hữu kiến thức Nền tảng (Foundation) vững chắc quan trọng hơn việc chạy theo hàng trăm công cụ mới. AI sẽ làm nổi bật năng lực tư duy của bạn thay vì thay thế nó.
*   **Kinh nghiệm thực tế:** Khi đi làm, vòng tròn công việc bao gồm: Thứ mình thích - Thứ bắt buộc phải làm (dù không thích) - và Lợi ích thu lại (Lương, Kinh nghiệm, Network, Kiến thức). Cần có tầm nhìn dài hạn và không nên chỉ định giá bản thân qua mức lương khởi điểm.
*   **Định hướng học tập hoặc phát triển tiếp theo:** Đi sâu vào Foundation thay vì học vẹt công cụ. Xây dựng thói quen làm việc có tính liêm chính cao, rèn luyện tư duy đặt câu hỏi "Tại sao", và tìm kiếm một đội ngũ đồng hành (team) để cùng thực hiện các dự án lớn.

---
### Một số hình ảnh khi tham gia sự kiện
![FCAJ Community Day - Diễn giả Thịnh trình bày Prompt Engineering](/images/4-EventParticipated/4.1-Event1/event1_1.png)
![FCAJ Community Day - Diễn giả Thảo trình bày phương pháp BMX](/images/4-EventParticipated/4.1-Event1/event1_2.png)
![FCAJ Community Day - Diễn giả Khang chia sẻ Growth Mindset](/images/4-EventParticipated/4.1-Event1/event1_3.png)
![FCAJ Community Day - Tập thể Ban tổ chức và người tham gia sự kiện](/images/4-EventParticipated/4.1-Event1/event1_4.png)

> Tóm lại, sự kiện đã giúp tôi củng cố và thay đổi cách nhìn nhận về phát triển phần mềm, làm việc với AI một cách hiệu quả và tầm quan trọng của việc tự học bền bỉ.
