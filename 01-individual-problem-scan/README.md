# 01 — Individual Problem Scan

## 1. Scan rộng: 5+ vấn đề quan sát được

Mục tiêu của phần này là bắt đầu từ vấn đề thật trong học tập, làm việc nhóm, báo cáo, chăm sóc khách hàng và xử lý tài liệu. Tôi không bắt đầu bằng một giải pháp như “xây chatbot” hoặc “xây agent”, mà scan các tình huống có người dùng thật, quy trình thật và điểm nghẽn có thể quan sát được.

| # | Lăng kính | Vấn đề quan sát được | Ai đang đau? | Dấu hiệu / evidence ban đầu | Mức AI phù hợp ban đầu |
|---|---|---|---|---|---|
| 1 | Làm việc nhóm | Khi làm bài nhóm, các ý kiến thường nằm rải rác ở Zalo, Google Docs, file Word và lời nhắn miệng. Nhóm mất thời gian tổng hợp ai làm gì, bản nào là bản mới nhất và phần nào còn thiếu. | Sinh viên làm bài nhóm, nhóm trưởng. | Trong nhiều bài nhóm, nhóm phải hỏi lại nhau nhiều lần: “file cuối là file nào?”, “ai làm phần này?”, “còn thiếu mục nào?”. Việc tổng hợp thủ công dễ gây sót việc hoặc trùng việc. | Workflow |
| 2 | Tổng hợp thông tin | Khi viết báo cáo hoặc bài thuyết trình, người làm phải đọc nhiều nguồn như tài liệu, slide, bài báo, ghi chú nhóm rồi tự rút ý chính. Bước khó nhất không phải tìm tài liệu, mà là biến thông tin rời rạc thành một dàn ý có logic. | Sinh viên, người viết báo cáo, nhóm làm thuyết trình. | Nhiều người có đủ tài liệu nhưng vẫn mất nhiều thời gian để chọn ý nào nên đưa vào, ý nào bỏ, sắp xếp luận điểm thế nào cho mạch lạc. | Workflow |
| 3 | Kiểm tra biểu mẫu / yêu cầu nộp | Khi nộp hồ sơ, bài tập hoặc form đăng ký, người dùng dễ bị thiếu file, sai tên file, sai định dạng hoặc bỏ sót một yêu cầu nhỏ trong hướng dẫn. | Sinh viên nộp bài, người nộp hồ sơ, người đăng ký chương trình. | Yêu cầu thường dài và có nhiều chi tiết như tên file, cấu trúc folder, định dạng PDF/Word, deadline, thông tin bắt buộc. Người dùng thường chỉ phát hiện sai sau khi bị nhắc hoặc bị trả lại hồ sơ. | Rule + Workflow |
| 4 | Lọc và ưu tiên công việc | Khi có nhiều deadline cùng lúc, sinh viên thường không biết nên làm việc nào trước, việc nào quan trọng hơn, và mỗi việc cần bao nhiêu thời gian. | Sinh viên đại học, người tham gia nhiều khóa học/dự án cùng lúc. | Lịch học, deadline bài tập, bài nhóm, thi cử và hoạt động ngoại khóa thường chồng chéo. Người dùng hay xử lý theo cảm tính, dẫn đến sát deadline mới làm. | Workflow |
| 5 | Hỗ trợ khách hàng lặp lại | Shop online phải trả lời lặp lại các câu hỏi về giao hàng, đổi trả, sản phẩm, tồn kho và trạng thái đơn. Cùng một nội dung nhưng khách diễn đạt theo nhiều cách khác nhau. | Chủ shop hoặc nhân viên chăm sóc khách hàng. | Câu hỏi lặp lại nhưng cách diễn đạt khác nhau; đôi khi khách hỏi kèm cảm xúc khó chịu hoặc thông tin không đầy đủ. Nhân viên mất thời gian trả lời thủ công và dễ trả lời không nhất quán. | Rule / Workflow |
| 6 | Quá tải tài liệu học tập | Sinh viên có nhiều slide, PDF, ghi chú và đề cương ôn thi, nhưng khó xác định phần nào trọng tâm và khó hiểu vì sao mình làm sai khi luyện tập. | Sinh viên đại học trước kỳ thi. | Sinh viên thường cần tóm tắt, lọc trọng tâm, giải thích khái niệm, đối chiếu công thức và phân tích lỗi sai từ tài liệu dài. Nếu tự làm thủ công sẽ mất nhiều thời gian. | Workflow / RAG |
| 7 | Kiểm tra chất lượng báo cáo | Người viết báo cáo không chắc bài đã có đủ mục, metric, boundary, citation hoặc logic ra quyết định chưa. | Sinh viên hoặc nhóm làm bài nộp, người viết báo cáo. | Rubric có sẵn nhưng khi viết nhanh dễ bỏ sót tiêu chí chấm điểm. Người viết thường cần một checklist để rà lại trước khi nộp. | Rule + Workflow |

