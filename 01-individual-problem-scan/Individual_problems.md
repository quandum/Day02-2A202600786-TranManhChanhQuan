# 01 — Individual Problem Scan (Template)

> Hướng dẫn: Sao chép phần dưới đây cho mỗi problem bạn scan. Điền thông tin ngắn gọn, cụ thể và có bằng chứng/ứng xử thật khi có thể.

## Scan rộng

- Mục tiêu: liệt kê ít nhất 5–10 problem liên quan đến role bạn đang phân tích.
- Gợi ý lăng kính: Lặp lại, Tốn thời gian, Pain từ người khác, AI có thể tốt hơn, Data access, Quy trình rườm rà.
- Bảng mẫu (copy cho từng problem):


| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Kỹ năng | Tôi có khó khăn trong việc phát âm | Tôi (người khuyết tật) | Gặp lỗi phát âm thường xuyên; hay bị hiểu sai |
| 2 | Di chuyển | Tôi có thể đi lại, nhưng tốc độ chậm, không thể đi xa, dễ vấp ngã | Tôi (người khuyết tật) | Đi bộ ngắn, cần nghỉ; gặp khó khăn trên quãng đường dài; dễ trượt/vấp |
| 3 | Quyết định mua | Tôi tốn rất nhiều thời gian để quyết định mua hoặc không mua một sản phẩm bất kỳ | Tôi (người tiêu dùng) | Dành nhiều thời gian research/so sánh; hay trì hoãn quyết định; bỏ giỏ hàng |
| 4 | Môi trường | Thời tiết nắng nóng mùa hè ở HN quá khắc nghiệt | Tôi (cư dân Hà Nội) | Nhiệt độ cao, khó ra ngoài, hay mệt/choáng, hoạt động ngoài trời giảm |
| 5 | Hiểu business | Tôi là người trong ngành IT, gặp khó khăn trong việc tìm hiểu góc nhìn business | Tôi (người làm IT) | Khó hiểu yêu cầu kinh doanh; không rõ ưu tiên; gặp khó khi trao đổi với PM/BD |


Ghi chú: Mỗi problem nên có **actor** và **dấu hiệu thật** (e.g., "mất 30 phút/tuần", "hay trễ deadline").

## Top 3

- Sau khi scan rộng, chọn top 3 theo tiêu chí: actor rõ, workflow rõ, pain có evidence, impact đo được.

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Khó khăn phát âm | Actor rõ, workflow giao tiếp lặp lại, impact trực tiếp tới khả năng giao tiếp và nghề nghiệp | Baseline (tần suất bị hiểu sai) cần đo cụ thể để làm metric |
| 2 | Khó khăn di chuyển (xe lăn điện) | Rất tác động đến tính độc lập và chất lượng cuộc sống; giải pháp thiết bị rõ ràng | Chi phí/tiếp cận thiết bị và đào tạo có thể là rào cản |
| 3 | Trì hoãn quyết định mua | Giải pháp AI cấu trúc thông tin dễ thử nghiệm; metric (thời gian quyết định, chuyển đổi) dễ đo | Nguồn dữ liệu review có bias; cần xác định ưu tiên người dùng rõ |

---

## Problem Cards (viết lại)


### Problem Card #1 — Khó khăn phát âm

Ý tưởng: AI phiên dịch giọng nói của chính mình (voice-to-voice normalization)

Tóm tắt (elevator): Một hệ thống realtime chuyển giọng nói của bạn thành phiên bản nói rõ, giữ nội dung và ngữ điệu cơ bản — giúp người nghe hiểu ngay lập tức và người dùng có thể học từ các sửa đổi.

Vấn đề cần giải: Bị hiểu sai do phát âm/giọng lệch dẫn tới gián đoạn giao tiếp, giảm tự tin và mất cơ hội.

Giải pháp (một câu): Ghi âm → ASR thích nghi với giọng lệch → phát hiện lỗi phát âm → tạo bản sửa (text và/hoặc audio) → phát lại/hiển thị cho người dùng.

Tính năng chính:
- Realtime STT chuyên cho giọng lệch; phoneme-level error detector;
- Correction engine (text normalization + sửa phát âm);
- Speech-to-speech: phát lại phiên bản đã sửa (giữ/chuẩn hoá giọng tùy chọn);
- Chế độ học: hiển thị phiên âm + bài tập ngắn; lịch theo dõi tiến trình.

Hành trình người dùng (MVP flow):
1) Bật chế độ "Phiên dịch cá nhân";
2) Nói 1–2 câu; app ghi âm và chạy pipeline;
3) Hiển thị text gốc + text đã chuẩn và phát lại audio đã chỉnh (nếu bật);
4) Người dùng chấp nhận/lưu/bắt đầu bài tập luyện.

