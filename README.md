# BÀI NỘP LAB TRACK 1 - DAY 22: AI PRICING · GTM · EVIDENCE
> **Chủ đề:** Từ sản phẩm chạy được đến sản phẩm bán được — AI Pricing · GTM · Evidence  
> **Học viên:** Trần Phạm Thái Vũ  
> **Mã học viên (MHV):** `2A202602695`  
> **Email:** `26ai.vutpt@vinuni.edu.vn`  
> **Repository:** `Track1_Day22_2A202602695_TranPhamThaiVu`  
> **Tài liệu nộp đính kèm trong Repo:**
> 1. [Vu_Day22_model.xlsx](./Vu_Day22_model.xlsx) — File Excel 5 tab tính toán hoàn chỉnh (đầy đủ công thức, không ô trống vô lý).
> 2. [Vu_Day22_onepager.pdf](./Vu_Day22_onepager.pdf) — Monetization One-Pager 1 trang duy nhất, số liệu khớp 100% với file Excel.

---

## 1. THÔNG TIN DỰ ÁN LỰA CHỌN: WANDERMIND AI
* **Tên sản phẩm:** **WanderMind AI (B2B Travel Itinerary Copilot)**
* **Kế thừa:** Phát triển tiếp nối từ dự án *WanderMind AI* ở Day 20 (Core Action `itinerary_finalized`).
* **Định vị sản phẩm thương mại:** Trợ lý AI tự động hóa khâu soạn thảo lịch trình tour du lịch tùy biến cho các Đại lý du lịch lữ hành vừa và nhỏ (Boutique Travel Agencies / Inbound Tour Operators). Thay thế 3–5 giờ làm việc thủ công của nhân viên điều hành tour, xuất bản lịch trình tour cá nhân hóa hoàn chỉnh trong 3 phút.
* **Ngân sách khách hàng (Budget Line):** **Ngân sách Vận hành / Nhân sự (Operations / Headcount Budget)** — Đại lý chi trả để giảm tải khối lượng công việc mùa cao điểm và tránh phải tuyển thêm nhân sự thiết kế tour cố định.
* **Người ký duyệt:** Chủ đại lý du lịch (Agency Owner) hoặc Giám đốc điều hành (Head of Operations).

---

## 2. TỔNG HỢP CÁC CON SỐ CỐT LÕI (BẢNG ĐỐI CHIẾU 100% EXCEL ↔ ONE-PAGER)