---

## 2. Top 3 vấn đề được chọn

Tôi chọn Top 3 dựa trên các tiêu chí: actor rõ, workflow rõ, bottleneck rõ, có thể đo impact, AI có vai trò cụ thể, và có thể đặt boundary để giảm rủi ro.

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Sinh viên quá tải tài liệu học tập và khó hiểu lỗi sai khi luyện tập | Đây là vấn đề gần với trải nghiệm thật của sinh viên, đặc biệt trước kỳ thi. Workflow rõ: thu gom tài liệu → hệ thống hóa → luyện đề → làm sai → tìm lại kiến thức liên quan. AI có thể hỗ trợ ở bước tìm đúng nguồn kiến thức và giải thích lỗi sai. | Cần xác định rõ phạm vi pilot: chỉ một môn học hay nhiều môn; tài liệu có đủ sạch không; lời giải thích thế nào được coi là đúng và sát với cách giảng viên dạy. |
| 2 | Kiểm tra chất lượng báo cáo/bài nộp theo rubric trước khi nộp | Vấn đề rõ, rủi ro thấp, dễ có checklist và rule. AI có thể hỗ trợ đọc rubric, rà bài, chỉ ra mục còn thiếu và gợi ý chỉnh sửa. | Có thể không cần AI mạnh nếu rubric đơn giản. Cần tránh để AI viết thay toàn bộ bài làm, vì mục tiêu là hỗ trợ kiểm tra chất lượng. |
| 3 | Hỗ trợ khách hàng lặp lại cho shop online | Có volume cao, câu hỏi lặp lại, dễ đo thời gian phản hồi và tỷ lệ xử lý tự động. Có thể so sánh rõ Rule / Workflow / Agent. | Cần có dữ liệu FAQ, chính sách bán hàng và giới hạn quyền trả lời. Một số tình huống nhạy cảm vẫn cần người thật xử lý. |

---

## 3. Problem Card #1 — Sinh viên quá tải tài liệu học tập và khó hiểu lỗi sai khi luyện tập

### Problem 1 câu

Sinh viên đại học mất nhiều thời gian để tự phân loại tài liệu, hệ thống hóa kiến thức và tìm lời giải thích cho những câu hỏi/bài tập làm sai trong giai đoạn ôn thi, dẫn đến việc ôn tập thiếu trọng tâm và kém hiệu quả.

### Actor

Sinh viên đại học đang ôn thi cuối kỳ, đặc biệt ở các môn có nhiều lý thuyết, công thức, mô hình hoặc bài tập tính toán như tài chính, kinh tế lượng, phân tích dữ liệu, quản trị rủi ro, time series.

### Thời điểm / bối cảnh

Giai đoạn 1–2 tuần trước kỳ thi, khi sinh viên phải xử lý nhiều loại tài liệu cùng lúc: slide bài giảng, giáo trình, đề cũ được phép tham khảo, bài tập mẫu, ghi chú trên lớp và câu hỏi ôn tập.

### Current workflow

```text
1. Thu gom slide, giáo trình, đề cũ, bài tập mẫu và ghi chú
2. Đọc tài liệu và tự gạch chân các khái niệm/công thức quan trọng
3. Tự lập đề cương hoặc bảng công thức
4. Làm câu hỏi luyện tập hoặc đề ôn thi
5. Gặp câu sai hoặc không hiểu cách làm
6. Tự dò lại slide/giáo trình để tìm phần kiến thức liên quan
7. Hỏi bạn bè, tìm trên mạng hoặc hỏi AI chung
8. Ghi chú lại cách làm đúng nếu tìm được lời giải thích phù hợp
```

### Bottleneck

Bottleneck chính nằm ở bước 6 và 7. Khi làm sai một câu hỏi, sinh viên thường không biết lỗi nằm ở đâu: sai công thức, hiểu sai khái niệm, nhầm điều kiện áp dụng, hay tính toán sai. Việc đối chiếu qua lại giữa câu hỏi, slide, giáo trình và đáp án mẫu tiêu tốn nhiều thời gian. Nếu hỏi AI chung, sinh viên có thể nhận được lời giải không sát với tài liệu môn học hoặc cách giảng viên yêu cầu.

### Impact

- Sinh viên tốn nhiều thời gian để tổ chức và tìm kiếm thông tin thay vì thực sự luyện tập.
- Dễ học vẹt công thức mà không hiểu điều kiện áp dụng.
- Dễ bỏ sót phần trọng tâm vì tài liệu quá dài.
- Lỗi sai lặp lại nhưng không được phân tích thành pattern rõ ràng.
- Kết quả ôn tập có thể không phản ánh đúng nỗ lực bỏ ra.

### Success metric