MVP (ít nhất để thử):
- STT tiếng Việt robust (pretrained) + phoneme aligner;
- Rule-based correction + small ML model cho sửa lỗi phổ biến;
- TTS đơn giản để phát lại phiên bản đã sửa;
- UI: bật/tắt, phát lại, hiển thị sửa, lưu bài tập.

Kiến trúc (tóm tắt):
- Frontend: app (mobile/desktop) thu âm, phát lại, UI;
- Backend/On-device: STT → phoneme detector → correction generator → TTS/voice conversion (tuỳ yêu cầu);
- Storage: lưu audio & logs mã hoá, opt-in cho training cá nhân.

Dữ liệu & training: cần corpus speech+transcript có đa dạng accent, dữ liệu phoneme-aligned; data augmentation cho lỗi phát âm.

Success metrics (gợi ý):
- Giảm % lần bị hỏi lại trong cuộc gọi ≥ 50% sau 4 tuần pilot;
- Tỉ lệ chấp nhận phiên bản AI ≥ 70% (người dùng chọn phát lại AI);
- Điểm hiểu (listener comprehension) cải thiện trên bộ test chuẩn.

Rủi ro & giảm thiểu:
- Thay đổi ý nghĩa: chỉ sửa phát âm, không sửa nội dung; luôn hiển thị văn bản gốc;
- Riêng tư: xử lý on-device hoặc mã hóa; opt-in voice cloning;
- Tâm lý người dùng: giữ ngữ điệu/giọng cá nhân, không ép chuyển giọng.

Lộ trình ngắn hạn (8–16 tuần):
1–4: Prototype STT + rule-based correction + TTS demo;
5–8: Pilot 10–20 người, thu feedback và đo metric;
9–16: Cải tiến ML, thêm tuỳ chọn voice-preserving conversion và onboarding đào tạo.


Problem (1 câu): Tôi thường bị hiểu sai khi nói do phát âm không rõ.

Actor: Tôi (người có khó khăn phát âm / người học ngôn ngữ).

Bối cảnh: Giao tiếp hàng ngày, gọi điện, thuyết trình, hoặc phỏng vấn.

Current workflow (hiện tại):
1) Cố phát âm; 2) Người nghe hỏi lại hoặc hiểu sai; 3) Tôi lặp lại, viết thay hoặc tránh nói.

Bottleneck: Lỗi phát âm do yếu khả năng điều khiển thanh quản

Impact: Hiểu nhầm, giảm tự tin, hạn chế cơ hội giao tiếp và nghề nghiệp.

Success metrics (ví dụ):
- Giảm số lần bị hỏi lại trong cuộc gọi trung bình từ hiện tại xuống 50% sau 4 tuần.
- Tăng số lần chủ động phát biểu trong nhóm từ X → X+Y trong 4 tuần.

Non-AI alternative: Gia sư phát âm, lớp luyện nói, hoặc ứng dụng luyện theo giáo viên.

AI intervention: Ứng dụng ghi âm → phân tích lỗi phát âm → trả về phiên âm, điểm lỗi và bài tập cá nhân hoá; người dùng luyện rồi so sánh tiến triển.

Quick plan (future workflow):
1) Ghi âm mẫu 30–60s; 2) AI phân tích & trả về lỗi chính (30–60s); 3) AI gợi ý bài tập ngắn; 4) Người dùng luyện + review kết quả.

Fallback / exit: Nếu AI chẩn đoán không chính xác hoặc không cải thiện sau 2 tuần, chuyển sang gia sư trực tiếp.

Rủi ro & kiểm soát: Sai sót trong chuẩn đoán; cần lưu trữ an toàn âm thanh và có human coach kiểm chứng bài tập quan trọng.

---

### Problem Card #2 — Khó khăn di chuyển (xe lăn điện)

Problem (1 câu): Tôi đi lại khó khăn, không thể đi xa và dễ vấp ngã.

Actor: Tôi (người hạn chế vận động / sau chấn thương).

Bối cảnh: Di chuyển trong nhà/ngoài đường để đi chợ, đi làm, tham gia hoạt động xã hội.

Current workflow: Chuẩn bị → đi quãng ngắn → mệt/đau phải nghỉ → hủy hoặc nhờ trợ giúp.

Bottleneck: Hạn chế thể lực và thăng bằng; quãng đường và chướng ngại vật là rào cản.

Impact: Giảm tính độc lập, tăng nhu cầu hỗ trợ, giảm chất lượng cuộc sống.

Success metrics (ví dụ):
- Tăng khoảng cách di chuyển an toàn không nghỉ (m) lên +50% trong 4 tuần sau khi dùng xe lăn điện.
- Giảm tần suất vấp/ngã xuống 0–1 lần/tháng.

