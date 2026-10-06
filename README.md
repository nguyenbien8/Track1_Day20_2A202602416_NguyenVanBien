# Track1_Day20_2A202602416_NguyenVanBien

## 1. Thông tin học viên & Dự án
- **Họ và tên:** Nguyễn Văn Biển
- **Mã học viên (MHV):** 2A202602416
- **Hình thức:** Bài nộp cá nhân (Individual Submission)
- **Dự án chọn làm:** **AI Notes** — Trợ lý ghi chú học tập thông minh gắn ngữ cảnh nguồn (Slide bài giảng / Audio transcript).
- **Core Job:** Khi gặp những khái niệm khó trong bài giảng diễn ra dồn dập, người học muốn nhanh chóng hiểu đúng và lưu lại giải thích chuẩn xác gắn liền với trang tài liệu gốc, để khi làm bài tập tuần và ôn thi có thể tự tin sử dụng mà không sợ hiểu sai hay mất công lùng sục lại slide.

---

## 2. LINK tệp Metrics Pack (Đã cấp quyền xem)
Toàn bộ Metrics Pack được hoàn thiện đầy đủ 7 mục (00–06 + Revision Log), vượt qua 5 Gates đánh giá:
- 📄 **Tệp Metrics Pack (Bản Markdown đầy đủ 00–06):** 
  - Xem trực tiếp trên Repo: [metrics-pack.md](metrics-pack.md)
  - Link GitHub: [https://github.com/nguyenbien8/Track1_Day20_2A202602416_NguyenVanBien/blob/main/metrics-pack.md](https://github.com/nguyenbien8/Track1_Day20_2A202602416_NguyenVanBien/blob/main/metrics-pack.md)
- 🖥️ **Tệp trình bày trực quan (Interactive Visual Presentation & Dashboard View):**
  - Mở tệp cục bộ / trình duyệt: [metrics-pack.html](metrics-pack.html)
  - Link GitHub Pages (đã host trực tuyến): [https://nguyenbien8.github.io/Track1_Day20_2A202602416_NguyenVanBien/metrics-pack.html](https://nguyenbien8.github.io/Track1_Day20_2A202602416_NguyenVanBien/metrics-pack.html)
  - Link HTMLPreview online: [https://htmlpreview.github.io/?https://github.com/nguyenbien8/Track1_Day20_2A202602416_NguyenVanBien/blob/main/metrics-pack.html](https://htmlpreview.github.io/?https://github.com/nguyenbien8/Track1_Day20_2A202602416_NguyenVanBien/blob/main/metrics-pack.html)
- 📝 **Nhật ký dùng AI (AI Support Log):** [ai-support-log.md](ai-support-log.md)

---

## 3. Tóm tắt cấu trúc chuỗi quyết định logic (00 — 06)
- **00 — Phạm vi & Core Job:** Persona sinh viên (Hoàng Minh) với bài toán tiếp thu bài giảng nhanh và nỗi sợ AI hallucination.
- **01 — Core Action Card:** `Kiểm chứng nguồn và bấm lưu ghi chú học tập` (`note_verified_and_saved`) — Đạt 5/5 tiêu chí tự kiểm (Gate 1 Passed).
- **02 — Action Nature Card & Cadence:** Nhịp tự nhiên xuất phát từ lịch học tín chỉ đại học (2–3 buổi/tuần). Kết luận Cadence: **Weekly** ở cấp User cá nhân (Gate 2 Passed).
- **03 — Metric System:** 
  - *Activation:* Hoàn tất `note_verified_and_saved` đầu tiên trong 48h sau upload slide.
  - *Engagement:* Active Study Days/Week (2–3 ngày) & Tỷ lệ xem nguồn $\ge 75\%$.
  - *North Star Metric (NSM):* **Weekly Verified Notes Saved (WVNS)** = Unit of Value + Quality Threshold + Frequency.
  - *3 Leading Indicators:* Source Click-Through Rate, First-24h Note Conversion, Draft Customization Ratio.
  - *3 Counter-Metrics:* Unverified Quick-Save Rate, AI Citation Error Flag Rate, Inference Cost per Verified Note (Gate 3 Passed).
- **04 — Retention Definition (Đủ 6 thành phần):** Unit (User) · Cohort entry (`first_note_verified_and_saved`) · Return event (`note_verified_and_saved` / `note_referenced_for_review`) · Window (Weekly W1–W8) · Threshold ($\ge 1$ lần/tuần) · Segment (In-semester).
- **05 — Product Loop:** Progress & Compounding Knowledge Loop (2 chu kỳ logic: Tiếp thu/Lưu trữ $\rightarrow$ Làm bài tập/Tái kích hoạt); Metric Hypothesis trỏ trực tiếp về W4 Retention (Gate 4A Passed).
- **06 — Tracking nhanh:** 6 Core Events dạng `object_action` (map 1-1 với metric) + 2 Acceptance Criteria kỹ thuật chống bắn event non và chống trùng lặp (Gate 4B & Gate 5 Passed).

---

## 4. Điều tôi mang về áp dụng cho dự án thật
1. **Tư duy "Nature trước, Nurture sau":**
   - Trước đây tôi hay có thói quen sao chép các dashboard mẫu trên mạng, mặc định đo DAU/MAU và dùng Push Notification để "kéo user quay lại mỗi ngày". Bài lab Day 20 giúp tôi nhận ra: **Nurture chỉ có tác dụng khuếch đại nhịp tự nhiên (Nature), không thể bịa ra một nhịp không tồn tại**. Với AI Notes, sinh viên học theo tuần thì phải đo Weekly; ép Daily chỉ tạo ra số ảo và làm phiền người dùng bằng notification rác.
2. **Phân biệt rạch ròi giữa Thao tác UI, Output của AI và Value của User:**
   - Việc người dùng bấm mở app hay AI sinh ra 100 trang tóm tắt **hoàn toàn chưa chứng minh giá trị được tạo ra**. Core Action thật sự phải là khoảnh khắc người dùng thẩm thấu giá trị: họ kiểm chứng nguồn và lưu lại ghi chú an toàn. Đây là bài học sống còn khi phát triển các sản phẩm AI tạo sinh (GenAI Product).
3. **Kỷ luật trong định nghĩa Retention & Tracking:**
   - Không bao giờ nói câu mơ hồ "D7 Retention của app là 30%". Một định nghĩa retention chuẩn bắt buộc phải có đủ 6 thành tố (Unit, Cohort Entry, Return Event, Window, Threshold, Segment).
   - Về mặt kỹ thuật, Data Tracking không phải là "thấy nút nào cũng track". Mọi event phải map 1-1 với một câu hỏi sản phẩm hoặc một metric cụ thể, và bắt buộc phải có Acceptance Criteria nghiêm ngặt để ngăn chặn việc bắn event khi user mới click chuột (chưa hoàn tất transaction từ server) hoặc bắn trùng do reload/autosave.
