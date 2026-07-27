# Individual Report — Day 02

## Persona

Tôi là sinh viên Công nghệ thông tin, đồng thời tham gia nghiên cứu Computer Vision và phát triển các dự án AI. Công việc hằng tuần của tôi gồm học tập trên trường, đọc paper, chạy thí nghiệm, viết báo cáo, làm project nhóm và đăng ký các chương trình học thuật.

Tôi thường sử dụng nhiều nền tảng như GitHub, Google Drive, Google Calendar, Gmail, Notion, Overleaf, W&B và các nhóm chat. Vì vậy, các vấn đề tôi quan sát chủ yếu liên quan đến việc thông tin bị phân tán, công việc lặp lại và khó quản lý ngữ cảnh.


---

# Phase 1 — Individual Problem Scan

## Bảng scan 10 vấn đề

| #  | Lăng kính                | Problem quan sát được                                                                                                             | Ai chịu ảnh hưởng?                         | Dấu hiệu thật                                                                                                                                             |
| -- | ------------------------ | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1  | Tốn thời gian            | Tôi khó theo dõi đầy đủ lịch học, lịch họp, deadline nghiên cứu và các cuộc hẹn vì thông tin nằm trên nhiều nền tảng.             | Tôi và các thành viên làm việc cùng tôi    | Lịch nằm trong email, nhóm chat, GitHub và Calendar. Tôi phải kiểm tra lại khoảng 3–5 lần mỗi ngày để tránh bỏ sót.                                       |
| 2  | Lặp lại                  | Tôi phải nhập lại cùng một bộ thông tin cá nhân khi đăng ký học bổng, chương trình nghiên cứu, cuộc thi hoặc biểu mẫu của trường. | Tôi                                        | Các trường như họ tên, mã sinh viên, trường, email, CV và kinh nghiệm được nhập lại nhiều lần mỗi tháng.                                                  |
| 3  | Tốn thời gian            | Tôi mất nhiều thời gian so sánh thông tin trước khi mua sản phẩm công nghệ nhưng vẫn khó biết lựa chọn nào phù hợp nhất.          | Tôi                                        | Một lần chọn linh kiện máy tính, chuột hoặc phụ kiện có thể mất 2–4 giờ đọc thông số, bài đánh giá và ý kiến cộng đồng.                                   |
| 4  | Pain từ người khác       | Công việc của tôi đôi khi bị dừng vì phải chờ người khác cấp quyền truy cập, xác nhận yêu cầu hoặc gửi tài liệu.                  | Tôi, trưởng nhóm, người quản lý tài nguyên | Tôi từng không clone được repository dù đã được thông báo là đã được thêm vào. Task bị dừng cho đến khi quyền truy cập được kiểm tra lại.                 |
| 5  | AI có thể hỗ trợ tốt hơn | Tôi khó tìm lại các đường link, tài liệu và quyết định cũ vì chúng nằm rải rác trên nhiều nền tảng.                               | Tôi                                        | Paper, repository, email, file Drive và ghi chú nằm ở ít nhất 4–5 nơi. Có lần tôi mất khoảng 10–20 phút chỉ để tìm lại một tài liệu đã từng đọc.          |
| 6  | Tốn thời gian            | Tôi mất nhiều thời gian tìm và sàng lọc paper trước khi xác định được tài liệu thực sự liên quan đến ý tưởng nghiên cứu.          | Tôi và các sinh viên nghiên cứu            | Với một ý tưởng mới, tôi thường phải mở khoảng 10–30 paper và mất 2–4 giờ để đọc abstract, method và kết luận trước khi có shortlist.                     |
| 7  | Lặp lại                  | Tôi phải ghi lại cấu hình, checkpoint và kết quả của từng lần chạy thí nghiệm ở nhiều nơi khác nhau.                              | Tôi                                        | Thông tin nằm trong file config, terminal, tên checkpoint, W&B và ghi chú cá nhân. Khi có nhiều run gần giống nhau, tôi khó nhớ chính xác điểm khác biệt. |
| 8  | AI có thể hỗ trợ tốt hơn | Tôi khó đánh giá dataset có thực sự phù hợp với bài toán trước khi tiền xử lý và chạy thử model.                                  | Tôi và các researcher Computer Vision      | Các vấn đề như lệch lớp, nhãn chưa tốt hoặc khác domain đôi khi chỉ được phát hiện sau khi đã tải dữ liệu, tiền xử lý hoặc train trong nhiều giờ.         |
| 9  | Pain từ người khác       | Khi làm việc nhóm, tôi khó biết chính xác ai đang làm task nào, task nào đang bị chặn và quyết định cuối cùng là gì.              | Tôi và các thành viên nhóm                 | Thông tin tiến độ nằm trong nhóm chat, GitHub Issue và tài liệu. Mọi người phải hỏi lại trạng thái hoặc nhắc nhau cập nhật.                               |
| 10 | Lặp lại                  | Tôi phải viết lại cùng một kết quả vào README, báo cáo, slide, worklog và journal.                                                | Tôi                                        | Một kết quả nghiên cứu hoặc project có thể phải được cập nhật vào 3–5 tài liệu, mất khoảng 30–60 phút mỗi tuần và dễ không đồng nhất.                     |

