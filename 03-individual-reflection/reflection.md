# 03 — Individual Reflection

**Thông tin cá nhân:**
- **Họ và tên:** Vũ Hữu Trường
- **Mã học viên:** 2A202601694
- **Thành viên nhóm:** Nhóm 6 người (Phan Trọng Đạt, Nguyễn Xuân Quân, Phạm Anh Minh, Phạm Ngọc Quốc Khánh, Vũ Hữu Trường, Trương Quang Minh)
- **Vai trò trong nhóm:** Member | Phụ trách ý tưởng và nội dung

---

## 1. Mức độ đóng góp cá nhân trong làm việc nhóm

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng đến sản phẩm chung |
|---|---|---|
| **Scan cá nhân** | Chuẩn bị và đóng góp các candidate problem cá nhân từ góc nhìn trải nghiệm thực tế. | Bổ sung dữ liệu đa dạng cho quỹ 6 đề xuất của nhóm. |
| **Thảo luận & Lắng nghe** | Chăm chú lắng nghe các thành viên pitch bài toán cá nhân, đặt câu hỏi làm rõ bối cảnh và điểm nghẽn. | Giúp nhóm nắm bắt nhanh bức tranh toàn cảnh của từng đề xuất. |
| **Challenge bài bạn khác** | Đặt câu hỏi phản biện cho các đề xuất khác (SME Marketing, Chấm công, Xe bus...): hỏi về tính khả thi trong scope lab, bằng chứng điểm đau và khả năng đo lường. | Giúp nhóm thấy bài Chấm công chỉ cần Rule/Tool có sẵn, bài Xe bus khó validate data, từ đó thu hẹp phạm vi chọn. |
| **Gom trùng / Cluster** | Cùng nhóm phân loại 6 candidates vào 5 cụm pattern (Marketing SME, Kiểm tra đầu vào, Vận hành/Ghi nhận, Giao thông, BA/Dev Communication). | Tạo cấu trúc so sánh minh bạch trước khi đưa vào ma trận chấm điểm. |
| **Chọn Candidate Problem** | Lập luận chọn bài toán **IT SLC: BA -> Dev Communication** dựa trên actor rõ, bottleneck đo được (60-90 phút/tính năng) và tính khả thi. | Nhóm chấm đạt 24 điểm (cao nhất) và thống nhất chọn đề tài này để đào sâu. |
| **Validation / Research** | Đóng góp nghiên cứu các giải pháp hiện có (Google PAIR Guidebook, Confluence KB, M365 Copilot) và chỉ ra điểm hạn chế. | Xác định AI/RAG chỉ hỗ trợ draft spec, không thể thay thế bước review tài liệu của con người. |
| **Workflow nhóm** | Cùng nhóm phân tích Current State (60-90 phút, qua 7 bước lặp) và Future State kỳ vọng (30-40 phút, qua 6 bước). | Xác định rõ bước 5 (BA review/chỉnh sửa) là **Human Boundary** quan trọng nhất trước khi gửi Dev. |
| **R/W/A & Decision** | Bảo vệ quan điểm chọn mức **Workflow** thay vì Agent, và chốt quyết định **Not Yet** cho dự án . | Giúp nhóm không bị "ngáo AI", giữ sự tỉnh táo: cần validate KB và dữ liệu thật trước khi Go. |

---

