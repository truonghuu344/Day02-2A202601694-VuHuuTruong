# 02 — Group Problem Statement

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|-----|-----------|-------------|--------------------|
| 1 | Phan Trọng Đạt | 2A202601138 | Thành viên nhóm |
| 2 | Nguyễn Xuân Quân | 2A202601976 | Thành viên nhóm |
| 3 | Phạm Anh Minh | 2A202601260 | Thành viên nhóm |
| 4 | Phạm Ngọc Quốc Khánh | 2A202601254 | Thành viên nhóm |
| 5 | Vũ Hữu Trường | 2A202601694 | Thành viên nhóm |
| 6 | Trương Quang Minh | 2A202601212 | Thành viên nhóm |

## Group convergence

Nhóm 5 người, mỗi người share candidate problem của mình. Tổng cộng nhóm có 6 candidates để thảo luận. Ở bước này nhóm chỉ chọn một **candidate problem** để đào sâu, chưa chốt Problem Statement hoàn chỉnh và chưa chốt solution.

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Marketing / vận hành SME | SME mất nhiều thời gian và chi phí khi thuê agency lập kế hoạch marketing | Chủ doanh nghiệp nhỏ cần hỗ trợ lập kế hoạch, giảm chi phí thuê ngoài và giảm thời gian chuẩn bị |
| Quy trình kiểm tra / đánh giá đầu vào | Quy trình kiểm tra đầu vào chưa hiệu quả và chưa cá nhân hóa | Người dùng cần được đánh giá đúng hơn trước khi đi vào một quy trình học tập, tuyển chọn hoặc tư vấn |
| Vận hành nội bộ / ghi nhận dữ liệu | Chấm công bị sai do ghi chép thủ công, quản lý shop điện tử | Quy trình thủ công dễ sai, thiếu đồng bộ dữ liệu và cần chuẩn hóa trước khi tự động hóa |
| Giao thông / thông tin thời gian thực | Sự thụ động và sai lệch thời gian khi đón xe bus tại các trạm không có bảng điện tử | Người dùng thiếu thông tin cập nhật đúng lúc để ra quyết định |
| BA / Dev communication | IT SLC: BA -> Dev Communication | BA phải chuyển yêu cầu nghiệp vụ sang ngôn ngữ kỹ thuật cho Dev, nhưng bị nghẽn vì thiếu technical context và Knowledge Base khó tra cứu |

## Shortlist và score

| Candidate | Actor rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|
| SME mất nhiều thời gian và chi phí khi thuê agency lập kế hoạch marketing | 3 | 4 | 3 | 4 | 4 | 3 | 21 |
| Quy trình kiểm tra đầu vào chưa hiệu quả và chưa cá nhân hóa | 3 | 3 | 3 | 4 | 3 | 4 | 20 |
| Chấm công bị sai do ghi chép thủ công | 4 | 5 | 4 | 3 | 4 | 3 | 23 |
| Sự thụ động và sai lệch thời gian khi đón xe bus tại các trạm không có bảng điện tử | 4 | 4 | 4 | 3 | 3 | 3 | 21 |
| Quản lý shop điện tử | 4 | 4 | 4 | 3 | 3 | 3 | 21 |
| IT SLC: BA -> Dev Communication | 5 | 4 | 4 | 4 | 4 | 3 | 24 |

Nhóm chọn: **IT SLC: BA -> Dev Communication**.

Vì sao chọn:

- Có actor rõ: BA là người viết spec/báo cáo kỹ thuật; Dev là người nhận spec và chịu ảnh hưởng nếu spec thiếu rõ.
- Có workflow hiện tại vẽ được rõ: BA nhận Business Requirement -> đọc Knowledge Base -> tra technical terms -> viết SRS/report -> gửi Dev -> Dev trả lại nếu thiếu logic -> BA sửa lại.
- Có bottleneck cụ thể: BA phải dịch business logic sang technical terms và viết report/spec đủ rõ cho Dev.
- Có baseline thời gian ban đầu: bước dịch sang technical terms và viết report mất khoảng 60-90 phút/tính năng.
- Impact có thể đo được: thời gian trao đổi BA-Dev, thời gian tìm Knowledge Base, số lần Dev trả lại spec, thời gian BA sửa lại tài liệu.
- Có thể validate nhanh bằng cách hỏi BA/Dev trong IT SLC hoặc xem lại log chat, comment trên tài liệu, version history và các lần Dev yêu cầu làm rõ.
- Có thể so sánh No AI / Rule / Workflow / Agent tương đối rõ: template và glossary có thể giúp một phần, nhưng bài toán có khả năng cần Workflow hoặc Agent có RAG để truy xuất Knowledge Base và draft spec.