---

# Phase 2 — Top 3 Problem Cards

## 1. Lựa chọn top 3

| Rank | Problem                                                 | Vì sao chọn                                                                                              | Điều còn chưa chắc                                                              |
| ---- | ------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| 1    | Tìm và sàng lọc paper cho một ý tưởng nghiên cứu        | Xảy ra thường xuyên, tốn nhiều thời gian, workflow rõ và có thể đo bằng thời gian cùng số paper phải đọc | Chất lượng của shortlist do AI tạo ra sẽ được đánh giá như thế nào              |
| 2    | Quản lý cấu hình và kết quả của các lần chạy thí nghiệm | Có pain trực tiếp, gây lãng phí thời gian và GPU, ảnh hưởng khả năng tái hiện kết quả                    | Các công cụ như W&B đã giải quyết được bao nhiêu phần của vấn đề                |
| 3    | Theo dõi deadline và task từ nhiều nền tảng             | Xảy ra hằng ngày, ảnh hưởng cả học tập lẫn nghiên cứu, có nguy cơ bỏ sót công việc                       | Có thể tích hợp dữ liệu từ các nền tảng mà vẫn đảm bảo quyền riêng tư hay không |

---

# Problem Card 1 — Sàng lọc paper nghiên cứu

## Problem một câu

Khi bắt đầu một ý tưởng nghiên cứu mới, tôi phải dành khoảng 2–4 giờ tìm và đọc sơ bộ nhiều paper từ các nguồn khác nhau trước khi xác định được 5–7 tài liệu thực sự liên quan.

## Actor

Tôi, trong vai trò sinh viên nghiên cứu Computer Vision và medical imaging.

Actor mở rộng có thể là sinh viên, học viên cao học hoặc researcher mới bắt đầu một đề tài.

## Thời điểm/Bối cảnh

Khi tìm research gap, xây dựng related work, tìm architecture tham chiếu hoặc lựa chọn conference và special issue phù hợp.

## Current workflow

1. Viết một số keyword mô tả ý tưởng.
2. Tìm trên Google Scholar, arXiv, IEEE hoặc các website tạp chí.
3. Mở nhiều tab chứa các paper có tiêu đề liên quan.
4. Đọc abstract, introduction, method và conclusion.
5. Ghi chú một số paper vào file hoặc đoạn chat riêng.
6. So sánh novelty, dataset, method và kết quả.
7. Chọn ra những paper đáng đọc sâu.

## Bottleneck

Bước đọc sơ bộ và so sánh nhiều paper.

Tôi phải tự đọc từng paper để xác định paper có thực sự liên quan hay chỉ trùng một số từ khóa. Bước này có thể mất khoảng 60–120 phút trong tổng workflow.

## Impact

* Một ý tưởng mới có thể mất 2–4 giờ chỉ để có được bức tranh ban đầu.
* Nhiều paper đã đọc nhưng không được lưu lại theo cấu trúc nên khó tái sử dụng.
* Tôi có thể bỏ sót paper quan trọng hoặc đọc lại paper đã từng xem.
* Việc research bị kéo dài khiến thời gian triển khai thí nghiệm bị chậm.

## Success metric

* Giảm thời gian tạo shortlist từ khoảng 2–4 giờ xuống dưới 60 phút.
* Giảm số paper cần đọc sơ bộ từ khoảng 20–30 xuống còn 5–10 paper ưu tiên.
* Mỗi paper trong shortlist phải có nguồn, lý do được chọn và phần nội dung liên quan.
* Tôi vẫn tự đọc và kiểm tra toàn văn của các paper quan trọng trước khi sử dụng.
* Không đưa citation vào báo cáo nếu chưa được tôi kiểm tra.

