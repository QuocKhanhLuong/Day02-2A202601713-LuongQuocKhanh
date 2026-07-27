# Individual Report — Day 02

## Persona

Tôi là sinh viên Công nghệ thông tin, đồng thời tham gia nghiên cứu Computer Vision và phát triển các dự án AI. Công việc hằng tuần của tôi gồm học tập trên trường, đọc paper, chạy thí nghiệm, viết báo cáo, làm project nhóm và đăng ký các chương trình học thuật.

Tôi thường sử dụng nhiều nền tảng như GitHub, Google Drive, Google Calendar, Gmail, Notion, Overleaf, W&B và các nhóm chat. Vì vậy, các vấn đề tôi quan sát chủ yếu liên quan đến việc thông tin bị phân tán, công việc lặp lại và khó quản lý ngữ cảnh.

> Các con số dưới đây là baseline ước tính ban đầu từ trải nghiệm cá nhân. Trước khi phát triển giải pháp, tôi cần xác nhận lại bằng log hoặc theo dõi trong một khoảng thời gian ngắn.

---

## Phase 1 — Individual Problem Scan

### Bảng scan 10 vấn đề

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Tốn thời gian | Tôi khó theo dõi đầy đủ lịch học, lịch họp, deadline nghiên cứu và các cuộc hẹn vì thông tin nằm trên nhiều nền tảng. | Tôi và các thành viên làm việc cùng tôi | Lịch nằm trong email, nhóm chat, GitHub và Calendar. Tôi phải kiểm tra lại khoảng 3–5 lần mỗi ngày để tránh bỏ sót. |
| 2 | Lặp lại | Tôi phải nhập lại cùng một bộ thông tin cá nhân khi đăng ký học bổng, chương trình nghiên cứu, cuộc thi hoặc biểu mẫu của trường. | Tôi | Các trường như họ tên, mã sinh viên, trường, email, CV và kinh nghiệm được nhập lại nhiều lần mỗi tháng. |
| 3 | Tốn thời gian | Tôi mất nhiều thời gian so sánh thông tin trước khi mua sản phẩm công nghệ nhưng vẫn khó biết lựa chọn nào phù hợp nhất. | Tôi | Một lần chọn linh kiện máy tính, chuột hoặc phụ kiện có thể mất 2–4 giờ đọc thông số, bài đánh giá và ý kiến cộng đồng. |
| 4 | Pain từ người khác | Công việc của tôi đôi khi bị dừng vì phải chờ người khác cấp quyền truy cập, xác nhận yêu cầu hoặc gửi tài liệu. | Tôi, trưởng nhóm, người quản lý tài nguyên | Đã có ít nhất một lần tôi không clone được repository dù được thông báo đã được thêm vào. Terminal trả lỗi `Repository not found`, khiến việc setup phải dừng để kiểm tra quyền truy cập. |
| 5 | AI có thể hỗ trợ tốt hơn | Tôi khó tìm lại các đường link, tài liệu và quyết định cũ vì chúng nằm rải rác trên nhiều nền tảng. | Tôi | Paper, repository, email, file Drive và ghi chú nằm ở ít nhất 4–5 nơi. Có lần tôi mất khoảng 10–20 phút chỉ để tìm lại một tài liệu đã từng đọc. |
| 6 | Tốn thời gian | Tôi mất nhiều thời gian tìm và sàng lọc paper trước khi xác định được tài liệu thực sự liên quan đến ý tưởng nghiên cứu. | Tôi và các sinh viên nghiên cứu | Với một ý tưởng mới, tôi thường mở và sàng lọc khoảng 20–30 paper, mất 2–4 giờ để chọn ra khoảng 5–7 paper cần đọc sâu. |
| 7 | Lặp lại | Tôi phải ghi lại cấu hình, checkpoint và kết quả của từng lần chạy thí nghiệm ở nhiều nơi khác nhau. | Tôi | Một đợt ablation thường có nhiều run gần giống nhau, trong khi thông tin bị chia giữa file config, terminal, checkpoint, W&B và ghi chú cá nhân. Khi quay lại, tôi có thể mất 10–15 phút để khôi phục ngữ cảnh của một run. |
| 8 | AI có thể hỗ trợ tốt hơn | Tôi khó đánh giá dataset có thực sự phù hợp với bài toán trước khi tiền xử lý và chạy thử model. | Tôi và các researcher Computer Vision | Một số vấn đề như lệch lớp, nhãn chưa tốt hoặc khác domain chỉ lộ ra sau khi đã tải dữ liệu, kiểm tra nhiều thư mục hoặc chạy thử trong nhiều giờ. |
| 9 | Pain từ người khác | Khi làm việc nhóm, tôi khó biết chính xác ai đang làm task nào, task nào đang bị chặn và quyết định cuối cùng là gì. | Tôi và các thành viên nhóm | Trạng thái công việc thường nằm ít nhất ở ba nơi: nhóm chat, GitHub Issue và tài liệu. Thành viên phải hỏi lại hoặc nhắc cập nhật vì không có một nguồn trạng thái thống nhất. |
| 10 | Lặp lại | Tôi phải viết lại cùng một kết quả vào README, báo cáo, slide, worklog và journal. | Tôi | Một kết quả nghiên cứu hoặc project có thể phải được cập nhật vào 3–5 tài liệu, mất khoảng 30–60 phút mỗi tuần và dễ không đồng nhất. |

