# Track1_Day20_2A202602416_NguyenVanBien

## 1. Thông tin cá nhân & Dự án
- **Họ và tên:** Nguyễn Văn Biển
- **Mã học viên (MHV):** 2A202602416
- **Nhóm:** DBH (Phạm Quốc Đạt - 2A202602384, Nguyễn Văn Biển - 2A202602416, Mai Tiến Huy - 2A202602914)
- **Dự án chọn làm:** **AI Notes** — Trợ lý ghi chú học tập thông minh gắn ngữ cảnh nguồn (Slide bài giảng / Audio transcript).
- **Mục tiêu sản phẩm:** Giải quyết bài toán sinh viên không kịp ghi chép và sợ AI bị ảo giác (hallucination) bằng cách cung cấp bản nháp giải thích gắn chặt với số trang slide nguồn, hỗ trợ kiểm chứng và tích lũy tri thức đáng tin cậy.

---

## 2. Link tệp Metrics Pack (Đã cấp quyền xem)
Toàn bộ hệ thống Metrics Pack chuẩn chỉnh theo framework Day 20 được lưu trữ trong repository này:
- 📄 **Tệp Metrics Pack chi tiết (Markdown đầy đủ 00–07):** [metrics-pack.md](metrics-pack.md)
- 🖥️ **Tệp trình bày trực quan (Interactive Visual Dashboard & Slide View):** [metrics-pack.html](metrics-pack.html) *(Mở trực tiếp trên bất kỳ trình duyệt nào để xem giao diện trực quan cao cấp, sơ đồ loop và bảng kiểm 5 Gates)*
- 📝 **Nhật ký tương tác AI:** [ai-support-log.md](ai-support-log.md)

---

## 3. Tóm tắt cấu trúc Metrics Pack (00 — 06)
1. **00 — Phạm vi & Core Job:** Sinh viên năm 3 (Hoàng Minh) cần nắm chắc khái niệm khó và lưu tài liệu ôn thi có trích dẫn nguồn xác thực.
2. **01 — Core Action Card:** `Kiểm chứng nguồn và bấm lưu ghi chú học tập` (`note_verified_and_saved`) — Đạt 5/5 tiêu chí tự kiểm (Gate 1 Passed).
3. **02 — Action Nature Card & Cadence:** Hành vi diễn ra theo chu kỳ tuần của môn học (2–3 buổi/tuần). Kết luận Cadence: **Weekly** ở cấp độ cá nhân (Gate 2 Passed).
4. **03 — Metric System:** 
   - **Activation:** Hoàn tất `note_verified_and_saved` đầu tiên trong 48h sau upload tài liệu.
   - **Engagement:** Active Study Days/Week (2–3 ngày) & Tỷ lệ xem nguồn $\ge 75\%$.
   - **North Star Metric (NSM):** **Weekly Verified Notes Saved (WVNS)** = Unit of Value + Quality Threshold + Frequency.
   - **3 Leading Indicators:** Source Click-through Rate, First-24h Conversion, Draft Customization Ratio.
   - **3 Counter-metrics:** Unverified Quick-Save Rate, AI Citation Error Flag Rate, Inference Cost per Verified Note (Gate 3 Passed).
5. **04 — Retention Definition (Đủ 6 thành phần):** Unit (User) · Cohort entry (`first_note_verified_and_saved`) · Return event (`note_verified_and_saved` / `note_referenced_for_review`) · Window (Weekly W1–W8) · Threshold ($\ge 1$ lần/tuần) · Segment (In-semester).
6. **05 — Product Loop:** Progress & Compounding Knowledge Loop (2 chu kỳ logic), kèm Metric Hypothesis trỏ trực tiếp về W4 Retention (Gate 4A Passed).
7. **06 — Tracking nhanh:** 6 Core Events chuẩn `object_action` (map 1-1 với metrics) + 2 Acceptance Criteria kỹ thuật chống bắn event non và chống trùng lặp (Gate 4B & 5 Passed).

---

## 4. Điều tôi mang về áp dụng cho dự án thật
1. **Tư duy "Nature trước, Nurture sau":**
   - Trước đây tôi hay có thói quen sao chép các dashboard mẫu trên mạng, mặc định đo DAU/MAU và dùng Push Notification để "kéo user quay lại mỗi ngày". Bài lab Day 20 giúp tôi nhận ra: **Nurture chỉ có tác dụng khuếch đại nhịp tự nhiên (Nature), không thể bịa ra một nhịp không tồn tại**. Với AI Notes, sinh viên học theo tuần thì phải đo Weekly; ép Daily chỉ tạo ra số ảo và làm phiền người dùng bằng notification rác.
2. **Phân biệt rạch ròi giữa Thao tác UI, Output của AI và Value của User:**
   - Việc người dùng bấm mở app hay AI sinh ra 100 trang tóm tắt **hoàn toàn chưa chứng minh giá trị được tạo ra**. Core Action thật sự phải là khoảnh khắc người dùng thẩm thấu giá trị: họ kiểm chứng nguồn và lưu lại ghi chú an toàn. Đây là bài học sống còn khi phát triển các sản phẩm AI tạo sinh (GenAI Product).
3. **Kỷ luật trong định nghĩa Retention & Tracking:**
   - Không bao giờ nói câu mơ hồ "D7 Retention của app là 30%". Một định nghĩa retention chuẩn bắt buộc phải có đủ 6 thành tố (Unit, Cohort Entry, Return Event, Window, Threshold, Segment).
   - Về mặt kỹ thuật, Data Tracking không phải là "thấy nút nào cũng track". Mọi event phải map 1-1 với một câu hỏi sản phẩm hoặc một metric cụ thể, và bắt buộc phải có Acceptance Criteria nghiêm ngặt để ngăn chặn việc bắn event khi user mới click chuột (chưa hoàn tất transaction từ server) hoặc bắn trùng do reload/autosave.
