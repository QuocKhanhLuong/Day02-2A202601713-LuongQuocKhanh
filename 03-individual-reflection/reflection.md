# Individual Reflection — Day 02

## Thông tin cá nhân

- **Họ và tên:** Lương Quốc Khánh
- **Mã học viên:** 2A202601713
- **Candidate problem cá nhân ưu tiên:** Theo dõi task và deadline đa nền tảng
- **Candidate problem nhóm lựa chọn:** Theo dõi task và deadline từ nhiều nền tảng
- **Quyết định cuối:** Go cho pilot Workflow phạm vi hẹp; Not Yet cho Agent và tích hợp toàn bộ nền tảng

---

## Tôi đã tham gia vào phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng |
|---|---|---|
| Scan cá nhân | Tôi scan 10 vấn đề từ trải nghiệm học tập, nghiên cứu và làm project. Sau khi nhận ra danh sách ban đầu còn quá rộng, tôi đưa persona của chính mình vào trung tâm và bổ sung actor, thời gian, tần suất hoặc dấu hiệu cụ thể cho từng vấn đề. | Danh sách cuối có đủ bốn lăng kính và giúp tôi nhận ra một pattern chung: phần lớn pain của tôi đến từ thông tin bị phân tán và phải tự nối lại ngữ cảnh. |
| Pitch Problem Card | Tôi chọn bài toán theo dõi task và deadline đa nền tảng để pitch. Tôi trình bày workflow phải kiểm tra Gmail, nhóm chat, Discord, GitHub và Calendar; baseline khoảng 20–30 phút/ngày và 3–5 lượt kiểm tra. | Candidate có actor, workflow, bottleneck và metric đủ rõ để các thành viên khác đối chiếu với trải nghiệm của họ. |
| Challenge bài của bạn khác | Tôi dùng câu hỏi: vấn đề cốt lõi nằm ở dữ liệu phân tán hay do người dùng chưa có một quy trình quản lý thống nhất; nếu Calendar, task manager và Rule đã đủ thì AI tạo thêm giá trị ở đâu? | Câu hỏi này giúp nhóm không nhảy ngay sang ý tưởng “AI agent quản lý mọi thứ”, đồng thời buộc nhóm giữ một baseline non-AI để so sánh trong pilot. |
| Gom trùng / cluster | Tôi đối chiếu 12 candidate problems của bốn thành viên và nhận ra các ý tưởng về daily standup, lịch họp, deadline tracker và task đa nền tảng thuộc cùng một cluster. | Nhóm hội tụ được một pain chung thay vì chọn một ý tưởng quá riêng cho từng domain. Ba thành viên đều có evidence trực tiếp với workflow này. |
| Chọn candidate problem | Tôi ủng hộ chọn bài toán theo dõi task/deadline vì xảy ra hằng ngày, actor rõ, có baseline định lượng, có thể vẽ before/after và có thể so sánh Rule–Workflow–Agent. | Nhóm lựa chọn candidate này thay vì Literature Review hoặc dashboard debugging, vì phạm vi dễ validate hơn và gần với trải nghiệm chung của nhóm. |
| Validation / research | Tôi tổng hợp evidence nội bộ từ báo cáo cá nhân: mất khoảng 15–30 phút/ngày, kiểm tra nhiều nền tảng, có trường hợp trễ daily hoặc bỏ sót deadline. Tôi cũng cùng nhóm đối chiếu với các hướng non-AI như Calendar, Google Tasks, Todoist, Zapier và workflow connector. | Nhóm nhận ra pain có thật nhưng evidence hiện mới chủ yếu từ nội bộ. Vì vậy báo cáo không coi baseline là kết luận chính thức và đề xuất time-log, labeled sample cùng so sánh Rule-only trong pilot. |
| Workflow nhóm | Tôi đóng góp current workflow và future workflow. Tôi nhấn mạnh tách nguồn structured và unstructured: Rule xử lý Calendar/GitHub/Notion có schema; AI chỉ parse email/chat tự do; người dùng Confirm/Edit/Dismiss trước khi tạo task. | Workflow tương lai có human boundary, source link, confidence và fallback rõ. Hệ thống không tự hành động khi nội dung hoặc deadline chưa chắc chắn. |
| Problem Statement | Tôi đóng góp phần actor, bottleneck, baseline, target và boundary. Tôi cùng nhóm thu hẹp bài toán từ “quản lý tất cả công việc” thành “thu thập candidate task/deadline từ nguồn được cấp quyền vào một inbox để người dùng xác nhận”. | Problem Statement v1 cụ thể hơn, đo được và tránh solution-first. Phạm vi không bao gồm tự gửi báo cáo, tự xác nhận lịch hoặc tự thay đổi deadline. |
| Rule / Workflow / Agent | Tôi đề xuất chọn Workflow. Rule là component cho nguồn có cấu trúc và deduplication; AI được dùng ở bước hiểu ngôn ngữ tự nhiên; Agent chưa cần thiết vì hệ thống không cần tự lập kế hoạch hoặc tự quyết định hành động. | Nhóm chọn đúng mức tự động hóa thay vì chọn Agent chỉ vì nghe mạnh hơn. Quyết định này giảm rủi ro privacy, hành động sai và khó audit. |
| Decision | Tôi đồng ý với quyết định Go cho pilot nhỏ với bốn thành viên, Gmail/Calendar và message do người dùng chủ động đưa vào; Not Yet cho full integration và Agent. | Pilot có output cụ thể, baseline so sánh, metric và điều kiện dừng/mở rộng. Nếu AI không cải thiện rõ so với Rule, nhóm có thể quay về giải pháp đơn giản hơn. |