---

## Phase 2 — Top 3 Problem Cards

### Lựa chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Tìm và sàng lọc paper cho một ý tưởng nghiên cứu | Xảy ra thường xuyên, tốn nhiều thời gian, workflow rõ và có thể đo bằng thời gian cùng số paper phải đọc | Chất lượng của shortlist do AI hỗ trợ sẽ được đánh giá như thế nào |
| 2 | Quản lý cấu hình và kết quả của các lần chạy thí nghiệm | Có pain trực tiếp, gây lãng phí thời gian và GPU, ảnh hưởng khả năng tái hiện kết quả | Các công cụ như W&B đã giải quyết được bao nhiêu phần của vấn đề |
| 3 | Theo dõi deadline và task từ nhiều nền tảng | Xảy ra hằng ngày, ảnh hưởng cả học tập lẫn nghiên cứu, có nguy cơ bỏ sót công việc | Có thể tích hợp dữ liệu từ các nền tảng mà vẫn đảm bảo quyền riêng tư hay không |

---

### Problem Card 1 — Sàng lọc paper nghiên cứu

#### Problem một câu

Khi bắt đầu một ý tưởng nghiên cứu mới, tôi thường mất khoảng 2–4 giờ để mở và sàng lọc 20–30 paper từ nhiều nguồn trước khi chọn được khoảng 5–7 paper thực sự cần đọc sâu.

#### Actor

Tôi, trong vai trò sinh viên nghiên cứu Computer Vision và medical imaging.

Actor mở rộng có thể là sinh viên, học viên cao học hoặc researcher mới bắt đầu một đề tài.

#### Thời điểm/Bối cảnh

Khi tìm research gap, xây dựng related work, tìm architecture tham chiếu hoặc lựa chọn conference và special issue phù hợp.

#### Current workflow

1. Viết một số keyword mô tả ý tưởng.
2. Tìm trên Google Scholar, arXiv, IEEE hoặc các website tạp chí.
3. Mở nhiều tab chứa các paper có tiêu đề liên quan.
4. Đọc abstract, introduction, method và conclusion.
5. Ghi chú một số paper vào file hoặc đoạn chat riêng.
6. So sánh novelty, dataset, method và kết quả.
7. Chọn ra những paper đáng đọc sâu.

#### Bottleneck

Bước đọc sơ bộ và so sánh nhiều paper.

Tôi phải tự đọc từng paper để xác định paper có thực sự liên quan hay chỉ trùng một số từ khóa. Bước này thường chiếm khoảng 60–120 phút trong tổng workflow.

#### Impact

- Một ý tưởng mới có thể mất 2–4 giờ chỉ để có được bức tranh ban đầu.
- Paper đã đọc không được lưu theo cấu trúc nên khó tái sử dụng và có thể phải tìm lại.
- Việc sàng lọc kéo dài làm chậm thời điểm bắt đầu thiết kế và chạy thí nghiệm.

#### Success metric

| Metric | Baseline hiện tại | Target | Cách đo |
|---|---|---|---|
| Tổng thời gian tạo shortlist | Khoảng 2–4 giờ cho một research question | Dưới 60 phút | Bấm giờ từ lúc bắt đầu viết keyword đến khi chốt shortlist |
| Số paper phải đọc sơ bộ thủ công | Khoảng 20–30 paper | Còn 8–10 paper được ưu tiên để kiểm tra, từ đó chọn 5–7 paper đọc sâu | Ghi lại số paper được mở, số paper qua vòng ưu tiên và số paper được giữ lại |
| Khả năng truy vết thông tin | Ghi chú rời rạc, không phải paper nào cũng có lý do được giữ lại | 100% paper trong shortlist có nguồn, lý do chọn và phần nội dung liên quan | Kiểm tra checklist trước khi lưu shortlist |