## Non-AI alternative

* Xây dựng bộ keyword cố định cho từng hướng nghiên cứu.
* Dùng Zotero hoặc Notion để lưu paper theo tag.
* Tạo template ghi chú gồm: problem, method, dataset, result, limitation.
* Chỉ tìm paper từ một số venue hoặc journal đã xác định trước.

Phương án này có thể giúp lưu trữ tốt hơn nhưng vẫn yêu cầu tôi đọc và so sánh từng paper thủ công.

## AI hypothesis

AI có thể hỗ trợ:

* Mở rộng và chuẩn hóa keyword tìm kiếm.
* Phân nhóm paper theo hướng kỹ thuật.
* Trích xuất problem, method, dataset, metric và limitation.
* So sánh các paper theo cùng một template.
* Chỉ ra paper nào cần được ưu tiên đọc sâu.

AI không được tự xác nhận novelty, tự tạo citation hoặc thay tôi kết luận rằng một hướng nghiên cứu chưa từng tồn tại.

## Quick gut

* [ ] No AI/process fix
* [ ] Rule
* [x] Workflow
* [ ] Agent
* [ ] Chưa biết

Workflow phù hợp hơn Agent vì AI chỉ nên hỗ trợ sàng lọc và tổng hợp. Người nghiên cứu vẫn phải kiểm tra paper gốc và đưa ra kết luận.

## Draft current workflow

```text
CURRENT STATE — khoảng 150 phút

[Viết keyword: 10']
→ [Tìm trên nhiều nguồn: 25']
→ [Mở và loại nhanh paper: 20']
→ [Đọc abstract/method: 60']  <-- bottleneck
→ [Ghi chú rời rạc: 15']
→ [So sánh và chọn shortlist: 20']
```

## Draft future workflow

```text
FUTURE STATE — mục tiêu dưới 60 phút

[Nhập research question + tiêu chí: 5']
→ [Workflow tìm và nhập metadata: 5']
→ [AI phân nhóm + trích xuất thông tin: 10']
→ [Tôi kiểm tra nguồn và đọc top paper: 30']  <-- human boundary
→ [Lưu structured note + shortlist: 10']

Fallback:
AI phân loại sai hoặc thiếu nguồn
→ tôi quay lại search thủ công và loại bỏ kết quả không kiểm chứng được.
```

---

# Problem Card 2 — Theo dõi thí nghiệm AI

## Problem một câu

Khi chạy nhiều thí nghiệm Computer Vision, tôi khó theo dõi đầy đủ sự khác nhau giữa các run vì cấu hình, log, checkpoint và kết quả nằm ở nhiều vị trí khác nhau.

## Actor

Tôi, trong vai trò researcher và người trực tiếp huấn luyện model.

## Thời điểm/Bối cảnh

Trong giai đoạn ablation study, hyperparameter tuning hoặc so sánh các phiên bản architecture.

## Current workflow

1. Sửa file cấu hình hoặc tham số trong command.
2. Chạy thí nghiệm.
3. Theo dõi log trong terminal hoặc W&B.
4. Lưu checkpoint và đặt tên thư mục.
5. Ghi kết quả tốt nhất vào ghi chú hoặc bảng.
6. Mở lại nhiều run để so sánh.
7. Cố gắng tái hiện run tốt nhất khi cần.

## Bottleneck

Thông tin ngữ cảnh của một run không được lưu đồng nhất.

Khi quay lại sau một thời gian, tôi phải kiểm tra file config, commit code, tên checkpoint và W&B để hiểu run đó đã thay đổi điều gì.

## Impact

* Tốn thời gian tìm lại run tốt nhất.
* Có nguy cơ so sánh các run không cùng điều kiện.
* Khó tái hiện chính xác kết quả cũ.
* Có thể chạy lại một cấu hình đã từng thử, gây lãng phí thời gian và GPU.
* Ablation table dễ thiếu thông tin hoặc ghi nhầm.

## Success metric

* Ít nhất 95% run có đầy đủ config, commit, dataset version và metric.
* Tìm lại thông tin của một run trong dưới 2 phút.
* Tái chạy cấu hình tốt nhất trong dưới 10 phút chuẩn bị.
* Không còn checkpoint không xác định được cấu hình.
* Giảm thời gian tổng hợp ablation table ít nhất 50%.

