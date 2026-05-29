# 01 — Individual Problem Scan
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

## Problem Cards

### Problem Card #1 — Khó khăn phát âm
**Problem 1:**  
Tôi muốn một thiết bị realtime chuyển tiếng Việt khó nghe của tôi thành tiếng Việt bình thường để người khác hiểu ngay.

**Actor:**  
Tôi (người có giọng nói khó nghe / phát âm không rõ).

**Thời điểm / bối cảnh:**  
Khi nói chuyện trực tiếp, gọi điện, họp online, hoặc cần người khác hiểu ngay điều tôi vừa nói.

**Current workflow:**

```text
1. Tôi nói bằng giọng khó nghe
2. Người nghe hỏi lại hoặc hiểu sai
3. Tôi phải lặp lại, nói chậm hơn, hoặc chuyển sang viết
```

**Bottleneck:**  
Người nghe không hiểu nội dung ngay lúc tôi nói, nên cuộc giao tiếp bị ngắt quãng.

**Impact:**  
Mất tự tin, mất thời gian lặp lại, và có thể làm giảm hiệu quả giao tiếp trong học tập, công việc, hoặc cuộc gọi.

**Success metric:**
- Giảm số lần phải nói lại trong một cuộc trò chuyện xuống ít nhất 50%.
- Giảm thời gian để người nghe hiểu đúng ý tôi xuống dưới 5 giây cho mỗi câu ngắn.

**Non-AI alternative:**  
Nói chậm hơn, luyện phát âm với giáo viên, hoặc dùng cách viết ra thay vì nói.

**AI hypothesis:**  
AI có thể nghe realtime, nhận ra phần nói khó nghe, và chuyển nó thành câu tiếng Việt rõ ràng hơn mà vẫn giữ nguyên ý chính.

**Quick gut:**  
Phù hợp với một thiết bị hỗ trợ realtime, vì pain xảy ra ngay lúc giao tiếp và có thể đo bằng số lần phải nhắc lại.

### Draft current workflow

```text
CURRENT STATE — 30–60 giây cho một trao đổi ngắn

[1 Nói bằng giọng khó nghe]
→ [2 Người nghe hỏi lại]
→ [3 Tôi lặp lại hoặc viết ra]
```

### Draft future workflow

```text
FUTURE STATE — realtime

[1 Tôi nói vào thiết bị]
→ [2 Thiết bị nhận âm thanh]
→ [3 AI chuyển thành tiếng Việt bình thường]
→ [4 Thiết bị hiển thị/phát lại câu rõ ràng]
→ [5 Người nghe hiểu ngay]

Fallback: nếu AI đoán sai, hiển thị bản gốc để tôi sửa nhanh.
```

**Fallback / Exit criteria:**  
Nếu AI làm sai nghĩa hoặc chậm quá, người dùng quay về cách nói thường, dùng text, hoặc chuyển sang hỗ trợ của người thật.

**Rủi ro & kiểm soát:**  
Sai ý nghĩa khi sửa câu, độ trễ realtime, và quyền riêng tư của giọng nói; cần cho phép xem bản gốc, chỉnh tay, và xoá dữ liệu.

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


