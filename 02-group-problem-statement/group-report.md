# Group Report — Day 02

**Candidate problem được chọn:** Aggregator & Centralized Deadline Tracker

**Mức giải pháp:** Workflow — Rule để đồng bộ/lọc dữ liệu, AI để trích xuất thông tin phi cấu trúc, người dùng xác nhận trước khi ghi

**Quyết định:** Go với pilot nhỏ; Not Yet đối với Agent tự trị và tích hợp toàn bộ nền tảng

> Bản này là group asset dùng chung của nhóm. Baseline thời gian hiện tại chủ yếu đến từ self-report và ước tính ban đầu; nhóm không coi các con số này là kết quả đã được kiểm chứng cho đến khi hoàn thành time-log và pilot. Micro survey chỉ được sử dụng như tín hiệu validation ban đầu, không đại diện cho toàn bộ sinh viên.

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|---:|---|---|---|
| 1 | Trần Nguyễn Mỹ Anh | 2A202601019 | Điều phối, chuẩn hóa Problem Statement và boundary |
| 2 | Lương Quốc Khánh | 2A202601713 | Problem owner, baseline, metric và kế hoạch validation |
| 3 | Hoàng Đức Anh | 2A202601223 | Workflow trước/sau và đánh giá khả thi kỹ thuật |
| 4 | Nguyễn Thu Huyền | 2A202601027 | Research phương án thay thế, risk và human review |
| 5 | Lý Thành Đạt | 2A202601469 | Điều phối, chuẩn hóa Problem Statement và boundary |
| 6 | Nguyễn Tiến Dũng | 2A202601707 | Problem owner, baseline, metric và kế hoạch validation |
| 7 | Lý Minh Hải | 2A202601503 | Workflow trước/sau và đánh giá khả thi kỹ thuật |
| 8 | Bùi Văn Khởi | 2A202601723 | Research phương án thay thế, risk và human review |
| 9 | Nguyễn Hoàng Khôi | 2A202601383 | Điều phối, chuẩn hóa Problem Statement và boundary |
| 10 | Lê Văn Huy | 2A202601235 | Problem owner, baseline, metric và kế hoạch validation |
| 11 | Nguyễn Minh Hoàng | 2A202601651 | Workflow trước/sau và đánh giá khả thi kỹ thuật |
| 12 | Hoàng Quang Minh | 2A202601301 | Research phương án thay thế, risk và human review |
| 13 | Nguyễn Công Hùng | 2A202601071 | Điều phối, chuẩn hóa Problem Statement và boundary |
| 14 | Ngô Hữu Nghĩa | 2A202601924 | Problem owner, baseline, metric và kế hoạch validation |
| 15 | Nguyễn Hữu Nhật Minh | 2A202601551 | Workflow trước/sau và đánh giá khả thi kỹ thuật |

---

## 1. Group convergence

### 1.1. Đầu vào từ bốn bài cá nhân

Mỗi thành viên trong nhóm phân tích đưa ba Problem Cards vào vòng hội tụ, tổng cộng 12 candidates.

| Thành viên | Candidate 1 | Candidate 2 | Candidate 3 |
|---|---|---|---|
| Trần Nguyễn Mỹ Anh | BEV Vision Debugging Tool | Triage failure case theo metric | Calibration Alignment Check |
| Lương Quốc Khánh | Sàng lọc paper nghiên cứu | Theo dõi thí nghiệm AI | Theo dõi task và deadline đa nền tảng |
| Hoàng Đức Anh | Daily Standup Reminder & Auto-Drafting | Tóm tắt yêu cầu Lab/Assignment | Aggregator & Centralized Deadline Tracker |
| Nguyễn Thu Huyền | Khảo sát và tổng hợp paper | Sàng lọc dataset lớn | Nhắc lịch daily và lịch họp định kỳ |

### 1.2. Gom cụm vấn đề

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Task, deadline và follow-up | Deadline Tracker, Daily Standup Reminder, lịch họp định kỳ | Thông tin hành động nằm rải rác; người dùng phải nhớ, kiểm tra và nhập lại |
| Research discovery và synthesis | Sàng lọc paper, Literature Review, sàng lọc dataset | Tìm, đọc và chuẩn hóa lượng lớn thông tin trước khi ra quyết định |
| Experiment và debugging | BEV Debugging, failure-case triage, calibration check, experiment tracking | Log, metric và artifact kỹ thuật nằm ở nhiều nơi, khó truy vết |
| Learning và document processing | Tóm tắt lab/assignment, meeting notes | Đọc tài liệu dài rồi chuyển thành checklist hoặc nội dung hành động |

### 1.3. Nhật ký pitch và challenge

