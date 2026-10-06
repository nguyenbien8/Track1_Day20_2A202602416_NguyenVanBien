# AI Support Log — Track 1 Day 20

**Học viên:** Nguyễn Văn Biển  
**MHV:** 2A202602416  
**Dự án:** AI Notes (Personal Learning Notes gắn ngữ cảnh nguồn)  

---

### 1. AI đã giúp tôi ở đâu?
- **Brainstorm danh sách ứng viên Core Action & phản biện góc nhìn người dùng:** AI hỗ trợ liệt kê các hành vi có thể diễn ra trong app (upload tài liệu, hỏi AI, xem tóm tắt, gắn nguồn, lưu ghi chú), giúp tôi nhanh chóng có dữ liệu để đưa lên bàn cân tự kiểm 5 tiêu chí.
- **Chuẩn hóa cú pháp tên Event:** Gợi ý các tên event tracking tuân thủ quy chuẩn `object_action` (ví dụ: `lecture_material_uploaded`, `note_verified_and_saved`, `source_citation_viewed`).
- **Gợi ý khung Acceptance Criteria kỹ thuật:** Đóng vai trò QA/Data Engineer để gợi ý các tình huống biên (edge cases) như reload trang (F5), rớt mạng retry, autosave nhằm viết tiêu chí nghiệm thu chặt chẽ chống duplicate và tránh bắn event non khi người dùng mới click nút trên client.

---

### 2. AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?
- **Đề xuất Core Action sai bản chất (Lỗi thao tác UI & Output AI):** Ban đầu AI gợi ý Core Action là *"Hỏi AI về bài giảng (Ask AI questions)"* hoặc *"Đọc tóm tắt bài giảng do AI tạo ra"*. Đây là lỗi kinh điển biến sản phẩm thành một wrapper chatbot ChatGPT thông thường, nhầm lẫn giữa thao tác giao diện / output hệ thống với hành vi tạo ra giá trị thực (Value Creation). Nếu user hỏi nhiều nhưng AI tóm tắt sai hoặc user không thẩm thấu kiến thức thì không có giá trị nào được tạo ra.
- **Ép Cadence Daily theo thói quen Dashboard (Vi phạm Nature vs Nurture):** AI tự động đề xuất đo `DAU` và `D7 Retention` với lý do *"để tối ưu hóa tần suất sử dụng mỗi ngày của học viên"*. Đây là tư duy rập khuôn tai hại: sinh viên đại học học theo tín chỉ (2–3 buổi/tuần cho mỗi môn), không sinh viên nào ngày nào cũng vào nạp bài mới của cùng một môn. Ép Daily sẽ dẫn đến việc dùng notification spam phiền nhiễu (nurture bóp méo nature).
- **North Star Metric thiếu Quality Threshold (Dễ bị Game):** AI đề xuất NSM là *"Số lượng câu hỏi được AI giải đáp hàng tuần"* hoặc *"Số ghi chú được tạo"*. Cả hai chỉ số này đều là số lượng thuần túy (vanity metrics), hoàn toàn có thể bị spam hoặc bot click mà không phản ánh việc sinh viên có thực sự học được gì hay không.

---

### 3. Tôi đã tự sửa hoặc quyết định lại điều gì?
- **Quyết định chọn Core Action là hành vi có kiểm chứng:** Tôi kiên quyết bác bỏ gợi ý của AI và chốt Core Action là **"Kiểm chứng nguồn và lưu ghi chú học tập gắn ngữ cảnh"** (`note_verified_and_saved`). Chỉ khi người học mở xem trích dẫn nguồn trên slide và bấm lưu, giá trị "tri thức tin cậy không hallucination" mới chính thức được xác lập.
- **Chuyển toàn bộ hệ thống Cadence sang Weekly:** Dựa trên quan sát thực tế lịch học đại học, tôi chốt nhịp tự nhiên là **Weekly (2–3 ngày học tích cực/tuần)**. Khung đo Retention chuyển sang **Weekly Brackets (W1 đến W8)** theo học kỳ, dứt khoát không dùng D7/D30.
- **Tái cấu trúc North Star Metric đúng công thức 3 vế:** Tôi tự xây dựng lại NSM = **Weekly Verified Notes Saved (WVNS)**, trong đó gắn chặt điều kiện kiểm chứng nguồn ($\ge 3$ giây) làm Quality Threshold, ngăn chặn hoàn toàn việc người dùng bấm "Lưu hàng loạt" mà không đọc.
- **Bổ sung Counter-metrics nghiêm ngặt cho AI:** Tôi tự thiết lập 2 counter-metrics: *Tỷ lệ lưu nhanh không xem nguồn (Unverified Quick-Save Rate)* để chống lười đọc, và *Tỷ lệ báo lỗi trích dẫn (AI Citation Error Flag Rate)* để giám sát hallucination của model AI.
