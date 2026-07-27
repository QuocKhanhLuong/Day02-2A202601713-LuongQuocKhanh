# Group Report — Day 02

> Candidate problem nhóm lựa chọn: **Theo dõi task và deadline từ nhiều nền tảng**.
>
> Bản này được tổng hợp từ bốn báo cáo cá nhân trong nhóm. Các baseline hiện tại là số liệu tự quan sát hoặc ước tính ban đầu; nhóm sẽ kiểm chứng lại bằng log trong pilot trước khi dùng làm cam kết sản phẩm.

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Đóng góp chính trong Phase 3–6 |
|---:|---|---|---|
| 1 | Lương Quốc Khánh | 2A202601713 | Đề xuất bài toán task/deadline đa nền tảng; tổng hợp workflow, metric và human boundary |
| 2 | Nguyễn Thu Huyền | 2A202601027 | Bổ sung evidence về báo cáo daily, lịch họp định kỳ và việc chuẩn bị context bị phân tán |
| 3 | Hoàng Đức Anh | 2A202601223 | Đề xuất Centralized Deadline Tracker; phân tích API integration, workflow và fallback |
| 4 | Trần Nguyễn Mỹ Anh | 2A202601019 | Challenge về độ tin cậy, fallback, quyền riêng tư và ranh giới giữa rule–AI–con người |

---

## Phase 3 — Group Convergence

### 3.1. Tổng hợp 12 candidate problems

| # | Người đưa ra | Candidate problem | Actor chính | Điểm nghẽn | Cảm nhận nhanh |
|---:|---|---|---|---|---|
| 1 | Lương Quốc Khánh | Sàng lọc paper nghiên cứu | Sinh viên/researcher | Đọc và so sánh 20–30 paper thủ công | Workflow |
| 2 | Lương Quốc Khánh | Theo dõi experiment AI | Researcher | Config, log, checkpoint và metric phân tán | Workflow |
| 3 | Lương Quốc Khánh | Theo dõi task và deadline đa nền tảng | Sinh viên/researcher | Tự nối thông tin từ Gmail, chat, GitHub và Calendar | Workflow |
| 4 | Nguyễn Thu Huyền | Khảo sát và tổng hợp Literature Review | Sinh viên nghiên cứu | Đọc chi tiết và ghi chú paper chiếm phần lớn thời gian | Workflow |
| 5 | Nguyễn Thu Huyền | Sàng lọc và kiểm soát dataset lớn | Sinh viên AI/Data | Chỉ biết dataset không phù hợp sau khi tải và xử lý | Workflow |
| 6 | Nguyễn Thu Huyền | Nhắc lịch báo cáo daily và lịch họp | Học viên/thành viên dự án | Nhớ lại công việc và chuẩn bị context họp quá muộn | Rule/Workflow |
| 7 | Hoàng Đức Anh | Daily Standup Reminder & Auto-Drafting | Learner | Lục lại activity hôm trước rồi viết standup | Workflow |
| 8 | Hoàng Đức Anh | Tóm tắt yêu cầu Lab/Assignment | Learner | Đọc nhiều file dài để tìm rubric và acceptance criteria | Workflow |
| 9 | Hoàng Đức Anh | Centralized Deadline Tracker | Learner | Lướt Slack/Discord rồi copy deadline thủ công | Rule/Workflow |
| 10 | Trần Nguyễn Mỹ Anh | BEV Vision Debugging Tool | Perception engineer | Đồng bộ và overlay Camera–LiDAR–BEV thủ công | Workflow |
| 11 | Trần Nguyễn Mỹ Anh | Triage failure case theo metric | CV researcher | Từ metric aggregate truy ngược về frame lỗi | Workflow |
| 12 | Trần Nguyễn Mỹ Anh | Calibration Alignment Check | Sensor-fusion engineer | Kiểm tra extrinsic/time offset bằng mắt | Workflow |

