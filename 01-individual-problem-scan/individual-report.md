# 01 — Individual Problem Scan

> Điền theo Phase 1 + Phase 2 trong `01-worksheet.md`. Tự scan trước, dùng AI sau để phản biện. Không copy ví dụ Weekly Report.

## Thông tin cá nhân

- Họ và tên: Ngô Lê Thủy Tiên
- Mã học viên: 2A202602614
- Vai trò / bối cảnh: Frontend Developer
- Công việc hằng tuần (3-5 gạch đầu dòng để soi problem):
  - Code và hoàn thiện các feature mới trên giao diện web theo design & spec đã chốt.
  - Fix bug từ QA/khách hàng báo về: reproduce lỗi, debug, sửa và tạo PR để review.
  - Họp sync hằng tuần với team (dev, designer, PM) để cập nhật tiến độ và chốt hướng xử lý các vấn đề đang vướng.
  - Phân tích yêu cầu khách hàng cùng dev team, designer và PM để rã yêu cầu lớn thành các task và subtask nhỏ có thể thực hiện được.
  - Estimate thời gian (story point / giờ) cho từng task và subtask trước khi bắt đầu sprint.

---

## Phase 1 — Scan 5+ problems (tối thiểu 5, khuyến khích 8-10)

**Cách điền:** mỗi dòng = việc gì + ai chịu + đo bằng gì. Cột `Dấu hiệu thật` bắt buộc có số: mất bao lâu (bấm giờ mấy lần), mấy lần/tuần, bao nhiêu người gặp, log/ticket/quote nào.

| # | Lăng kính (Lặp lại / Tốn thời gian / AI có thể tốt hơn / Pain từ người khác) | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật (số + bằng chứng) |
|---|---|---|---|---|
| 1 | Tốn thời gian | Reproduce bug do ticket QA/khách hàng thiếu bước tái hiện, môi trường, trình duyệt và screenshot/video | Frontend Dev, QA Tester | 8-10 bug/tuần, mỗi bug mất 20-30 phút chỉ để dựng lại đúng trạng thái lỗi (tổng ~4 giờ/tuần); ~3 ticket/tuần bị chuyển về "Need More Info" trong Asana. |
| 2 | AI có thể tốt hơn | Rã yêu cầu khách hàng (email/biên bản họp dạng văn xuôi) thành danh sách task và subtask cụ thể trước sprint | Frontend Dev, PM, Designer | Mỗi sprint (2 tuần) có 1 buổi phân tích yêu cầu 90 phút + 60 phút tự ngồi rã tay 1 yêu cầu lớn thành 8-12 subtask; 2/3 sprint gần nhất phát sinh thêm subtask "quên chưa liệt kê" giữa sprint. |
| 3 | Tốn thời gian | Estimate story point/giờ cho từng task và subtask: phải tự mò code cũ và tìm màn hình tương tự để đoán effort | Frontend Dev, Tech Lead, PM | Sprint planning 2 tuần/lần mất 60-75 phút riêng cho khâu estimate ~12 task; sai lệch estimate vs. actual trung bình 30-40% trên các task đụng vào code legacy. |
| 4 | Lặp lại | Dựng lại UI component từ Figma thủ công: đọc spacing, màu, font, state hover/disabled rồi gõ lại thành code | Frontend Dev | 4-6 component mới/sprint, mỗi component mất 40-60 phút cho riêng phần convert design → markup/CSS (chưa tính logic); trung bình 2 vòng sửa lại vì lệch spacing/màu so với design. |
| 5 | Lặp lại | Viết mô tả Pull Request + checklist self-review trước khi gửi cho reviewer | Frontend Dev, Reviewer/Tech Lead | 5-7 PR/tuần, mỗi PR mất 10-15 phút viết mô tả + liệt kê file thay đổi (tổng ~1.2 giờ/tuần); PR mô tả sơ sài thường bị reviewer hỏi lại 1-2 vòng comment. |
| 6 | Pain từ người khác | PM và Designer hỏi lại trạng thái task vì Asana chưa được cập nhật kịp sau khi code xong | PM, Designer, Frontend Dev | Trung bình 5-6 lần/tuần bị nhắn Slack hỏi "task này xong chưa / đã lên staging chưa"; mỗi lần ngắt mạch code 10-15 phút. |
| 7 | Lặp lại | Fix lỗi responsive & cross-browser lặp đi lặp lại (Safari, mobile < 400px) sau khi feature đã code xong | Frontend Dev, QA Tester | ~4 bug/tuần thuộc nhóm responsive/Safari, tốn 30 phút/bug; cùng một dạng lỗi (overflow ngang, layout vỡ ở breakpoint nhỏ) lặp lại ở 3 màn hình khác nhau trong 1 tháng. |
| 8 | AI có thể tốt hơn | Viết unit test/test case cho component vừa hoàn thành (happy path + các state lỗi) | Frontend Dev, QA Lead | 3-4 component/tuần cần test, mỗi bộ test mất 45 phút; coverage FE hiện ~45%, thường bị bỏ qua khi sát deadline sprint. |

