# 02 — Group Problem Statement

## 1. Group convergence

Sau khi scan các vấn đề cá nhân, nhóm gom các ý tưởng thành 4 cụm chính:

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Học tập / ôn thi | Quá tải tài liệu học tập, khó hiểu lỗi sai, cần ôn trọng tâm | Sinh viên có nhiều tài liệu nhưng thiếu cách học có hệ thống và thiếu lời giải thích sát tài liệu môn học |
| Kiểm tra bài nộp | Rà rubric, kiểm tra báo cáo, thiếu metric/boundary/citation | Người làm bài cần một vòng kiểm tra chất lượng trước khi nộp |
| Chăm sóc khách hàng | Trả lời câu hỏi lặp lại, phân loại khiếu nại, tra cứu chính sách | Câu hỏi nhiều, lặp lại, nhưng cách diễn đạt tự nhiên và có cảm xúc |
| Làm việc nhóm | Tổng hợp ý kiến, theo dõi ai làm gì, bản nào là mới nhất | Thông tin rải rác ở nhiều kênh và dễ sót việc |

Nhóm chọn bài toán thuộc cụm **Học tập / ôn thi** vì đây là pain point gần với trải nghiệm thật của sinh viên, có workflow rõ, có thể đo impact và có thể so sánh rõ No AI / Rule / Workflow / Agent.

---

## 2. Shortlist và score

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm pilot được | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Hỗ trợ sinh viên phân tích lỗi sai và ôn tập có trọng tâm | 5 | 5 | 4 | 5 | 4 | 5 | 5 | 33 |
| Kiểm tra chất lượng báo cáo theo rubric | 5 | 4 | 4 | 4 | 5 | 4 | 5 | 31 |
| Hỗ trợ khách hàng lặp lại cho shop online | 4 | 4 | 4 | 5 | 4 | 5 | 3 | 29 |

### Vì sao chọn bài toán #1

- Actor rõ: sinh viên đại học đang ôn thi.
- Workflow rõ: thu gom tài liệu → hệ thống hóa → luyện tập → làm sai → tìm lời giải thích.
- Bottleneck rõ: tìm đúng phần kiến thức liên quan và hiểu vì sao mình sai.
- AI có vai trò cụ thể: truy xuất tài liệu, giải thích lỗi sai, gợi ý phần cần ôn lại.
- Có thể đặt boundary rõ: chỉ trả lời dựa trên tài liệu môn học, phải trích nguồn, không tự bịa kiến thức.

### Vì sao không chọn các bài khác

- **Kiểm tra chất lượng báo cáo:** rất an toàn và dễ triển khai, nhưng scope nhỏ hơn; có thể xử lý tốt bằng checklist/rule nếu rubric rõ.
- **Hỗ trợ khách hàng lặp lại:** thực tế và có volume lớn, nhưng ít gắn với trải nghiệm học tập của nhóm và cần dữ liệu vận hành của shop để mô phỏng tốt.

---

## 3. Selected problem

> **Trợ lý AI hỗ trợ sinh viên phân tích lỗi sai và ôn tập có trọng tâm từ tài liệu môn học.**

Bài toán không được định nghĩa là “xây chatbot ôn thi” hay “xây AI Agent ôn thi” ngay từ đầu. Vấn đề cốt lõi là: sinh viên có nhiều tài liệu nhưng khó biến tài liệu đó thành hiểu biết có thể áp dụng, đặc biệt khi làm sai câu hỏi hoặc bài tập.

---

## 4. Target users

Người dùng chính:

- Sinh viên đại học đang ôn thi cuối kỳ.
- Sinh viên học các môn có nhiều lý thuyết, công thức, mô hình và bài tập tính toán.
- Ví dụ: tài chính, kinh tế lượng, phân tích dữ liệu, quản trị rủi ro, time series, mô hình tài chính.

Người dùng phụ / stakeholder:

- Nhóm học tập muốn chia sẻ lời giải thích đáng tin cậy.
- Trợ giảng hoặc mentor muốn giảm số câu hỏi lặp lại.
- Giảng viên muốn sinh viên học đúng theo tài liệu/barem của môn học.

---

## 5. Current workflow

```text
CURRENT STATE

[1 Thu gom slide, giáo trình, đề cũ, bài tập mẫu]
→ [2 Đọc và tự gạch ý quan trọng]
→ [3 Tự lập đề cương / bảng công thức]
→ [4 Làm câu hỏi luyện tập]
→ [5 Gặp câu sai hoặc không hiểu]
→ [6 Tự dò lại slide/giáo trình để tìm kiến thức liên quan]
→ [7 Hỏi bạn bè, tìm trên mạng hoặc hỏi AI chung]
→ [8 Ghi chú lại nếu tìm được lời giải phù hợp]
```

### Bottleneck hiện tại

Bottleneck chính nằm ở bước 6 và 7.

Sinh viên thường không biết câu mình làm sai thuộc chương nào, công thức nào, điều kiện áp dụng nào. Khi tài liệu dài, việc tìm lại đúng slide/trang rất tốn thời gian. Nếu hỏi AI chung, câu trả lời có thể đúng về mặt tổng quát nhưng không sát với tài liệu, ký hiệu, cách trình bày hoặc yêu cầu của giảng viên.

---

## 6. Impact

| Tác động | Mô tả |
|---|---|
| Mất thời gian | Sinh viên dành nhiều giờ để tìm kiếm và đối chiếu tài liệu thay vì luyện tập thêm. |
| Học thiếu trọng tâm | Tài liệu dài khiến sinh viên khó biết phần nào quan trọng hơn. |
| Lỗi sai lặp lại | Sinh viên làm sai cùng một dạng nhưng không nhận ra pattern lỗi. |
| Rủi ro học sai | Nếu dùng nguồn ngoài hoặc AI chung không kiểm soát, sinh viên có thể học lời giải không sát tài liệu môn học. |
| Căng thẳng trước kỳ thi | Khối lượng tài liệu lớn làm sinh viên bị quá tải và dễ học vẹt. |

---

## 7. Proposed AI workflow

```text
FUTURE STATE — Workflow + RAG có kiểm soát

[1 Sinh viên chọn môn học và upload/chọn bộ tài liệu được phép sử dụng]
→ [2 Sinh viên nhập câu hỏi, bài làm sai hoặc nội dung chưa hiểu]
→ [3 Hệ thống kiểm tra input: không chứa dữ liệu nhạy cảm hoặc yêu cầu gian lận]
→ [4 Hệ thống truy xuất phần tài liệu liên quan bằng RAG]
→ [5 AI tạo lời giải thích: vì sao sai, kiến thức liên quan, cách làm đúng]
→ [6 AI trích nguồn từ slide/trang/tài liệu liên quan]
→ [7 Sinh viên đánh giá: đã hiểu / chưa hiểu]
→ [8 Nếu chưa hiểu hoặc AI không có nguồn → yêu cầu bổ sung tài liệu hoặc chuyển sang người thật]
```

### AI intervention point

AI không thay toàn bộ quá trình ôn thi. AI chỉ can thiệp vào đoạn có pain lớn nhất:

> Khi sinh viên làm sai hoặc không hiểu một câu hỏi, hệ thống giúp tìm kiến thức liên quan và giải thích dựa trên tài liệu môn học.

### Human boundary

Sinh viên vẫn phải tự học, tự luyện tập và tự quyết định có tin vào lời giải thích hay không. Nếu câu trả lời không có nguồn hoặc sinh viên vẫn chưa hiểu, cần hỏi người thật như bạn học, trợ giảng, mentor hoặc giảng viên.

---

## 8. Problem Statement v1