## 2. Nhật ký sử dụng AI trong quá trình làm bài

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI hời hợt / sai ở đâu? | Tôi đã tự sửa gì bằng nhận định cá nhân? |
|---|---|---|---|---|
| **Scan cá nhân & Shortlist** | Gợi ý cách đặt tên Problem Card và làm rõ lăng kính quan sát. | Giúp diễn đạt ngắn gọn 1 câu cho các điểm đau. | Đề xuất giải pháp AI quá sớm khi chưa phân tích kỹ workflow hiện tại. | Lọc bỏ phần solution của AI, giữ lại mô tả hiện trạng và dấu hiệu thật. |
| **Problem Card & Workflow** | Phản biện quy trình handoff giữa BA và Dev, gợi ý các bước trong Current/Future workflow. | Gợi ý bổ sung bước Tra cứu Knowledge Base và Mapping logic mà ban đầu nhóm dễ bỏ qua. | AI hay cho rằng AI có thể tự động gửi trực tiếp spec cho Dev sau khi sinh văn bản để tiết kiệm thời gian. | Kiên quyết chèn bước **BA Review (Human Boundary)** làm ranh giới kiểm soát chất lượng kỹ thuật bắt buộc. |
| **Research giải pháp** | Tra cứu các case study ứng dụng RAG trong tra cứu tài liệu nội bộ và viết đặc tả kỹ thuật. | Tổng hợp nhanh điểm mạnh/yếu của các công cụ như Confluence, Copilot. | AI tự đưa ra các con số giả định như "giảm 90% lỗi spec" không có nguồn trích dẫn. | Bỏ các thông số ảo, thay bằng success metric thực tế dựa trên số lần Dev trả lại spec (1-3 lần -> 0-1 lần). |
| **Đánh giá R/W/A & Decision** | Phân tích ưu/nhược điểm giữa Rule, Workflow và Agent cho bài toán BA -> Dev. | Liệt kê các rủi ro kỹ thuật: KB cũ/sai, AI hallucination suy diễn sai technical logic. | AI có xu hướng khuyên chọn "Agent" cho hiện đại và đánh giá quyết định là "Go" ngay lập tức. | Cùng nhóm kiên quyết hạ xuống chọn **Workflow**, và chốt quyết định **Not Yet** vì thiếu dữ liệu baseline thực tế. |

---

## 3. Bài học cá nhân & Phản tư (Reflection)

* **Điều tôi học được khi nghe bài của các bạn khác trong nhóm:**  
  Mỗi người có một góc nhìn domain khác nhau (từ vận hành, marketing đến kỹ thuật). Việc dùng ma trận chấm điểm (Score Matrix) với các tiêu chí rõ ràng (Actor, Pain Evidence, Impact, Scope Lab, R/W/A) giúp nhóm loại bỏ được cảm tính cá nhân để chọn bài toán thực sự phù hợp nhất.

* **Nhóm có lúc nào bị "Solution-first" (chưa hiểu problem đã nhảy vào nghĩ solution AI) không?**  
  Có. Lúc mới chọn đề tài BA -> Dev, một số ý kiến trong nhóm đã nghĩ ngay đến việc xây một "AI Agent thông minh tự động đọc Business Requirement rồi sinh ra code/spec hoàn chỉnh luôn". Tuy nhiên, sau khi phân tích kỹ workflow và rủi ro AI bị hallucination (suy diễn sai logic hệ thống khiến Dev triển khai sai nghiêm trọng), nhóm đã lùi lại: chỉ dừng ở mức **Workflow RAG hỗ trợ Draft**, còn quyền duyệt cuối thuộc về BA.

* **Tôi có thay đổi ý kiến sau khi bị nhóm challenge không?**  
  Có. Ban đầu tôi nghĩ bài toán chấm công thủ công dễ làm hơn. Nhưng sau khi nhóm challenge rằng bài toán chấm công hoàn toàn giải quyết được bằng Rule/Code truyền thống hoặc phần mềm thương mại có sẵn mà không cần AI, tôi đã nhận ra tầm quan trọng của việc đánh giá "Độ phù hợp với AI (Rule vs Workflow vs Agent)" và chuyển sang ủng hộ đề tài BA -> Dev.

* **Điều khó nhất khi làm Problem Statement v1 là gì?**  
  Là việc xác định **Success Metric** và **Boundary** thực sự đo lường được. Việc viết "giúp BA làm nhanh hơn" rất dễ, nhưng phải quy đổi ra con số baseline cụ thể (từ 60-90 phút xuống dưới 30-40 phút/tính năng, giảm số lần Dev trả lại từ 1-3 lần xuống 0-1 lần) và đặt ra ranh giới (AI không tự gửi spec, không bịa logic) đòi hỏi nhóm phải đào sâu quy trình thực tế.

* **Nếu được làm lại bài này, tôi sẽ đổi/cải thiện điều gì?**  
  Tôi sẽ chủ động phỏng vấn nhanh 1-2 bạn BA/Dev thực tế hoặc xin 2-3 bản spec/log comment thật trước buổi lab. Điều này sẽ giúp nhóm có ngay bằng chứng xác thực (evidence) để chốt quyết định **Go** thay vì phải dừng ở mức **Not Yet** do thiếu dữ liệu baseline thực tế.