| Metric | Trước | Mục tiêu pilot |
|---|---:|---:|
| Thời gian tìm lời giải thích cho một câu làm sai | 10–20 phút/câu | Dưới 2 phút/câu |
| Thời gian lập đề cương trọng tâm từ tài liệu | Vài giờ đến vài ngày | Giảm ít nhất 50% |
| Tỷ lệ câu trả lời có trích nguồn từ tài liệu môn học | Không ổn định | 90%+ câu trả lời quan trọng có nguồn |
| Tỷ lệ sinh viên hiểu được vì sao mình sai sau giải thích | Chưa đo | Đạt 4/5 điểm hài lòng trở lên trong khảo sát nhỏ |
| Tỷ lệ câu AI phải từ chối do thiếu nguồn | Chưa có | Được ghi nhận thay vì AI tự bịa |

### Non-AI alternative

- Giảng viên cung cấp đề cương ôn tập chi tiết hơn.
- Sinh viên tự lập bảng công thức và bảng lỗi sai.
- Nhóm học tập phân công mỗi người tóm tắt một chương.
- Tạo checklist chương/mục/công thức cần ôn.

Các phương án này có thể hữu ích nhưng vẫn phụ thuộc nhiều vào công sức thủ công và không hỗ trợ tốt khi sinh viên gặp một câu hỏi cụ thể cần giải thích ngay.

### AI hypothesis

AI có thể hỗ trợ bằng cách nhận câu hỏi sinh viên làm sai, tìm phần kiến thức liên quan trong tài liệu môn học, giải thích vì sao đáp án đúng/sai, chỉ ra lỗi tư duy hoặc lỗi công thức, và gợi ý phần cần ôn lại. Tuy nhiên, AI phải trả lời dựa trên tài liệu được cung cấp và phải trích dẫn nguồn.

### Boundary

Giải pháp sẽ:

- Hỗ trợ giải thích lỗi sai dựa trên tài liệu môn học được cung cấp.
- Tóm tắt khái niệm/công thức liên quan đến câu hỏi.
- Chỉ ra phần kiến thức sinh viên nên ôn lại.
- Trích dẫn slide/trang/tài liệu nếu có nguồn.

Giải pháp sẽ không:

- Không cam kết thay thế giảng viên hoặc trợ giảng.
- Không tự tạo kiến thức ngoài tài liệu nếu không có nguồn.
- Không xử lý mọi môn học ngay từ đầu.
- Không tạo full đề thi tự động ở bản pilot đầu tiên.
- Không lưu dữ liệu cá nhân nhạy cảm của sinh viên nếu chưa có cơ chế bảo vệ dữ liệu.

### Quick gut

**Workflow + RAG có kiểm soát.** Có thể phát triển thành Agent trong tương lai, nhưng pilot nên bắt đầu từ workflow rõ: nhận câu hỏi → truy xuất nguồn → giải thích → sinh viên phản hồi.

### Draft current workflow

```text
CURRENT STATE

[1 Thu gom tài liệu]
→ [2 Tự đọc và gạch ý]
→ [3 Làm câu hỏi luyện tập]
→ [4 Làm sai / không hiểu]
→ [5 Tự tìm lại trong slide/giáo trình]
→ [6 Hỏi bạn bè hoặc AI chung]
→ [7 Ghi chú nếu hiểu]
```

### Draft future workflow

```text
FUTURE STATE

[1 Sinh viên upload/chọn tài liệu môn học]
→ [2 Sinh viên nhập câu hỏi hoặc câu làm sai]
→ [3 Hệ thống truy xuất phần tài liệu liên quan]
→ [4 AI giải thích lỗi sai + công thức/khái niệm liên quan]
→ [5 AI trích nguồn và gợi ý phần cần ôn lại]
→ [6 Sinh viên đánh giá đã hiểu/chưa hiểu]
→ [7 Nếu chưa rõ hoặc thiếu nguồn → chuyển sang hỏi người thật / bổ sung tài liệu]
```

---

## 4. Problem Card #2 — Kiểm tra chất lượng báo cáo/bài nộp theo rubric trước khi nộp

### Problem 1 câu

Sinh viên hoặc nhóm làm bài nộp thường không chắc bài đã đáp ứng đủ rubric chưa, dẫn đến việc bỏ sót tiêu chí như metric, boundary, workflow, citation hoặc logic ra quyết định.

### Actor

Sinh viên làm bài lab, nhóm làm báo cáo, người viết bài nộp có rubric rõ ràng.

### Current workflow

```text
1. Đọc đề bài và rubric
2. Viết bài theo hiểu biết của nhóm
3. Tự rà lại bằng mắt thường
4. Nộp bài
5. Sau đó mới phát hiện thiếu mục hoặc bị trừ điểm
```

### Bottleneck