#### Non-AI alternative

- Xây dựng bộ keyword cố định cho từng hướng nghiên cứu.
- Dùng Zotero hoặc Notion để lưu paper theo tag và template chung.
- Giới hạn tìm kiếm trong các venue hoặc journal đã xác định trước.

Phương án này giúp lưu trữ tốt hơn nhưng vẫn yêu cầu tôi đọc và so sánh từng paper thủ công.

#### AI hypothesis

AI có thể hỗ trợ mở rộng keyword, phân nhóm paper, trích xuất problem–method–dataset–metric–limitation và tạo bảng so sánh để tôi ưu tiên tài liệu cần đọc sâu.

AI không được tự xác nhận novelty, tự tạo citation hoặc thay tôi kết luận rằng một hướng nghiên cứu chưa từng tồn tại. Tôi vẫn phải mở paper gốc, kiểm tra nội dung và xác nhận mọi citation trước khi sử dụng.

#### Quick gut

- [ ] No AI/process fix
- [ ] Rule
- [x] Workflow
- [ ] Agent
- [ ] Chưa biết

Workflow phù hợp hơn Agent vì AI chỉ nên hỗ trợ sàng lọc và tổng hợp. Người nghiên cứu vẫn chịu trách nhiệm kiểm tra paper gốc và đưa ra kết luận.

#### Draft current workflow

```text
CURRENT STATE — khoảng 150 phút

[Viết keyword: 10']
→ [Tìm trên nhiều nguồn: 25']
→ [Mở và loại nhanh paper: 20']
→ [Đọc abstract/method: 60']  <-- bottleneck
→ [Ghi chú rời rạc: 15']
→ [So sánh và chọn shortlist: 20']
```

#### Draft future workflow

```text
FUTURE STATE — mục tiêu khoảng 55 phút

[Nhập research question + tiêu chí: 5']
→ [Workflow tìm và nhập metadata: 5']
→ [AI phân nhóm + trích xuất thông tin: 10']
→ [Tôi kiểm tra nguồn và đọc top paper: 25']  <-- human boundary
→ [Lưu structured note + shortlist: 10']

Fallback:
AI phân loại sai hoặc thiếu nguồn
→ tôi quay lại search thủ công và loại bỏ kết quả không kiểm chứng được.
```

---

### Problem Card 2 — Theo dõi thí nghiệm AI

#### Problem một câu

Khi chạy nhiều thí nghiệm Computer Vision, tôi khó theo dõi đầy đủ sự khác nhau giữa các run vì cấu hình, log, checkpoint và kết quả nằm ở nhiều vị trí khác nhau.

#### Actor

Tôi, trong vai trò researcher và người trực tiếp huấn luyện model.

#### Thời điểm/Bối cảnh

Trong giai đoạn ablation study, hyperparameter tuning hoặc so sánh các phiên bản architecture.

#### Current workflow

1. Sửa file cấu hình hoặc tham số trong command.
2. Chạy thí nghiệm.
3. Theo dõi log trong terminal hoặc W&B.
4. Lưu checkpoint và đặt tên thư mục.
5. Ghi kết quả tốt nhất vào ghi chú hoặc bảng.
6. Mở lại nhiều run để so sánh.
7. Cố gắng tái hiện run tốt nhất khi cần.

#### Bottleneck

Thông tin ngữ cảnh của một run không được lưu đồng nhất. Khi quay lại sau một thời gian, tôi phải kiểm tra file config, commit code, tên checkpoint và W&B để hiểu run đó đã thay đổi điều gì; việc này ước tính mất khoảng 10–15 phút cho một run.

#### Impact

- Tốn thời gian tìm lại và tái hiện run tốt nhất.
- Có nguy cơ so sánh các run không cùng điều kiện hoặc chạy lại cấu hình đã thử.
- Ablation table dễ thiếu thông tin, gây lãng phí thời gian và GPU.

#### Success metric

Các baseline phần trăm dưới đây là ước tính ban đầu và sẽ được xác nhận bằng cách audit 10 run gần nhất.