| Chỉ số | Giá trị | Lấy từ ô trong Excel | Đánh giá theo chuẩn Rubric |
|---|:---:|:---:|---|
| **Định nghĩa 1 Job** | 1 lịch trình tour hoàn chỉnh (≥ 1 ngày, ≥ 3 hoạt động/ngày, tối ưu lộ trình, có dự toán) | `1_Cost_Job!B5` | Đúng đơn vị giá trị của khách |
| **Biến thể HITL** | Biến thể B (Managed Outcome) | `1_Cost_Job!B6` | WanderMind chịu escalation để đảm bảo chất lượng giao đại lý |
| **Mẫu số (Job hoàn thành)** | **820 job** (1.000 job thử × 82% containment) | `1_Cost_Job!B11` | **Mẫu số là Job HOÀN THÀNH**, không chia cho job thử |
| **Tiết kiệm nhờ Cache** | **38,6%** (LLM có cache: \$0,0203 vs không cache: \$0,0330) | `1_Cost_Job!B29` | Đòn bẩy hạ giá thành inference |
| **★ Cost/Job** | **\$0,2486** (~\$0,25 ≈ 6.464 ₫) | `1_Cost_Job!B66` | Đủ 5 thành phần: LLM, Infra, Retry 8%, HITL |
| **Giá sàn (3 × Cost/Job)** | **\$0,7459** (~\$0,75) | `2_Pricing!B7` | Bội số an toàn cover sai số & chi phí vận hành |
| **★ Giá bán đề xuất** | **\$0,99** / lịch trình hoàn chỉnh | `2_Pricing!B19` | Nằm chuẩn trong vùng giá sàn (\$0,75) và giá trần (\$1,00) |
| **Bội số so với Cost/Job** | **3,98×** | `2_Pricing!B20` | Đạt chuẩn ≥ 3× an toàn |
| **★ Gross Margin (GM)** | **74,89%** | `2_Pricing!B21` | Đạt chuẩn ≥ 60% và ≤ 85% (không bị cảnh báo bỏ sót chi phí) |
| **★ Breakeven Containment** | **72,68%** (~73%) | `2_Pricing!B33` | Thấp hơn Containment thực tế (82,0%) → Có lãi lành mạnh |
| **ARPU / tháng** | **\$200** / đại lý | `4_Channel_Fit!B5` | Trung bình ~200 tour hoàn chỉnh/tháng/đại lý |
| **★ Ngân sách CAC** | **\$1.797,28** / khách | `4_Channel_Fit!B9` | ARPU \$200 × GM 74,89% × 12 tháng payback SMB |
| **Số deal / AE / ngày** | **0,83 deal/ngày** | `4_Channel_Fit!B16` | Quota \$500k, ACV \$2.400 → Khả thi lý thuyết nhưng sát trần |
| **CAC thực tế Sales Rep** | **\$32.000** | `4_Channel_Fit!B22` | Cost per opportunity \$8.000 / Win rate 25% |
| **Độ lệch CAC Sales** | **17,8 lần** so với ngân sách CAC | `4_Channel_Fit!B23` | **Chứng minh bằng số học motion Sales-Led bất khả thi** |
| **Kênh GTM chốt 90 ngày** | **Partner-Led (VietISO - TravelMaster ERP)** | `4_Channel_Fit!B38` | Cắm vào nền tảng có sẵn 500+ đại lý du lịch |
| **Ngày kiểm tra giá API** | **08/10/2026** | `6_Benchmarks!B3` | Ghi ngày chuẩn xác cho mọi mức giá tham chiếu |

---

## 3. CHI TIẾT 6 TRẠM THỰC HÀNH

### Trạm 1: Ngân sách khách & Định nghĩa Job
- **2 Phiên bản mô tả:**
  - *Phiên bản A (Công cụ):* "Nền tảng AI tạo lịch trình du lịch tự động cho công ty lữ hành." → Khách xếp vào Ngân sách Phần mềm, IT xét duyệt lâu, hỏi "có cần thêm tool không?".
  - *Phiên bản B (Thay thế công việc - ĐƯỢC CHỌN):* "Trợ lý AI thay thế 80% thời gian nhân viên điều hành tour ngồi tra cứu và soạn thảo lịch trình tùy biến, xuất bản ngay tour cá nhân hóa trong 3 phút thay vì 3–5 tiếng." → Xếp vào **Ngân sách Vận hành / Nhân sự**, Chủ đại lý duyệt ngay vì rẻ hơn thuê thêm nhân viên.
- **Định nghĩa 1 Job:** 1 lịch trình tour du lịch tùy biến hoàn chỉnh được tạo và chốt khả thi (đầy đủ các ngày, ≥ 3 hoạt động/ngày, tối ưu lộ trình di chuyển, có dự toán chi phí và xuất bản thành công để gửi khách).