| Candidate | Tín hiệu ủng hộ từ bài cá nhân | Challenge chính | Kết luận sau challenge |
|---|---|---|---|
| Aggregator & Centralized Deadline Tracker | Hai thành viên độc lập mô tả trực tiếp cùng pain; một thành viên có pain gần kề về daily và lịch họp; tần suất hằng ngày; baseline ước tính 15–30 phút/ngày | Vấn đề do thông tin phân tán hay do chưa có quy trình quản lý thống nhất? API và quyền riêng tư có làm scope quá lớn không? | Giữ candidate nhưng thu hẹp MVP còn hai nguồn, read-only mặc định và bắt buộc xác nhận |
| Sàng lọc/Literature Review paper | Hai thành viên gặp pain; tác động thời gian lớn | Chất lượng shortlist, hallucination và citation được đo thế nào? | Có giá trị nhưng quality metric khó xác nhận hơn trong pilot ngắn |
| Daily Standup Reminder | Workflow rõ, lặp lại hằng ngày, dễ làm pilot | Reminder cố định và template có đủ không; có thật sự cần AI không? | Phần lớn pain reminder có thể giải bằng Rule; xem đây là một use case con của task tracker |
| BEV Vision Debugging | Bottleneck và safety boundary rõ | Baseline 90–120 phút là ước lượng; domain hẹp và cần dữ liệu/công cụ chuyên biệt | Giữ cho bài toán chuyên ngành khác; không chọn làm bài chung |

### 1.4. Shortlist và score

Thang điểm cho mỗi tiêu chí: 1–5. Điểm “Pain có evidence” phản ánh bằng chứng hiện có trong bốn repository và micro survey, không coi ước lượng cá nhân là khảo sát diện rộng.

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm pilot nhỏ | So sánh R/W/A | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Aggregator & Centralized Deadline Tracker | 5 | 5 | 4 | 5 | 4 | 5 | 5 | **33** |
| Sàng lọc/Literature Review paper | 5 | 5 | 4 | 4 | 4 | 4 | 5 | **31** |
| Daily Standup Reminder | 5 | 5 | 4 | 4 | 5 | 4 | 4 | **31** |
| BEV Vision Debugging | 5 | 5 | 3 | 4 | 3 | 5 | 4 | **29** |

Nhóm chọn: **Aggregator & Centralized Deadline Tracker**.

Vì sao chọn:

- Hai thành viên độc lập ghi nhận trực tiếp cùng một pain trên các tập nền tảng khác nhau; một thành viên ghi nhận pain gần kề về daily và lịch họp.
- Workflow lặp lại hằng ngày, bottleneck và điểm can thiệp cụ thể.
- Có baseline ban đầu về thời gian và số lượt kiểm tra lại.
- Micro survey cho thấy pain về đa nền tảng, bỏ sót thông tin và tìm lại context xuất hiện ở phần lớn mẫu khảo sát.
- Có thể tách rõ phần Rule, phần AI và phần người dùng phải quyết định.
- Có thể kiểm chứng bằng pilot read-only trước khi xin quyền ghi hoặc tích hợp sâu.

Vì sao chưa chọn các candidate khác:

- **Literature Review:** impact lớn nhưng khó đánh giá chất lượng shortlist và độ đúng của tổng hợp trong thời gian ngắn.
- **Daily Standup Reminder:** phần reminder có thể giải đủ tốt bằng lịch cố định và template; phạm vi pain hẹp hơn.
- **BEV Vision Debugging:** phù hợp một nhóm chuyên môn hẹp, cần dữ liệu đa cảm biến và môi trường đánh giá riêng.

Nếu có disagreement, nhóm xử lý bằng cách ưu tiên candidate có actor chung, workflow thật, baseline có thể đo và pilot nhỏ; không chọn theo mức độ “ngầu” của giải pháp AI.

---

## 2. Quick validation

### 2.1. Bằng chứng hiện có

| Nguồn | Mẫu | Tín hiệu xác nhận | Tín hiệu phản bác/chưa chắc | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Bốn individual reports | 4 thành viên | 2/4 mô tả trực tiếp việc tổng hợp task/deadline đa nền tảng; 1/4 có pain gần kề về daily và lịch họp | Không phải tất cả thành viên đều gặp cùng mức độ pain | Actor của pilot là sinh viên/researcher tham gia nhiều khóa học hoặc dự án, không khái quát cho mọi sinh viên |
| Hai Problem Cards trực tiếp | 2 workflows | Baseline ước tính 15–30 phút/ngày; 3–5 lượt kiểm tra/ngày; nguồn gồm LMS, Calendar, Slack/Discord, Notion, Gmail và GitHub | Các số liệu là self-estimate, chưa có time-log; “sót deadline” chưa ghi rõ trong cửa sổ thời gian nào | Ghi baseline là giả thuyết; bắt buộc đo lại trước pilot |
| Micro survey | 20 phản hồi | 65% phải kiểm tra nhiều nền tảng; 65% dễ bỏ sót task/deadline; 80% khó tìm lại nội dung cũ; 60% khó xác định ưu tiên | Convenience sample, câu hỏi dạng checkbox, chưa đo tần suất và mức độ nghiêm trọng | Giữ survey như tín hiệu ban đầu; không suy rộng cho toàn bộ sinh viên; bổ sung time-log và interview ở bước sau |
| Challenge trong bài của Quốc Khánh | 1 challenge chính | Pain nằm ở việc nối mẩu thông tin thành task có action, deadline và context | Có thể nguyên nhân chính là thiếu một quy trình cá nhân thống nhất, không phải thiếu AI | Pilot phải so sánh với No AI: một task manager và khung giờ review cố định |
| Ghi chú metric trong bài của Mỹ Anh | Review chéo | Nhấn mạnh cần log thực nghiệm trước khi cam kết metric | Không được dùng ước lượng làm kết quả đã kiểm chứng | Thêm giai đoạn baseline 7 ngày, audit lỗi và assumption log |