| Field | Nội dung |
|---|---|
| Actor | Sinh viên đại học đang ôn thi cuối kỳ, đặc biệt ở các môn có nhiều lý thuyết, công thức và bài tập tính toán. |
| Workflow | Sinh viên thu gom tài liệu, tự hệ thống hóa, làm câu hỏi luyện tập, gặp câu sai, rồi tự tìm lại trong slide/giáo trình hoặc hỏi bạn bè/AI chung. |
| Bottleneck | Bước tìm đúng phần kiến thức liên quan và hiểu vì sao mình sai mất nhiều thời gian, đặc biệt khi tài liệu dài và cách giải phải sát với môn học. |
| Impact | Sinh viên mất thời gian tổ chức thông tin, dễ học thiếu trọng tâm, lặp lại lỗi sai và có rủi ro học lời giải không sát tài liệu. |
| AI intervention point | Sau khi sinh viên nhập câu hỏi hoặc bài làm sai, hệ thống truy xuất tài liệu liên quan và tạo lời giải thích có trích nguồn. |
| Success metrics | Giảm thời gian tìm lời giải thích; tăng tỷ lệ câu trả lời có nguồn; tăng mức độ hiểu sau giải thích; giảm số lỗi sai lặp lại. |
| Boundary | Không thay giảng viên, không tự bịa kiến thức ngoài tài liệu, không tạo đề thi gian lận, không triển khai full Agent cá nhân hóa ngay từ đầu. |

---

## 9. Problem Statement hoàn chỉnh

Trong bối cảnh sinh viên đại học phải ôn thi với nhiều nguồn tài liệu như slide bài giảng, giáo trình, đề cũ được phép tham khảo, bài tập mẫu và ghi chú lớp học, nhiều sinh viên gặp khó khăn trong việc xác định phần kiến thức trọng tâm và hiểu vì sao mình làm sai khi luyện tập. Quy trình hiện tại thường gồm việc tự thu gom tài liệu, tự hệ thống hóa kiến thức, làm câu hỏi ôn tập, sau đó tự dò lại slide/giáo trình hoặc hỏi bạn bè khi gặp lỗi sai. Bottleneck chính nằm ở bước tìm đúng phần kiến thức liên quan và chuyển nó thành lời giải thích dễ hiểu, sát với cách dạy của môn học.

Nhóm đề xuất một trợ lý AI hỗ trợ ôn thi theo mô hình **Workflow + RAG có kiểm soát**. Hệ thống cho phép sinh viên nhập câu hỏi, bài làm sai hoặc nội dung chưa hiểu; sau đó truy xuất phần tài liệu liên quan trong bộ tài liệu môn học; tạo lời giải thích về lỗi sai, công thức/khái niệm liên quan và gợi ý phần cần ôn lại. Câu trả lời phải có trích dẫn nguồn từ tài liệu được cung cấp. Nếu hệ thống không tìm được nguồn phù hợp hoặc không đủ tự tin, hệ thống phải thông báo “chưa đủ thông tin” thay vì tự bịa.

Thành công của pilot được đo bằng thời gian sinh viên cần để nhận được lời giải thích cho một câu làm sai, tỷ lệ câu trả lời có trích nguồn, mức độ hài lòng/hiểu bài sau giải thích và tỷ lệ lỗi sai lặp lại giảm sau một số vòng luyện tập. Phạm vi pilot chỉ áp dụng cho một môn học hoặc một bộ tài liệu cụ thể, không thay thế giảng viên, không tạo full đề thi tự động, không xử lý các yêu cầu gian lận và chưa triển khai full Agent cá nhân hóa lộ trình học.

---

## 10. Success metrics

| Metric | Baseline hiện tại | Target cho pilot | Cách đo |
|---|---:|---:|---|
| Thời gian tìm lời giải thích cho một câu làm sai | 10–20 phút/câu | Dưới 2 phút/câu | Sinh viên tự bấm giờ trước/sau khi dùng workflow |
| Tỷ lệ câu trả lời có nguồn | Không ổn định | 90%+ câu quan trọng có nguồn | Kiểm tra câu trả lời có dẫn slide/trang/tài liệu liên quan |
| Mức độ hiểu sau giải thích | Chưa đo | Trung bình 4/5 trở lên | Khảo sát nhanh sau mỗi câu: “Bạn đã hiểu vì sao sai chưa?” |
| Tỷ lệ sinh viên phải hỏi người thật ngay sau câu trả lời AI | Cao nếu tự học | Giảm dần qua pilot | Ghi nhận số lần escalate |
| Tỷ lệ lỗi sai lặp lại cùng dạng | Chưa đo | Giảm sau 2–3 vòng luyện tập | So sánh kết quả luyện tập trước/sau |

