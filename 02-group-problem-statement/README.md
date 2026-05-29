# 02 — Group Problem Statement

## 0. Mục tiêu của phần nhóm

Phần này tổng hợp các Problem Cards cá nhân thành một candidate problem duy nhất để nhóm đào sâu. Nhóm không bắt đầu bằng câu hỏi “xây chatbot/agent gì?”, mà đi từ vấn đề thật, actor thật, workflow hiện tại, bottleneck, metric, rồi mới quyết định nên dùng Rule, Workflow hay Agent.

Bài nộp nhóm này tập trung vào 3 candidate nổi bật trong danh sách 15 vấn đề đã scan:

1. **Chỉnh sửa CV theo từng JD tuyển dụng.**
2. **Đọc, dịch và tổng hợp paper tiếng Anh.**
3. **Viết báo cáo tiến độ hàng tuần từ nhiều nguồn thông tin.**

---

## 1. Group convergence

Sau khi mỗi thành viên trình bày top problems của mình, nhóm gom các vấn đề về 3 cụm chính:

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Tìm việc / định vị bản thân | Chỉnh sửa CV theo JD, viết cover letter, rà keyword tuyển dụng | Người dùng có tài liệu gốc nhưng không biết chỉnh thế nào cho khớp yêu cầu cụ thể mà vẫn trung thực. |
| Học tập / nghiên cứu | Đọc paper tiếng Anh, dịch thuật ngữ chuyên ngành, tóm tắt nghiên cứu | Người dùng mất thời gian chuyển đổi giữa tài liệu gốc, bản dịch và ghi chú, dễ đứt mạch đọc. |
| Báo cáo / tổng hợp tiến độ | Viết weekly report, recap họp nhóm, tổng hợp tiến độ lab/project | Thông tin nằm rải rác ở nhiều nơi; người phụ trách phải lọc, sắp xếp và viết lại thành narrative rõ ràng. |

Nhóm chọn 3 candidate dưới đây để chấm điểm sâu hơn vì đều có actor rõ, workflow hiện tại mô tả được, AI có thể hỗ trợ ở một bước cụ thể và có thể đặt boundary để giảm rủi ro.

---

## 2. Shortlist và scoring

Thang điểm: **1–10** cho mỗi tiêu chí.

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng / 70 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Viết báo cáo tiến độ hàng tuần** | 9 | 10 | 8 | 9 | 10 | 9 | 9 | **64** |
| **Chỉnh sửa CV theo JD tuyển dụng** | 9 | 9 | 8 | 7 | 9 | 8 | 9 | **59** |
| **Đọc, dịch và tổng hợp paper tiếng Anh** | 8 | 8 | 8 | 8 | 7 | 8 | 8 | **55** |

### Nhóm chọn

```text
Viết báo cáo tiến độ hàng tuần từ nhiều nguồn thông tin.
```

### Vì sao chọn candidate này?

Nhóm chọn **viết báo cáo tiến độ hàng tuần** vì đây là bài toán có workflow lặp lại rõ nhất, phù hợp scope lab nhất và có metric đo được ngay bằng thời gian, số lỗi thiếu thông tin, số lần người nhận phải hỏi lại. Bài toán cũng cho phép so sánh rõ giữa Rule, Workflow và Agent:

- **Rule:** template/checklist báo cáo.
- **Workflow:** gom input → AI cấu trúc → AI draft narrative → người phụ trách review → gửi.
- **Agent:** chỉ cần ở giai đoạn sau nếu hệ thống tự đi hỏi thành viên, tự kéo dữ liệu từ nhiều tool và tự theo dõi follow-up.

### Vì sao không chọn hai candidate còn lại làm bài chính?

**Không chọn “Chỉnh sửa CV theo JD” làm bài chính** vì tuy pain thực tế và dễ hiểu, success metric cuối cùng như tỷ lệ được gọi phỏng vấn khó đo trong thời gian ngắn. Ngoài ra, bài này cần boundary rất mạnh để tránh AI thổi phồng kinh nghiệm hoặc thêm thông tin không đúng sự thật.

**Không chọn “Đọc, dịch và tổng hợp paper tiếng Anh” làm bài chính** vì đây là bài tốt nhưng scope kỹ thuật dễ bị rộng nếu nhóm cố giữ nguyên layout PDF, công thức, bảng biểu và hình ảnh. Trong lab ngắn, bài này nên thu hẹp thành “trích xuất bảng so sánh paper theo template” nếu muốn làm chắc.

---

## 3. Candidate analysis