---

## Tôi đã dùng AI như thế nào?

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Tôi dùng AI sau khi đã tự nêu bối cảnh để mở rộng và cấu trúc danh sách problem theo bốn lăng kính. | AI giúp chuyển các quan sát rời rạc thành bảng có actor và dấu hiệu, đồng thời nhắc tôi không bắt đầu bằng solution. | Những gợi ý đầu tiên quá rộng theo nhiều ngành nghề; sau đó lại quá hẹp vào riêng research/project. Một số dấu hiệu chỉ mang tính định tính. | Tôi yêu cầu đưa persona của chính mình vào trung tâm, chọn 5 vấn đề đời sống và 5 vấn đề học tập/nghiên cứu, rồi thay các ý chung bằng trải nghiệm cụ thể của tôi. |
| Problem Card | Tôi dùng AI để đưa top 3 vào template Problem–Actor–Workflow–Bottleneck–Impact–Metric–Alternative–Hypothesis. | AI giúp bảo đảm không thiếu field và tạo workflow trước/sau dễ đọc. | Bản đầu có baseline Card 1 không thống nhất; workflow ghi “dưới 60 phút” nhưng tổng đúng 60 phút; Card 2 và Card 3 tick hai Quick gut mâu thuẫn. | Tôi dùng review để sửa baseline, đổi workflow thành 55 phút, chỉ chọn một mức Quick gut và chuyển metric sang bảng Baseline–Target–Cách đo. |
| Workflow | Tôi dùng AI để vẽ ASCII workflow, đánh dấu bottleneck, human boundary và fallback. | AI thể hiện được luồng before/after và giúp nhìn ra bước nào nên là Rule, AI hoặc con người. | AI ban đầu có xu hướng đưa quá nhiều bước vào AI và chưa làm rõ nguồn structured so với unstructured. | Tôi thu hẹp AI vào bước parse nội dung tự do; Rule làm ingestion/dedup; con người xác nhận trước mọi thay đổi chính thức. |
| Research | Tôi dùng AI và GitHub để đọc báo cáo của các thành viên, gom candidate, so sánh các existing pattern và tạo bảng khoảng trống. | AI xử lý nhanh nhiều báo cáo dài và chỉ ra sự trùng nhau giữa daily report, lịch họp và deadline tracker. | AI có thể khiến phần tổng hợp trông chắc chắn hơn evidence thật. Dữ liệu của nhóm mới là self-report và chưa có phỏng vấn ngoài nhóm. | Tôi giữ ghi chú “baseline ước tính”, không tự nhận đã validate diện rộng, và thêm kế hoạch time-log 14 ngày cùng labeled sample trong pilot. |
| Problem Statement | Tôi dùng AI để kiểm tra đủ actor, workflow, bottleneck, impact, metric và boundary. | AI giúp phát hiện statement quá rộng và hỗ trợ viết lại thành một workflow cụ thể hơn. | Bản solution-first dễ trở thành “AI assistant quản lý mọi công việc trên mọi nền tảng”, vượt quá pain đã chứng minh. | Tôi thu hẹp thành candidate-task inbox, giới hạn nguồn được cấp quyền và cấm hệ thống tự gửi, tự nhận lịch hoặc tự đổi deadline. |
| Rule / Workflow / Agent | Tôi dùng AI để phản biện ba mức giải pháp. | AI giúp tách Rule cho phần deterministic, AI cho ngôn ngữ phi cấu trúc và Agent cho tự lập kế hoạch/hành động. | Ban đầu tôi từng để Quick gut ở trạng thái vừa Workflow vừa Chưa biết, thể hiện quyết định chưa dứt khoát. | Tôi chốt Workflow và giải thích rõ Rule chỉ là component. Agent được để Not Yet vì chưa có nhu cầu tự hành động và rủi ro lớn hơn lợi ích. |
| Decision | Tôi dùng AI để xây decision table và thiết kế pilot nhỏ nhất. | AI giúp biến ý tưởng thành thử nghiệm có actor, nguồn dữ liệu, output, baseline và metric. | AI có thể đề xuất target đẹp nhưng chưa có log thật, ví dụ recall hoặc số deadline bỏ sót. | Tôi đánh dấu metric cần đo trong pilot, giới hạn claim trong các nguồn pilot và yêu cầu so sánh Rule-only với Workflow có AI trước khi mở rộng. |