| Metric | Baseline hiện tại | Target | Cách đo |
|---|---|---|---|
| Thời gian khôi phục ngữ cảnh một run | Khoảng 10–15 phút/run | Dưới 2 phút/run | Chọn ngẫu nhiên 10 run cũ và bấm giờ đến khi xác định được config, commit, dataset và metric |
| Tỷ lệ run có đủ metadata bắt buộc | Ước tính khoảng 60–70% run có đủ config, commit, dataset version và metric | Ít nhất 95% | Audit 10 run gần nhất trước pilot và toàn bộ run trong pilot |
| Thời gian chuẩn bị để tái chạy cấu hình tốt nhất | Khoảng 20–30 phút | Dưới 10 phút | Bấm giờ từ lúc chọn run đến khi có command/config sẵn sàng chạy |
| Thời gian tổng hợp ablation table | Khoảng 30–60 phút cho một đợt | Giảm ít nhất 50% | So sánh thời gian tổng hợp trước và sau trên hai đợt ablation tương đương |

#### Non-AI alternative

- Dùng một file YAML chuẩn cho mỗi run và quy tắc đặt tên checkpoint.
- Dùng W&B hoặc MLflow thống nhất cho toàn bộ thí nghiệm.
- Tạo script tự lưu Git commit, config, dataset version và môi trường.

Phần lớn vấn đề cần được giải bằng quy trình và automation có cấu trúc trước khi AI có dữ liệu đủ tốt để hỗ trợ.

#### AI hypothesis

Sau khi metadata đã được chuẩn hóa, AI có thể tóm tắt điểm khác nhau giữa các run, phát hiện run thiếu thông tin, nhóm các run cùng loại ablation và tạo bản nháp bảng kết quả.

AI không được tự chọn kết quả tốt nhất chỉ dựa trên một metric hoặc tự quyết định hướng nghiên cứu tiếp theo. Tôi vẫn kiểm tra metric gốc và đưa ra kết luận.

#### Quick gut

- [ ] No AI/process fix
- [ ] Rule
- [x] Workflow
- [ ] Agent
- [ ] Chưa biết

Lựa chọn chính là Workflow. Các rule đặt tên và script logging là thành phần bên trong workflow, không phải một phương án độc lập được chọn song song.

#### Draft current workflow

```text
CURRENT STATE

[Sửa config thủ công]
→ [Chạy model]
→ [Log trong terminal/W&B]
→ [Đặt tên checkpoint thủ công]
→ [Ghi metric vào note]  <-- bottleneck: dữ liệu phân tán, 10–15 phút khi tìm lại/run
→ [Mở từng run để so sánh]
→ [Tạo ablation table]
```

#### Draft future workflow

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

### Problem Card 3 — Theo dõi task và deadline phân tán

#### Problem một câu

Tôi phải kiểm tra nhiều nền tảng mỗi ngày để tổng hợp task và deadline cho việc học, nghiên cứu và hoạt động nhóm, làm tăng nguy cơ bỏ sót hoặc xử lý công việc muộn.

#### Actor

Tôi, trong vai trò sinh viên, researcher và thành viên nhiều nhóm dự án.

#### Thời điểm/Bối cảnh

Hằng ngày và đặc biệt trong những tuần có nhiều deadline, lịch phỏng vấn, cuộc họp hoặc hoạt động nhóm.

#### Current workflow

1. Kiểm tra Gmail.
2. Kiểm tra nhóm chat và Discord.
3. Kiểm tra GitHub Issue hoặc thông báo repository.
4. Kiểm tra Google Calendar.
5. Ghi lại task quan trọng vào ghi chú hoặc nhớ trong đầu.
6. Tự xác định mức độ ưu tiên.
7. Kiểm tra lại các nền tảng trong ngày.

#### Bottleneck

Chuyển thông tin phân tán thành một danh sách hành động có deadline và ngữ cảnh rõ ràng. Nhiều tin nhắn chỉ chứa một phần thông tin, nên tôi phải mở lại thread, email hoặc tài liệu để hiểu task cần làm gì.

#### Impact

- Mất khoảng 20–30 phút mỗi ngày để kiểm tra và tổng hợp.
- Tăng cognitive load và nguy cơ quên deadline hoặc xác nhận lịch muộn.
- Phải mở lại nhiều nguồn hoặc hỏi lại người khác khi thiếu ngữ cảnh.

#### Success metric