### 3.2. Gom trùng và tạo cluster

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A — Task, deadline và báo cáo định kỳ | #3, #6, #7, #9 | Thông tin hành động và thời hạn nằm rải rác; người dùng phải tự nhớ, tìm, chép lại và kiểm tra nhiều lần | Ba thành viên có trải nghiệm trực tiếp; workflow xảy ra hằng ngày |
| B — Đọc và cấu trúc tài liệu | #1, #4, #8 | Đọc nhiều nguồn dài rồi trích xuất phần liên quan thành checklist hoặc matrix | AI có lợi thế ngôn ngữ, nhưng fact-check khó và metric chất lượng phức tạp hơn |
| C — Experiment và debugging | #2, #10, #11, #12 | Log, metric và artifact phân tán; khó truy ngược nguyên nhân lỗi | Impact kỹ thuật cao nhưng domain hẹp và dữ liệu/pipeline phức tạp |
| D — Dataset preparation | #5 | Chỉ phát hiện dataset không phù hợp sau khi tải và xử lý | Pain thật nhưng phụ thuộc loại dữ liệu và hạ tầng cụ thể |

### 3.3. Shortlist

| Candidate | Vì sao vào shortlist | Rủi ro / điều chưa rõ |
|---|---|---|
| Theo dõi task và deadline đa nền tảng | Ba thành viên gặp trực tiếp; actor, workflow và baseline thời gian rõ; có thể tạo pilot nhỏ | Quyền truy cập API, quyền riêng tư, trùng task và AI hiểu nhầm tin nhắn |
| Literature Review Workflow | Hai thành viên có pain rõ; AI phù hợp với đọc, trích xuất và so sánh văn bản | Hallucination, citation sai và khó đo “chất lượng hiểu paper” |
| Experiment/Debug Dashboard | Nhóm có kinh nghiệm CV; impact lên chu kỳ nghiên cứu lớn | Scope kỹ thuật rộng, khó dùng chung cho nhiều người và khó hoàn thành validation trong lab |

### 3.4. Score để đồng thuận

Thang điểm: 1–5 cho từng tiêu chí.

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm pilot nhỏ | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Task/deadline đa nền tảng | 5 | 5 | 5 | 5 | 4 | 5 | 5 | **34** |
| Literature Review Workflow | 5 | 5 | 4 | 4 | 4 | 5 | 5 | **32** |
| Experiment/Debug Dashboard | 4 | 4 | 4 | 4 | 2 | 4 | 4 | **26** |

**Candidate nhóm chọn:**

> Theo dõi task và deadline từ nhiều nền tảng cho sinh viên/learner tham gia đồng thời việc học, nghiên cứu và project nhóm.

**Vì sao chọn:**

- Ba trong bốn thành viên mô tả trực tiếp pain liên quan deadline, daily report hoặc lịch họp phân tán.
- Workflow xảy ra hằng ngày và có baseline thời gian ban đầu từ 15–30 phút/ngày.
- Bottleneck không chỉ là thiếu nhắc lịch; người dùng phải đọc thông báo tự do, hiểu hành động cần làm, lấy deadline rồi nhập lại vào công cụ cá nhân.
- Có thể tách rõ phần Rule, AI và human review.
- Có thể pilot với 2–3 nguồn thay vì tích hợp toàn bộ nền tảng ngay lập tức.

**Vì sao chưa chọn các candidate còn lại:**

- Literature Review có impact lớn nhưng rủi ro citation/hallucination cao và metric chất lượng khó thống nhất trong thời gian lab.
- Experiment/Debug Dashboard phù hợp domain CV nhưng scope hẹp, phụ thuộc schema dữ liệu và yêu cầu công triển khai lớn hơn.

**Cách nhóm xử lý disagreement:**

Nhóm không chọn theo mức độ “ngầu” của giải pháp AI. Nhóm thống nhất ưu tiên candidate có nhiều thành viên tự trải nghiệm, có baseline dễ đo, workflow vẽ được và có pilot nhỏ. Các ý tưởng daily standup và lịch họp được xem là use case con của bài toán task/deadline, không mở rộng thành một trợ lý tự động làm mọi việc.

---

## Phase 4 — Quick Validation và Research giải pháp