Vì sao không chọn các bài khác:

- SME mất nhiều thời gian và chi phí khi thuê agency lập kế hoạch marketing: pain có thật nhưng actor và context còn rộng; cần thêm dữ liệu về loại SME, loại kế hoạch marketing và chi phí hiện tại.
- Quy trình kiểm tra đầu vào chưa hiệu quả và chưa cá nhân hóa: có thể làm trong lab nhưng problem chưa đủ cụ thể; chưa rõ kiểm tra đầu vào cho lĩnh vực nào và metric cá nhân hóa đo bằng gì.
- Chấm công bị sai do ghi chép thủ công: pain và evidence khá rõ, nhưng có thể giải bằng rule/process hoặc phần mềm chấm công hiện có; chưa chắc cần AI.
- Sự thụ động và sai lệch thời gian khi đón xe bus tại các trạm không có bảng điện tử: impact rõ với người đi xe bus, nhưng nhóm có thể khó validate dữ liệu thời gian thực và khó làm trong scope lab.
- Quản lý shop điện tử: actor và workflow còn rộng; cần thu hẹp là quản lý tồn kho, đơn hàng, chăm sóc khách hay báo cáo doanh thu thì mới đào sâu được.

## Current workflow

```text
CURRENT STATE — khoảng 60-90 phút/tính năng

[1 BA nhận yêu cầu nghiệp vụ (Business Requirement)]
→ [2 BA lục tìm và đọc tài liệu hệ thống, Knowledge Base cũ]
→ [3 BA tra cứu thuật ngữ kỹ thuật và cố map business logic vào tech logic]  <-- bottleneck
→ [4 BA viết tài liệu đặc tả (SRS/Report) và gửi cho Dev]
→ [5 Dev đọc không hiểu hoặc thấy thiếu logic hệ thống]
→ [6 Dev trả lại yêu cầu giải thích]
→ [7 BA quay lại bước 3 để sửa spec/report]
```

Bottleneck chính:

```text
Dịch yêu cầu nghiệp vụ sang technical terms và viết report/spec đủ rõ cho Dev.
Thời gian nghẽn ước tính: 60-90 phút/tính năng.
```

## Future workflow