---

## 11. Boundary

### Giải pháp sẽ làm

- Nhận câu hỏi hoặc bài làm sai từ sinh viên.
- Truy xuất tài liệu môn học được cung cấp.
- Giải thích vì sao sinh viên sai hoặc chưa hiểu đúng.
- Nêu công thức/khái niệm liên quan.
- Gợi ý phần cần ôn lại.
- Trích nguồn từ tài liệu.
- Từ chối hoặc yêu cầu bổ sung tài liệu nếu không đủ căn cứ.

### Giải pháp sẽ không làm

- Không thay thế giảng viên/trợ giảng.
- Không đảm bảo mọi lời giải đều đúng tuyệt đối.
- Không trả lời nếu không có căn cứ trong tài liệu.
- Không tự tạo số liệu hoặc công thức ngoài tài liệu.
- Không tạo đề thi gian lận hoặc hỗ trợ cheating trong kỳ thi.
- Không triển khai cá nhân hóa toàn bộ lộ trình học ở bản pilot đầu tiên.
- Không lưu thông tin cá nhân nhạy cảm nếu chưa có cơ chế bảo vệ dữ liệu.

---

## 12. Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro / hạn chế | Chọn? |
|---|---|---|---|---|
| No AI | Sinh viên tự học bằng slide, giáo trình, đề cũ và hỏi bạn bè | Đủ nếu tài liệu ngắn, câu hỏi đơn giản, sinh viên đã biết phần mình yếu | Không giải quyết tốt việc tìm đúng kiến thức liên quan trong tài liệu dài | Không chọn |
| Rule | Checklist chương, bảng công thức, keyword matching câu hỏi với chương | Hữu ích để phân loại sơ bộ hoặc kiểm tra định dạng | Không giải thích tốt lỗi sai phức tạp, không xử lý được nhiều cách diễn đạt tự nhiên | Dùng một phần |
| Workflow | Nhận câu hỏi → truy xuất tài liệu → AI giải thích → trích nguồn → sinh viên phản hồi | Phù hợp vì quy trình tuyến tính, có thể kiểm soát nguồn và có human boundary | Vẫn có rủi ro giải thích sai nếu tài liệu thiếu hoặc truy xuất sai | Chọn cho pilot |
| Agent | Tự lập kế hoạch ôn tập, nhớ lịch sử lỗi sai, gọi nhiều tool, tạo bài test, điều chỉnh lộ trình học | Hữu ích ở giai đoạn nâng cao khi có dữ liệu học tập và cơ chế đánh giá chất lượng | Scope rộng, cần state, nhiều tool, rủi ro hallucination và cá nhân hóa sai | Chưa chọn cho pilot |

### Mức chọn

```text
Workflow + RAG có kiểm soát.
```

### Vì sao không chọn full Agent ngay

Bài toán có tiềm năng phát triển thành Agent trong tương lai, vì hệ thống có thể cần ghi nhớ sinh viên yếu chương nào, tự tạo bài luyện tập và điều chỉnh lộ trình học. Tuy nhiên, ở giai đoạn pilot, việc chọn full Agent là quá rộng và khó kiểm soát. Mục tiêu đầu tiên nên là giải quyết bottleneck rõ nhất: giải thích lỗi sai dựa trên tài liệu môn học có trích nguồn.

---

## 13. Risk & controls