### 2.2. Kết quả micro survey

Nhóm thực hiện khảo sát nhanh với 20 người về các khó khăn khi theo dõi công việc và học tập trên nhiều nền tảng. Báo cáo chỉ sử dụng số liệu tổng hợp và không công khai danh tính người trả lời.

| Nội dung khảo sát | Đồng ý | Tỷ lệ |
|---|---:|---:|
| Thường xuyên phải kiểm tra nhiều nền tảng để theo dõi công việc hoặc việc học | 13/20 | **65%** |
| Dễ bỏ sót thông báo, nhiệm vụ hoặc deadline do thông tin phân tán | 13/20 | **65%** |
| Mất nhiều thời gian tìm lại nội dung, quyết định hoặc tài liệu đã trao đổi | 16/20 | **80%** |
| Phải sao chép hoặc cập nhật cùng một thông tin trên nhiều nền tảng | 11/20 | **55%** |
| Việc chuyển đổi giữa các nền tảng gây khó khăn khi xác định ưu tiên tiếp theo | 12/20 | **60%** |

Tổng hợp theo người trả lời:

- **18/20 người (90%)** gặp ít nhất một trong năm vấn đề.
- **13/20 người (65%)** đồng ý với ít nhất ba vấn đề.
- **8/20 người (40%)** đồng ý với toàn bộ năm vấn đề.
- Trung bình mỗi người chọn **3,25/5 pain points**.

### 2.3. Insight sau validation

```text
Pain cốt lõi không phải “thiếu một chatbot quản lý lịch”.
Pain là việc người dùng phải biến các mẩu thông tin phân tán thành một task
có hành động, deadline, ngữ cảnh và nguồn gốc rõ ràng.
```

Các insight chính:

1. **Pain về context mạnh hơn pain về copy dữ liệu.** Khó tìm lại nội dung, quyết định hoặc tài liệu cũ đạt tỷ lệ cao nhất, 80%. Vì vậy candidate task cần giữ `source link`, `context summary` và raw message để người dùng đối chiếu.
2. **Đa nền tảng và bỏ sót deadline đều đạt 65%.** Hai tín hiệu này xác nhận trực tiếp candidate problem mà nhóm đã chọn.
3. **Khó xác định ưu tiên đạt 60%, nhưng survey chưa chứng minh người dùng muốn AI tự quyết định priority.** MVP chỉ nên đưa ra gợi ý; quyền sắp xếp cuối cùng thuộc người dùng.
4. **Sao chép/cập nhật thông tin đạt 55%, thấp nhất trong năm câu.** Đồng bộ hai chiều trên mọi nền tảng là extension, không phải bottleneck chính của MVP.

Sau survey, nhóm thu hẹp problem từ:

> “Gom task từ mọi nền tảng vào một nơi.”

thành:

> “Hỗ trợ người dùng phát hiện và chuẩn hóa task/deadline từ các nguồn phân tán thành candidate task có action, deadline, context và source link để review trong một nơi duy nhất.”

Trạng thái bằng chứng:

- **Đã có:** hai trải nghiệm trực tiếp độc lập, một trải nghiệm gần kề, workflow cụ thể và micro survey 20 người.
- **Chưa có:** time-log đủ dài, mức độ nghiêm trọng theo tần suất, precision/recall của việc trích xuất deadline và số lần trễ hạn trong một cửa sổ đo cố định.
- **Hành động tiếp theo:** đo baseline 7 ngày, phỏng vấn sâu 5–10 người và sau đó chạy pilot 14 ngày.

---

## 3. Research giải pháp hiện có

Research snapshot: **27/07/2026**. Nhóm ưu tiên tài liệu chính thức của sản phẩm và nền tảng.