## Non-AI alternative

* Dùng duy nhất một file YAML cho mỗi run.
* Bắt buộc quy tắc đặt tên checkpoint.
* Dùng W&B hoặc MLflow cho toàn bộ thí nghiệm.
* Tạo script tự lưu Git commit, config và môi trường.
* Dùng bảng Excel để so sánh run.

Phần lớn vấn đề có thể được cải thiện bằng quy trình và automation thông thường trước khi dùng AI.

## AI hypothesis

AI có thể hỗ trợ ở bước sau:

* Tóm tắt điểm khác nhau giữa các run.
* Phát hiện run thiếu metadata.
* Nhóm các run cùng loại ablation.
* Viết bản nháp bảng kết quả.
* Gợi ý run tiếp theo dựa trên lịch sử đã có.

AI không được tự chọn kết quả tốt nhất chỉ dựa trên một metric hoặc tự quyết định hướng nghiên cứu tiếp theo.

## Quick gut

* [ ] No AI/process fix
* [x] Rule
* [x] Workflow
* [ ] Agent
* [ ] Chưa biết

Ưu tiên Rule và Workflow trước. AI chỉ có giá trị sau khi dữ liệu thí nghiệm đã được ghi nhận đầy đủ và có cấu trúc.

## Draft current workflow

```text
CURRENT STATE

[Sửa config thủ công]
→ [Chạy model]
→ [Log trong terminal/W&B]
→ [Đặt tên checkpoint thủ công]
→ [Ghi metric vào note]  <-- bottleneck: dữ liệu phân tán
→ [Mở từng run để so sánh]
→ [Tạo ablation table]
```

## Draft future workflow

```text
FUTURE STATE

[Chọn config chuẩn]
→ [Script tự lưu config + Git commit + dataset version]
→ [Tự động log metric và checkpoint]
→ [Dashboard so sánh run]
→ [AI draft summary các khác biệt]
→ [Tôi kiểm tra và chọn kết luận]  <-- human boundary

Fallback:
AI summary sai
→ sử dụng trực tiếp config và metric gốc trên dashboard.
```

---

# Problem Card 3 — Theo dõi task và deadline phân tán

## Problem một câu

Tôi phải kiểm tra nhiều nền tảng mỗi ngày để tổng hợp task và deadline cho việc học, nghiên cứu và hoạt động nhóm, làm tăng nguy cơ bỏ sót hoặc xử lý công việc muộn.

## Actor

Tôi, trong vai trò sinh viên, researcher và thành viên nhiều nhóm dự án.

## Thời điểm/Bối cảnh

Hằng ngày và đặc biệt trong những tuần có nhiều deadline, lịch phỏng vấn, cuộc họp hoặc hoạt động nhóm.

## Current workflow

1. Kiểm tra Gmail.
2. Kiểm tra nhóm chat và Discord.
3. Kiểm tra GitHub Issue hoặc thông báo repository.
4. Kiểm tra Google Calendar.
5. Ghi lại task quan trọng vào ghi chú hoặc nhớ trong đầu.
6. Tự xác định mức độ ưu tiên.
7. Kiểm tra lại các nền tảng trong ngày.

## Bottleneck

Chuyển thông tin phân tán thành một danh sách hành động có deadline và ngữ cảnh rõ ràng.

Nhiều tin nhắn chỉ chứa một phần thông tin, nên tôi phải mở lại thread, email hoặc tài liệu để hiểu task cần làm gì.

## Impact

* Mất khoảng 20–30 phút mỗi ngày để kiểm tra và tổng hợp.
* Tăng cognitive load vì phải nhớ task từ nhiều nguồn.
* Có nguy cơ quên deadline hoặc xác nhận lịch muộn.
* Khó ưu tiên giữa việc học, nghiên cứu và project.
* Phải hỏi lại người khác khi thiếu ngữ cảnh.

## Success metric

* Giảm thời gian tổng hợp kế hoạch hằng ngày xuống dưới 10 phút.
* Không bỏ sót hard deadline trong ít nhất bốn tuần.
* Mỗi task đều có deadline, nguồn gốc và đường link ngữ cảnh.
* Các task do hệ thống gợi ý chỉ được tạo sau khi tôi xác nhận.
* Giảm số lần phải mở lại nhiều nền tảng để tìm ngữ cảnh.

