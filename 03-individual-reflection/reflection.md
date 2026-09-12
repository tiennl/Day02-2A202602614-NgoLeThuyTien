# 03 — Individual Reflection

> Viết bằng lời của bạn (Phase 7 trong `01-worksheet.md`). Có thể dùng AI gợi ý câu hỏi tự soi, không dùng AI viết thay. 8-12 câu, có chuyện cụ thể.

## Thông tin cá nhân

- Họ và tên: Ngô Lê Thủy Tiên
- Mã học viên: 2A202602614
- Nhóm: EQ200
- Candidate problem nhóm chọn: AI Workflow đếm khuẩn lạc tự động trên đĩa Petri bằng Watershed + AI Vision, có Overlay mask chấm màu cho NCV click ±1 và tự động xuất Excel.

---

## 1. Tôi đã tham gia vào phần nào?

Ghi việc cụ thể + kết quả cụ thể. Không ghi chung chung kiểu "tham gia thảo luận".

| Hoạt động | Tôi đã làm gì? (việc cụ thể) | Kết quả / ảnh hưởng tới nhóm |
|---|---|---|
| Scan cá nhân | Scan 8 problems theo đủ 4 lăng kính từ công việc Frontend hằng tuần, mỗi dòng bắt buộc có số thật: 8-10 bug/tuần × 25 phút reproduce, 90 phút rã task mỗi sprint, 4-6 component/sprint × 60 phút, 3 ticket "Need More Info"/tuần trên Asana. | Mang 3 candidate vào vòng trình bày của nhóm (#4, #5, #6 trong bảng 18 candidates), là nguồn duy nhất cho cụm bài toán quy trình phần mềm. |
| Pitch Problem Card | Pitch Card #1 "Rã yêu cầu khách hàng thành task/subtask sprint": workflow 5 bước, bottleneck ở bước 4 (rã tay 60 phút), impact 3 task phát sinh giữa sprint làm lệch estimate 30-40%. | Bài vào shortlist 6 bài và xếp hạng 2 với 31/35 điểm, chỉ thua bài đếm khuẩn lạc (35/35). |
| Challenge bài của bạn khác | Hỏi Tình: "Khuẩn dính chùm và bọt khí thì nhóm lấy gì làm ground-truth để dám nói AI đúng 93%?". Hỏi Linh: các nền tảng họp (Zoom AI Companion, Teams Copilot) đã tóm tắt action item sẵn rồi, phần còn lại cho mình là gì? | Nhóm bổ sung cách đo độ chính xác bằng đối chiếu với 2 chuyên gia đếm độc lập; candidate #10 bị loại với lý do khoảng trống sản phẩm quá hẹp. |
| Gom trùng / cluster | Gộp 3 bài cùng dạng "bóc tách văn bản thô thành việc có cấu trúc" (#1 của Dũng, #4 của tôi, #10 của Linh) thành 1 cụm để chấm 1 lần. | Từ 18 candidate rút còn 6 bài shortlist, tránh việc nhóm chấm điểm 3 lần cho cùng một pattern bài toán. |
| Chọn candidate problem | Tự chấm bài của chính mình 4/5 ở cột "Impact đo được" và "Làm trong lab" vì không xây được ground-truth khách quan cho danh sách task do AI sinh ra; bỏ phiếu cho bài Petri. | Nhóm không phải tranh luận dài giữa 2 bài dẫn đầu; chốt đồng thuận 100% cho bài đếm khuẩn lạc. |
| Validation / research | Rà lại số liệu Linh phỏng vấn về: yêu cầu quy đổi câu "đếm lệch nhau 10-15%" thành một phép đo kiểm chứng được — 2 kỹ thuật viên đếm độc lập trên cùng 30 đĩa thật. | Bảng 4.1 có thêm dòng "Log / dữ liệu thực nghiệm 30 đĩa" với con số lệch 8-16% khi > 100 CFU, thay vì chỉ có cảm nhận từ interview. |
| Workflow nhóm | Soi future workflow 5 bước và đặt 2 câu hỏi: ảnh mờ/đĩa thạch nứt thì hệ thống làm gì, và 45 giây review có đủ cho đĩa 250 CFU không. | Nhóm thêm fallback "Ảnh không đạt chuẩn, vui lòng chụp lại / quay về đếm tay"; con số 45 giây được ghi nhận là giả định cần đo lại trong pilot. |
| Problem Statement | Viết lại 2 field Success Metric và Boundary cho v1: tách metric thành 3 dòng đo được, và tách Boundary thành LÀM / KHÔNG LÀM với giới hạn TNTC > 300 CFU, dải tối ưu 30-300 CFU. | PS v1 có boundary 3 ý "KHÔNG LÀM" rõ ràng (không tự lưu khi chưa review, không định danh chủng, không xử lý đĩa TNTC) thay vì mô tả chung chung. |
| Rule / Workflow / Agent | Phản biện phương án Agent (robot lấy đĩa, tự chỉnh tiêu cự, tự gửi mail kết quả) bằng câu hỏi: nếu AI tự lưu và tự gửi một kết quả sai thì ai là người phát hiện ra? | Nhóm chốt mức Workflow, chỉ giữ Rule ở bước 5 (format + ghi Excel), không làm Agent. |
| Decision | Viết 3 điều kiện exit/rollback định lượng và 3 số đo của pilot 30 đĩa (thời gian/đĩa, độ chính xác sau review, tỷ lệ phải click sửa ±1). | Quyết định Go đi kèm điều kiện dừng cụ thể, không phải Go vô điều kiện. |

**Dấu tay rõ nhất của tôi trong artifact cuối (1-2 câu):**

```text
Phần Success Metric, Boundary (LÀM / KHÔNG LÀM) trong PS v1 và toàn bộ 3 điều kiện exit/rollback ở Phase 6.3 là do tôi viết.
Cụ thể là việc tách "độ chính xác ≥ 93% sau khi NCV review" (metric thành công) khỏi "độ chính xác < 80% trước khi con người can thiệp" (ngưỡng dừng dự án) — trước đó nhóm chỉ có một con số 93% duy nhất và không ai biết nó đo ở thời điểm nào.
```

---

## 2. Bảng dùng AI (mỗi dòng 1 phase có dùng AI — 2 cột cuối bắt buộc)

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Hỏi AI liệt kê bottleneck lặp lại trong công việc hằng tuần của một Frontend Dev làm việc cùng PM và Designer, kèm gợi ý cách đo bằng số. | Gợi ý tách riêng "việc trước khi code" (rã yêu cầu, estimate) và "việc sau khi code" (viết PR, fix bug QA trả về) — nhờ đó tôi soi ra problem #2, #3, #5 vốn bị bỏ sót vì tôi mặc định chỉ việc code mới đáng tính. | Gợi ý "tự động hoá CI/CD pipeline và tối ưu bundle size" — đó là việc của DevOps/Tech Lead, tôi không làm hằng tuần và không có số liệu thời gian thật. | Bỏ hết các dòng không tự bấm giờ hoặc không đếm được bằng ticket Asana; chỉ giữ 8 dòng mà tôi trả lời được câu "mất bao lâu, mấy lần/tuần, bằng chứng ở đâu". |
| Problem Card | Nhờ AI phản biện Card #1 (rã yêu cầu thành task sprint) để tìm điểm yếu trước khi mang đi pitch. | Chỉ ra rằng estimate gợi ý dựa trên task lịch sử sẽ lệch rất mạnh ở task đụng code legacy chưa từng có tiền lệ trong repo, dễ khiến team commit nhầm scope với khách hàng. | AI chỉ nêu rủi ro chung chung, không đề xuất cơ chế chặn rủi ro đó; và vẫn khuyên "cứ dùng AI estimate cho nhanh". | Đổi output estimate từ 1 con số sang khoảng min-max, bắt AI gắn cờ "low confidence" và để trống estimate khi không tìm được task tương tự, thêm mục bắt buộc "Giả định & câu hỏi cần làm rõ với PM" thay vì để AI tự suy diễn ràng buộc nghiệp vụ. |
| Workflow | Nhờ AI rà lại future workflow 5 bước của nhóm xem thiếu nhánh nào. | Nhắc rằng workflow chỉ mô tả đường đi thuận lợi (happy path), chưa có nhánh xử lý khi đầu vào không đạt chuẩn. | AI mô tả một future state rất mượt nhưng mặc định ảnh chụp luôn đủ nét và đĩa thạch luôn nguyên vẹn — đúng thứ không bao giờ xảy ra trong lab thật. | Đề xuất nhóm thêm fallback ngay ở bước 1: ảnh mờ/rung/đĩa nứt thì hệ thống cảnh báo chụp lại hoặc cho NCV quay về đếm tay trên bàn soi. |
| Research | Không dùng. Phần này Khoa phụ trách; tôi chỉ mở lại 3 link (OpenCFU, ImageJ Colony Counter, Interscience Scan 1200) để kiểm tra link còn sống và điểm yếu ghi trong bảng có đúng như tài liệu gốc không. | — | — | — |
| Problem Statement | Nhờ AI soi xem field nào trong PS v0 còn mơ hồ. | Chỉ đúng chỗ đau nhất: "độ chính xác ≥ 93%" chưa nói rõ đo so với cái gì và đo ở thời điểm nào — trước hay sau khi NCV click ±1. | AI đề xuất bổ sung một loạt metric nghe rất kỹ thuật (precision, recall, F1, IoU) — chính xác về mặt thuật toán nhưng NCV và trưởng phòng lab không đọc được, và không ai trong lab đo được bằng tay. | Giữ đúng 3 metric mà người trong lab tự kiểm chứng được (phút/đĩa, % chính xác so với 2 chuyên gia đếm tay, số thao tác gõ Excel), rồi tự tách thành 2 mốc: ≥ 93% sau review là mục tiêu, < 80% trước review là ngưỡng rollback. |
| Rule / Workflow / Agent | Hỏi AI khi nào một bài toán đếm vật thể trên ảnh mới thật sự cần tới Agent. | Xác nhận rằng pipeline có thứ tự bước cố định thì Workflow là đủ, không cần khả năng tự lập kế hoạch. | Lần hỏi đầu, do tôi mô tả bài toán "nhiều bước, nhiều công nghệ", AI lập tức vẽ ra một kiến trúc multi-agent có agent điều phối — solution-first, phức tạp hơn nhu cầu thật. | Quay lại 5 câu hỏi chốt trong worksheet, thấy quy trình đi thẳng một đường không rẽ nhánh và người review đứng ngay ở bước 4, nên chốt Workflow và chỉ để Rule ở bước export Excel. |
| Decision | Nhờ AI liệt kê các điều kiện rollback thường gặp khi triển khai một AI workflow trong phòng lab. | Gợi ý đúng nguyên tắc: ngưỡng dừng phải là số đo được, không được viết kiểu "khi thấy không hiệu quả nữa". | Ngưỡng AI đưa ra là con số chung chung (accuracy < 90%) không gắn với thao tác thật của NCV, và thiếu hẳn điều kiện về thời gian. | Quy đổi thành 3 điều kiện quan sát được ngay tại bàn làm việc: độ chính xác trước review < 80%, NCV phải click sửa > 20 lần/đĩa, hoặc tổng thời gian thao tác > 10 phút/đĩa (tức là chậm hơn đếm tay). |

> Nếu phase nào không dùng AI, ghi `Không dùng` và vì sao tự làm.

---

## 3. Reflection câu hỏi mở

Chọn 3-4 câu trong 6 câu dưới để viết thành đoạn 8-12 câu (không trả lời bullet 1 dòng):
- Tôi học được gì khi nghe top 3 problems của các bạn khác?
- Nhóm có lúc nào bị solution-first, đòi làm Agent cho ngầu không?
- Tôi có thay đổi ý kiến sau khi bị challenge không, vì sao đổi?
- Tôi đóng góp gì thật sự vào artifact cuối, phần nào có dấu tay của tôi?
- Điều khó nhất khi viết Problem Statement là gì, metric hay boundary?
- Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

**Reflection:**

```text
Tôi vào lab với niềm tin khá chắc rằng bài "rã yêu cầu khách hàng thành task sprint" của mình sẽ là bài nhóm chọn, vì nó có số đẹp: 90 phút mỗi sprint, 3 task phát sinh giữa chừng, estimate lệch 30-40%. Nghe top 3 của các bạn khác, đặc biệt là bài đếm khuẩn lạc đĩa Petri của Tình, tôi mới thấy mình đang thiếu một thứ mà các con số của tôi không bù được: ground-truth. Với đĩa Petri, "đúng" là một con số mà hai chuyên gia đếm tay độc lập có thể kiểm chứng; còn với danh sách task do AI sinh ra, "đúng" phụ thuộc vào gu của từng Tech Lead, nên tôi không có cách nào chứng minh AI làm tốt hay tệ. Lúc chấm điểm, chính tôi là người hạ bài của mình xuống 4/5 ở cột "Impact đo được" chứ không phải ai khác ép, và đó là lúc tôi hiểu bài toán tốt cho AI không phải bài đau nhất với mình, mà là bài mà mình định nghĩa được thế nào là đúng.

Nhóm tôi có bị solution-first, và chính tôi mắc trước tiên. Trong Card #2 của phần cá nhân, tôi đã tick "Agent" cho bài reproduce bug chỉ vì nghe một AI tự đọc ticket rồi tự comment hỏi lại reporter thì oai hơn là một cái template bug report bắt buộc điền. Khi lên nhóm, xu hướng đó lặp lại ở bài Petri với đề xuất robot tự lấy đĩa, tự chỉnh tiêu cự, tự gửi mail kết quả. Tôi hỏi lại một câu duy nhất: nếu AI tự lưu và tự gửi một kết quả đếm sai thì ai là người phát hiện ra, và sau bao lâu? Không ai trả lời được, và nhóm hạ ngay xuống mức Workflow — giữ con người ở bước click ±1 trước khi bấm Export.

Khó nhất khi viết Problem Statement, với tôi, không phải metric mà là boundary. Metric chỉ là chọn con số và cách đo, làm một lần là xong; boundary buộc nhóm phải nói ra những thứ mình cố tình không làm, và mỗi dòng "KHÔNG LÀM" là một lần phải cãi nhau — không định danh chủng vi khuẩn, không tự lưu kết quả khi chưa có NCV xác nhận, không nhận đĩa TNTC trên 300 CFU. Ai cũng muốn sản phẩm làm được nhiều hơn, nên viết boundary là phần bị phản đối nhiều nhất. Nhưng nhờ dừng lại ở dải 30-300 CFU mà cả metric lẫn kế hoạch pilot 30 đĩa mới trở nên đo được, thay vì hứa một thứ hệ thống không gánh nổi.

Nếu làm lại, tôi sẽ challenge mạnh hơn ở đúng con số 93%. Đó là con số nhóm đặt ra theo kỳ vọng, không phải rút ra từ một lần thử thật nào, và tôi đã dừng lại ở chỗ làm rõ cách đo thay vì hỏi thẳng: dựa vào đâu mà là 93% chứ không phải 85%? Tôi cũng sẽ đẩy phần validation xa hơn 3 người phỏng vấn, vì cả ba đều làm trong cùng một mô hình phòng lab, và chỉ cần một lab dùng môi trường nuôi cấy khác (thạch máu, MacConkey) là giả định về màu sắc và độ tương phản của ảnh đầu vào có thể sập.
```

---

## 4. Tự kiểm cuối bài (check trước khi nộp repo)

- ✅ [12đ] Cá nhân có 5+ problems + top 3 Problem Cards — 8 problems, 3 Problem Cards đủ field
- ✅ [12đ] Tôi đã pitch rõ + challenge nhóm đúng trọng tâm (ghi ở bảng mục 1)
- ✅ Nhóm có nhật ký hội tụ từ candidates về 1 bài — 18 candidates → cluster → shortlist 6 → score → 1 bài
- ✅ [15đ] Nhóm có workflow trước/sau — 6 bước (15-20'/đĩa) → 5 bước (< 2'/đĩa), có handoff, bottleneck, fallback
- ✅ [20đ] Nhóm có PS v0/v1 với metric + boundary rõ
- ✅ [15đ] Nhóm có so sánh No AI / Rule / Workflow / Agent — chọn Workflow, Rule ở bước export, không làm Agent
- ✅ [10đ] Nhóm có Go / Not Yet / No-Go + lý do rõ — Go, kèm pilot 30 đĩa và 3 điều kiện rollback
- ✅ [10đ] Reflection này có vai trò thật + AI giúp/sai ở đâu + điều học được + nếu làm lại đổi gì
- ✅ [6đ] Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp AI
