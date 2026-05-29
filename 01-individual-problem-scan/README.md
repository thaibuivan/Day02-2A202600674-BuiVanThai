# 01 — Individual Problem Scan

## 1. Scan rộng: 5+ vấn đề quan sát được

Mục tiêu của phần này là bắt đầu từ **vấn đề thật**, không bắt đầu từ một giải pháp như “xây chatbot” hoặc “xây Agent”. Tôi scan các vấn đề từ bối cảnh học lab AI, thao tác GitHub, làm bài nhóm, học tài liệu và một số tình huống hỗ trợ khách hàng.

| # | Lăng kính | Vấn đề quan sát được | Ai đang đau? | Dấu hiệu / evidence ban đầu | Mức AI phù hợp ban đầu |
|---|---|---|---|---|---|
| 1 | Tốn thời gian / bị kẹt khi làm lab | Học viên bị kẹt khi cài thư viện, thiết lập API key, chạy file template, xử lý TODO, đọc lỗi Python hoặc thao tác GitHub. | Học viên AI.20K, nhất là người mới dùng GitHub, VS Code, Colab hoặc Python local. | Trong quá trình làm lab, học viên thường cần hỏi lại nhiều bước nhỏ: clone repo, tạo file, tạo folder, set environment variable, đọc README, phân biệt file/folder/branch, hiểu lỗi Python. | Workflow |
| 2 | Tìm kiếm thông tin | Hướng dẫn làm bài nằm rải rác ở slide, README, worksheet, file mẫu và yêu cầu trên GitHub nên học viên khó tìm đúng phần cần đọc. | Học viên đang làm lab và nộp bài. | Thông tin có tồn tại nhưng phân tán ở nhiều nguồn, dẫn đến việc học viên hỏi lại những điều đã có trong tài liệu. | Workflow / RAG |
| 3 | Kiểm tra bài nộp | Học viên không chắc cấu trúc repo GitHub đã đúng yêu cầu chưa. | Học viên nộp bài lab Day 02. | Yêu cầu có các folder như `01-individual-problem-scan/`, `02-group-problem-statement/`, `03-individual-reflection/`; người mới dễ nhầm giữa branch, folder, file, commit và README. | Rule + Workflow |
| 4 | Định nghĩa bài toán mơ hồ | Nhóm dễ bắt đầu bằng câu “muốn xây chatbot” nhưng chưa rõ người dùng, pain point, workflow, metric và boundary. | Nhóm làm lab Day 02. | Nhiều ý tưởng AI ban đầu nghe hấp dẫn nhưng chưa có actor, bottleneck, dữ liệu, metric hoặc phạm vi cụ thể. | Workflow |
| 5 | Hỗ trợ khách hàng lặp lại | Shop online nhỏ phải trả lời lặp lại các câu hỏi về giao hàng, đổi trả, sản phẩm, tồn kho và trạng thái đơn. | Chủ shop hoặc nhân viên CSKH. | Câu hỏi lặp lại nhưng cách diễn đạt khác nhau, đôi khi có cảm xúc hoặc thiếu thông tin. | Rule / Workflow |
| 6 | Quá tải tài liệu học tập | Sinh viên có nhiều slide/PDF nhưng ít thời gian ôn thi nên khó xác định trọng tâm và tự luyện tập. | Sinh viên đại học trước kỳ thi. | Sinh viên thường cần tóm tắt, lọc trọng tâm, giải thích khái niệm và tạo câu hỏi luyện tập từ tài liệu dài. | Workflow |
| 7 | Kiểm tra chất lượng báo cáo | Người viết báo cáo không chắc bài đã có đủ mục, metric, boundary, citation hoặc logic ra quyết định chưa. | Sinh viên hoặc nhóm làm bài nộp. | Rubric có sẵn nhưng khi viết nhanh dễ bỏ sót tiêu chí chấm điểm. | Rule + Workflow |

## 2. Top 3 vấn đề được chọn

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Trợ lý AI hỗ trợ học viên xử lý lỗi và hoàn thành lab AI.20K | Actor rõ, workflow lặp lại, pain hiện rõ trong quá trình học, có thể pilot nhỏ bằng tài liệu khóa học, metric đo được bằng thời gian xử lý lỗi. | Cần kiểm chứng độ chính xác câu trả lời và xác định rõ assistant được phép dùng nguồn tài liệu nào. |
| 2 | Công cụ kiểm tra cấu trúc repo GitHub trước khi nộp | Rule rõ, dễ kiểm tra đúng/sai, rất hữu ích với người mới. | Có thể hơi hẹp nếu chỉ kiểm tra tên folder/file; phù hợp hơn nếu là một chức năng con của Problem #1. |
| 3 | Problem Statement Coach | Rất sát mục tiêu Day 02 vì giúp nhóm tránh ý tưởng AI mơ hồ. | Metric chất lượng khó đo hơn vì feedback về Problem Statement có phần chủ quan. |

