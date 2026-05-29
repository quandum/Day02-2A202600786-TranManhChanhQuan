# 02 — Group Problem Statement

## Group Convergence

Nhóm 3-4 người, mỗi người share top 3. Tổng cộng có khoảng 12 candidates.

| Cluster                            | Candidate examples                                                                                                            | Pattern chung                                                          |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Tìm kiếm / hỏi đáp thông tin | Tìm thông tin giữa Discord + PDF + GitHub + LMS, tìm lại thông tin trong Discord/Zalo lớp, check/lọc kênh thông tin | Tìm đúng thông tin trong nhiều nguồn rời rạc                   |
| Review / feedback                  | Kiểm tra bài nộp còn thiếu phần nào, TA nhận câu hỏi thiếu context                                                 | Đọc đầu vào/bài nộp/câu hỏi và chỉ ra thiếu sót           |
| Hỗ trợ kỹ thuật                | Non-tech cài Env / IDE / Tool                                                                                                | Hướng dẫn từng bước khi người học gặp lỗi setup             |
| Quản lý tài chính              | Quản lý chi tiêu nhóm ở chung, quản lý tài chính cá nhân                                                           | Ghi nhận, tổng hợp và đối soát các khoản chi                  |
| Decision support                   | Suy nghĩ bữa tiếp theo ăn gì, quyết định mua hay không mua sản phẩm                                                | Hỗ trợ ra quyết định khi có nhiều lựa chọn                    |
| Accessibility support              | Khó khăn trong phát âm, di chuyển chậm/dễ vấp ngã                                                                    | Hỗ trợ người dùng có hạn chế trong giao tiếp hoặc di chuyển |

---

## Shortlist và Score

| Candidate                                          | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng        |
| -------------------------------------------------- | --------- | ------------ | ----------------- | ------------------ | -------------- | ---------------------- | ------------------ | ------------ |
| Tìm thông tin giữa Discord + PDF + GitHub + LMS | 5         | 5            | 5                 | 5                  | 5              | 5                      | 5                  | **35** |
| Non-tech cài Env / IDE / Tool                     | 5         | 5            | 5                 | 4                  | 5              | 4                      | 4                  | **32** |
| Kiểm tra bài nộp còn thiếu phần nào         | 5         | 5            | 4                 | 4                  | 5              | 3                      | 5                  | **31** |
| TA nhận câu hỏi thiếu context                  | 5         | 4            | 4                 | 4                  | 5              | 4                      | 4                  | **30** |
| Tìm lại thông tin trong Discord/Zalo lớp       | 4         | 4            | 5                 | 4                  | 4              | 5                      | 4                  | **30** |
| Quản lý chi tiêu nhóm ở chung                 | 4         | 5            | 4                 | 4                  | 4              | 3                      | 4                  | **28** |
| Check, lọc kênh thông tin                       | 4         | 4            | 4                 | 3                  | 4              | 3                      | 4                  | **26** |
| Quyết định mua hàng                            | 4         | 4            | 3                 | 3                  | 4              | 3                      | 3                  | **24** |
| Quản lý tài chính cá nhân                    | 4         | 4            | 3                 | 3                  | 4              | 2                      | 3                  | **23** |
| Suy nghĩ bữa tiếp theo ăn gì                  | 3         | 3            | 3                 | 2                  | 5              | 2                      | 4                  | **22** |
| Hỗ trợ phát âm                                 | 3         | 3            | 3                 | 3                  | 2              | 4                      | 2                  | **20** |
| Hỗ trợ di chuyển                                | 3         | 3            | 3                 | 3                  | 1              | 4                      | 2                  | **19** |

Nhóm chọn: Tìm thông tin giữa Discord + PDF + GitHub + LMS

### Vì sao chọn

* Có workflow rõ nhất.
* Pain xảy ra thường xuyên trong bối cảnh học tập và làm lab.
* Có baseline thời gian để đo lường.
* Có thể validate nhanh với sinh viên và TA.
* Có nhiều solution AI đã được chứng minh như RAG, Semantic Search, QA Bot.
* Dễ vẽ before/after và đo impact.
* Dễ demo trong phạm vi lab.

### Vì sao không chọn các bài khác

