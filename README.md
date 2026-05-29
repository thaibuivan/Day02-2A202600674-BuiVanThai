# Day02 — 2A202600674 — Bui Van Thai

## Tổng quan

Repo này là bài nộp Day 02 Lab với chủ đề **Tìm đúng bài toán cho AI**.

Mục tiêu của bài lab là không bắt đầu từ một giải pháp như “xây chatbot” hay “xây agent”, mà đi từ vấn đề thật:

```text
Vấn đề thật
→ Actor
→ Workflow hiện tại
→ Bottleneck
→ Metric
→ Boundary
→ Rule / Workflow / Agent
→ Go / Not Yet / No-Go
```

Bài nộp gồm ba phần chính:

1. Scan vấn đề cá nhân.
2. Problem Statement của nhóm.
3. Reflection cá nhân sau buổi lab.

---

## Cấu trúc repo

```text
Day02--2A202600674-BuiVanThai-/
├── README.md
├── 01-individual-problem-scan/
│   └── README.md
├── 02-group-problem-statement/
│   └── README.md
└── 03-individual-reflection/
    └── README.md
```

---

## Các phần bài nộp

### 1. Individual Problem Scan

Link: [01-individual-problem-scan](01-individual-problem-scan/README.md)

Phần này ghi lại quá trình scan các vấn đề cá nhân, chọn top problem cards và mô tả actor, workflow, bottleneck, metric, AI fit cho từng vấn đề.

---

### 2. Group Problem Statement

Link: [02-group-problem-statement](02-group-problem-statement/README.md)

Phần này tổng hợp các candidate problems của nhóm, chấm điểm và chọn một vấn đề để đi sâu.

Ba vấn đề được shortlist gồm:

1. Chỉnh sửa CV theo từng JD tuyển dụng.
2. Đọc, dịch và tổng hợp paper tiếng Anh.
3. Viết báo cáo tiến độ hàng tuần từ nhiều nguồn thông tin.

Vấn đề nhóm chọn để đi sâu là:

> **Viết báo cáo tiến độ hàng tuần từ nhiều nguồn thông tin.**

Nhóm chọn bài toán này vì actor rõ, workflow rõ, bottleneck cụ thể, impact đo được và phù hợp để triển khai trong phạm vi lab dưới dạng **Workflow**, không cần bắt đầu bằng một Agent hoàn chỉnh.

---

### 3. Individual Reflection

Link: [03-individual-reflection](03-individual-reflection/README.md)

Phần này ghi lại vai trò cá nhân của tôi trong quá trình làm lab, cách AI đã hỗ trợ, điểm AI chưa đủ, và bài học rút ra về việc xác định đúng bài toán trước khi chọn giải pháp AI.

---

## Final selected problem

**Problem:** Viết báo cáo tiến độ hàng tuần từ nhiều nguồn thông tin.

**Actor chính:** Người phụ trách báo cáo tiến độ, nhóm trưởng, PM hoặc leader.

**Bottleneck:** Thông tin tiến độ nằm rải rác ở nhiều nơi như chat, task board, checklist và ghi chú họp. Người phụ trách phải mất thời gian tổng hợp, lọc ý quan trọng và viết lại thành báo cáo có logic.

**AI level được chọn:** Workflow.

**Lý do không chọn Agent ngay:** Giai đoạn đầu chưa cần một agent tự động đi lấy dữ liệu, nhắc thành viên, theo dõi follow-up hoặc tự gửi báo cáo. AI chỉ nên hỗ trợ draft narrative từ dữ liệu đã được người dùng cung cấp hoặc chọn lọc.

**Decision:** Go với scope nhỏ.

---

## Boundary

Giải pháp đề xuất sẽ:

* Hỗ trợ gom và cấu trúc thông tin tiến độ.
* Hỗ trợ draft báo cáo theo format.
* Gợi ý các mục như done, in progress, blocked, risks và next actions.
* Để người phụ trách review trước khi gửi.

Giải pháp sẽ không:

* Không tự gửi báo cáo.
* Không tự đánh giá năng lực thành viên.
* Không tự bịa tiến độ nếu input thiếu.
* Không thay thế trách nhiệm của người phụ trách báo cáo.
* Không tích hợp phức tạp với nhiều công cụ trong giai đoạn pilot.

---

## Student

**Name:** Bui Van Thai
**Student ID:** 2A202600674
**Course:** AI.20K — Cohort 2
**Lab:** Day 02 — Finding the Right Problem for AI