Rubric thường có nhiều tiêu chí nhỏ. Khi viết bài nhanh, người làm dễ tập trung vào nội dung chính mà quên kiểm tra đầy đủ các tiêu chí chấm điểm.

### Impact

- Bài có thể đúng ý tưởng nhưng thiếu thành phần cần chấm điểm.
- Nhóm mất điểm vì lỗi trình bày hoặc thiếu mục, không phải vì thiếu năng lực.
- Người làm bài không có vòng kiểm tra chất lượng trước khi nộp.

### Success metric

- Giảm số tiêu chí rubric bị bỏ sót.
- Tỷ lệ bài nộp có đầy đủ các mục bắt buộc tăng lên.
- Thời gian tự kiểm tra bài giảm xuống dưới 10 phút.

### Non-AI alternative

Dùng checklist thủ công theo rubric. Cách này rẻ và hiệu quả nếu rubric đơn giản.

### AI hypothesis

AI có thể đọc rubric và bài nộp, sau đó tạo bảng kiểm tra: mục nào đã có, mục nào thiếu, mục nào còn mơ hồ. AI không viết thay toàn bộ bài, chỉ giúp review và gợi ý chỉnh sửa.

### Boundary

- Không để AI tự viết toàn bộ bài nộp.
- Không thay thế đánh giá của giảng viên.
- Chỉ kiểm tra theo rubric được cung cấp.

### Quick gut

**Rule + Workflow.** Rule phù hợp để kiểm tra các mục bắt buộc; AI hỗ trợ nhận xét phần nội dung mơ hồ.

### Vì sao không chọn làm #1

Vấn đề này an toàn và dễ triển khai, nhưng scope hơi nhỏ. Trong khi đó, bài toán ôn thi có pain lớn hơn, nhiều bước hơn và thể hiện rõ hơn việc lựa chọn giữa Rule / Workflow / Agent.

---

## 5. Problem Card #3 — Hỗ trợ khách hàng lặp lại cho shop online

### Problem 1 câu

Shop online mất nhiều thời gian trả lời các câu hỏi lặp lại về sản phẩm, giao hàng, đổi trả và trạng thái đơn, trong khi khách hàng diễn đạt cùng một nhu cầu theo nhiều cách khác nhau.

### Actor

Chủ shop online, nhân viên chăm sóc khách hàng, khách hàng mua hàng online.

### Current workflow

```text
1. Khách nhắn tin hỏi thông tin
2. Nhân viên đọc tin nhắn
3. Nhân viên tìm thông tin sản phẩm/chính sách
4. Nhân viên trả lời thủ công
5. Nếu khách hỏi tiếp, nhân viên lặp lại quy trình
6. Nếu vấn đề khó, nhân viên chuyển cho chủ shop xử lý
```

### Bottleneck

Các câu hỏi đơn giản nhưng lặp lại nhiều lần. Tuy nhiên, khách diễn đạt khác nhau, có thể thiếu thông tin hoặc có cảm xúc tiêu cực, nên không thể chỉ dùng một bảng FAQ cứng trong mọi trường hợp.

### Impact

- Nhân viên tốn nhiều thời gian cho câu hỏi lặp lại.
- Khách phải chờ lâu, dễ giảm trải nghiệm mua hàng.
- Câu trả lời không nhất quán giữa các nhân viên.
- Chủ shop khó mở rộng chăm sóc khách hàng khi volume tăng.

### Success metric

- Giảm thời gian phản hồi trung bình.
- Tăng tỷ lệ câu hỏi đơn giản được xử lý tự động.
- Giảm số tin nhắn cần nhân viên can thiệp.
- Không tăng tỷ lệ phản hồi sai chính sách.

### Non-AI alternative

Tạo FAQ, mẫu tin nhắn trả lời nhanh, chatbot rule-based theo keyword.

### AI hypothesis

AI có thể phân loại ý định của khách, tìm câu trả lời phù hợp trong chính sách/shop database, tạo phản hồi tự nhiên và chuyển người thật khi khách tức giận hoặc vấn đề vượt quyền.

### Boundary

- Không tự cam kết hoàn tiền/đổi trả nếu ngoài chính sách.
- Không tự thay đổi đơn hàng.
- Không trả lời nếu thiếu dữ liệu sản phẩm hoặc trạng thái đơn.
- Các trường hợp khiếu nại nghiêm trọng phải chuyển cho người thật.

### Quick gut

**Rule / Workflow.** Rule đủ cho FAQ cố định; workflow phù hợp hơn khi cần phân loại ý định, truy xuất thông tin và chuyển người thật.

### Vì sao không chọn làm #1

Bài toán thực tế và dễ hiểu, nhưng khá phổ biến. Trong bối cảnh bài lab và trải nghiệm cá nhân, bài toán ôn thi gần với người học hơn và có nhiều điểm để phân tích sâu về RAG, workflow, boundary và risk.