### Candidate 1 — Viết báo cáo tiến độ hàng tuần

**Problem 1 câu:**  
Sinh viên hoặc nhóm trưởng mất nhiều thời gian mỗi tuần để tổng hợp tiến độ từ nhiều nguồn rời rạc như tin nhắn nhóm, task list, ghi chú họp và file kế hoạch, sau đó viết thành báo cáo có cấu trúc cho giảng viên, mentor hoặc leader.

**Actor:**  
Sinh viên làm dự án nhóm, nhóm trưởng, PM/leader hoặc người phụ trách gửi báo cáo định kỳ.

**Current workflow:**

```text
1. Hỏi từng thành viên cập nhật tiến độ
2. Xem task board, checklist hoặc file kế hoạch
3. Đọc lại tin nhắn nhóm và ghi chú họp
4. Tổng hợp việc đã làm, việc chưa xong, vấn đề và rủi ro
5. Viết báo cáo tiến độ theo format yêu cầu
6. Review, chỉnh format và gửi cho người nhận
```

**Bottleneck:**  
Bottleneck nằm ở bước 4–5. Người phụ trách không chỉ copy thông tin, mà phải lọc ý quan trọng, sắp xếp logic và viết thành narrative dễ hiểu. Đây là bước tốn thời gian nhất và khó làm bằng rule thuần túy.

**Success metric:**

| Metric | Trước | Mục tiêu pilot |
|---|---:|---:|
| Thời gian viết report/tuần | 60–90 phút | Dưới 30 phút |
| Số lần người nhận hỏi lại do thiếu context | Chưa ổn định | Giảm ít nhất 50% |
| Tỷ lệ report đủ 4 mục: done / blocked / risk / next actions | Không ổn định | 90%+ |
| Mức độ người phụ trách phải sửa draft AI | Chưa đo | Draft dùng được sau 10–15 phút review |

**AI fit:**  
Workflow. AI hỗ trợ cấu trúc input và draft narrative; người thật vẫn review và gửi.

---

### Candidate 2 — Chỉnh sửa CV theo JD tuyển dụng

**Problem 1 câu:**  
Sinh viên năm cuối hoặc fresher thường mất nhiều thời gian chỉnh sửa CV cho từng JD vì không biết kỹ năng nào nên nhấn mạnh, phần nào còn thiếu và cách diễn đạt kinh nghiệm sao cho phù hợp nhưng vẫn trung thực.

**Actor:**  
Sinh viên năm cuối, fresher, người mới đi tìm thực tập hoặc việc làm đầu tiên.

**Current workflow:**

```text
1. Tìm JD tuyển dụng
2. Đọc yêu cầu công việc
3. So sánh JD với CV hiện tại
4. Chỉnh lại phần kỹ năng, kinh nghiệm và project
5. Viết/chỉnh cover letter nếu cần
6. Nộp hồ sơ
```

**Bottleneck:**  
Bottleneck nằm ở bước 3–4. Người dùng không biết CV đang thiếu gì so với JD, keyword nào quan trọng và nên viết lại trải nghiệm thế nào cho rõ hơn mà không sai sự thật.

**Success metric:**

| Metric | Trước | Mục tiêu pilot |
|---|---:|---:|
| Thời gian chỉnh CV cho 1 JD | 30–60 phút | Dưới 15 phút |
| Số keyword quan trọng trong JD được phản ánh đúng trong CV | Không rõ | Tăng theo checklist |
| Số điểm AI gợi ý nhưng người dùng phải bỏ vì không đúng sự thật | Chưa đo | Giữ thấp, có cảnh báo trung thực |

**AI fit:**  
Workflow. AI đọc JD, so sánh CV, gợi ý chỉnh sửa; người dùng duyệt nội dung cuối.

**Boundary:**  
Không thêm kỹ năng/kinh nghiệm không có thật; không tự nộp hồ sơ thay người dùng; không cam kết tăng tỷ lệ đậu phỏng vấn.

---

### Candidate 3 — Đọc, dịch và tổng hợp paper tiếng Anh

**Problem 1 câu:**  
Sinh viên AI hoặc người làm nghiên cứu mất nhiều thời gian đọc paper tiếng Anh vì phải vừa hiểu thuật ngữ học thuật, vừa giữ đúng cấu trúc paper, vừa trích xuất thông tin quan trọng để so sánh với các paper khác.

**Actor:**  
Sinh viên AI, sinh viên nghiên cứu, thực tập sinh làm literature review.

**Current workflow:**