#### Non-tech cài Env / IDE / Tool

* Pain lớn và xảy ra thường xuyên.
* Tuy nhiên lỗi setup rất đa dạng theo hệ điều hành và môi trường.
* Khó cover hết edge cases trong phạm vi lab.

#### Kiểm tra bài nộp còn thiếu phần nào

* Workflow rất rõ.
* Rubric có sẵn.
* Tuy nhiên nếu chỉ kiểm tra checklist thì AI value chưa thực sự nổi bật.

#### TA nhận câu hỏi thiếu context

* Giúp giảm thời gian trao đổi giữa TA và sinh viên.
* Tuy nhiên cần định nghĩa rõ thế nào là một câu hỏi "đủ context".

#### Quản lý chi tiêu nhóm ở chung

* Pain gần với trải nghiệm thực tế.
* Tuy nhiên AI value chưa rõ ràng bằng bài toán tìm kiếm thông tin.

#### Suy nghĩ bữa tiếp theo ăn gì / Quyết định mua hàng

* Dễ hiểu và phổ biến.
* Tuy nhiên impact khó đo lường.
* Dễ trở thành hệ thống recommendation đơn giản thay vì một AI product rõ ràng.

#### Hỗ trợ phát âm / Hỗ trợ di chuyển

* Có ý nghĩa xã hội và tác động tích cực.
* Tuy nhiên khó triển khai và đánh giá trong phạm vi thời gian của lab.
* Nhóm hiện chưa có đủ domain expertise để xây dựng và kiểm chứng giải pháp.

# Quick Validation

Nhóm hỏi nhanh sinh viên và TA trong lớp/lab.

| Nguồn                     | Số người | Tín hiệu xác nhận                                                                         | Tín hiệu phản bác                                                    | Nhóm sửa problem thế nào                                                                                                    |
| -------------------------- | ----------: | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| Quick interview sinh viên |           5 | 4/5 người từng mất nhiều thời gian tìm lại thông tin giữa Discord, PDF, GitHub, LMS | 1 người nói thường hỏi thẳng bạn bè nhanh hơn                  | Thu hẹp problem: không phải “search mọi thứ”, mà là “trả lời câu hỏi lab từ các nguồn học tập chính thức” |
| Hỏi TA/Mentor             |           2 | TA thường nhận câu hỏi lặp lại, nhiều câu đã có trong tài liệu                  | Một số câu hỏi cần debug trực tiếp, AI không thể trả lời hết | Thêm boundary: AI chỉ trả lời dựa trên tài liệu có sẵn, câu phức tạp thì chuyển TA                               |
| Mini poll trong lớp       |           8 | 6/8 người từng không biết nên tìm ở Discord, PDF, GitHub hay LMS trước              | Một số bạn quen dùng Ctrl+F trong PDF                                | Thêm non-AI alternative: checklist link + FAQ cố định                                                                       |

Insight sau validation:

```text
Pain thật không nằm ở việc "lấy số" đơn thuần. Pain nằm ở đoạn biến nhiều nguồn rời rạc thành narrative đủ rõ cho người khác ra quyết định.
```

# Research Giải Pháp

Nhóm tìm các hướng đã có sẵn, không giả định phải tự build từ đầu.

| Nguồn / tool / case              | Link                                | Họ giải quyết phần nào?                         | Điểm mạnh                                  | Khoảng trống / rủi ro                            | Bài học cho nhóm                                                 |
| --------------------------------- | ----------------------------------- | ---------------------------------------------------- | --------------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------- |
| ChatGPT / Custom GPT              | https://chatgpt.com                 | Hỏi đáp theo tài liệu được upload            | Dễ thử nghiệm, phù hợp prototype nhanh   | Cần kiểm soát nguồn và hallucination           | Có thể dùng để test prompt và RAG flow ban đầu              |
| GitHub Copilot Chat               | https://github.com/features/copilot | Hỏi đáp với codebase/GitHub repo                 | Mạnh với code và repo                      | Không gom được Discord/PDF/LMS đầy đủ       | GitHub chỉ là một nguồn, không phải toàn bộ solution        |
| Slack AI / Discord Search pattern | https://slack.com                   | Search và summary conversation                      | Tốt cho hội thoại                          | Chỉ xử lý một nguồn, data access có thể khó | Conversation search nên là input, không phải toàn bộ workflow |
| LMS FAQ / Course FAQ              | LMS nội bộ                        | Cung cấp câu trả lời cố định                  | Dễ dùng, ít rủi ro                        | Không linh hoạt với câu hỏi cụ thể           | FAQ tốt cho câu hỏi lặp, nhưng chưa đủ cho nhiều nguồn    |
| RAG chatbot pattern               | LangChain / LlamaIndex              | Gom tài liệu, chunk, retrieve, answer with sources | Phù hợp nhất với bài toán nhiều nguồn | Cần chuẩn bị data và đánh giá độ đúng    | Hướng chính nên là RAG + citation + human fallback             |