---

## Reflection câu hỏi mở

### Tôi học được gì khi nghe top 3 problems của các bạn khác?

Tôi nhận ra một problem có thể xuất hiện dưới nhiều biểu hiện khác nhau. Với tôi, pain là phải kiểm tra Gmail, Calendar, GitHub và nhóm chat. Với Thu Huyền, nó xuất hiện dưới dạng trễ daily report và thiếu context trước buổi họp. Với Đức Anh, đó là deadline bị trôi trong LMS, Slack và Notion. Khi gom lại, nhóm không chọn một feature riêng như “nhắc daily” mà nhìn thấy bài toán sâu hơn: thông tin hành động và thời hạn bị phân tán, còn người dùng phải tự phát hiện, diễn giải và nhập lại.

Tôi cũng học được rằng candidate có vẻ kỹ thuật hoặc mới lạ hơn chưa chắc phù hợp hơn. Literature Review và BEV debugging đều có impact rõ, nhưng bài task/deadline có actor chung, tần suất hằng ngày và khả năng pilot nhanh hơn.

### Nhóm có lúc nào bị solution-first không?

Có. Ở giai đoạn đầu, hướng giải pháp rất dễ trượt thành một AI agent tự đọc toàn bộ email/chat, tự tạo task, tự lên lịch và tự gửi nhắc nhở. Cách nghĩ này bắt đầu từ năng lực của AI thay vì từ bottleneck thật.

Sau khi vẽ workflow, nhóm thấy phần lớn dữ liệu có cấu trúc có thể được xử lý bằng API, webhook và Rule. AI chỉ thực sự cần thiết ở bước hiểu message hoặc email phi cấu trúc. Việc tạo task, nhận lịch và thay đổi deadline vẫn phải do người dùng xác nhận. Điều này làm giải pháp ít “ngầu” hơn nhưng hợp lý và an toàn hơn.

### Tôi có thay đổi ý kiến sau khi bị challenge không?

Có. Ban đầu tôi nghĩ vấn đề phù hợp với một Agent đa nền tảng vì có nhiều nguồn dữ liệu và nhiều thao tác. Sau khi tự hỏi Rule hoặc task manager hiện có đã giải quyết được bao nhiêu phần, tôi thay đổi sang Workflow.

Tôi cũng thay đổi cách nhìn về output. Output không nên là task chính thức được tạo tự động, mà là một **Candidate Task** có title, deadline, context, source link và confidence. Người dùng quyết định Confirm, Edit hoặc Dismiss. Thay đổi này làm rõ trách nhiệm và tạo được fallback khi AI sai.