```text
FUTURE STATE — kỳ vọng dưới 30-40 phút/tính năng

[1 BA nhập yêu cầu nghiệp vụ bằng ngôn ngữ tự nhiên (plain text)]
→ [2 AI Agent truy xuất IT SLC Knowledge Base hiện tại bằng RAG]
→ [3 AI Agent gợi ý technical terms và map business logic sang tech logic]
→ [4 AI Agent draft spec/report theo form chuẩn]
→ [5 BA review, chỉnh sửa và duyệt]  <-- human boundary
→ [6 Dev nhận spec rõ hơn ngay từ lần đầu]

Fallback:
Nếu AI truy xuất sai Knowledge Base, dùng sai thuật ngữ hoặc suy diễn thiếu căn cứ,
BA phải chỉnh lại và không gửi trực tiếp cho Dev.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Thời gian BA viết spec/report kỹ thuật cho một tính năng | 60-90 phút/tính năng | Dưới 30-40 phút/tính năng | Target chính |
| Số lần Dev trả lại spec để hỏi thêm/làm rõ | 1-3 lần/tính năng | 0-1 lần/tính năng | Cần validate bằng log/comment thật |
| Thời gian BA tìm kiếm Knowledge Base liên quan | Chưa đo chính xác | Giảm ít nhất 50% | Cần đo baseline trong phase validation |
| Mức độ đầy đủ của spec lần đầu gửi Dev | Phụ thuộc kinh nghiệm BA | Có checklist/format rõ hơn | BA vẫn là người duyệt cuối |

## Pitch và phản biện

Pitch ngắn:

```text
Trong IT SLC, BA thường nhận yêu cầu nghiệp vụ nhưng khi viết spec hoặc báo cáo kỹ thuật cho Dev thì gặp khó vì thiếu technical background. BA phải tự lục Knowledge Base cũ, tra thuật ngữ, cố map business logic sang tech logic rồi viết SRS/report. Dev nhiều khi đọc không hiểu hoặc thấy thiếu logic hệ thống nên trả lại để BA giải thích, tạo vòng lặp tốn thời gian. Candidate problem này đáng đào sâu vì actor rõ, workflow rõ, bottleneck đo được và có thể thử hướng AI/RAG để hỗ trợ BA draft spec tốt hơn, nhưng BA vẫn phải review trước khi gửi Dev.
```

Câu hỏi phản biện nhóm cần đặt:

- Người dùng chính là BA hay cả Dev cũng là người dùng của hệ thống?
- Pain lớn nhất nằm ở thiếu technical terms, thiếu Knowledge Base, hay thiếu form spec chuẩn?
- Rule/template + glossary có đủ giải quyết 70-80% vấn đề chưa?
- Có thật sự cần Agent, hay Workflow RAG + draft spec + BA review là đủ?
- Ranh giới người-máy nằm ở đâu: AI được draft đến mức nào, có được suy diễn technical logic không, có được gửi thẳng cho Dev không?
- Cần evidence gì để chứng minh problem thật: số lần Dev trả lại spec, thời gian BA viết spec, log chat BA-Dev hay version history của tài liệu?

Kết luận hội tụ:

```text
Nhóm thống nhất chọn candidate problem: IT SLC: BA -> Dev Communication.
Problem Statement hoàn chỉnh sẽ chỉ được viết sau khi nhóm validate pain, research giải pháp hiện có và làm rõ boundary giữa BA, Dev và AI.
```

## Quick validation

Nhóm kiểm chứng nhanh trước khi viết Problem Statement để tách phần đã có bằng chứng khỏi giả định còn mở.

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Thảo luận nhanh trong nhóm | 5 thành viên | Nhóm thống nhất BA -> Dev communication là workflow có thật trong môi trường IT/SLC; điểm đau nằm ở việc BA phải chuyển business requirement thành spec đủ rõ cho Dev. | Chưa có log thật từ BA/Dev; baseline 60-90 phút/tính năng mới là ước tính từ candidate pitch. | Ghi rõ đây là candidate problem cần validate thêm, chưa dùng số liệu như bằng chứng chắc chắn. |
| Quan sát workflow mẫu | 1 workflow BA -> Dev | Workflow có vòng lặp rõ: BA nhận requirement -> đọc KB -> viết spec -> Dev trả lại nếu thiếu logic -> BA sửa. | Chưa biết vòng lặp này xảy ra với mọi spec hay chỉ với tính năng phức tạp. | Thu hẹp vào spec/report kỹ thuật cho tính năng cần nhiều mapping business logic sang tech logic. |
| Research giải pháp hiện có | 3 hướng giải pháp | Có các hướng phổ biến: template spec/checklist, glossary kỹ thuật, internal knowledge search/RAG assistant. | Chưa kiểm chứng chất lượng Knowledge Base của IT SLC; nếu KB cũ/sai thì RAG có thể làm sai nhanh hơn. | Không chốt Agent tự động hoàn toàn; giữ human review của BA là boundary bắt buộc. |

### Research giải pháp đã có

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Google PAIR Guidebook | https://pair.withgoogle.com/guidebook/ | Gợi ý thực hành human-centered AI: hiểu nhu cầu người dùng, điểm thất bại, phản hồi và trách nhiệm của người dùng/người thiết kế. | Giúp nhóm kiểm tra boundary người-máy và tránh để AI thay quyết định nghiệp vụ/kỹ thuật. | Không phải tool trực tiếp cho BA viết spec; chỉ là khung tư duy. | Cần để BA review cuối, ghi rõ điểm AI có thể sai và cơ chế phản hồi/sửa. |
| Atlassian Confluence Knowledge Base | https://www.atlassian.com/software/confluence/knowledge-management | Lưu trữ Knowledge Base, tài liệu hệ thống, quyết định kỹ thuật và hướng dẫn nội bộ. | Phù hợp với vấn đề tài liệu rải rác và tra cứu lại kiến thức cũ. | Nếu tài liệu không cập nhật thì search/RAG vẫn trả về thông tin cũ. | Cần kiểm soát chất lượng KB trước khi dùng AI truy xuất. |
| Microsoft Copilot / M365 Copilot | https://www.microsoft.com/en-us/microsoft-365/copilot | Hỗ trợ viết nháp, tóm tắt và truy xuất nội dung trong môi trường tài liệu doanh nghiệp. | Cho thấy pattern phổ biến: AI draft, người thật review. | Không tự đảm bảo spec đúng technical logic nếu nguồn không đủ hoặc prompt mơ hồ. | AI nên hỗ trợ draft và tổng hợp, không tự gửi spec cho Dev. |

### Bằng chứng và giả định

| Loại | Nội dung | Trạng thái |
|---|---|---|
| Đã có tín hiệu | Workflow BA -> Dev có vòng lặp trả lại spec khi Dev không hiểu hoặc thấy thiếu logic hệ thống. | Tín hiệu từ candidate pitch và thảo luận nhóm. |
| Đã có tín hiệu | Bottleneck nằm ở bước dịch business requirement sang technical terms và viết report/spec. | Tín hiệu từ workflow mô tả. |
| Còn giả định | Thời gian 60-90 phút/tính năng là baseline đại diện. | Cần validate bằng phỏng vấn BA hoặc log thời gian thật. |
| Còn giả định | Dev trả lại spec 1-3 lần/tính năng. | Cần kiểm chứng bằng comment, chat, ticket hoặc version history. |
| Còn giả định | IT SLC Knowledge Base đủ sạch để dùng RAG. | Cần audit KB: độ cập nhật, nguồn sở hữu, cấu trúc, quyền truy cập. |

## Workflow + Problem Statement

### Current workflow chi tiết

| Bước | Actor | Input | Output | Thời gian/tần suất | Ghi chú |
|---|---|---|---|---|---|
| 1 | BA | Business Requirement từ stakeholder | Yêu cầu nghiệp vụ ban đầu | Mỗi tính năng | Input thường ở ngôn ngữ business, chưa đủ technical detail. |
| 2 | BA | Requirement + tài liệu hệ thống/KB cũ | Các đoạn tài liệu liên quan | 10-20 phút/tính năng | Có thể mất thời gian vì KB phân tán hoặc không cập nhật. |
| 3 | BA | Requirement + KB + thuật ngữ kỹ thuật | Mapping business logic -> tech logic | 30-45 phút/tính năng | Bottleneck chính; BA thiếu technical context nên phải tra cứu nhiều. |
| 4 | BA | Mapping + form tài liệu | SRS/report draft | 20-30 phút/tính năng | Draft có thể thiếu logic hệ thống hoặc thuật ngữ technical. |
| 5 | Dev | SRS/report draft | Comment/câu hỏi/lý do trả lại | 10-20 phút/lần review | Dev phải hỏi lại nếu spec chưa đủ rõ. |
| 6 | BA + Dev | Comment của Dev | Spec được sửa hoặc giải thích thêm | 15-30 phút/vòng lặp | Handoff lặp lại làm chậm tiến độ. |

Bottleneck chính:

```text
BA phải tự dịch business logic sang technical terms và viết spec/report đủ rõ cho Dev,
trong khi Knowledge Base khó tra cứu và technical context chưa nằm sẵn trong workflow.
```

### Future workflow chi tiết

| Bước | Actor | Rule / AI / Người | Input | Output | Boundary |
|---|---|---|---|---|---|
| 1 | BA | Người | Business Requirement plain text | Yêu cầu đầu vào rõ hơn | BA chịu trách nhiệm mô tả đúng business need. |
| 2 | Hệ thống | Workflow + AI/RAG | Requirement + IT SLC KB | Các tài liệu/đoạn KB liên quan | AI phải hiển thị nguồn hoặc ít nhất ghi rõ phần nào lấy từ KB. |
| 3 | Hệ thống | AI | KB liên quan + requirement | Gợi ý technical terms và mapping logic | Không được coi là đúng tuyệt đối. |
| 4 | Hệ thống | AI | Mapping + template spec | Draft SRS/report chuẩn form | AI chỉ draft, không gửi trực tiếp cho Dev. |
| 5 | BA | Người | Draft spec/report | Spec đã review và chỉnh sửa | Human boundary chính: BA duyệt trước khi gửi. |
| 6 | Dev | Người | Spec đã duyệt | Feedback hoặc acceptance | Dev vẫn có quyền phản hồi nếu spec thiếu/sai. |

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Số bước chính | 6 | 6 | Không nhất thiết giảm số bước, mà giảm effort ở bước tra cứu/draft. |
| Tổng thời gian BA viết spec/report | 60-90 phút/tính năng | Dưới 30-40 phút/tính năng | Baseline cần validate thêm. |
| Số bước thủ công nặng của BA | 3 bước: tìm KB, map logic, viết draft | 1-2 bước: nhập requirement, review/chỉnh draft | AI hỗ trợ tìm KB và draft, BA vẫn duyệt. |
| Bottleneck chính | Dịch business logic sang technical terms | BA review độ đúng của AI draft | Bottleneck mới chấp nhận được vì là điểm kiểm soát chất lượng. |
| Risk mới | Không có hallucination AI | AI dùng sai KB, suy diễn sai technical logic | Cần nguồn trích dẫn, checklist review và fallback. |

### Problem Statement v0

| Field | Nội dung |
|---|---|
| Actor | BA trong IT SLC cần viết spec/báo cáo kỹ thuật cho Dev; Dev là người nhận và dùng spec để triển khai. |
| Workflow | BA nhận Business Requirement, tìm Knowledge Base cũ, tra technical terms, map business logic sang tech logic, viết SRS/report, gửi Dev; nếu Dev không hiểu hoặc thấy thiếu logic thì trả lại để BA giải thích/sửa. |
| Bottleneck | Bước dịch yêu cầu nghiệp vụ sang technical terms và viết spec/report đủ rõ cho Dev mất khoảng 60-90 phút/tính năng. |
| Impact | Tăng thời gian trao đổi BA-Dev, làm chậm handoff sang Dev, tăng số vòng Dev trả lại spec và làm BA mất thời gian tìm Knowledge Base. |
| Success Metric | Giảm thời gian viết spec/report từ 60-90 phút xuống dưới 30-40 phút/tính năng; giảm số lần Dev trả lại spec xuống 0-1 lần/tính năng; giảm ít nhất 50% thời gian tìm KB liên quan. |
| Boundary | AI không được gửi spec trực tiếp cho Dev, không được tự bịa technical logic, phải dựa trên KB/nguồn được cung cấp; BA phải review và duyệt cuối. |

## Rule / Workflow / Agent + Decision

### Ma trận độ mơ hồ và độ phức tạp

| Tiêu chí | Đánh giá |
|---|---|
| Độ mơ hồ | Cao: cùng một business requirement có thể được diễn giải thành nhiều cách viết spec/technical mapping khác nhau. |
| Độ phức tạp | Cao vừa: workflow có nhiều bước, cần truy xuất KB, mapping logic, draft tài liệu và human review. |
| Ô phù hợp | Độ mơ hồ cao + độ phức tạp cao vừa: Workflow có AI/RAG hoặc Agent có boundary rõ có thể phù hợp. |

### So sánh Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| Rule | Template spec, glossary technical terms, checklist trước khi gửi Dev | Đủ nếu spec chỉ thiếu format và thuật ngữ cố định | Không tự tìm đúng KB, không map được business logic phức tạp | Không chọn làm toàn bộ, nhưng dùng như thành phần bắt buộc |
| Workflow | BA nhập requirement -> RAG tìm KB -> AI gợi ý terms/mapping -> AI draft spec -> BA review -> gửi Dev | Đủ nếu các bước tương đối cố định và BA luôn review cuối | Phụ thuộc chất lượng KB; AI có thể draft sai nếu nguồn thiếu | Chọn |
| Agent | Agent tự truy xuất KB, tự hỏi thêm nếu thiếu thông tin, tự lập kế hoạch draft spec theo từng loại tính năng | Phù hợp nếu nhiều nhánh, nhiều loại spec, cần tự quyết định bước tiếp theo | Phức tạp hơn cần thiết; rủi ro suy diễn technical logic và quyền truy cập KB | Chưa chọn cho pilot đầu |

Mức chọn:

```text
Workflow.
```

Vì sao chọn:

- Bottleneck nằm ở chuỗi bước rõ: tìm KB, dịch term, map logic, draft spec, BA review.
- AI/RAG hữu ích ở bước truy xuất và draft, nhưng quyết định cuối vẫn cần BA.
- Workflow đủ để pilot nhỏ; Agent tự lập kế hoạch có thể để sau khi đã validate KB và form spec.

Vì sao không chọn mức đơn giản hơn:

```text
Rule/template giúp chuẩn hóa form nhưng chưa giải quyết tốt việc tìm đúng Knowledge Base
và map business logic sang technical logic theo từng tính năng.
```

### Problem Statement v1

| Field | Nội dung |
|---|---|
| Actor | BA trong IT SLC viết spec/báo cáo kỹ thuật cho Dev; Dev dùng spec để triển khai và phản hồi khi thiếu logic. |
| Workflow | BA nhận Business Requirement -> tìm KB -> tra technical terms -> map business logic sang tech logic -> viết SRS/report -> Dev review -> BA sửa nếu Dev trả lại. |
| Bottleneck | BA mất khoảng 60-90 phút/tính năng ở bước tìm KB, dịch technical terms và draft spec đủ rõ cho Dev. |
| Impact | Handoff BA -> Dev chậm, Dev phải hỏi lại, BA mất thời gian sửa spec, tiến độ triển khai bị kéo dài. |
| Success Metric | Giảm thời gian viết spec/report xuống dưới 30-40 phút/tính năng; giảm số lần Dev trả lại xuống 0-1 lần/tính năng; giảm ít nhất 50% thời gian tìm KB. |
| Boundary | AI chỉ truy xuất/gợi ý/draft; không tự gửi Dev; không tự bịa logic; BA review và duyệt cuối. |
| AI intervention point | Sau khi BA nhập Business Requirement và trước khi BA viết draft spec thủ công: AI/RAG tìm KB, gợi ý terms/mapping và draft spec. |
| Mức chọn | Workflow: RAG tìm KB + AI draft spec + BA review. |
| Rủi ro & người thật kiểm tra | Rủi ro: KB cũ, AI suy diễn sai technical logic, draft thiếu edge case. Người kiểm tra: BA review nội dung trước khi gửi; Dev phản hồi nếu spec vẫn thiếu. |

### Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | BA và Dev rõ; workflow BA -> Dev có các bước cụ thể. |
| Baseline và success metric đã đo được chưa? | Not Yet | Có baseline ước tính 60-90 phút/tính năng, cần validate bằng dữ liệu thật. |
| Có data/input đủ dùng chưa? | Not Yet | Cần kiểm tra KB, spec cũ, log comment hoặc chat BA-Dev. |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes, nếu có review | Chỉ chấp nhận nếu BA review trước khi gửi Dev. |
| Có người review/owner vận hành không? | Yes | BA là người duyệt cuối; Dev phản hồi ở vòng review. |
| Có cách non-AI đơn giản hơn không? | Yes | Template/glossary/checklist có thể làm baseline hoặc fallback. |

Decision:

```text
Not Yet.
```

Lý do:

```text
Problem có actor, workflow và bottleneck rõ, nhưng baseline thời gian, số lần Dev trả lại
và chất lượng Knowledge Base vẫn cần validate bằng dữ liệu thật. Nhóm chưa nên chốt Go
cho AI workflow trước khi kiểm chứng các giả định này.
```

Nếu Not Yet, cần validate gì trước:

```text
1. Hỏi nhanh 2-3 BA/Dev về thời gian viết spec và số lần Dev trả lại.
2. Lấy 2-3 spec cũ để xem phần nào thường thiếu: technical terms, data flow, API, edge case hay business rule.
3. Kiểm tra Knowledge Base có đủ cập nhật, có nguồn sở hữu và có thể truy xuất bằng RAG không.
4. Thử pilot thủ công: BA paste requirement + vài đoạn KB liên quan, AI draft spec, BA đo thời gian sửa.
```