### 4.1. Quick validation ban đầu

Nhóm chưa thực hiện khảo sát bên ngoài. Validation hiện tại chỉ dựa trên bốn báo cáo cá nhân, vì vậy được xem là **tín hiệu ban đầu**, chưa phải bằng chứng đại diện cho toàn bộ sinh viên.

| Nguồn | Số người / mẫu | Tín hiệu xác nhận | Tín hiệu phản bác / giới hạn | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Báo cáo cá nhân trong nhóm | 4 người | 3/4 người mô tả trực tiếp pain về deadline, daily report, lịch họp hoặc task phân tán | 1 thành viên không đưa vấn đề này vào top 3; mức pain khác nhau giữa từng người | Thu hẹp actor vào learner/sinh viên làm nhiều project, không tuyên bố vấn đề đúng với mọi người |
| Baseline của Quốc Khánh | 1 workflow cá nhân | Mất khoảng 20–30 phút/ngày và kiểm tra 3–5 lượt/ngày | Là số tự ước tính, chưa có log 14 ngày | Đưa time-log vào pilot thay vì coi số này là dữ liệu chính thức |
| Baseline của Đức Anh | 1 workflow cá nhân | Mất khoảng 15–20 phút/ngày; có lúc bỏ sót deadline do thông báo trôi | Chưa ghi log số lần bỏ sót trong một khoảng thời gian cố định | Chọn metric “deadline có nguồn nhưng không được capture” để đo rõ hơn |
| Baseline của Thu Huyền | 1 workflow cá nhân | Daily report có thể trễ 3–4 lần/tuần; việc nhớ task và chuẩn bị họp tốn thời gian | Scope rộng hơn task tracker vì bao gồm viết report và chuẩn bị meeting | Chỉ giữ bước capture task/deadline/context; auto-draft report là extension, không phải core pilot |

**Insight sau validation nội bộ:**

> Pain cốt lõi không phải “không có ứng dụng nhắc việc”. Pain nằm ở bước biến thông báo và yêu cầu rời rạc từ nhiều nguồn thành một task có hành động, deadline, nguồn gốc và mức độ ưu tiên rõ ràng.

### 4.2. Research giải pháp đã có

Research được thực hiện ngày 27/07/2026 trên tài liệu chính thức của các công cụ.