### Tôi đóng góp gì thật sự vào artifact cuối?

Đóng góp chính của tôi là đưa ra candidate task/deadline đa nền tảng từ trải nghiệm cá nhân, cung cấp baseline thời gian và tần suất, sau đó giúp hội tụ các ý tưởng tương tự của các thành viên.

Tôi cũng đóng góp vào việc thu hẹp scope, xây current/future workflow, xác định human boundary, lựa chọn Workflow thay cho Agent và thiết kế pilot so sánh Rule-only với Workflow có AI. Tôi không chỉ tổng hợp nội dung, mà còn dùng các lỗi trong bản draft ban đầu để siết lại metric và tính nhất quán của artifact.

### Điều khó nhất khi viết Problem Statement là gì?

Điều khó nhất là tách problem khỏi solution. Câu “xây một AI assistant tổng hợp task” nghe rõ nhưng thực chất mới mô tả sản phẩm. Problem Statement cần nói được ai đang gặp vấn đề, họ đang làm workflow nào, nghẽn tại bước nào, tác động ra sao, đo cải thiện bằng gì và hệ thống không được làm gì.

Khó thứ hai là metric. “Không bỏ sót deadline” nghe tốt nhưng không thể cam kết cho mọi nguồn khi hệ thống chưa được cấp quyền truy cập. Vì vậy nhóm phải sửa thành: không bỏ sót deadline đã xuất hiện trong các nguồn của pilot, đo bằng labeled sample và audit trong một khoảng thời gian xác định.

### Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

Tôi sẽ challenge sớm hơn ở ba điểm:

1. **Baseline thật:** yêu cầu mỗi thành viên time-log ít nhất 3–7 ngày thay vì dựa vào trí nhớ.
2. **Non-AI baseline:** thử trước một workflow dùng Calendar, Google Tasks và Rule để biết AI có thực sự tạo thêm giá trị hay không.
3. **Privacy và quyền truy cập:** xác định ngay nguồn nào được phép đọc, dữ liệu lưu bao lâu, người dùng xóa dữ liệu thế nào và hệ thống xử lý private chat ra sao.

Tôi cũng sẽ phỏng vấn thêm 5–10 sinh viên ngoài nhóm. Điều này giúp kiểm tra xem pain có phổ biến hay chỉ xuất hiện ở những người đang tham gia nhiều project giống nhóm tôi.

---

## Mạch tư duy tôi rút ra

```text
Problem thật
→ vẽ Current Workflow
→ xác định Bottleneck
→ đo Baseline và Impact
→ đặt Success Metric
→ xác định Boundary
→ thử Non-AI/Rule trước
→ chỉ dùng AI tại bước cần hiểu ngữ cảnh
→ đặt Human Review và Fallback
→ quyết định Go / Not Yet / No-Go
```

Bài học quan trọng nhất của tôi là **AI suitability không được quyết định bởi việc AI có làm được hay không, mà bởi AI có tạo thêm giá trị so với Rule/Workflow đơn giản hơn trong một boundary chấp nhận được hay không**.

---

## Tự kiểm cuối bài

- [x] [12đ cá nhân] Cá nhân có 5+ problems và top 3 Problem Cards.
- [x] [12đ cá nhân] Tôi đã chuẩn bị và trình bày candidate problem, đồng thời challenge nhóm về non-AI alternative và mức cần thiết của AI.
- [x] Nhóm có nhật ký hội tụ từ candidates về một bài.
- [x] [15đ nhóm] Nhóm có workflow trước/sau.
- [x] [20đ nhóm] Nhóm có Problem Statement v0/v1 với metric và boundary rõ.
- [x] [15đ nhóm] Nhóm có so sánh No AI / Rule / Workflow / Agent.
- [x] [10đ nhóm] Nhóm có quyết định Go / Not Yet / No-Go và lý do rõ.
- [x] [10đ cá nhân] Reflection cá nhân nói rõ vai trò trong nhóm, cách dùng AI, điều học được và điều sẽ thay đổi nếu làm lại.
- [x] [6đ cá nhân] Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp với AI.