| Nguồn/tool | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống/rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Google Tasks + Google Calendar/Gmail | [Google Tasks Help](https://support.google.com/tasks/answer/7675772) · [Create task from Gmail](https://support.google.com/mail/answer/9920317) · [Calendar API](https://developers.google.com/workspace/calendar/api/guides/overview) | Tạo task từ Gmail, hiển thị task trong Calendar và cung cấp API cho dữ liệu lịch | Phù hợp làm destination/hub; dữ liệu ngày giờ có cấu trúc và dễ truy vết trong hệ sinh thái Google | Không tự chuyển thông báo ngoài Google thành task đáng tin cậy; quyền API phải giới hạn | Dùng Google Tasks/Calendar làm output của pilot, không coi là toàn bộ solution |
| Slack Workflow Builder + connectors/Events API | [Workflow Builder](https://slack.com/help/articles/360035692513-Guide-to-Slack-Workflow-Builder) · [Connectors](https://slack.com/help/articles/20155812595219-Slack-connectors-for-Workflow-Builder) · [Events API](https://docs.slack.dev/apis/events-api/) | Trigger workflow từ hoạt động/tin nhắn, nhận event và gọi bước ở Google Calendar, Gmail, Google Tasks, GitHub, Notion | Hỗ trợ event-driven automation và nhiều connector | Phụ thuộc OAuth scope, workspace policy, app approval và gói sử dụng; không được quét toàn bộ workspace/DM | Chỉ đọc channel hoặc message được chọn; pilot có thể dùng forward/copy-paste trước live integration |
| Notion Database Automation + AI Autofill | [Database automations](https://www.notion.com/help/database-automations) · [Notion AI Autofill](https://www.notion.com/help/autofill) | Tự động hóa database và trích xuất key information từ nội dung page/row | Tốt khi dữ liệu đã ở trong Notion; có thể làm review dashboard | Nguồn ngoài vẫn cần ingestion; AI Autofill không giải quyết toàn bộ provenance và quyền truy cập | Dashboard phải giữ source link và trạng thái approve/dismiss |
| Zapier Paths, Webhooks và Email Parser | [Paths](https://zapier.com/features/paths) · [Webhooks](https://zapier.com/features/webhooks) · [Email Parser](https://zapier.com/features/parser) | Rule-based routing, webhook và trích xuất trường từ email có mẫu | Giải quyết tốt trigger, filter và chuyển dữ liệu giữa nhiều app | Parser template yếu với text mơ hồ; flow phức tạp, chi phí và quyền truy cập tăng theo số tích hợp | Dùng automation cho phần deterministic; AI chỉ cho text phi cấu trúc |
| GitHub Notifications | [GitHub Docs](https://docs.github.com/en/subscriptions-and-notifications/concepts/about-notifications) | Triage activity trong issue, PR, CI và repository | Có filter, saved state và lý do nhận notification | Notification không đồng nghĩa với task có deadline; chỉ giải quyết trong GitHub | Chỉ lấy item được assign/mention hoặc qua rule rõ, không kéo toàn bộ notification |
| Todoist Calendar Integration | [Todoist Help](https://www.todoist.com/help/articles/use-the-calendar-integration-rCqwLCt3G) | Hiển thị Calendar event cạnh task và đồng bộ task đã time-block sang Google/Outlook Calendar | Planning UI trưởng thành; là baseline cạnh tranh trực tiếp cho centralized task/calendar | Không tự hiểu mọi message tự do thành candidate task; vẫn cần người dùng capture hoặc connector riêng | Nhóm phải chứng minh phần capture/provenance tốt hơn việc chỉ dùng Todoist + Calendar |
| Akiflow Universal Inbox | [Akiflow Task Management](https://akiflow.com/task-management) · [Akiflow Inbox](https://product.akiflow.com/help/articles/5284502-your-inbox) | Gom task từ nhiều integration vào một Inbox, hỗ trợ chuyển email/message thành task và lên lịch | Gần với ý tưởng universal task inbox; chứng minh nhu cầu aggregation đã có sản phẩm giải quyết | Là sản phẩm thương mại đã khá đầy đủ; ý tưởng nhóm không mới nếu chỉ “gom task về một chỗ” | Khoảng trống cần pitch không phải centralized inbox chung, mà là pilot có provenance, confidence, ground-truth evaluation và human approval rõ |

### Research takeaway

```text
Không cần build Agent tự trị ngay.
Các nền tảng hiện có đã xử lý tốt phần trigger, API, filter, calendar view
và thậm chí universal inbox.

Khoảng trống nhóm cần kiểm chứng không phải “gom mọi task về một nơi” nói chung,
mà là chuyển text phi cấu trúc thành candidate task có action, deadline, context,
source link và confidence; người dùng vẫn phải xác nhận trước mọi write action.
```

### Đánh giá mức độ research

- **Đủ yêu cầu lab:** Có hơn 3 existing solutions/patterns, nhiều hơn 2 nguồn tham khảo và phần phân tích bước nào đã/chưa được giải quyết.
- **Đã có cả component và competitor:** Google/Slack/Notion/Zapier/GitHub đại diện cho hạ tầng; Todoist và Akiflow là sản phẩm cạnh tranh trực tiếp.
- **Chưa đủ để claim novelty hoặc product-market fit:** Chưa test tool thật, chưa phỏng vấn sâu và chưa so sánh định lượng với Todoist/Akiflow.
- **Hành động cần thêm:** chạy baseline No-AI, thử ít nhất một competitor và phỏng vấn 5–10 sinh viên trước khi mở rộng thành sản phẩm.

---

## 4. Workflow before/after

### 4.1. Current workflow

```text
CURRENT STATE — baseline giả thuyết 15–30 phút/ngày

[1 Mở LMS/Gmail: 3–5']
→ [2 Mở Google Calendar: 2–3']
→ [3 Lướt Slack/Discord tìm thông báo: 5–8']  <-- bottleneck
→ [4 Kiểm tra GitHub/Notion: 3–5']
→ [5 Nối các mẩu thông tin thành task: 3–5']   <-- bottleneck
→ [6 Gõ lại task/deadline vào note hoặc nhớ trong đầu: 2–5']
→ [7 Mở lại các nguồn 3–5 lần trong ngày]
```

Bàn giao hiện tại:

```text
Nguồn thông báo
→ người học tự đọc
→ bộ nhớ/note cá nhân
→ task hoặc calendar event
```

Hai điểm nghẽn:

1. **Discovery:** thông báo quan trọng bị trôi giữa nhiều nguồn.
2. **Normalization:** người dùng phải tự suy ra action, deadline, context và nhập lại.

| Bước | Actor | Input | Output | Thời gian/tần suất | Ghi chú |
|---|---|---|---|---|---|
| 1 | Learner | LMS/Gmail | Danh sách thông báo ban đầu | 3–5 phút/ngày | Có cả thông báo không phải task |
| 2 | Learner | Google Calendar | Event trong ngày/tuần | 2–3 phút/ngày | Structured data |
| 3 | Learner | Slack/Discord message | Candidate deadline/task | 5–8 phút/ngày | Bottleneck discovery; message dễ bị trôi |
| 4 | Learner | GitHub/Notion | Issue/task/project context | 3–5 phút/ngày | Nguồn có mức cấu trúc khác nhau |
| 5 | Learner | Các mẩu thông tin | Task có action, deadline, context | 3–5 phút/ngày | Bottleneck normalization |
| 6 | Learner | Task đã hiểu | Note/task/calendar item | 2–5 phút/ngày | Nhập lại thủ công, có thể thiếu source |
| 7 | Learner | Trí nhớ và nguồn cũ | Kiểm tra lại | 3–5 lượt/ngày | Tăng cognitive load |

### 4.2. Future workflow

```text
FUTURE STATE — mục tiêu ≤8 phút/ngày

[1 Read-only sync từ Calendar + 1 nguồn thông báo đã chọn: <1'] -- API/Rule
→ [2 Rule lọc ngày giờ, keyword và loại event rõ: <1']          -- Rule
→ [3 AI trích xuất candidate task + deadline + context: <1']    -- AI step
→ [4 Rule gộp trùng và gắn source link: <1']                    -- Rule
→ [5 Người dùng approve/edit/dismiss: 4–5']                     -- human boundary
→ [6 Chỉ item đã approve mới được ghi vào hub: <1']             -- controlled write
→ [7 Một daily review; mở nguồn gốc khi cần xác minh]
```

Schema tối thiểu của một candidate task:

```text
title
action
due_at hoặc "chưa xác định"
source_name
source_url/message_id
context_summary
confidence
status = pending_review | approved | dismissed
```

Fallback:

- Không chắc ngày/giờ hoặc action → đánh dấu `chưa xác định`, không tự tạo task.
- Không có quyền đọc nguồn → bỏ qua nguồn đó và hiển thị trạng thái thiếu dữ liệu.
- AI lỗi hoặc confidence thấp → hiển thị raw message để người dùng nhập thủ công.
- Pipeline dừng → người dùng quay về Calendar + checklist review cố định.

Bottleneck mới:

```text
Người dùng review candidate tasks.
```

Đây là bottleneck chấp nhận được vì nó giữ quyền quyết định và kiểm soát lỗi ở người dùng.

### 4.3. Before/after impact

| Metric | Trước — baseline giả thuyết | Sau kỳ vọng | Cách đo |
|---|---:|---:|---|
| Thời gian tổng hợp kế hoạch | 15–30 phút/ngày | ≤8 phút/ngày | Bấm giờ 7 ngày baseline và 14 ngày pilot |
| Lượt mở lại nền tảng để tìm task | 3–5 lượt/ngày | ≤1 lượt review tổng hợp/ngày; mở nguồn khi xác minh | Tally theo ngày |
| Task có source link | Chưa đo; nhiều item ghi tay | 100% item do hệ thống tạo | Audit cuối ngày |
| Deadline quan trọng bị bỏ sót bởi workflow | Chưa có baseline theo cửa sổ cố định | 0 trong 14 ngày pilot | So sánh với ground truth do người dùng lập cuối ngày |
| Precision của candidate task | Chưa có | ≥90% | Candidate đúng / tổng candidate hệ thống tạo |
| Recall trên tập message được gắn nhãn | Chưa có | ≥95%; deadline critical mục tiêu 100% | So với ground truth do hai người dùng gắn nhãn |
| Hành động không được phê duyệt | Không áp dụng | 0 | Audit log mọi write action |

---

## 5. Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Sinh viên/researcher tham gia đồng thời nhiều lớp học và dự án, phải theo dõi task/deadline trên nhiều nền tảng. |
| **Workflow** | Mỗi ngày người dùng mở LMS/Gmail, Calendar, Slack/Discord, GitHub/Notion; đọc thông báo; nối ngữ cảnh; ghi lại task và tự ưu tiên. |
| **Bottleneck** | Việc phát hiện thông báo quan trọng và chuyển các mẩu thông tin thành task có action, deadline, context và nguồn gốc rõ ràng. |
| **Impact** | Baseline ước tính 15–30 phút/ngày, 3–5 lượt kiểm tra lại và có nguy cơ bỏ sót deadline; micro survey cho thấy 65% mẫu gặp pain đa nền tảng hoặc bỏ sót task/deadline, nhưng số liệu thời gian vẫn cần đo lại bằng log. |
| **Success Metric** | Giảm thời gian xuống ≤8 phút/ngày, ≤1 lượt review tổng hợp, 100% task có source link, không có write action chưa được duyệt. |
| **Boundary** | Không đọc nguồn chưa được cấp quyền; không tự gửi email/tin nhắn; không xác nhận lịch; không đổi deadline; không tạo, sửa hoặc xóa task chính thức trước khi người dùng approve. |

---

## 6. Rule / Workflow / Agent

### 6.0. Vị trí trong ma trận AI suitability

**Độ phức tạp:** cao — có nhiều nguồn và các bước ingestion, filtering, extraction, deduplication, review và controlled write.

**Độ mơ hồ:** trung bình — Calendar event và GitHub Issue có cấu trúc rõ; email/chat có thể chứa task ẩn, ngày tương đối hoặc thay đổi lịch.

Hệ thống không cần AI tự đặt mục tiêu hay tự chọn hành động tiếp theo, do đó chưa cần Agent.

### 6.1. So sánh các mức

| Mức | Phương án | Khi nào đủ | Rủi ro/giới hạn | Chọn? |
|---|---|---|---|---|
| **No AI / Process fix** | Chọn một task manager, khung giờ review cố định và quy ước mọi deadline phải vào Calendar | Đủ nếu nhóm có thể tuân thủ một nguồn chính và số thông báo ít | Vẫn phải nhập tay từ nguồn ngoài; phụ thuộc kỷ luật của nhiều người | Dùng làm baseline đối chứng |
| **Rule** | Filter email/keyword, webhook, sync Calendar, template task | Đủ với thông báo có format và ngày giờ rõ | Bỏ sót câu tự nhiên mơ hồ; khó gộp context từ nhiều message | Dùng cho data sync, filter, dedup và write guard |
| **Workflow** | Read-only sync → Rule filter → AI extract → Rule dedup/source link → user approve → controlled write | Hợp vì đường đi cố định, AI chỉ xử lý text phi cấu trúc và có human review | AI có thể false positive, bỏ sót hoặc suy ra sai ngày | **Chọn** |
| **Agent** | Tự chọn nguồn, tự hỏi thêm, tự ưu tiên và tự tạo/đổi task/calendar | Chỉ đáng cân nhắc khi cần nhiều nhánh động và cơ chế quyền/rollback đã trưởng thành | Scope và permission lớn; khó kiểm soát hành động sai; chưa cần cho MVP | Chưa chọn |

Mức chọn:

```text
Workflow.
```

Vì sao:

- Data collection và các deadline có cấu trúc nên dùng API/Rule.
- AI chỉ có lợi thế ở tin nhắn ngôn ngữ tự nhiên, gộp context và chuẩn hóa candidate task.
- Người dùng review trước mọi write action nên rủi ro có thể kiểm soát và rollback.
- Luồng xử lý cố định, chưa cần khả năng tự lập kế hoạch của Agent.

Vì sao không chỉ chọn Rule:

Rule có thể giải tốt phần Calendar/GitHub/Notion có schema và reminder cố định, nhưng khó hiểu các câu như “deadline lùi sang tối thứ Sáu”, “chuẩn bị evaluation trước buổi mentor” hoặc một task được chia qua nhiều message. Pilot phải chứng minh AI cải thiện recall hoặc thời gian so với Rule-only.

---

## 7. Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Sinh viên/researcher đang tham gia nhiều lớp học hoặc dự án và theo dõi task/deadline qua Calendar cùng các kênh thông báo. |
| **Workflow** | Mở từng nền tảng → tìm thông báo có hành động → nối context → suy ra deadline → nhập task → kiểm tra lại trong ngày. |
| **Bottleneck** | Chuyển thông báo phân tán, đặc biệt là text phi cấu trúc, thành một candidate task có action, deadline, context và source link đáng tin cậy. |
| **Impact** | Baseline giả thuyết 15–30 phút/ngày và 3–5 lượt kiểm tra lại; có nguy cơ bỏ sót hoặc xử lý muộn. Micro survey 20 người ghi nhận 65% phải kiểm tra nhiều nền tảng, 65% dễ bỏ sót task/deadline và 80% khó tìm lại context cũ. Baseline thời gian chính thức sẽ được đo trong 7 ngày. |
| **Success Metric** | ≤8 phút/ngày; ≤1 lượt review tổng hợp; 100% task có source link; precision ≥90%; recall ≥95%; 0 write action chưa duyệt. |
| **Boundary** | Pilot chỉ dùng Calendar và một nguồn thông báo được chọn; read-only mặc định; dữ liệu ngoài scope không được đọc; item mơ hồ phải gắn `chưa xác định`; người dùng approve trước khi ghi. |
| **AI intervention point** | Sau bước Rule lọc candidate message và trước bước người dùng review. |
| **Mức chọn** | Workflow: Rule sync/filter/dedup, AI extract text, người dùng approve, Rule kiểm soát write. |
| **Rủi ro & người thật kiểm tra** | False positive, bỏ sót, sai múi giờ/ngày tương đối, lộ dữ liệu và duplicate. Người dùng đối chiếu source link, chỉnh/sửa hoặc dismiss trước khi tạo task. |

### Problem Statement một câu

> Sinh viên/researcher tham gia nhiều lớp học và dự án đang mất ước tính 15–30 phút mỗi ngày để mở nhiều nền tảng và tự chuyển các thông báo rời rạc thành task có action, deadline và ngữ cảnh; micro survey 20 người cho thấy 65% phải kiểm tra nhiều nền tảng và 65% dễ bỏ sót task/deadline. Nhóm đề xuất một Workflow read-only dùng Rule để lọc/đồng bộ, AI để tạo candidate task và bắt buộc người dùng xác nhận trước khi ghi, với mục tiêu giảm thời gian xuống ≤8 phút/ngày mà không có hành động chưa được phê duyệt.

---

## 8. Final decision

Decision:

```text
Go với Workflow pilot nhỏ.
Not Yet với Agent tự trị hoặc tích hợp toàn bộ nền tảng.
```

### 8.1. Decision table

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Nhóm có trải nghiệm trực tiếp, micro survey và workflow hằng ngày vẽ được |
| Baseline và success metric đã đo được chưa? | Not Yet | Survey xác nhận pain nhưng baseline thời gian vẫn cần time-log và labeled sample |
| Có data/input đủ dùng chưa? | Yes cho pilot nhỏ | Calendar và message người dùng chủ động chọn/forward là đủ để thử |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes với boundary | Candidate chỉ được Edit/Dismiss; hệ thống không tự ghi |
| Có người review/owner vận hành không? | Yes | Mỗi learner review inbox của mình; nhóm audit pilot |
| Có cách non-AI đơn giản hơn không? | Yes | Task manager + Calendar + Rule là baseline bắt buộc |

### 8.2. Pilot nhỏ nhất

- **Người dùng:** Quốc Khánh và Đức Anh — hai thành viên có Problem Card trực tiếp.
- **Thời lượng:** 7 ngày đo baseline + 14 ngày chạy pilot.
- **Nguồn:** Google Calendar và một kênh thông báo được hai người dùng chủ động chọn/cấp quyền; giai đoạn đầu có thể dùng export hoặc copy-paste thay vì live integration.
- **Destination:** một centralized review list; chỉ khi approve mới tạo Google Task/Calendar event.
- **Ground truth:** cuối mỗi ngày, mỗi người tự lập danh sách task/deadline thực tế và đối chiếu với output.
- **Đối chứng No AI:** task manager duy nhất + khung giờ review cố định + rule/filter đơn giản.
- **Output cần đo:** thời gian, số lượt mở nguồn, precision, recall, source-link coverage, số item phải sửa và số write action chưa duyệt.
- **Validation định tính bổ sung:** phỏng vấn 5–10 người trong mẫu survey để hiểu tình huống bỏ sót, cách workaround và mức độ nghiêm trọng.

### 8.3. Go / No-Go gate sau pilot

Go sang MVP tích hợp API nếu:

- Median thời gian review ≤8 phút/ngày và giảm ít nhất 40% so với baseline đo được.
- Precision ≥90%, recall ≥95% và không bỏ sót deadline được đánh dấu critical.
- 100% task có source link.
- Không có hành động ghi nào xảy ra trước khi người dùng approve.
- Hai người dùng đánh giá centralized view hữu ích hơn phương án No AI.

Giữ ở Rule/Process fix nếu:

- AI không tạo thêm lợi ích rõ so với filter, template và task manager duy nhất.
- Trên 30% candidate cần sửa lớn hoặc trên 20% candidate bị dismiss.
- Tiết kiệm thời gian dưới 20%.

Dừng hoặc rollback về read-only nếu:

- Có write action chưa được phê duyệt.
- Có truy cập dữ liệu ngoài source/channel đã cho phép.
- AI tự suy ra deadline nhưng không gắn cờ không chắc chắn hoặc không giữ source link.
- Workflow bỏ sót một deadline critical trong pilot; chỉ tiếp tục sau khi root-cause và thêm guard.

### 8.4. Decision rationale

- Problem có workflow, actor, bottleneck và metric đủ cụ thể để kiểm chứng.
- Hai thành viên độc lập gặp pain trực tiếp, một thành viên có pain gần kề và micro survey cung cấp tín hiệu từ 20 người.
- Survey xác nhận pain nhưng không thay thế time-log, interview hoặc pilot thực tế.
- Phương án No AI và Rule được giữ làm baseline, không mặc định AI là đáp án.
- AI nằm ở một bước cần xử lý ngôn ngữ phi cấu trúc; mọi hành động có hậu quả đều thuộc human boundary.
- Scope pilot nhỏ, read-only trước, có exit criteria và rollback rõ.

---

## 9. Assumption và evidence log

| Claim | Trạng thái | Cần làm để xác nhận |
|---|---|---|
| 65% mẫu phải kiểm tra nhiều nền tảng | Đã ghi nhận trong micro survey 20 người | Lặp lại trên mẫu lớn và đa dạng hơn nếu cần claim rộng |
| 65% mẫu dễ bỏ sót task/deadline | Đã ghi nhận trong micro survey 20 người | Interview để xác định tần suất và hậu quả cụ thể |
| 80% mẫu khó tìm lại context/tài liệu cũ | Đã ghi nhận trong micro survey 20 người | Quan sát workflow và đo thời gian tìm lại trong pilot |
| Người dùng mất 15–30 phút/ngày | Ước lượng từ hai bài cá nhân | Time-log 7 ngày |
| Người dùng mở lại nền tảng 3–5 lần/ngày | Ước lượng cá nhân | Tally số lượt mở nguồn trong 7 ngày |
| Có nguy cơ/sự cố bỏ sót deadline | Survey xác nhận perception; chưa có incident log | Ghi số incident trong baseline và pilot |
| Rule không đủ cho text mơ hồ | Giả thuyết kỹ thuật | So sánh Rule-only với Rule + AI trên cùng tập message |
| Centralized view giúp giảm cognitive load | Survey cho thấy 60% khó xác định ưu tiên; causal impact chưa xác nhận | Survey ngắn cuối pilot và so sánh thời gian |
| Hai nguồn đủ tạo giá trị ban đầu | Giả thuyết scope | Đo coverage; chỉ thêm nguồn thứ ba nếu coverage thiếu có ý nghĩa |
| Ý tưởng tạo giá trị khác biệt với Todoist/Akiflow | Chưa xác nhận | Cho người dùng thử ít nhất một competitor và so sánh capture, provenance, review effort |

---

## 10. Checklist đối chiếu yêu cầu đề bài

### Phase 3 — Group convergence

- [x] Có đầu vào từ 12 candidates của bốn thành viên phân tích.
- [x] Có gom trùng/cluster.
- [x] Có nhật ký pitch và challenge.
- [x] Có shortlist và score 1–5.
- [x] Có candidate được chọn và lý do không chọn candidate khác.

### Phase 4 — Validation và research

- [x] Có quick validation từ bốn individual reports và review chéo.
- [x] Có micro survey 20 người và số liệu tổng hợp.
- [x] Có tín hiệu xác nhận, tín hiệu phản bác và cách nhóm thu hẹp problem.
- [x] Có ít nhất 3 existing solutions/patterns.
- [x] Có hyperlink tới nguồn chính thức.
- [x] Có phân tích họ giải quyết bước nào, khoảng trống và bài học cho nhóm.
- [x] Có research takeaway.
- [ ] Chưa có interview sâu hoặc observation thực tế — cần làm trước khi claim product-market fit.

### Phase 5 — Workflow và Problem Statement

- [x] Có current workflow với actor, input, output, thời gian và bottleneck.
- [x] Có future workflow phân biệt Rule, AI và human boundary.
- [x] Có fallback nếu AI sai hoặc connector lỗi.
- [x] Có before/after metric và cách đo.
- [x] Có Problem Statement v0 với Actor, Workflow, Bottleneck, Impact, Success Metric và Boundary.

### Phase 6 — Rule / Workflow / Agent và Decision

- [x] Có đánh giá độ phức tạp và độ mơ hồ.
- [x] Có so sánh No AI / Rule / Workflow / Agent.
- [x] Có lý do chọn Workflow và lý do chưa chọn Agent.
- [x] Có Problem Statement v1 và AI intervention point.
- [x] Có Decision table.
- [x] Có quyết định Go / Not Yet rõ ràng.
- [x] Có pilot nhỏ nhất, metric, Go/No-Go gate và rollback.
- [x] Có assumption/evidence log để không biến ước lượng thành fact.

### Kết luận kiểm tra

Bản group report đã đáp ứng đầy đủ các mục bắt buộc Phase 3–6 trong worksheet. Research đủ cho yêu cầu lab, đã bao phủ cả giải pháp hạ tầng lẫn competitor trực tiếp, và micro survey 20 người đã bổ sung validation ngoài nhóm. Phần còn thiếu ở mức kiểm chứng sản phẩm là interview sâu, time-log và benchmark sử dụng thực tế; nội dung này được ghi thành next step thay vì tự nhận đã hoàn thành.

---

*Group Report — Day 02 Lab v3*