```text
1. Tìm và tải paper
2. Đọc Abstract, Introduction, Method, Experiment, Conclusion
3. Dịch các đoạn khó hoặc thuật ngữ chuyên ngành
4. Trích xuất method, dataset, metric, result, limitation
5. Ghi vào bảng so sánh hoặc note cá nhân
6. Tổng hợp lại để phục vụ báo cáo/đồ án
```

**Bottleneck:**  
Bottleneck nằm ở bước 3–5. Người đọc phải chuyển qua lại giữa bản gốc, công cụ dịch và ghi chú; nếu dịch toàn file PDF thì dễ mất format, bảng biểu hoặc công thức.

**Success metric:**

| Metric | Trước | Mục tiêu pilot |
|---|---:|---:|
| Thời gian đọc/tổng hợp 1 paper | 45–90 phút | 20–30 phút |
| Tỷ lệ field quan trọng được trích đúng | Không ổn định | 90%+ trên template |
| Tỷ lệ thuật ngữ chuyên ngành cần sửa lại | Chưa đo | Giảm dần qua glossary |

**AI fit:**  
Workflow / RAG. AI hỗ trợ dịch theo ngữ cảnh, trích thông tin vào template và chỉ ra phần cần đọc kỹ. Không cần Agent nếu chỉ xử lý từng paper theo template.

---

## 4. Quick validation

Validation ban đầu dựa trên quan sát của nhóm trong các bài lab/dự án gần đây. Nhóm cần thay bằng số liệu thật nếu có khảo sát nhanh sau buổi học.

| Nguồn | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---|---|---|
| Trải nghiệm làm bài nhóm/lab | Mỗi lần gần deadline, người phụ trách thường phải đọc lại nhiều nguồn để viết phần tiến độ. | Nếu nhóm đã dùng template cập nhật rất tốt thì báo cáo không quá tốn thời gian. | Không làm “agent quản lý dự án”, chỉ làm workflow hỗ trợ draft report từ input đã được chuẩn hóa. |
| Quan sát từ các dự án sinh viên | Thông tin thường rải rác ở chat, Google Docs, file kế hoạch và lời nhắn miệng. | Nếu input quá thiếu, AI vẫn không thể viết báo cáo đúng. | Thêm bước rule/template: thành viên phải cập nhật theo form ngắn trước khi AI draft. |
| So sánh với CV/paper candidates | CV và paper đều có pain thật nhưng scope hoặc metric khó kiểm chứng hơn trong thời gian lab. | Paper translation có thể hấp dẫn hơn về kỹ thuật. | Ưu tiên candidate có workflow rõ, làm được trong lab và ít rủi ro hơn. |

**Insight sau validation:**

```text
Pain thật không nằm ở việc “không biết viết báo cáo”, mà nằm ở việc tổng hợp dữ liệu rời rạc thành một câu chuyện tiến độ rõ ràng: tuần này đã làm gì, đang kẹt ở đâu, rủi ro là gì và tuần sau cần làm gì.
```

---

## 5. Research giải pháp đã có

Nhóm không giả định phải tự build toàn bộ từ đầu. Các công cụ hiện có cho thấy AI có thể tóm tắt, tạo action items và hỗ trợ recap, nhưng vẫn cần người thật review trước khi gửi báo cáo chính thức.