Ứng viên được chọn để phát triển tiếp là **Problem #1: Trợ lý AI hỗ trợ học viên xử lý lỗi và hoàn thành lab AI.20K**, vì bài này bao trùm cả việc tìm hướng dẫn, kiểm tra GitHub, hiểu lỗi và định hướng bước tiếp theo.

---

# Problem Card #1 — Trợ lý AI hỗ trợ học viên xử lý lỗi và hoàn thành lab AI.20K

## Problem 1 câu

Học viên AI.20K thường mất nhiều thời gian trong lab vì không biết kết nối lỗi hiện tại của mình — GitHub, cài thư viện, API key, file template, TODO hoặc lỗi Python — với đúng hướng dẫn chính thức và bước xử lý tiếp theo.

## Actor

Học viên AI.20K ở trình độ mới bắt đầu hoặc trung bình, đang làm lab cá nhân hoặc bài nộp GitHub.

## Thời điểm / bối cảnh

Trong buổi lab hoặc khi tự làm bài ở nhà, đặc biệt ở các bước:

- clone hoặc tạo repo GitHub;
- tạo folder/file đúng yêu cầu;
- cài thư viện Python;
- set API key hoặc biến môi trường;
- chạy file `.py` hoặc notebook;
- đọc lỗi Python;
- hoàn thành phần TODO trong template;
- nộp bài lên GitHub.

## Current workflow

```text
1. Học viên đọc slide / README / worksheet / file mẫu.
2. Học viên thử làm theo hướng dẫn.
3. Gặp lỗi hoặc không hiểu bước tiếp theo.
4. Tự tìm trên slide, Google, hỏi bạn, hỏi mentor hoặc hỏi AI chung chung.
5. Nhận một gợi ý sửa lỗi.
6. Thử lại.
7. Nếu chưa được, quay lại bước 4.
```

## Bottleneck

Bottleneck nằm ở bước **xác định nguyên nhân lỗi và tìm đúng hướng dẫn phù hợp**. Học viên thường không biết lỗi đến từ:

- sai thư mục;
- thiếu thư viện;
- chưa set API key;
- chạy sai file;
- hiểu sai yêu cầu TODO;
- cấu trúc repo chưa đúng;
- hoặc lỗi Python bình thường.

## Impact

- Mất thời gian trong buổi lab.
- Dễ phụ thuộc quá nhiều vào mentor.
- Có thể sửa sai hướng vì chưa hiểu nguyên nhân lỗi.
- Chậm tiến độ làm bài và nộp GitHub.
- Mentor phải trả lời lặp lại các lỗi giống nhau.

## Success metric

| Metric | Baseline hiện tại | Target pilot |
|---|---:|---:|
| Thời gian trung bình để unblock một lỗi phổ biến | Cần đo trong pilot | Giảm ít nhất 40% |
| Tỷ lệ lỗi phổ biến được xử lý sau hướng dẫn đầu tiên | Cần đo trong pilot | Từ 60% trở lên |
| Số câu hỏi lặp lại mentor phải trả lời | Cần đo trong pilot | Giảm theo từng buổi lab |
| Tỷ lệ câu trả lời có dẫn nguồn tài liệu khóa học | Chưa có | 90%+ với câu hỏi có tài liệu hỗ trợ |
| Tỷ lệ câu trả lời phải chuyển mentor vì không chắc | Chưa có | Chuyển đúng các case ngoài phạm vi |

## Non-AI alternative

- FAQ cố định cho các lỗi thường gặp.
- Checklist nộp bài GitHub.
- Video hướng dẫn cài đặt.
- Template README chi tiết hơn.

Các phương án này hữu ích nhưng chưa đủ trong trường hợp học viên mô tả lỗi bằng ngôn ngữ tự nhiên, có nhiều biến thể hoặc không biết chính xác mình sai ở bước nào.

## AI hypothesis

AI có thể hỗ trợ bằng cách:

- phân loại lỗi theo nhóm;
- tìm đúng phần hướng dẫn trong tài liệu khóa học;
- giải thích lỗi bằng ngôn ngữ dễ hiểu;
- đưa ra từng bước sửa;
- nhắc học viên không gửi API key hoặc thông tin nhạy cảm;
- chuyển mentor nếu không đủ thông tin hoặc ngoài phạm vi.

## Boundary

Giải pháp **làm**:

- giải thích lỗi phổ biến;
- hướng dẫn thao tác từng bước;
- tìm thông tin trong tài liệu khóa học;
- kiểm tra logic cấu trúc repo ở mức mô tả;
- đề xuất câu hỏi cần hỏi mentor khi không chắc.

Giải pháp **không làm**:

- không tự chạy lệnh trên máy học viên;
- không tự sửa code/file;
- không tự commit hoặc push GitHub;
- không lưu API key;
- không trả lời nếu không có nguồn hoặc không đủ thông tin;
- không thay mentor đánh giá bài nộp cuối cùng.

## Quick gut

**Workflow**.

Lý do: workflow có các bước rõ ràng: nhận mô tả lỗi → kiểm tra thông tin nhạy cảm → phân loại lỗi → truy xuất hướng dẫn chính thức → sinh hướng dẫn → học viên thử → nếu không được thì chuyển mentor. Chưa cần Agent vì hệ thống không cần tự chạy lệnh, tự sửa file hoặc tự nộp bài.

## Draft current workflow

```text
CURRENT STATE

[1 Đọc tài liệu]
→ [2 Thử làm]
→ [3 Gặp lỗi]
→ [4 Tự tìm / hỏi bạn / hỏi mentor / hỏi AI chung]
→ [5 Thử sửa]
→ [6 Nếu chưa được thì lặp lại]
```

## Draft future workflow

```text
FUTURE STATE

[1 Học viên mô tả lỗi hoặc dán safe error message]
→ [2 Hệ thống kiểm tra không có API key/thông tin nhạy cảm]
→ [3 AI phân loại lỗi]
→ [4 AI truy xuất hướng dẫn chính thức]
→ [5 AI đưa hướng dẫn từng bước kèm nguồn]
→ [6 Học viên thử lại]
→ [7 Nếu không chắc hoặc chưa xử lý được → chuyển mentor]
```

---

# Problem Card #2 — Công cụ kiểm tra cấu trúc repo GitHub trước khi nộp

## Problem 1 câu

Học viên mới dùng GitHub dễ nộp sai cấu trúc repo vì nhầm giữa folder, file, branch, commit và README.

## Actor

Học viên AI.20K nộp bài lab qua GitHub.

## Bottleneck

Không chắc repo đã đúng cấu trúc yêu cầu hay chưa.

## Metric

- Tỷ lệ repo đúng cấu trúc ngay lần nộp đầu.
- Số lỗi folder/file sai tên.
- Số lần mentor phải nhắc sửa cấu trúc repo.

## Quick gut

**Rule + Workflow**.

Rule đủ cho kiểm tra tên folder/file, nhưng Workflow hữu ích nếu cần giải thích lỗi và hướng dẫn sửa.

## Vì sao chưa chọn làm #1

Bài này rất rõ nhưng phạm vi hơi hẹp. Nó phù hợp để trở thành một module trong Trợ lý AI hỗ trợ lab.

---

# Problem Card #3 — Problem Statement Coach

## Problem 1 câu

Nhóm làm lab dễ bắt đầu bằng một ý tưởng công nghệ như “xây chatbot” mà chưa xác định rõ user, pain point, workflow, metric và boundary.

## Actor

Nhóm học viên trong buổi lab Day 02.

## Bottleneck

Bottleneck nằm ở việc biến ý tưởng mơ hồ thành Problem Statement đủ rõ để ra quyết định Go / Not Yet / No-Go.

## Metric

- Số Problem Statement đạt đủ actor, workflow, bottleneck, impact, metric, boundary.
- Số lần phải sửa vì quá rộng hoặc quá mơ hồ.
- Điểm rubric phần Problem Statement.

## Quick gut

**Workflow**.

AI đóng vai trò phản biện theo checklist, không tự quyết định thay nhóm.

## Vì sao chưa chọn làm #1

Bài này sát nội dung Day 02 nhưng metric chất lượng khó đo hơn và có phần chủ quan. Problem #1 có workflow vận hành rõ hơn và dễ pilot hơn.