## Research takeaway

Không nên build một agent tự đọc mọi nguồn và tự quyết định hoàn toàn. Hướng hợp lý hơn là workflow RAG: gom tài liệu chính thức, cho AI truy xuất đúng đoạn liên quan, trả lời kèm nguồn, và chuyển TA khi câu hỏi vượt ngoài tài liệu.

## Workflow before/after

File nhóm nộp kèm:

```text
02-group-problem-statement-workflow.png/pdf/md
```

Nội dung workflow:

```text
CURRENT STATE — 6 bước, 15–20 phút

┌────────────────────────────────────────────────────────────────────────────┐
│                    STUDENT NEEDS COURSE INFORMATION                        │
│        deadline / lab guide / repo / PDF / LMS / Discord / Drive           │
└──────────────────────────────────┬─────────────────────────────────────────┘
                                   │
                                   ▼
┌──────────────────┐   ┌──────────────────┐   ┌──────────────────┐
│ Bước 1           │ → │ Bước 2           │ → │ Bước 3           │
│ Search Discord   │   │ Open PDF/Slides  │   │ Open GitHub Repo │
│                  │   │                  │   │                  │
│ Ai: Student      │   │ Ai: Student      │   │ Ai: Student      │
│ ◷ 3'             │   │ ◷ 3'             │   │ ◷ 3'             │
│ In: question     │   │ In: lab keyword  │   │ In: repo link    │
│ Out: threads     │   │ Out: guide info  │   │ Out: README/code │
└──────────────────┘   └──────────────────┘   └──────────────────┘
                                                     │
                                                     ▼
┌──────────────────┐   ┌──────────────────┐   ┌──────────────────────┐
│ Bước 4           │ → │ Bước 5           │ → │ Bước 6               │
│ Open LMS/Drive   │   │ Compare Sources  │   │ Ask TA / Friend      │
│                  │   │                  │   │ if not confident     │
│ Ai: Student      │   │ Ai: Student      │   │ Ai: Student + TA     │
│ ◷ 2'             │   │ ◷ 4' 🔴          │   │ ◷ ?'                 │
│ In: course page  │   │ In: many sources │   │ In: unclear context  │
│ Out: announcement│   │ Out: confidence  │   │ Out: answer          │
└──────────────────┘   └──────────────────┘   └──────────────────────┘

🔴 = Bottleneck
Main bottleneck: Student phải tự đọc, so sánh và xác thực thông tin từ nhiều nguồn.

FUTURE STATE — AI KNOWLEDGE ASSISTANT + VECTOR DB/RAG — 5 bước, ~2 phút

┌────────────────────────────────────────────────────────────────────────────┐
│                    STUDENT NEEDS COURSE INFORMATION                        │
└──────────────────────────────────┬─────────────────────────────────────────┘
                                   │
                                   ▼
┌──────────────────┐   ┌──────────────────┐   ┌──────────────────────────┐
│ Bước 1           │ → │ Bước 2           │ → │ Bước 3                   │
│ Ask AI Assistant │   │ Intent Detection │   │ RAG Retrieval            │
│                  │   │                  │   │ + Vector DB Search       │
│ 🟦 AI xử lý      │   │ 🟦 AI xử lý      │   │ 🟦 AI xử lý              │
│ ◷ 20s            │   │ ◷ 10s            │   │ ◷ 30s                    │
│ In: question     │   │ In: question     │   │ In: embedded query       │
│ Out: intent      │   │ Out: task type   │   │ Out: relevant chunks     │
└──────────────────┘   └──────────────────┘   └──────────────────────────┘
                                                     │
                                                     ▼
┌──────────────────────────────┐      ┌──────────────────────────────┐
│ Knowledge Sources            │      │ Vector DB / RAG Layer         │
│                              │      │                              │
│ - Discord FAQ                │ ───▶ │ - Chunking                   │
│ - PDF / Slides               │      │ - Embedding                  │
│ - GitHub README              │      │ - Semantic Search            │
│ - LMS Announcement           │      │ - Source Ranking             │
│ - Google Drive Docs          │      │ - Freshness Check            │
└──────────────────────────────┘      └──────────────────────────────┘
                                                     │
                                                     ▼
┌──────────────────────────┐   ┌──────────────────────────┐
│ Bước 4                   │ → │ Bước 5                   │
│ Generate Answer          │   │ Student Verify / Use      │
│ + Citations              │   │ Official Source           │
│                          │   │                          │
│ 🟦 AI xử lý              │   │ 🟢 Human boundary         │
│ ◷ 45s                    │   │ ◷ 15s                     │
│ In: retrieved chunks     │   │ In: cited answer          │
│ Out: final answer        │   │ Out: continue lab         │
└──────────────────────────┘   └──────────────────────────┘

🟦 = AI xử lý
🟢 = Human boundary
Fallback: Nếu confidence thấp → AI tạo context package → chuyển cho TA.
Bottleneck mới: Student chỉ cần verify source, không phải tự tìm và đối chiếu nhiều nơi.
```