| Nguồn / tool / case | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|
| [Notion AI Meeting Notes](https://www.notion.com/product/ai-meeting-notes) | Ghi chú họp, follow-up, cập nhật project sau meeting | Tốt cho meeting recap và action items | Không trực tiếp gom input từ nhiều nguồn rời rạc của bài lab | AI nên draft, nhưng cần người phụ trách kiểm tra context. |
| [Gemini in Google Docs](https://workspace.google.com/products/docs/ai/) | Tóm tắt tài liệu và hỗ trợ viết trong Docs | Phù hợp nếu nhóm đã làm việc trong Google Docs | Không tự đảm bảo báo cáo đủ done / blocked / risk / next actions | Cần template/rubric report rõ trước khi dùng AI viết. |
| [Fellow AI Meeting Assistant](https://fellow.ai/) | Transcribe, summarize, action items, meeting insights | Mạnh ở dữ liệu họp và follow-up | Weekly report còn cần task list, chat recap, trạng thái từng người | Có thể học pattern: transcript/notes → summary → action items → human review. |
| Template/checklist thủ công | Chuẩn hóa format report | Rẻ, dễ làm, ít rủi ro | Không giải quyết tốt phần narrative khi input rời rạc | Rule/template nên là baseline bắt buộc trước khi thêm AI. |

**Research takeaway:**

```text
Không nên build một Agent tự chạy toàn bộ báo cáo ngay. Hướng hợp lý hơn là Workflow: chuẩn hóa input bằng form/template, dùng AI để cấu trúc và draft narrative, sau đó người phụ trách review trước khi gửi.
```

---

## 6. Workflow before/after

### Current workflow

```text
CURRENT STATE — khoảng 75–90 phút/tuần

[1 Hỏi từng thành viên cập nhật tiến độ: 10']
→ [2 Xem task board/checklist/file kế hoạch: 10']
→ [3 Đọc lại tin nhắn nhóm và ghi chú họp: 15']
→ [4 Tổng hợp việc đã làm, việc chưa xong, risk: 15']
→ [5 Viết narrative báo cáo: 25']  <-- bottleneck chính
→ [6 Review + chỉnh format: 10']
→ [7 Gửi báo cáo: 5']
```

### Future workflow

```text
FUTURE STATE — mục tiêu dưới 30 phút/tuần

[1 Thành viên cập nhật theo form/template cố định: 5']  -- Rule/process
→ [2 Hệ thống gom input vào một cấu trúc chung: 2']     -- Rule/script
→ [3 AI phân loại: done / in progress / blocked / risk / next action: 1']
→ [4 AI draft báo cáo tiến độ theo format: 1']          -- Workflow step
→ [5 Người phụ trách review, sửa bối cảnh và xác nhận: 15']  <-- human boundary
→ [6 Gửi báo cáo cuối: 2']

Fallback:
- Nếu AI draft sai, thiếu context hoặc quá chung chung → người phụ trách bỏ draft và dùng template thủ công.
- Nếu input thiếu từ một thành viên → hệ thống đánh dấu “missing update”, không tự bịa tiến độ.
- Nếu có thông tin nhạy cảm hoặc mâu thuẫn → người phụ trách quyết định có đưa vào report hay không.
```

### Before/after impact

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Tổng thời gian | 75–90 phút | Dưới 30 phút | Target chính |
| Số bước thủ công | 7/7 | 2–3/6 | Người thật vẫn review và gửi |
| Bước nghẽn chính | Viết narrative | Review/edit | Bottleneck mới là điểm kiểm soát chất lượng |
| Tỷ lệ report thiếu mục | Chưa ổn định | Giảm nhờ template | Cần checklist done/blocked/risk/next |
| Rủi ro mới | Không có hallucination | AI có thể bịa/diễn giải sai | Cần input chuẩn + human review |

---

## 7. Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Sinh viên làm nhóm, nhóm trưởng, PM/leader hoặc người phụ trách gửi báo cáo tiến độ định kỳ. |
| **Workflow** | Thu thập update từ thành viên, đọc task list/chat/ghi chú họp, tổng hợp việc đã làm, vấn đề, rủi ro và next actions, sau đó viết báo cáo. |
| **Bottleneck** | Thông tin tiến độ nằm rải rác và chưa có cấu trúc; người phụ trách mất nhiều thời gian biến dữ liệu thô thành narrative rõ ràng. |
| **Impact** | Tốn 75–90 phút mỗi tuần, dễ sót việc, report thiếu context, người nhận phải hỏi lại. |
| **Success Metric** | Giảm thời gian viết report xuống dưới 30 phút; report đủ done/blocked/risk/next actions; giảm số lần bị hỏi lại. |
| **Boundary** | AI không tự gửi báo cáo, không tự bịa update, không đánh giá năng lực thành viên; người phụ trách review trước khi gửi. |

---

## 8. Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ? | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI / process fix** | Dùng template report và yêu cầu thành viên tự cập nhật đều | Đủ nếu nhóm nhỏ, input ít và người phụ trách có thời gian | Vẫn phải tự viết narrative; dễ thiếu context nếu update rời rạc | Không chọn làm giải pháp chính, nhưng dùng làm baseline |
| **Rule** | Checklist, form cố định, auto-fill các mục done/blocked/risk | Đủ cho cấu trúc report đơn giản | Không xử lý tốt phần viết narrative và gom ý từ ghi chú tự do | Chọn một phần |
| **Workflow** | Form/template → gom input → AI phân loại/draft → người phụ trách review → gửi | Phù hợp nhất vì các bước rõ, có human boundary | AI có thể diễn giải sai nếu input thiếu | **Chọn** |
| **Agent** | AI tự lấy dữ liệu từ nhiều tool, hỏi thành viên chưa update, tự tạo follow-up và tự gửi | Chỉ cần khi tích hợp nhiều hệ thống và quyền hành động phức tạp | Rủi ro quá quyền, gửi sai thông tin, privacy/access issue | Not Yet |

### Mức chọn

```text
Workflow.
```

### Vì sao?

Bài toán cần AI ở bước viết và cấu trúc narrative, nhưng không cần Agent tự quyết định hành động. Input/output của pilot có thể kiểm soát rõ: dữ liệu update trong tuần → draft report → người phụ trách review → gửi. Cách này đủ tạo giá trị nhưng vẫn giữ người thật ở điểm kiểm soát cuối.

---

## 9. Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Người phụ trách báo cáo tiến độ nhóm hằng tuần: nhóm trưởng, PM/leader, hoặc sinh viên đại diện nhóm. |
| **Workflow** | Thành viên cập nhật theo form/template → hệ thống gom input → AI phân loại done/blocked/risk/next actions → AI draft report → người phụ trách review và gửi. |
| **Bottleneck** | Bước viết narrative từ nhiều input rời rạc tốn thời gian và dễ sót thông tin quan trọng. |
| **Impact** | Mỗi tuần mất 75–90 phút để tạo một report; report không rõ có thể làm mentor/giảng viên/leader phải hỏi lại và khiến nhóm chậm xử lý blocker. |
| **Success Metric** | Giảm thời gian report xuống dưới 30 phút; 90%+ report đủ 4 mục done/blocked/risk/next actions; giảm ít nhất 50% câu hỏi follow-up do thiếu context. |
| **Boundary** | AI không tự gửi report, không tự tạo thông tin chưa có trong input, không đánh giá cá nhân, không xử lý dữ liệu nhạy cảm ngoài phạm vi nhóm. |
| **AI intervention point** | AI tham gia ở bước phân loại input và draft narrative, sau khi dữ liệu đã được chuẩn hóa bằng form/template. |
| **Mức chọn** | Workflow: Rule/template chuẩn hóa input + AI draft + human review. |
| **Rủi ro & người thật kiểm tra** | Risk: AI hiểu sai blocker hoặc viết quá chung. Người thật kiểm tra: người phụ trách review, sửa context, xác nhận trước khi gửi. |

---

## 10. Final decision

### Decision

```text
Go với scope nhỏ cho Workflow pilot.
Not Yet cho full Agent.
```

### Lý do Go cho pilot

- Actor rõ: người phụ trách report hằng tuần.
- Workflow hiện tại rõ và lặp lại.
- Bottleneck cụ thể: viết narrative từ nhiều input rời rạc.
- Impact đo được bằng thời gian, độ đầy đủ report và số lần người nhận hỏi lại.
- Có thể làm trong lab bằng dữ liệu giả lập hoặc report thật đã ẩn thông tin.
- Human boundary rõ: người phụ trách luôn review trước khi gửi.

### Lý do Not Yet cho full Agent

- Chưa cần AI tự đi lấy dữ liệu từ nhiều hệ thống.
- Chưa nên để AI tự nhắc thành viên, tự đánh giá người làm chậm hoặc tự gửi báo cáo.
- Cần thêm chính sách phân quyền, privacy và cách xử lý dữ liệu thiếu/mâu thuẫn trước khi cho Agent hành động.

### Pilot nhỏ nhất

```text
Input:
- 1 template cập nhật tiến độ hằng tuần cho từng thành viên
- 1 task list hoặc checklist của nhóm
- 1 ghi chú họp ngắn nếu có

Output:
- 1 báo cáo tiến độ có 4 mục:
  1. Done
  2. In progress / blocked
  3. Risk
  4. Next actions

Đo lường:
- Thời gian tạo report
- Số mục bị thiếu
- Số câu người phụ trách phải sửa
- Số câu hỏi follow-up từ người nhận
```

### Exit / rollback

- Nếu AI draft sai nhiều hoặc mất nhiều thời gian sửa hơn viết tay → quay về template thủ công.
- Nếu input từ thành viên quá thiếu → hệ thống chỉ tạo checklist thiếu update, không draft report.
- Nếu report chứa thông tin nhạy cảm → người phụ trách tự biên tập trước khi gửi.

### Decision rationale

```text
Nhóm chọn Workflow vì bài toán đủ rõ để tự động hóa một phần, nhưng vẫn cần người thật kiểm soát chất lượng. Đây là quyết định cân bằng giữa giá trị AI và rủi ro vận hành: AI giúp giảm thời gian tổng hợp/viết, còn con người giữ quyền xác nhận nội dung cuối.
```