## Non-AI alternative

* Chuyển toàn bộ deadline vào Google Calendar.
* Dùng một task manager duy nhất.
* Thiết lập bộ lọc email và notification.
* Dành một khung giờ cố định mỗi ngày để planning.
* Dùng template weekly review.

Giải pháp này đơn giản và ít rủi ro nhưng vẫn yêu cầu tôi nhập task thủ công từ nhiều nguồn.

## AI hypothesis

AI có thể:

* Trích xuất task, ngày giờ và người liên quan từ email hoặc tin nhắn được cấp quyền.
* Gộp các thông báo nói về cùng một task.
* Tóm tắt ngữ cảnh và gắn link nguồn.
* Đề xuất priority dựa trên deadline và lịch hiện có.
* Nhắc tôi xác nhận trước khi tạo task hoặc calendar event.

AI không được tự gửi email, tự xác nhận lịch hoặc thay đổi deadline khi chưa có sự đồng ý của tôi.

## Quick gut

* [ ] No AI/process fix
* [ ] Rule
* [x] Workflow
* [ ] Agent
* [x] Chưa biết

Có thể bắt đầu bằng Workflow. Chỉ chuyển sang Agent nếu có cơ chế quyền truy cập, xác nhận và rollback đủ rõ.

## Draft current workflow

```text
CURRENT STATE — khoảng 20–30 phút/ngày

[Kiểm tra email]
→ [Kiểm tra nhóm chat/Discord]
→ [Kiểm tra GitHub]
→ [Kiểm tra Calendar]
→ [Tự nối thông tin và nhớ task]  <-- bottleneck
→ [Ghi task thủ công]
→ [Kiểm tra lại nhiều lần]
```

## Draft future workflow

```text
FUTURE STATE — mục tiêu dưới 10 phút/ngày

[Workflow lấy thông báo từ nguồn được cho phép]
→ [Rule lọc nội dung có khả năng là task/deadline]
→ [AI trích xuất task + tóm tắt context]
→ [Tôi review và xác nhận]  <-- human boundary
→ [Tạo task hoặc calendar event]
→ [Giữ link quay lại nguồn gốc]

Fallback:
Không chắc ngày giờ hoặc nội dung
→ không tự tạo task, chỉ đánh dấu để tôi kiểm tra.
```

---

# Card tôi muốn pitch nhất

**Problem Card 1 — Sàng lọc paper nghiên cứu.**

## Vì sao tôi chọn

Đây là vấn đề tôi trực tiếp gặp thường xuyên và hiểu rõ workflow hiện tại. Vấn đề không chỉ là “tìm paper”, mà là phải biến một số lượng lớn tài liệu thành shortlist có cấu trúc để đưa ra quyết định nghiên cứu.

Pain có thể đo bằng:

* Thời gian tìm và đọc sơ bộ.
* Số paper phải mở.
* Số paper cuối cùng được giữ lại.
* Số lần phải tìm lại paper đã từng đọc.
* Tỷ lệ thông tin do AI đưa ra được kiểm chứng đúng từ paper gốc.

Bài toán cũng có ranh giới người–máy khá rõ: AI hỗ trợ tìm, phân nhóm và trích xuất; researcher chịu trách nhiệm đọc nguồn, xác nhận citation và kết luận novelty.

## Câu hỏi tôi muốn nhóm challenge

> Pain lớn nhất thực sự nằm ở việc tìm paper, đọc paper hay quản lý lại kiến thức sau khi đã đọc? Nếu chỉ dùng Zotero, tagging và template ghi chú thì đã giải quyết đủ vấn đề chưa, hay AI thực sự tạo thêm giá trị ở bước sàng lọc và so sánh?

---

# Self-check Phase 1–2

* [x] Có ít nhất 5 problems từ trải nghiệm thật.
* [x] Có nhiều lăng kính khác nhau.
* [x] Mỗi problem có actor và dấu hiệu ban đầu.
* [x] Có top 3 Problem Cards.
* [x] Mỗi card có current workflow từ 3–7 bước.
* [x] Mỗi card có bottleneck và impact.
* [x] Mỗi card có success metric.
* [x] Có non-AI alternative.
* [x] Có AI hypothesis và human boundary.
* [x] Có draft workflow trước/sau.
* [x] Đã chọn một card ưu tiên.
* [x] Có câu hỏi để nhóm phản biện.