| Metric | Baseline hiện tại | Target | Cách đo |
|---|---|---|---|
| Thời gian tổng hợp kế hoạch hằng ngày | Khoảng 20–30 phút/ngày | Dưới 10 phút/ngày | Bấm giờ trong 14 ngày trước và 14 ngày sau pilot |
| Số lượt kiểm tra lại các nền tảng | Khoảng 3–5 lượt/ngày | Một lượt review tổng hợp; chỉ mở nguồn khi cần xác minh | Tự tally số lần mở Gmail, chat, GitHub và Calendar để tìm task |
| Khả năng truy vết task | Nhiều task được ghi thủ công và có thể thiếu nguồn hoặc deadline | 100% task được tạo có link nguồn; task chưa rõ deadline phải được đánh dấu `chưa xác định` | Audit danh sách task cuối mỗi ngày trong bốn tuần |

#### Non-AI alternative

- Chuyển toàn bộ deadline vào Google Calendar và dùng một task manager duy nhất.
- Thiết lập bộ lọc email, notification và một khung giờ planning cố định.
- Dùng template weekly review để kiểm tra task còn thiếu ngữ cảnh.

Giải pháp này đơn giản và ít rủi ro nhưng vẫn yêu cầu tôi nhập task thủ công từ nhiều nguồn.

#### AI hypothesis

AI có thể trích xuất task, ngày giờ và người liên quan từ nguồn được cấp quyền; gộp các thông báo nói về cùng một việc; tóm tắt ngữ cảnh và đề xuất priority.

AI không được tự gửi email, tự xác nhận lịch, thay đổi deadline hoặc tạo task chính thức khi chưa có sự đồng ý của tôi.

#### Quick gut

- [ ] No AI/process fix
- [ ] Rule
- [x] Workflow
- [ ] Agent
- [ ] Chưa biết

Có thể bắt đầu bằng Workflow có bước xác nhận của người dùng. Chỉ cân nhắc Agent sau này nếu quyền truy cập, xác nhận và rollback được kiểm chứng đủ an toàn.

#### Draft current workflow

```text
CURRENT STATE — khoảng 20–30 phút/ngày

[Kiểm tra email]
→ [Kiểm tra nhóm chat/Discord]
→ [Kiểm tra GitHub]
→ [Kiểm tra Calendar]
→ [Tự nối thông tin và nhớ task]  <-- bottleneck
→ [Ghi task thủ công]
→ [Kiểm tra lại 3–5 lần/ngày]
```

#### Draft future workflow

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

## Card tôi muốn pitch nhất

**Problem Card 1 — Sàng lọc paper nghiên cứu.**

### Vì sao tôi chọn

Đây là vấn đề tôi trực tiếp gặp thường xuyên và hiểu rõ workflow hiện tại. Vấn đề không chỉ là “tìm paper”, mà là biến một số lượng lớn tài liệu thành shortlist có cấu trúc để hỗ trợ quyết định nghiên cứu.

Pain có thể đo bằng thời gian sàng lọc, số paper phải mở, số paper được giữ lại và khả năng truy vết thông tin về từng paper. Ranh giới người–máy cũng rõ: AI hỗ trợ tìm, phân nhóm và trích xuất; researcher chịu trách nhiệm đọc nguồn, xác nhận citation và kết luận novelty.

### Câu hỏi tôi muốn nhóm challenge

> Pain lớn nhất thực sự nằm ở việc tìm paper, đọc paper hay quản lý lại kiến thức sau khi đã đọc? Nếu chỉ dùng Zotero, tagging và template ghi chú thì đã giải quyết đủ vấn đề chưa, hay AI thực sự tạo thêm giá trị ở bước sàng lọc và so sánh?

### Trạng thái pitch/challenge

Tôi đã chuẩn bị card và câu hỏi phản biện, nhưng chưa ghi nhận ở đây rằng hoạt động pitch/challenge đã diễn ra. Sau buổi thảo luận nhóm, tôi sẽ cập nhật trong `03-individual-reflection/reflection.md`: candidate đã challenge, câu hỏi đã đặt và việc thảo luận đó làm nhóm thay đổi nhận định như thế nào.

---

## Self-check Phase 1–2

- [x] Có ít nhất 5 problems từ trải nghiệm thật.
- [x] Có nhiều lăng kính khác nhau.
- [x] Mỗi problem có actor và dấu hiệu ban đầu.
- [x] Có top 3 Problem Cards.
- [x] Mỗi card có current workflow từ 3–7 bước.
- [x] Mỗi card có bottleneck và impact.
- [x] Mỗi card có success metric.
- [x] Có non-AI alternative.
- [x] Có AI hypothesis và human boundary.
- [x] Có draft workflow trước/sau.
- [x] Đã chọn một card ưu tiên.
- [x] Có câu hỏi để nhóm phản biện.