> Gợi ý tự soi: tuần trước mất nhiều thời gian nhất vào việc gì? Việc gì hay trì hoãn? Người khác hay hỏi lại câu gì? Workflow nào ai cũng biết là chậm?

**AI đã dùng ở Phase 1 (nếu có):**
- Prompt đã hỏi: `"Tôi là Frontend Developer trong team có PM và Designer, công việc hằng tuần gồm code feature, fix bug, họp sync, estimate task và rã yêu cầu khách hàng thành task và subtask. Liệt kê các điểm nghẽn (bottleneck) lặp lại trong quy trình này và gợi ý cách đo bằng số."`
- Ý dùng được: Gợi ý tách riêng nhóm "công việc trước khi code" (rã yêu cầu, estimate) và "công việc sau khi code" (viết PR, fix bug QA trả về) — nhờ đó soi ra được problem #2, #3 và #5 mà ban đầu tôi bỏ sót vì nghĩ chỉ có việc code mới đáng tính.
- Ý bỏ vì không phải pain thật: Gợi ý "tự động hoá CI/CD pipeline và tối ưu bundle size" — đây là việc của DevOps/Tech Lead trong team tôi, bản thân tôi không làm hằng tuần và không có số liệu thời gian thực tế để chứng minh.

**Self-check Phase 1:**
- ✅ Đủ 5+ dòng, mỗi dòng có actor + số đo cụ thể (đã làm 8 dòng)
- ✅ Dùng ít nhất 3/4 lăng kính (đã dùng cả 4 lăng kính)
- ✅ Không có dòng chung chung kiểu "mất nhiều thời gian"

---

## Phase 2 — Top 3 Problem Cards

### 2.1. Chọn top 3

Giữ bài nào: actor cụ thể, workflow vẽ được 3-7 bước, bottleneck ở 1 bước, impact đo được. Loại bài quá rộng.

| Rank | Lấy từ Phase 1 | Problem (copy từ bảng scan) | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|---|
| 1 | Dòng #2 | Rã yêu cầu khách hàng (email/biên bản họp dạng văn xuôi) thành danh sách task và subtask cụ thể trước sprint | 1. Sót task ở bước này kéo theo vỡ estimate cả sprint (sai lệch 30-40%).<br>2. Workflow từ text thô sang danh sách việc có cấu trúc rất hợp với LLM.<br>3. Ảnh hưởng cả 3 vai: Dev, PM, Designer. | Liệu AI có nắm được các ràng buộc ngầm của dự án (phân quyền theo role, dữ liệu cũ) mà chỉ người làm lâu mới biết? |
| 2 | Dòng #1 | Reproduce bug do ticket QA/khách hàng thiếu bước tái hiện, môi trường, trình duyệt và screenshot/video | 1. Tốn nhiều thời gian nhất trong tuần (~4 giờ/tuần).<br>2. Bottleneck nằm gọn ở 1 bước: vòng hỏi-đáp làm rõ context.<br>3. Có số đo sẵn trong Asana (số ticket "Need More Info"). | Người báo lỗi thường chỉ gửi 1-2 câu kiểu "tôi thấy lỗi ở chỗ này chỗ kia", ảnh chụp màn hình thì cắt cụt không thấy full link web, cũng không có log để check lại — vậy AI lấy context ở đâu để chuẩn hoá được bước tái hiện? |
| 3 | Dòng #4 | Dựng lại UI component từ Figma thủ công: đọc spacing, màu, font, state hover/disabled rồi gõ lại thành code | 1. Lặp lại 4-6 lần/sprint với cùng một dạng thao tác.<br>2. Bottleneck rõ ở bước gõ markup/CSS theo design token.<br>3. Kết quả đo được bằng số vòng designer trả về. | AI sinh code có bám đúng design token & convention của dự án không, hay tự chế class mới? |