Chosen non-AI solution: Xe lăn điện kèm đào tạo sử dụng và lịch bảo trì.

Future workflow (với xe lăn điện):
1) Mua/được cấp + đào tạo cơ bản;
2) Kiểm tra lộ trình và tình trạng pin trước khi ra ngoài;
3) Sử dụng hàng ngày theo hướng dẫn; ghi nhật ký sự cố/khó khăn;
4) Lịch bảo trì định kỳ và review với therapist.

Fallback / exit: Nếu xe lăn điện không phù hợp (an toàn/tiếp cận/kỹ thuật), chuyển sang vật lý trị liệu chuyên sâu và hỗ trợ di chuyển thay thế.

Rủi ro & kiểm soát: Hỏng thiết bị/pin; tai nạn do địa hình không phù hợp; cần quy trình bảo trì, hướng dẫn an toàn và human oversight.

---

### Problem Card #3 — Trì hoãn quyết định mua

Problem (1 câu): Tôi dành quá nhiều thời gian so sánh và phân vân trước khi mua, dẫn tới bỏ giỏ hàng hoặc trì hoãn.

Actor: Tôi (người mua hàng trực tuyến).

Bối cảnh: Mua sắm khi có nhiều lựa chọn, review và thông số khác nhau.

Current workflow: Tìm → đọc review/spec → so sánh nhiều nguồn → lưu wishlist hoặc bỏ giỏ hàng.

Bottleneck: Quá nhiều thông tin và thiếu tiêu chí cá nhân để so sánh nhanh.

Impact: Mất thời gian, trải nghiệm kém; với nhà bán hàng là giảm chuyển đổi.

Success metrics (ví dụ):
- Giảm thời gian quyết định trung bình từ 60 phút xuống ≤30 phút trong pilot.
- Tăng tỉ lệ chuyển đổi từ giỏ hàng → mua lên +10%.

Non-AI alternative: Checklist tiêu chí cá nhân, template so sánh, bộ lọc ưu tiên.

AI intervention: Nhập URL/sản phẩm → AI tóm tắt điểm khác biệt chính, xếp hạng theo ưu tiên người dùng và đưa ra 1–2 đề xuất tối ưu.

Future workflow: Người dùng cung cấp ưu tiên (giá, hiệu năng, thương hiệu) → AI tóm tắt & xếp hạng trong 1–2 phút → người dùng quyết định hoặc yêu cầu thêm chi tiết.

Fallback / exit: Nếu AI gợi ý thiếu nguồn hoặc gây sai lệch, người dùng quay lại checklist thủ công.

Rủi ro & kiểm soát: Bias từ review/nguồn quảng cáo; cần hiển thị nguồn và độ tin cậy của dữ liệu.


**Thời điểm / bối cảnh:**
Mua sắm online khi có nhiều lựa chọn, thông số kỹ thuật và review trái chiều.

**Current workflow:**
```text
1. Tìm sản phẩm
2. So sánh nhiều nguồn (spec, review, giá)
3. Chần chừ, lưu vào wishlist, thường bỏ giỏ hàng
```

**Bottleneck:**
Quá nhiều thông tin, thiếu tiêu chí rõ ràng để so sánh.

**Impact:**
Mất thời gian, trải nghiệm mua sắm kém, doanh số thấp (với nhà bán hàng).

**Success metric:**
- Giảm thời gian quyết định trung bình (phút) xuống 50% trong pilot.
- Tăng tỉ lệ chuyển đổi từ giỏ hàng → mua.

**Non-AI alternative:**
Checklist tiêu chí cá nhân, template so sánh, review trusted sources.

**AI hypothesis:**
AI có thể tóm tắt điểm khác biệt chính, gợi ý lựa chọn phù hợp theo ưu tiên cá nhân và rút gọn options.

**Quick gut:**
Rất phù hợp cho một tính năng trợ giúp quyết định (assistant + checklist cá nhân).

### Draft current workflow
```text
CURRENT STATE — (ví dụ: 30–120 phút nghiên cứu)

[1 Tìm & đọc] → [2 So sánh dài] → [3 Trì hoãn/bỏ giỏ]
```

### Draft future workflow
```text
FUTURE STATE — (ví dụ: 5–15 phút)

[1 Nhập URL/option: 1']
→ [2 AI tóm tắt & xếp hạng theo ưu tiên: 1']
→ [3 Người dùng quyết định + feedback]
```

**Fallback / Exit criteria:**
Nếu AI gợi ý sai ưu tiên hoặc thiếu nguồn tin quan trọng, người dùng bỏ chức năng và dùng checklist thủ công.

**Rủi ro & kiểm soát:**
Bias từ nguồn review, quảng cáo trá hình; cần nguồn tin rõ ràng và minh bạch.