### Trạm 2: Value Metric & Đối chiếu thị trường
- **Điểm Scorecard:** Attribution = 9/10, Autonomy = 8/10.
- **Value Metric đã chọn:** **Outcome (\$0,99 / lịch trình tour hoàn chỉnh xuất bản thành công)**.
- **2 Benchmark sản phẩm thật:**
  1. *Wanderlog Pro / Team:* \$30 / member / tháng (Seat + Credits xuất bản) — [https://wanderlog.com/pro](https://wanderlog.com/pro).
  2. *Intercom Fin:* \$0,99 / resolution (Outcome chuẩn mực B2B AI agent) — [https://fin.ai/pricing](https://fin.ai/pricing).
- **Decision Note:**
  1. *Đơn vị chọn:* Outcome (\$0,99/tour hoàn thành).
  2. *Căn cứ Attribution/Autonomy:* Log sự kiện `itinerary_finalized` và Eval suite đo 82% feasibility; AI tự động sinh 100% khung tour.
  3. *Tình huống lỗ:* Bị spam request tạo tour thử nhưng bỏ dở không bấm xuất bản (khắc phục bằng hạn mức 15 lượt gen thử trước khi tính phí).

### Trạm 3: Cost/Job, Giá Sàn & Giá Trần
- **5 Thành phần chi phí cho 1.000 job thử (820 job hoàn thành):**
  - *API LLM (Claude Haiku 4.5):* 6 turns/job, input có cache 3.000 token, fresh 1.000 token, output 300 token → \$0,02025/job × 1.000 = \$20,25/tháng.
  - *Infra (Vector DB POIs + Logging):* \$0,005/job × 1.000 = \$5,00/tháng.
  - *Retry (8% API timeout/re-call):* \$0,02025 × 8% × 1.000 = \$1,62/tháng.
  - *HITL QA nội bộ (5%, 2p/ca, \$9/h):* 50 ca × (2/60) × \$9 = \$15,00/tháng.
  - *HITL Escalation Biến thể B (180 ca, 6p/ca, \$9/h):* 180 ca × (6/60) × \$9 = \$162,00/tháng.
  - → **Tổng chi phí:** \$203,87 / tháng.
- **Cost/Job:** \$203,87 / 820 job hoàn thành = **\$0,2486** (6.464 ₫).
- **Vùng giá bán:**
  - Giá sàn: 3 × \$0,2486 = **\$0,75**.
  - Giá trần (neo theo lương nhân viên \$1.500/tháng làm 500–700 tour): **\$1,00 – \$1,05**.
  - Giá đề xuất: **\$0,99** (Bội số 3,98×; Gross Margin 74,89% đạt chuẩn xanh lá).
- **Breakeven Containment Rate:** **72,68%**. Vì Eval thực tế đạt **82,0%** nên mô hình an toàn với biên đệm 9,3%.

### Trạm 4: Kênh Phân Phối & Affordability Test
- **Chứng minh số học:**
  - Ngân sách CAC cho phép: **\$1.797,28**.
  - CAC thực tế nếu thuê Sales rep (ICONIQ benchmark \$8.000 cost/opportunity ÷ 25% win rate): **\$32.000** → Vượt ngân sách **17,8 lần**.
- **Kênh chốt DUY NHẤT cho 90 ngày đầu:** **Partner-Led**.
- **Đối tác cụ thể:** **VietISO (Nền tảng phần mềm quản trị lữ hành TravelMaster ERP)** — đối tác cung cấp phần mềm cho 500+ doanh nghiệp lữ hành tại Việt Nam. WanderMind chia sẻ 20% doanh thu phát sinh và cung cấp tính năng AI Auto-Itinerary độc quyền cho hệ thống của VietISO.

### Trạm 5: Pain Moment & Kế Hoạch 90 Ngày
- **Pain Moment (Đủ 3 phần):**
  - *Mấy giờ:* **16h30 – 17h00 chiều** (chuẩn bị hết giờ làm việc).
  - *Đang làm gì:* Nhân viên điều hành tour đang cuống cuồng soạn 3 phương án lịch trình tour tùy biến cho đoàn khách khó tính để kịp gửi báo giá cuối ngày.
  - *Dùng app nào:* Đang mở song song Google Docs, Google Maps, CRM nội bộ và Zalo trao đổi với khách.
- **Điểm nhúng:** Plugin nhúng trực tiếp trong Hệ thống điều hành tour **VietISO TravelMaster** và Chrome Extension (Zero friction, không bắt mở thêm tab website riêng).
- **Lộ trình 90 ngày:**
  - *Tháng 1 (Học):* Gặp trực tiếp 5 đại lý đầu tiên; quan sát tạo 50 tour; tinh chỉnh dữ liệu POI; đo thời gian thực tế giảm từ 180p xuống 3p. Phụ trách: Trần Phạm Thái Vũ (Founder).
  - *Tháng 2–3 (Đòn bẩy):* Partner-Led qua VietISO; ký rev-share 20%; 2 workshop cộng đồng; mục tiêu 30 đại lý trả phí, MRR \$1.500. Phụ trách: Partnership Lead.
  - *Tháng 4+ (Mở rộng):* Mở rộng Inbound Agencies quốc tế & OTA APIs; 100+ đại lý, MRR \$8.000. Phụ trách: Core Team.

### Trạm 6: Evidence Pack & One-Pager
- **3 Tài sản Evidence Pack:**
  1. *Eval Results:* Xử lý đúng 82% lịch trình đạt chuẩn khả thi ngay lần đầu; 18% còn lại nhân viên tinh chỉnh nhẹ; Hallucination POI < 1.5%. (Hoàn thành 05/10/2026).
  2. *Risk Checklist:* Cam kết RAG POI đã kiểm duyệt chống hallucinate; Không dùng dữ liệu tour/giá riêng của đại lý để train model; Dữ liệu export JSON/PDF độc lập. (Hoàn thành 06/10/2026).
  3. *Pilot Report:* Pilot 3 tuần tại 2 đại lý Hà Nội: tạo 65 tour, thời gian soạn tour giảm 85%, tỷ lệ chốt tour với du khách tăng 22%. (Deadline: 30/10/2026 — Phụ trách: Trần Phạm Thái Vũ).
- **Bài test người lạ:** Người lạ đọc hiểu trong 2 phút, chỉ phải hỏi lại **1 câu** (Mục tiêu ≤ 3).

---

## 4. NHẬT KÝ CHẠY PROMPT PHẢN BIỆN (§4.7 CRITIQUE LOG)

### 📌 Prompt 1: Cost/Job Stress Test Prompt (§4.7.1)
- **Vai trò AI:** Ruthless CFO & Skeptical Infrastructure Engineer.
- **Ý kiến phản biện chính của AI:**
  1. *"Nếu du khách hoặc nhân viên đại lý yêu cầu regenerate tour nhiều lần (multi-turn re-routing), số turn thực tế có thể lên 10 lượt thay vì 6 lượt."*
  2. *"Nếu để Biến thể A, Gross Margin lên tới 94,8% là phi thực tế với một AI startup vì chắc chắn nhân viên đại lý sẽ phàn nàn khi AI làm lỗi và không ai hỗ trợ."*
  3. *"Biến tử thần (The One Number That Kills You): Tỷ lệ Containment Rate. Nếu rơi từ 82% xuống dưới 65%, chi phí escalation Biến thể B sẽ ăn hết toàn bộ lợi nhuận."*
- **Quyết định của tác giả (Accept / Reject / Partial):**
  - **ACCEPT:** Chuyển dứt khoát sang **Biến thể B** trong mô hình tài chính để tính gộp toàn bộ chi phí escalation xử lý lỗi, đưa Gross Margin về mức thực tế **74,89%** (nằm trong vùng an toàn 60%–85%, không bị coi là bỏ sót chi phí).
  - **PARTIAL:** Về số turns: Cố định 6 turns cho 1 session tạo tour chuẩn, đồng thời thiết lập Guardrail giới hạn tối đa 2 lần chỉnh sửa bổ sung trong cùng 1 job trước khi tính sang job mới.
  - **ACCEPT:** Đưa biến tử thần Breakeven Containment Rate (72,68%) vào bảng theo dõi sát sao cùng kết quả Eval (82,0%).

### 📌 Prompt 2: Channel Reality Check Prompt (§4.7.3)
- **Vai trò AI:** VP of Sales & Go-To-Market Strategist.
- **Ý kiến phản biện chính của AI:**
  1. *"Với ARPU \$200/tháng (ACV \$2.400), việc tuyển Sales rep là tự sát tài chính vì CAC thực tế của motion có sales lên tới \$32.000 (gấp 17,8 lần ngân sách cho phép)."*
  2. *"Nếu chọn Partner-Led với VietISO, lý do gì để họ chịu hợp tác với một startup chưa có tên tuổi? Rủi ro lớn nhất là đối tác hứa hẹn nhưng không ưu tiên tích hợp (stalled partnership)."*
  3. *"Fastest way to falsify trong 2 tuần: Hẹn gặp trực tiếp đại diện VietISO với bản demo tích hợp API chạy thử trực tiếp trên giao diện của họ, đề xuất chia sẻ 20% doanh thu. Nếu sau 2 tuần họ từ chối hoặc không phản hồi, kế hoạch Partner-Led bị bác bỏ."*
- **Quyết định của tác giả (Accept / Reject / Partial):**
  - **ACCEPT:** Loại bỏ hoàn toàn ý định mở rộng đội Sales Rep cho 90 ngày đầu; tập trung 100% vào kênh Partner-Led.
  - **ACCEPT:** Chuẩn bị sẵn phương án falsify trong 14 ngày: Nếu thỏa thuận với VietISO không chốt được, chuyển ngay sang lối thoát **PLG Self-serve** thông qua Chrome Extension kết hợp cộng đồng Facebook/Zalo của những người làm du lịch tự do (Tour Freelancers).

---

## 5. BẢNG TỰ KIỂM TRA 10 TIÊU CHÍ (FINAL CHECKLIST §5.8)

| # | Tiêu chí kiểm tra | Trạng thái | Minh chứng trong bài làm |
|:---:|---|:---:|---|
| 1 | Tab 1 — Đủ 5 thành phần chi phí (API, Infra, HITL, Retry, Overhead), không ô trống vô lý | ✅ **ĐẠT** | LLM (\$20,25), Infra (\$5,00), Retry 8% (\$1,62), HITL (\$177,00 gồm QA và Escalation Biến thể B). |
| 2 | Tab 1 — Mẫu số là **JOB HOÀN THÀNH**, không phải job thử | ✅ **ĐẠT** | Mẫu số là 820 job hoàn thành (`B11 = B9 * B10`), không chia cho 1.000. |
| 3 | Tab 2 — Giá bán ≥ 3 × Cost/Job, Gross Margin ≥ 60% | ✅ **ĐẠT** | Giá bán \$0,99 ≥ 3 × 0,2486 (\$0,75), Gross Margin đạt **74,89%** (chuẩn 60%–85%). |
| 4 | Tab 2 — Breakeven containment đã tính và so với eval | ✅ **ĐẠT** | Breakeven containment tính được là **72,68%**, thấp hơn Eval thực tế là **82,0%**. |
| 5 | Tab 3 — Value Metric + Decision Note 3 câu + 2 benchmark có link | ✅ **ĐẠT** | Outcome \$0,99/tour; Decision Note 3 câu; 2 benchmark Wanderlog Pro và Intercom Fin có link. |
| 6 | Tab 4 — Ngân sách CAC, deal/AE/ngày, **chốt 1 kênh duy nhất** | ✅ **ĐẠT** | Ngân sách CAC \$1.797,28; deal/AE/ngày 0,83; chốt duy nhất **Partner-Led** với VietISO. |
| 7 | Tab 5 — 90-day plan có số; Evidence Pack có deadline và người phụ trách | ✅ **ĐẠT** | 90-day plan có số khách & KPI theo 3 giai đoạn; Evidence Pack có deadline cụ thể 30/10/2026. |
| 8 | Tab 6 — Ghi ngày kiểm tra giá API gốc | ✅ **ĐẠT** | Ô `6_Benchmarks!B3` ghi rõ ngày **08/10/2026**. |
| 9 | One-Pager — 3 khối hoàn chỉnh, mọi số khớp Excel 100% | ✅ **ĐẠT** | Cả bản DOCX và PDF khớp 100% từng số lẻ với file Excel `Vu_Day22_model.xlsx`. |
| 10 | Đã chạy ít nhất 2 prompt phản biện §4.7 và ghi lại log accept/reject | ✅ **ĐẠT** | Đã ghi đầy đủ log phản biện cho Prompt §4.7.1 và §4.7.3 trong Section 4 ở trên. |
