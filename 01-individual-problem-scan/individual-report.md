ví dụ: Tổng hợp & Phản hồi Customer Support Ticket cho Startup E-commerce
Nhân vật: An, Customer Support Lead tại một thương hiệu thời trang online (khoảng 30 nhân sự).

Scan 10 problems
| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Phân loại ticket và gán nhãn thủ công trên Zendesk | CS Agent, Lead | 100+ ticket/ngày, tốn 60 phút/ngày |
| 2 | Tốn thời gian | Đọc lại lịch sử tin nhắn rải rác từ Facebook, Zalo, Web để trả lời khi khách quay lại |CS Agent, Khách hàng| Mất 5-7 phút/ticket |
| 3 | Tốn thời gian | Viết báo cáo tổng hợp lỗi sản phẩm tuần (Quality Report) gửi bên Sản xuất | CS Lead, QC Manager | 120 phút mỗi chiều thứ Sáu |
| 4 | Lặp lại | Trả lời các câu hỏi về chính sách đổi trả / phí ship | CS Agent | Lặp lại 40% dung lượng chat |
| 5 | AI có thể tốt hơn | Tóm tắt đoạn chat dài để bàn giao cho ca trực sau | CS Agent ca tối/sáng | Mất 15 phút mỗi chuyển ca |
| 6 | Pain từ người khác | Khách phàn nàn vì CS trả lời sai chính sách ưu đãi đợt Campaign | CS Agent, Khách hàng | 5-10 khiếu nại/chiến dịch |
| 7 | Pain từ người khác | Team Dev không biết bug app nghiêm trọng tới mức nào do CS mô tả chung chung | DE-commerce/Tech Team | Trả qua trả lại 3-4 lần/ticket bug |
| 8 | Lặp lại | Soạn email xin lỗi và đề xuất đền bù cho khách hàng bị giao hàng trễ | CS Lead | Mất 10 phút/email cá nhân hóa |
| 9 | Tốn thời gian | Tìm lại lý do hủy đơn hàng của các khách hàng VIP để chăm sóc lại | Sales Lead, CS | Mất 2 tiếng/tuần |
| 10 | AI có thể tốt hơn | Đánh giá thái độ (sentiment) và điểm hài lòng khách hàng sau khi đóng ticket | CS Lead | Chỉ review mẫu được 5% ticket |

## Top3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Báo cáo lỗi sản phẩm tuần | Workflow rõ, bottleneck tốn thời gian, impact lớn tới khâu sản xuất | Tiêu chuẩn phân loại lỗi thế nào là chuẩn |
| 2 | Tóm tắt lịch sử chat đa kênh | Pain lớn của CS agent, giảm trực tiếp thời gian xử lý (AHT) | Kết nối dữ liệu Zalo/FB về một nơi |
| 3 | Phân loại & Gán nhãn ticket | Tính lặp lại cao, có thể tự động hóa dễ | Khả năng phân loại đúng với tiếng Việt teen code |

## Problem Card #1 — Báo cáo tổng hợp lỗi sản phẩm tuần

**Problem 1 câu:**  
Mỗi thứ Sáu, CS Lead mất khoảng 120 phút đọc lại 150+ ticket lỗi trong tuần để làm Báo cáo chất lượng sản phẩm gửi QC, dễ bỏ sót dữ liệu và làm trễ kế hoạch xử lý lô hàng lỗi.

**Actor:**  
An — CS Lead chịu trách nhiệm gửi báo cáo chất lượng cho Trưởng phòng Sản xuất/QC.

**Thời điểm / bối cảnh:**  
15:00 Chiều thứ Sáu hằng tuần, trước buổi họp Quality Review.

**Current workflow:**
1. Export dữ liệu ticket tuần từ Zendesk ra CSV.
2. Lọc các ticket có tag/lý do "Lỗi hàng hóa".
3. Đọc từng câu chat và ghi chú thủ công loại lỗi (rách chỉ, phai màu, hỏng zip...) vào Google Sheets.
4. Nhóm các lỗi theo mã sản phẩm (SKU).
5. Viết narrative nhận xét: SKU lỗi nhiều nhất, xu hướng, đề xuất.
6. Format bài trình bày và gửi email/Slack cho QC.

**Bottleneck:**  
Bước 3 & 5 — Đọc thủ công hàng trăm tin nhắn để phân loại chính xác và viết nhận xét tổng hợp (tốn ~75 phút).

**Impact:**  
120 phút/tuần cho CS Lead. Báo cáo gửi muộn khiến QC không kịp giữ lại lô hàng lỗi ở kho trước ca xuất hàng sáng thứ Bảy.

**Success metric:**  
Giảm tổng thời gian tổng hợp từ 120 phút xuống dưới 30 phút, tăng số lượng ticket lỗi được phân loại chính xác lên >90%.

**Non-AI alternative:**  
Bắt CS Agent chọn dropdown "Loại lỗi chi tiết" khi đóng ticket. (Nhược điểm: Tăng AHT của Agent, Agent hay chọn đại để xong việc).

**AI hypothesis:**  
Script rút data → AI đọc nội dung chat thô để tự phân loại lỗi & nhóm SKU → AI draft narrative nhận xét → CS Lead review & gửi.

**Quick gut:**  
Workflow.

### Draft current workflow
CURRENT STATE — 120 phút
[1 Export CSV: 5'] → [2 Lọc ticket lỗi: 10'] → [3 Đọc chi tiết & ghi chú thủ công: 50' (BOTTLENECK 1)] → [4 Nhóm theo SKU: 15'] → [5 Viết narrative: 25' (BOTTLENECK 2)] → [6 Format & Gửi: 15']

### Draft future workflow
FUTURE STATE — 25 phút
[1 Auto-pull data: 2'] → [2 AI phân loại lỗi & nhóm SKU: 3'] → [3 AI draft narrative: 3'] → [4 CS Lead review & chỉnh sửa: 15' (HUMAN BOUNDARY)] → [5 CS Lead gửi: 2']