> Các dòng còn lại của Phase 1 (#3 estimate, #5 mô tả PR, #6 hỏi lại trạng thái task, #7 responsive/cross-browser, #8 unit test) tạm loại: #3 đã nằm gọn trong workflow của Card #1; #6 là vấn đề quy trình cập nhật Asana chứ không cần AI; #5, #7, #8 impact nhỏ hơn và chưa đo được rõ bằng 3 bài trên.

### 2.2. Problem Cards chi tiết (lặp lại cho cả 3 cards)

---

#### Problem Card #1 — Rã yêu cầu khách hàng thành danh sách task và subtask

```text
Problem 1 câu:
Frontend Dev mất khoảng 140 phút mỗi sprint (ngoài buổi họp phân tích 90 phút) để tự đọc biên bản họp/email khách hàng rồi rã tay thành 8-12 task và subtask rồi estimate, nhưng 2/3 sprint gần nhất vẫn phát sinh task bị bỏ sót giữa sprint.

Actor:
Frontend Developer, Product Manager, Designer, Tech Lead.

Thời điểm / bối cảnh:
Đầu mỗi sprint (2 tuần/lần), sau buổi phân tích yêu cầu với khách hàng và trước buổi sprint planning.

Current workflow 3-7 bước:
1. Đọc email/biên bản họp + tài liệu yêu cầu khách hàng gửi (20 phút).
2. Họp phân tích yêu cầu cùng PM & Designer để làm rõ scope và luồng màn hình (90 phút).
3. Đối chiếu yêu cầu với Figma và code hiện có để xem cái gì tái sử dụng được, cái gì phải làm mới (30 phút).
4. Tự ngồi rã thành 8-12 task và subtask, viết mô tả từng việc trên Asana (60 phút) <-- BOTTLENECK.
5. Estimate story point cho từng task rồi gửi PM/Tech Lead confirm (30 phút).

Bottleneck:
Bước 4: rã yêu cầu văn xuôi thành task có cấu trúc tốn 60 phút và phụ thuộc hoàn toàn vào trí nhớ cá nhân, nên hay sót các đầu việc "ẩn" (validation, state lỗi, responsive, phân quyền theo role).

Impact:
Trung bình 3 task phát sinh giữa sprint mỗi lần, làm estimate lệch 30-40% và PM phải cắt scope giữa chừng.

Success metric:
Giảm thời gian rã task + estimate từ 90 phút xuống 30 phút mỗi sprint; giảm số task phát sinh giữa sprint từ 3 xuống còn tối đa 1.

Non-AI alternative:
Dùng checklist template rã task chuẩn cho mọi feature (nhược điểm: vẫn phải tự đọc và map thủ công, checklist cứng không bám được đặc thù từng yêu cầu khách hàng).

AI hypothesis:
Dùng LLM đọc biên bản họp + mô tả yêu cầu + danh sách màn hình Figma để sinh draft task và subtask theo template cố định (component mới / sửa component cũ / tích hợp API / state & validation / responsive / test), kèm khoảng estimate gợi ý dựa trên các task tương tự đã làm trong repo.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #1** (ASCII / Mermaid / ảnh đính kèm):

```text
CURRENT STATE — 230 phút / sprint

[1. Đọc yêu cầu KH: 20'] → [2. Họp phân tích với PM & Designer: 90'] → [3. Đối chiếu Figma & code cũ: 30'] → [4. Rã tay 8-12 task và subtask trên Asana: 60'] <-- bottleneck → [5. Estimate & gửi PM confirm: 30']

FUTURE STATE — 120 phút / sprint (giữ nguyên buổi họp 90')

[1. Họp phân tích với PM & Designer: 90'] → [2. Paste biên bản + link Figma cho AI: 5'] → [3. AI sinh draft task/subtask + khoảng estimate: 3'] → [4. Dev & PM review, cắt/gộp/bổ sung task: 20'] <-- human boundary → [5. Đẩy sang Asana: 2']

Fallback: Subtask nào AI không tìm được task tương tự trong lịch sử sẽ bị gắn cờ "low confidence" và để trống estimate, Dev cùng Tech Lead chốt tay số cuối trong sprint planning.
```

File đính kèm (nếu vẽ riêng): `01-individual-problem-scan-workflow-card-1.png`

---

#### Problem Card #2 — Reproduce bug từ ticket QA/khách hàng thiếu context

```text
Problem 1 câu:
Frontend Dev mất khoảng 4 giờ/tuần chỉ để đoán màn hình và môi trường, hỏi lại người báo lỗi rồi dựng lại trạng thái dữ liệu cho 8-10 bug ticket mà nội dung chỉ có 1-2 câu mô tả kèm một ảnh chụp bị cắt cụt, trước khi thực sự bắt đầu debug.

Actor:
Frontend Developer, QA Tester, người báo lỗi (CSKH hoặc người dùng nội bộ).

Thời điểm / bối cảnh:
Mỗi khi có bug ticket mới được QA hoặc CSKH tạo trên Asana, đặc biệt là bug P1 cần xử lý trong ngày.

Current workflow 3-7 bước:
1. Nhận task trên Asana và đọc mô tả lỗi (3 phút).
2. Soi ảnh chụp màn hình đính kèm để đoán đang ở route nào, account nào, role gì, trình duyệt nào - ảnh thường bị crop mất thanh địa chỉ nên không thấy full link (5 phút).
3. Comment ticket hoặc nhắn Slack hỏi lại link đầy đủ, tài khoản test, bước tái hiện rồi chờ phản hồi (10 phút thao tác, có ticket chờ tới nửa ngày) <-- BOTTLENECK.
4. Dựng lại đúng state dữ liệu trên môi trường staging cho tới khi lỗi xuất hiện (7 phút).
5. Bắt đầu debug và khoanh vùng component gây lỗi.

Bottleneck:
Bước 3: vòng hỏi-đáp làm rõ context. Người báo lỗi thường chỉ viết kiểu "tôi thấy lỗi ở chỗ này chỗ kia", không có link, không có log, nên khoảng 3 ticket/tuần bị chuyển về trạng thái "Need More Info" và dev phải bỏ dở việc đang làm rồi quay lại sau.

Impact:
~4 giờ/tuần không tạo ra dòng code nào; bug P1 bị trễ 0.5-1 ngày chỉ vì chờ thông tin, và cả team FE đều gặp cùng vấn đề.

Success metric:
Giảm thời gian trung bình từ lúc nhận ticket đến lúc reproduce được từ 25 phút xuống 10 phút; giảm số ticket "Need More Info" từ 3 xuống tối đa 1 ticket/tuần.

Non-AI alternative:
Bắt buộc template bug report có field link đầy đủ + tài khoản test + bước tái hiện, và hướng dẫn chụp màn hình phải lấy cả thanh địa chỉ (nhược điểm: người báo lỗi vẫn gõ 1-2 câu cho xong, ảnh vẫn crop thiếu, và không ai chịu cài extension ghi log chỉ để báo lỗi).

AI hypothesis:
Một AI agent gắn vào webhook tạo ticket, làm việc với đúng thứ đang có là 1-2 câu mô tả + 1 ảnh crop: đối chiếu ảnh chụp với thư viện ảnh các màn hình của sản phẩm để đoán 2-3 route nghi ngờ, đọc mô tả để suy ra chức năng đang lỗi, rồi tự comment hỏi lại người báo lỗi ngay bằng một checklist ngắn 4 câu (link đầy đủ, tài khoản/role, trình duyệt, thao tác trước khi lỗi) thay vì đợi dev phát hiện ticket thiếu thông tin sau nửa ngày.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết
```

**Draft workflow Card #2:**

```text
CURRENT STATE — 25 phút / bug (x 8-10 bug/tuần)

[1. Đọc ticket: 3'] → [2. Đoán môi trường: 5'] → [3. Hỏi lại reporter & chờ: 10'] <-- bottleneck → [4. Dựng lại state trên staging: 7'] → [5. Bắt đầu debug]

FUTURE STATE — 10 phút / bug

[1. Ticket được tạo → webhook: 1'] → [2. AI match ảnh chụp với thư viện màn hình, đoán 2-3 route nghi ngờ: 2'] → [3. AI tự comment checklist 4 câu hỏi reporter ngay: 1'] → [4. Dev đọc bản chuẩn hoá & dựng lại state: 6'] <-- human boundary

Fallback: Nếu ảnh crop quá ít thông tin để AI khớp được route nào và reporter không trả lời checklist trong 2 giờ, AI gắn nhãn "Cannot reproduce - need screen share" để QA Lead hẹn gọi share màn hình trực tiếp thay vì để ticket treo.
```

File đính kèm: `01-individual-problem-scan-workflow-card-2.png`

---

#### Problem Card #3 — Dựng UI component từ Figma thành code thủ công

```text
Problem 1 câu:
Frontend Dev mất 60 phút cho mỗi component mới chỉ để đọc spec Figma rồi gõ lại thành markup/CSS theo đúng design token, với 4-6 component mỗi sprint và trung bình 2 vòng designer trả về vì lệch spacing/màu.

Actor:
Frontend Developer, Designer.

Thời điểm / bối cảnh:
Trong sprint, ngay sau khi design được chốt và trước khi ghép logic/API vào component.

Current workflow 3-7 bước:
1. Mở Figma, đọc spec spacing, màu, font, các state hover/disabled/error của component (10 phút).
2. Kiểm tra design system trong repo xem đã có component tương tự để tái sử dụng chưa (5 phút).
3. Gõ markup + CSS/Tailwind theo đúng design token của dự án (25 phút) <-- BOTTLENECK.
4. So lại pixel với Figma và chỉnh các chỗ lệch spacing/màu (10 phút).
5. Gửi Designer review, nhận feedback và sửa vòng 2 (10 phút).

Bottleneck:
Bước 3: thao tác "dịch" thuộc tính design sang code hoàn toàn thủ công, lặp lại giống nhau ở mọi component nhưng vẫn dễ gõ sai token nên phải quay lại bước 4-5.

Impact:
Khoảng 5 giờ/sprint chỉ cho phần convert design sang code; vòng review với Designer kéo dài thêm khoảng 1 ngày cho mỗi component.

Success metric:
Giảm thời gian mỗi component từ 60 phút xuống 25 phút; giảm số vòng Designer trả về từ 2 xuống tối đa 1.

Non-AI alternative:
Chuẩn hoá design token và mở rộng component library dùng chung (nhược điểm: chỉ giúp với component đã có sẵn trong library, component hoàn toàn mới vẫn phải gõ tay từ đầu).

AI hypothesis:
Dùng AI đọc Figma frame (qua plugin/MCP) cùng file design token của dự án để sinh draft markup + class đúng token, dev chỉ review và bổ sung logic, state và accessibility.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #3:**

```text
CURRENT STATE — 60 phút / component

[1. Đọc spec Figma: 10'] → [2. Check design system: 5'] → [3. Gõ markup + CSS theo token: 25'] <-- bottleneck → [4. So pixel & chỉnh lệch: 10'] → [5. Designer review & sửa vòng 2: 10']

FUTURE STATE — 25 phút / component

[1. Trỏ AI vào Figma frame + file design token: 3'] → [2. AI sinh draft markup/CSS theo token: 2'] → [3. Dev review, bổ sung logic/state/accessibility: 15'] <-- human boundary → [4. So pixel & chỉnh: 5']

Fallback: Component có animation hoặc interaction phức tạp, hoặc AI sinh class không nằm trong design token, thì dev dựng tay từ component gần nhất trong design system thay vì sửa code AI.
```

File đính kèm: `01-individual-problem-scan-workflow-card-3.png`

---

### 2.3. Card muốn pitch nhất (chuẩn bị 2 phút)

**Card tôi muốn pitch nhất:**

```text
Problem Card #1 — Rã yêu cầu khách hàng thành danh sách task và subtask (Phase 1, dòng #2)
```

**Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):**

```text
Đây là bước đầu vào của cả sprint: nếu rã sót task thì mọi thứ phía sau (estimate, commitment với khách hàng) đều lệch theo. Hiện tôi mất 90 phút mỗi sprint để rã tay và estimate 8-12 task, nhưng 2/3 sprint gần nhất vẫn phát sinh trung bình 3 task giữa chừng khiến estimate sai 30-40%. Nếu để AI sinh draft task theo template rồi Dev và PM chỉ review, thời gian giảm còn 30 phút và quan trọng hơn là các đầu việc "ẩn" như validation, state lỗi hay responsive không bị bỏ quên.
```

**Câu hỏi tôi muốn nhóm challenge (1-2 câu hỏi đúng chỗ yếu):**

```text
"AI chỉ đọc được biên bản họp và Figma, vậy làm sao nó biết các ràng buộc ngầm của dự án (phân quyền theo role, dữ liệu cũ chưa migrate) mà chỉ người làm lâu mới nắm - và khi đó khoảng estimate AI gợi ý còn đáng tin không?"
```

**AI phản biện Card (nếu có):**
- Điểm yếu AI chỉ ra: Estimate gợi ý dựa trên các task lịch sử sẽ lệch rất mạnh với những task đụng vào code legacy chưa từng có tiền lệ trong repo, dễ khiến team commit nhầm scope với khách hàng.
- Tôi sửa gì: Đổi output estimate từ một con số sang khoảng min-max, và bắt buộc AI gắn cờ "low confidence" + để trống estimate cho task không tìm được task tương tự. Đồng thời yêu cầu AI luôn xuất thêm mục "Giả định & câu hỏi cần làm rõ với PM" thay vì tự suy diễn ràng buộc nghiệp vụ.

### Self-check nộp phần 01
- ✅ Có 5+ problems + top 3 Cards đủ field (đã làm 8 problems & 3 Cards chi tiết)
- ✅ Mỗi Card có workflow trước/sau + bottleneck + metric + fallback
- ✅ Đã chọn 1 card pitch + câu hỏi challenge