| Risk | Vì sao quan trọng | Control đề xuất |
|---|---|---|
| AI hallucination | Sinh viên có thể học sai và làm sai trong kỳ thi | Chỉ trả lời dựa trên tài liệu được cung cấp; bắt buộc trích nguồn; có chế độ “không đủ thông tin” |
| Truy xuất sai nguồn | Lời giải thích có thể dựa trên chương không liên quan | Hiển thị nguồn được dùng; cho sinh viên phản hồi “nguồn không đúng” |
| Giải thích không sát cách dạy của môn học | Mỗi môn có ký hiệu, cách trình bày và barem riêng | Ưu tiên tài liệu chính thức của môn; không dùng nguồn ngoài nếu không được phép |
| Sinh viên phụ thuộc quá mức | Sinh viên có thể chỉ đọc lời giải mà không tự học | Thiết kế câu trả lời theo hướng gợi mở, yêu cầu sinh viên thử lại câu tương tự |
| Dữ liệu cá nhân / bài làm riêng | Có thể chứa thông tin cá nhân hoặc điểm số | Không yêu cầu thông tin nhạy cảm; không lưu dữ liệu cá nhân ở pilot |
| Hỗ trợ gian lận | Sinh viên có thể dùng trong bài kiểm tra không được phép | Boundary rõ: chỉ dùng cho ôn tập; không hỗ trợ làm bài thi đang diễn ra |

---

## 14. Quick validation plan

Trong thời gian lab, nhóm chưa có điều kiện validation rộng, nên pilot cần kiểm tra nhanh với dữ liệu nhỏ.

| Hoạt động validation | Cách làm | Kết quả kỳ vọng |
|---|---|---|
| Kiểm tra với 1 môn học cụ thể | Chọn một bộ slide + 20 câu hỏi luyện tập có đáp án | Xem hệ thống có truy xuất đúng phần tài liệu không |
| Test với 3–5 sinh viên | Cho sinh viên nhập các câu làm sai và đánh giá lời giải thích | Đo mức độ hiểu và thời gian tiết kiệm |
| So sánh với tự học | Một nhóm tự dò tài liệu, một nhóm dùng workflow | So sánh thời gian tìm lời giải và độ hài lòng |
| Kiểm tra hallucination | Đưa câu hỏi ngoài phạm vi tài liệu | Hệ thống phải từ chối hoặc yêu cầu bổ sung tài liệu |

---

## 15. Final decision

```text
Go for limited pilot; Not Yet for full Agent.
```

### Pilot nhỏ nhất

- Chọn một môn học cụ thể.
- Dùng một bộ tài liệu đã xác định: slide, bài tập mẫu, đề cũ được phép tham khảo.
- Chọn 20–30 câu hỏi luyện tập có đáp án.
- Sinh viên nhập câu sai hoặc câu chưa hiểu.
- Hệ thống truy xuất tài liệu, giải thích và trích nguồn.
- Đo thời gian, độ hài lòng và số lỗi cần sửa.

### Điều kiện để Go rộng hơn

- Tỷ lệ câu trả lời có nguồn đạt mức chấp nhận được.
- Sinh viên đánh giá lời giải thích hữu ích.
- Hệ thống biết từ chối khi không có nguồn.
- Không phát hiện lỗi nghiêm trọng như bịa công thức hoặc trích sai tài liệu nhiều lần.

### Điều kiện rollback / dừng pilot

- Nếu AI thường xuyên bịa kiến thức hoặc giải thích sai.
- Nếu sinh viên phải hỏi người thật lại gần như mọi câu.
- Nếu hệ thống không truy xuất được đúng tài liệu liên quan.
- Nếu có rủi ro hỗ trợ gian lận hoặc dùng sai mục đích.

### Rationale

Quyết định Go for limited pilot hợp lý vì bài toán rõ, pain thật, workflow có thể kiểm soát và có metric đo được. Tuy nhiên, full Agent là Not Yet vì cần nhiều dữ liệu hơn về hành vi học tập, lịch sử lỗi sai, năng lực từng sinh viên và cơ chế kiểm định chất lượng trước khi cho hệ thống tự điều chỉnh lộ trình học.
