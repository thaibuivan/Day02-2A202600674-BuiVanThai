# Workflow Before / After

## Current workflow — Trước khi có AI

```text
[1 Thu gom tài liệu]
    ↓
[2 Đọc slide/giáo trình và tự gạch ý]
    ↓
[3 Tự lập đề cương hoặc bảng công thức]
    ↓
[4 Làm câu hỏi luyện tập]
    ↓
[5 Gặp câu sai hoặc không hiểu]
    ↓
[6 Tự tìm lại trong slide/giáo trình]
    ↓
[7 Hỏi bạn bè / tìm mạng / hỏi AI chung]
    ↓
[8 Ghi chú lại nếu hiểu]
```

### Pain points trong workflow hiện tại

- Tài liệu dài và phân tán.
- Sinh viên khó biết câu sai liên quan đến chương/công thức nào.
- Hỏi AI chung có thể không sát với tài liệu môn học.
- Lỗi sai không được phân tích thành pattern để ôn lại.

---

## Future workflow — Sau khi có AI Workflow + RAG

```text
[1 Sinh viên chọn môn học và tài liệu]
    ↓
[2 Sinh viên nhập câu hỏi / câu làm sai / nội dung chưa hiểu]
    ↓
[3 Hệ thống kiểm tra input và phạm vi]
    ↓
[4 RAG truy xuất phần tài liệu liên quan]
    ↓
[5 AI giải thích lỗi sai + kiến thức liên quan]
    ↓
[6 AI trích dẫn nguồn]
    ↓
[7 Sinh viên đánh giá: đã hiểu / chưa hiểu]
    ↓
[8 Nếu chưa hiểu hoặc thiếu nguồn → bổ sung tài liệu / hỏi người thật]
```

### AI nằm ở đâu?

AI nằm ở các bước:

- Truy xuất phần tài liệu liên quan.
- Giải thích lỗi sai bằng ngôn ngữ dễ hiểu.
- Gợi ý phần kiến thức cần ôn lại.
- Tạo câu trả lời có trích nguồn.

### Con người kiểm soát ở đâu?

- Sinh viên chọn tài liệu môn học.
- Sinh viên kiểm tra câu trả lời có giúp hiểu không.
- Nếu câu trả lời thiếu nguồn hoặc chưa rõ, sinh viên phải hỏi người thật.
- Giảng viên/trợ giảng vẫn là người xác nhận cuối cùng nếu có tranh cãi về đáp án.

---

## Before/After impact

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Thời gian tìm lời giải thích | 10–20 phút/câu | Dưới 2 phút/câu | Target chính của pilot |
| Số nguồn phải tự dò | Nhiều file | 1–3 đoạn liên quan được truy xuất | Giảm search effort |
| Rủi ro học sai từ nguồn ngoài | Cao | Giảm nếu có trích nguồn | Phụ thuộc chất lượng RAG |
| Vai trò người thật | Hỏi khi bí | Hỏi khi AI thiếu nguồn/chưa rõ | Human boundary vẫn cần |