### Before/after impact

| Metric                          |                     Trước |          Sau kỳ vọng | Ghi chú                                            |
| ------------------------------- | --------------------------: | ---------------------: | --------------------------------------------------- |
| Tổng thời gian                |      15–20 phút/lần tìm |               ~2 phút | Target chính                                       |
| Số bước                      |                           6 |                      5 | Giảm effort ở bước tìm và đối chiếu nguồn |
| Số nguồn phải mở thủ công |                 4–5 nguồn |        1 giao diện AI | Giảm context switching                             |
| Bước thủ công               |                         6/6 |                    1/5 | Student vẫn verify nguồn cuối                    |
| Bottleneck chính               |             Compare sources |    Verify cited answer | Human boundary                                      |
| Risk mới                       | Không có AI hallucination | Có hallucination risk | Cần citation + confidence check                    |

## Problem Statement v0

| Field                    | Nội dung                                                                                                                                                             |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Actor**          | Sinh viên đang làm lab hoặc assignment.                                                                                                                           |
| **Workflow**       | Sinh viên có câu hỏi → search Discord/Zalo → mở PDF/Slides → mở GitHub Repo → mở LMS/Drive → tự so sánh nhiều nguồn → hỏi TA nếu vẫn chưa chắc. |
| **Bottleneck**     | Bước compare sources mất nhiều thời gian vì sinh viên phải tự đọc, lọc, đối chiếu và xác thực thông tin từ nhiều nguồn rời rạc.               |
| **Impact**         | Mỗi câu hỏi nhỏ có thể mất 15–20 phút; sinh viên chậm tiến độ; TA nhận nhiều câu hỏi lặp lại.                                                     |
| **Success Metric** | Giảm thời gian tìm câu trả lời xuống khoảng 2 phút; giảm số câu hỏi lặp gửi TA; tăng tỷ lệ câu trả lời có citation đúng nguồn.               |
| **Boundary**       | AI không bịa câu trả lời; không trả lời nếu thiếu nguồn; không thay TA xử lý case debug phức tạp; luôn hiển thị nguồn tham chiếu.                |

## Rule / Workflow / Agent

