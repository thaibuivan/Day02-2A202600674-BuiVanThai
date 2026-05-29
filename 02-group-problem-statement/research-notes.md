# Research Notes

## 1. Câu hỏi cần validate

| Câu hỏi | Mục đích | Cách kiểm chứng đề xuất |
|---|---|---|
| Sinh viên mất bao lâu để tìm lời giải thích cho một câu làm sai? | Xác định baseline thời gian | Ghi thời gian khi sinh viên tự làm 10-20 câu luyện tập. |
| Sinh viên có tin lời giải thích nếu AI không trích nguồn không? | Kiểm tra vai trò của citation | So sánh hai phiên bản: có nguồn và không nguồn. |
| Tài liệu môn học có đủ để trả lời câu hỏi luyện tập không? | Kiểm tra khả năng RAG | Map 30-50 câu hỏi với slide/trang tương ứng. |
| Những câu nào cần người thật review? | Thiết kế HITL | Gắn cờ các câu thiếu nguồn, câu tính toán phức tạp, hoặc sinh viên bấm chưa hiểu. |
| Có nên tạo đề thi thử ngay không? | Tránh scope creep | Pilot trước với giải thích lỗi sai, chưa tạo đề thi chính thức. |

---

## 2. Assumptions trong pilot

- Pilot dùng tài liệu được phép sử dụng: slide, giáo trình, bài tập mẫu hoặc đề ôn tập hợp lệ.
- Pilot chỉ tập trung vào một môn học cụ thể để tránh scope quá rộng.
- Câu hỏi luyện tập có đáp án hoặc ít nhất có tài liệu nguồn để đối chiếu.
- AI không tự dự đoán đề thi và không sử dụng tài liệu không rõ nguồn.
- Thành công không chỉ là trả lời nhanh, mà phải trả lời có căn cứ và dễ hiểu.

---

## 3. Risks cần theo dõi

| Risk | Dấu hiệu | Cách xử lý |
|---|---|---|
| AI trả lời không có nguồn | Không citation hoặc citation sai | Bắt buộc hiển thị nguồn; nếu không có nguồn thì không trả lời chắc chắn. |
| AI giải thích đúng chung chung nhưng không sát môn | Câu trả lời không khớp slide/cách giảng | Ưu tiên RAG từ tài liệu môn học thay vì knowledge chung. |
| Sinh viên phụ thuộc vào AI | Chỉ copy lời giải mà không học | Thiết kế câu trả lời theo kiểu giải thích từng bước và hỏi lại người học. |
| Tool tính toán sai | Bài tài chính/thống kê có kết quả số sai | Với bài tính phức tạp, bổ sung calculator/Python tool hoặc chuyển review. |
| Dữ liệu đầu vào lộn xộn | Slide scan mờ, file thiếu chương, câu hỏi không rõ | Chuẩn hóa tài liệu và yêu cầu người dùng mô tả rõ câu hỏi. |

---

## 4. Ghi chú về hướng Agent

Bài toán có thể phát triển thành Agent khi hệ thống cần:

- ghi nhớ lịch sử học tập của từng sinh viên;
- phát hiện sinh viên yếu chương nào;
- tự chọn bài luyện tập tiếp theo;
- gọi nhiều công cụ như RAG, calculator, quiz generator;
- điều chỉnh lộ trình học theo tiến độ.

Tuy nhiên, giai đoạn đầu chưa chọn full Agent vì:

- chưa có dữ liệu lịch sử học tập;
- rủi ro hallucination trong giáo dục cao;
- cần kiểm soát nguồn và chất lượng trước;
- workflow giải thích lỗi sai đã đủ rõ để pilot.