| Nguồn / tool / pattern | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Google Tasks + Google Calendar/Gmail | [Google Tasks Help](https://support.google.com/tasks/answer/7675772) | Tạo task từ Gmail/Calendar/Chat; task có ngày xuất hiện trong Calendar | Miễn phí, phù hợp hệ sinh thái Google, nguồn email có thể truy vết | Không tự tổng hợp Slack/Discord/Notion/LMS; người dùng vẫn phải chủ động tạo task | Google Tasks có thể là output của pilot, nhưng chưa phải lớp aggregation |
| Todoist Calendar Integration | [Todoist Help](https://www.todoist.com/help/articles/use-the-calendar-integration-rCqwLCt3G) | Hiển thị calendar event cùng task và đồng bộ task time-blocked với lịch | UI planning tốt, giảm việc đổi qua lại giữa task và calendar | Không tự hiểu mọi tin nhắn tự do thành task; tích hợp nguồn vẫn cần cấu hình | Dashboard thống nhất hữu ích, nhưng capture và provenance vẫn là khoảng trống cần giải |
| Slack Workflow Builder + connectors | [Slack Workflow Builder](https://slack.com/help/articles/360035692513-Guide-to-Slack-Workflow-Builder) · [Slack connectors](https://slack.com/help/articles/20155812595219-Slack-connectors-for-Workflow-Builder) | Tự động hóa quy trình và gọi hành động ở Google Calendar, Gmail, Google Tasks, GitHub, Notion... | No-code, trigger/step rõ, phù hợp rule và structured workflow | Slack-centric; phụ thuộc paid plan, admin/app approval; không bao phủ Discord/LMS và vẫn có rủi ro parse text | Structured action nên xử lý bằng connector/rule, không cần Agent |
| Zapier integrations | [Google Calendar + Slack](https://zapier.com/apps/google-calendar/integrations/slack) · [Google Tasks + Notion](https://zapier.com/apps/google-tasks/integrations/notion) | Đồng bộ sự kiện/task giữa các ứng dụng bằng trigger-action | Nhiều connector, nhanh để prototype | Mỗi integration cần setup riêng; rule thuần túy khó hiểu deadline trong tin nhắn tự do, deduplicate và giữ context | Có thể dùng làm baseline non-AI hoặc lớp automation trong pilot |
| Akiflow Universal Inbox | [Akiflow Task Management](https://akiflow.com/task-management) | Gom task từ nhiều nguồn, chuyển Slack/email thành task và time-block trên lịch | Gần với vision “universal task inbox” | Là sản phẩm thương mại; coverage tùy integration; chưa giải trực tiếp bài toán learner/LMS/Discord và validation nguồn | Nhóm không nên claim ý tưởng chưa tồn tại; novelty nằm ở scope learner, capture có nguồn và human confirmation |

**Research takeaway:**

- Thị trường đã có task manager, calendar sync và automation connector; nhóm không nên xây thêm một todo app chung chung.
- Rule/API giải tốt dữ liệu có cấu trúc như calendar event, assigned issue hoặc task database.
- AI chỉ có giá trị rõ ở nguồn phi cấu trúc: email/chat chứa yêu cầu, deadline hoặc thay đổi lịch bằng ngôn ngữ tự nhiên.
- Khoảng trống nhóm chọn để khảo sát là: **candidate task inbox có provenance, deduplication, confidence và human confirmation trước khi ghi vào hệ thống chính thức**.

---

## Phase 5 — Workflow và Problem Statement

### 5.1. Current workflow bản nhóm

```text
CURRENT STATE — khoảng 20–30 phút/ngày, kiểm tra 3–5 lượt/ngày

[1 Mở LMS/Gmail để tìm assignment và yêu cầu mới: 4']
→ [2 Mở Google Calendar để xem lịch và deadline đã có: 2']
→ [3 Lướt Slack/Discord/Zalo tìm thông báo bị trôi: 8']  <-- bottleneck 1
→ [4 Mở GitHub/Notion kiểm tra issue và task nhóm: 3']
→ [5 Tự hiểu nội dung, xác định hành động + deadline: 5'] <-- bottleneck 2
→ [6 Copy/gõ lại vào note, Calendar hoặc task manager: 5']
→ [7 Tự sắp xếp priority và kiểm tra lại trong ngày: 2–5']
```

| Bước | Actor | Input | Output | Thời gian/tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | Learner | Email/LMS notification | Danh sách yêu cầu có thể cần làm | 3–5 phút, ít nhất 1 lần/ngày | Một số nguồn có dữ liệu cấu trúc |
| 2 | Learner | Calendar event/task | Lịch và deadline đã biết | Khoảng 2 phút/ngày | Không chứa task từ các nền tảng khác |
| 3 | Learner | Tin nhắn Slack/Discord/Zalo | Thông báo deadline hoặc thay đổi yêu cầu | Khoảng 8 phút/ngày | **Bottleneck:** tin nhắn bị trôi và phi cấu trúc |
| 4 | Learner | GitHub Issue/Notion task | Trạng thái project | Khoảng 3 phút/ngày | Có thể trùng với thông báo chat |
| 5 | Learner | Nội dung đã đọc | Task, deadline và context do người dùng tự diễn giải | Khoảng 5 phút/ngày | **Bottleneck:** cognitive load và ambiguity |
| 6 | Learner | Task tự diễn giải | Bản ghi trong task manager/calendar | Khoảng 5 phút/ngày | Copy thủ công, dễ thiếu link nguồn |
| 7 | Learner | Danh sách task | Priority trong ngày | 2–5 phút, lặp lại 3–5 lượt/ngày | Deadline và priority có thể thay đổi |

**Bottleneck chính:**

> Learner phải tự đọc nguồn phi cấu trúc, nhận ra câu nào thực sự tạo ra một hành động/deadline, nối với context liên quan rồi copy sang công cụ cá nhân. Reminder thông thường không giải được bước diễn giải và chuyển đổi này.

### 5.2. Future workflow bản nhóm

```text
FUTURE STATE — mục tiêu dưới 10 phút/ngày

[1 Rule/connectors lấy item từ nguồn được cấp quyền: Gmail, Calendar, GitHub/Notion]
→ [2 AI chỉ phân tích email/chat được chọn để tạo Candidate Task]
→ [3 Rule chuẩn hóa: title, deadline, source link, deduplicate, confidence]
→ [4 Learner review: Confirm / Edit / Dismiss]  <-- human boundary
→ [5 Sau khi Confirm mới tạo task hoặc calendar event]
→ [6 Dashboard tạo daily digest và gợi ý priority; learner quyết định]

Fallback:
- Thiếu hoặc mâu thuẫn deadline → gắn `Needs review`, không tự tạo task chính thức.
- Confidence thấp → chỉ hiển thị candidate kèm link nguồn.
- Connector lỗi → giữ dữ liệu cũ, báo source chưa đồng bộ; người dùng vẫn nhập task thủ công.
- AI hiểu sai → người dùng Dismiss/Edit; hệ thống không gửi email, nộp bài hay thay đổi deadline.
```

#### Before/after impact

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Số bước chính | 7 | 6 | Số bước không giảm nhiều, nhưng phần tìm–copy được tự động hóa và review được gom một chỗ |
| Tổng thời gian | Khoảng 20–30 phút/ngày | Dưới 10 phút/ngày | Đo bằng time-log 14 ngày trước và 14 ngày pilot |
| Số lượt mở lại nhiều nền tảng | Khoảng 3–5 lượt/ngày | 1 lượt review tổng hợp; chỉ mở nguồn khi cần xác minh | Đếm lượt mở nguồn để tìm task/deadline |
| Số bước thủ công | 7 | 2: review và quyết định priority | Việc tạo task chính thức vẫn cần xác nhận |
| Khả năng truy vết | Nhiều task không có link nguồn | 100% candidate/task tự động có source link | Audit task cuối ngày |
| Deadline bị bỏ sót do không capture | Chưa có baseline nhóm; một số thành viên ghi nhận có xảy ra | 0 deadline đã xuất hiện trong nguồn pilot nhưng không được đưa vào candidate inbox trong 4 tuần | Chỉ đo trên nguồn đã cấp quyền, không claim toàn bộ nền tảng |
| Risk mới | Không có risk AI nhưng dễ bỏ sót thủ công | False positive, false deadline, duplicate, privacy/API permission | Mitigate bằng confidence, provenance và human confirmation |

### 5.3. Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Sinh viên/learner đồng thời tham gia việc học, nghiên cứu và project nhóm, sử dụng từ 4 nền tảng trở lên để nhận task và deadline |
| **Workflow** | Mỗi ngày mở Gmail/LMS, Calendar, chat, GitHub/Notion; đọc thông báo; tự xác định hành động và deadline; nhập lại vào công cụ cá nhân |
| **Bottleneck** | Tìm thông báo phi cấu trúc bị trôi và chuyển nó thành task có context, deadline và nguồn gốc rõ ràng |
| **Impact** | Mất khoảng 20–30 phút/ngày, kiểm tra 3–5 lượt/ngày và vẫn có nguy cơ quên/trễ task |
| **Success Metric** | Dưới 10 phút/ngày; 1 lượt review tổng hợp; 100% task tự động có source link; 0 deadline thuộc nguồn pilot bị bỏ qua trong 4 tuần |
| **Boundary** | Chỉ đọc nguồn được cấp quyền; không tự gửi/nộp, xác nhận lịch, đổi deadline hoặc tạo task chính thức khi chưa có người dùng xác nhận |

---

## Phase 6 — Rule / Workflow / Agent và Decision

### 6.0. Ma trận độ phù hợp với AI

**Vị trí của bài toán:** độ phức tạp cao, độ mơ hồ trung bình.

**Vì sao:**

- Có ít nhất 3 nguồn dữ liệu và nhiều bước ingestion, parsing, deduplication, review và sync.
- Structured item như Calendar event hoặc GitHub Issue có độ mơ hồ thấp và nên dùng Rule.
- Email/chat tự do có thể chứa deadline, thay đổi lịch, lời nhắc hoặc chỉ là thảo luận nên cần hiểu ngữ cảnh.
- AI không cần tự quyết định mục tiêu hoặc tự thay đổi workflow; vì vậy chưa cần Agent.

### 6.1. So sánh Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | API/webhook lấy Calendar, GitHub Issue, Notion task; keyword/regex tìm ngày; reminder cố định | Đủ cho nguồn có schema và deadline rõ | Bỏ sót câu tự nhiên, hiểu nhầm ngày, không nối được context và duplicate | Không chọn làm mức tổng thể; dùng như component |
| **Workflow** | Rule ingestion + AI parse nguồn phi cấu trúc + chuẩn hóa/deduplicate + human review + confirmed sync | Phù hợp khi các bước rõ nhưng một bước cần hiểu ngôn ngữ | False positive, quyền riêng tư, connector lỗi | **Chọn** |
| **Agent** | Tự chọn nguồn cần kiểm tra, tự tạo/đổi task, tự lên lịch và gửi nhắc | Chỉ phù hợp khi cần tự lập kế hoạch và hành động đa công cụ | Quyền truy cập rộng, tự hành động sai, khó audit/rollback | Không chọn ở giai đoạn này |

**Mức chọn:** `Workflow`.

**Vì sao chọn:**

Workflow cho phép dùng Rule ở phần chắc chắn, AI ở đúng bước phi cấu trúc và đặt con người tại điểm quyết định. Quy trình có thể audit qua source link, confidence và trạng thái Confirm/Edit/Dismiss.

**Vì sao không chỉ chọn Rule:**

Rule có thể giải phần sync Calendar/GitHub/Notion và reminder định kỳ, nhưng chưa giải tốt các thông báo như “deadline lùi sang tối thứ Sáu”, “nhớ hoàn thiện phần evaluation trước buổi mentor” hoặc task ẩn trong thread chat. Tuy nhiên, pilot phải so sánh với baseline Rule để chứng minh AI thực sự tạo thêm giá trị.

**Vì sao không chọn Agent:**

Bài toán không cần AI tự lập kế hoạch hoặc tự hành động. Việc tự gửi báo cáo, nhận lịch, đổi deadline hoặc tạo task không xác nhận tạo rủi ro lớn hơn lợi ích và làm mờ trách nhiệm của người dùng.

### 6.2. Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Sinh viên/learner tham gia đồng thời việc học, nghiên cứu và project nhóm, thường nhận task/deadline qua Gmail/LMS, Calendar, chat và công cụ project |
| **Workflow** | Kiểm tra từng nền tảng, đọc thông báo, diễn giải hành động và deadline, nhập lại vào task manager rồi kiểm tra nhiều lần trong ngày |
| **Bottleneck** | Nhận diện task/deadline trong nội dung phi cấu trúc, nối đúng context và loại trùng trước khi tạo bản ghi chính thức |
| **Impact** | Baseline cá nhân khoảng 15–30 phút/ngày và 3–5 lượt kiểm tra; có trường hợp trễ daily hoặc bỏ sót deadline do thông báo trôi |
| **Success Metric** | Giảm thời gian review xuống dưới 10 phút/ngày; chỉ cần 1 lượt review tổng hợp; ≥90% precision và ≥95% recall trên candidate task đã được người dùng gắn nhãn trong pilot; 100% candidate có source link; không tự tạo task khi confidence thấp |
| **Boundary** | Chỉ xử lý nguồn được người dùng chọn; không đọc toàn bộ private chat; không tự gửi/nộp/xác nhận/đổi deadline; dữ liệu nhạy cảm không được dùng ngoài mục đích pilot |
| **AI intervention point** | Chỉ dùng AI để trích xuất và tóm tắt candidate task từ email/chat phi cấu trúc; Rule xử lý nguồn có schema, deduplicate và sync |
| **Mức chọn** | Workflow |
| **Rủi ro & người thật kiểm tra** | False positive, deadline sai, duplicate và privacy; learner phải Confirm/Edit/Dismiss trước khi task được tạo |

### 6.3. Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Nhóm có ba trải nghiệm trực tiếp và workflow hằng ngày vẽ được |
| Baseline và success metric đã đo được chưa? | Not Yet | Có baseline ước tính nhưng cần time-log và labeled sample trong pilot |
| Có data/input đủ dùng chưa? | Yes cho pilot nhỏ | Có thể dùng Gmail/Calendar của người tham gia và message được họ chủ động đưa vào; chưa cần full workspace access |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes với boundary | Candidate sai chỉ bị Edit/Dismiss; hệ thống không tự hành động |
| Có người review/owner vận hành không? | Yes | Mỗi learner review inbox của chính mình; nhóm chịu trách nhiệm audit pilot |
| Có cách non-AI đơn giản hơn không? | Yes | Google Tasks/Calendar, Todoist, Zapier và reminder là baseline bắt buộc để so sánh |

**Decision:**

> **Go cho pilot Workflow có phạm vi hẹp; Not Yet cho Agent hoặc tích hợp toàn bộ nền tảng.**

**Lý do:**

Pain đã xuất hiện ở nhiều thành viên và có workflow/metric rõ. AI có một intervention point hợp lý là parse nội dung phi cấu trúc, nhưng giá trị tăng thêm so với Rule chưa được chứng minh. Vì vậy nhóm chỉ Go với pilot có human confirmation và baseline non-AI.

**Pilot nhỏ nhất:**

1. **Actor:** 4 thành viên nhóm trong 2–4 tuần.
2. **Nguồn structured:** Google Calendar và email Gmail được gắn label riêng cho pilot.
3. **Nguồn unstructured:** người dùng chủ động forward/paste message từ Slack/Discord/Zalo vào một inbox pilot; chưa yêu cầu quyền đọc toàn workspace.
4. **Output:** Candidate Task gồm title, deadline, source, context, confidence và trạng thái `Confirm / Edit / Dismiss`.
5. **Sau Confirm:** tạo Google Task hoặc Calendar event; không tự gửi/nộp bất kỳ nội dung nào.
6. **Baseline A:** người dùng dùng Google Tasks/Calendar + reminder/template, không có AI parsing.
7. **Workflow B:** Rule ingestion + AI extraction + human confirmation.
8. **Đo:** thời gian review, precision/recall candidate task, số duplicate, số deadline nguồn pilot bị bỏ sót và mức hài lòng 1–5.

**Điều cần validate tiếp trước khi mở rộng:**

- Thu thập time-log 14 ngày để xác nhận baseline thực tế.
- Gắn nhãn tối thiểu 100 message/email thành `task`, `deadline`, `không phải task` để đo precision/recall.
- Kiểm tra OAuth scope, retention và quyền xóa dữ liệu.
- So sánh Rule-only với Workflow có AI; nếu AI không cải thiện đáng kể recall hoặc thời gian, quay về Rule/connector đơn giản.

---

## Self-check bản nhóm

- [x] Đã trình bày và gom 12 candidate problems thành cluster.
- [x] Có shortlist, score và lý do chọn candidate.
- [x] Có validation nội bộ và ghi rõ giới hạn bằng chứng.
- [x] Có research ít nhất 3 existing solutions/patterns.
- [x] Có current workflow với actor, input, output, thời gian và bottleneck.
- [x] Có future workflow với Rule, AI, human boundary và fallback.
- [x] Có metric trước/sau và cách đo trong pilot.
- [x] Có Problem Statement v0 và v1.
- [x] Có so sánh Rule / Workflow / Agent.
- [x] Có quyết định Go / Not Yet rõ ràng và pilot nhỏ nhất.