| Mức               | Phương án                                                                                                       | Khi nào đủ                                                                           | Rủi ro                                                                   | Chọn?                                                                |
| ------------------ | ------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| **Rule**     | FAQ cố định, pinned post, checklist link                                                                        | Đủ nếu câu hỏi ít, lặp lại rõ ràng và tài liệu rất ổn định             | Không xử lý được câu hỏi đa dạng hoặc nhiều cách diễn đạt | Không chọn làm toàn bộ, nhưng có thể dùng cho FAQ phổ biến |
| **Workflow** | Data cleaning → chunking → embedding → Vector DB → RAG retrieval → AI answer with citations → student verify | Hợp vì bài toán có nguồn rõ, cần tìm và tổng hợp thông tin từ nhiều nơi | Retrieval sai, nguồn cũ, hallucination                                  | **Chọn**                                                       |
| **Agent**    | Agent tự truy cập Discord/LMS/GitHub, tự hỏi thêm, tự tạo ticket cho TA                                     | Chỉ cần nếu workflow nhiều nhánh và cần tự hành động                         | Quá rộng, nhiều permission/risk, khó demo trong lab                   | Chưa chọn                                                           |

Mức chọn:

```text
Workflow.
```

Vì sao:

- Data có thể chuẩn bị trước bằng rule/script.
- RAG phù hợp để tìm thông tin trong nhiều nguồn tài liệu.
- AI chỉ hỗ trợ retrieve, summarize và cite source.
- Student vẫn verify câu trả lời nên kiểm soát hallucination.
- Chưa cần agent vì hệ thống chưa cần tự hành động hoặc tự quyết định thay người dùng.

## Problem Statement v1

| Field                                       | Nội dung                                                                                                                                         |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Actor**                             | Sinh viên đang làm lab/assignment và cần tìm thông tin từ tài liệu khóa học.                                                          |
| **Workflow**                          | Có câu hỏi → search Discord/Zalo → mở PDF/Slides → mở GitHub Repo → mở LMS/Drive → compare sources → hỏi TA nếu chưa chắc.        |
| **Bottleneck**                        | Sinh viên phải tự compare nhiều nguồn rời rạc, dễ dùng nhầm thông tin cũ hoặc không biết nguồn nào đáng tin cậy.              |
| **Impact**                            | Mỗi lần tìm mất 15–20 phút; làm chậm tiến độ lab; TA bị hỏi lại nhiều câu đã có trong tài liệu.                              |
| **Success Metric**                    | Giảm time-to-answer xuống khoảng 2 phút; giảm câu hỏi lặp cho TA; tăng tỷ lệ câu trả lời có nguồn chính xác.                    |
| **Boundary**                          | AI chỉ trả lời khi có source; câu trả lời phải có citation; nếu confidence thấp thì fallback sang TA.                                 |
| **AI intervention point**             | Sau khi student nhập câu hỏi, trước khi student phải tự mở Discord/PDF/GitHub/LMS.                                                        |
| **Mức chọn**                        | Workflow: Vector DB + RAG retrieval + AI answer with citations + human verification.                                                              |
| **Rủi ro & người thật kiểm tra** | Risk: hallucination, retrieve sai nguồn, tài liệu cũ. Người thật kiểm tra: Student verify citation; TA review các câu hỏi quan trọng. |

## Final decision

Decision:

```text
Go với scope nhỏ.
```

Pilot nhỏ nhất:

- Dùng 3 nguồn chính thức trước: PDF/Slides, GitHub README, LMS Announcement.
- Thêm Discord FAQ sau nếu data access cho phép.
- Tạo 20–30 câu hỏi thường gặp.
- Build prototype RAG chatbot.
- Mỗi answer phải có citation/source.
- Đo time-to-answer và số câu phải fallback sang TA.

Exit / rollback:

- Nếu AI trả lời sai nguồn quá 10–15% trong test set → không dùng trực tiếp, chuyển về FAQ + search.
- Nếu student vẫn phải hỏi TA hơn 50% số câu → giảm scope còn FAQ bot.
- Nếu Discord/Zalo khó lấy data → chỉ dùng PDF + GitHub + LMS trước.
- Nếu answer không có citation → không cho hiển thị như câu trả lời cuối.

Decision rationale:

- Problem rõ, workflow rõ, metric rõ.
- Có non-AI alternative là FAQ/checklist.
- AI nằm ở một bước cụ thể: retrieve và summarize thông tin từ nhiều nguồn.
- Có human boundary rõ: student verify source, TA xử lý case khó.
- Phù hợp để demo bằng Vector DB + RAG trong phạm vi lab.

---

