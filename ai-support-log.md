# AI Support Log — viết ngắn

**Học viên:** Nguyễn Văn Biển · **MHV:** 2A202602416 · **Dự án:** AI Notes (Personal Learning Notes gắn ngữ cảnh nguồn)

---

## AI đã giúp tôi ở đâu?
- **Brainstorm danh sách ứng viên Core Action:** AI giúp liệt kê nhanh các hành vi tiềm năng trong app (upload slide, hỏi chatbot, đọc tóm tắt AI, click đối chiếu nguồn, bấm lưu ghi chú) để tôi đưa vào bảng tự kiểm 5 tiêu chí.
- **Chuẩn hóa cú pháp tên Event:** Gợi ý định dạng chuẩn `object_action` (ví dụ: `lecture_material_uploaded`, `note_verified_and_saved`, `source_citation_viewed`).
- **Gợi ý khung Acceptance Criteria kỹ thuật:** Đóng vai trò QA/Data Engineer gợi ý các tình huống biên (edge cases) như reload trang (F5), rớt mạng retry, autosave định kỳ để viết tiêu chí nghiệm thu chặt chẽ chống duplicate và chặn bắn event khi chưa có HTTP 200 từ server.

---

## AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?
- **Đề xuất Core Action sai bản chất (Lỗi thao tác UI & Output của AI):** Ban đầu AI gợi ý chọn Core Action là *"Hỏi AI về bài giảng (Ask AI questions)"* hoặc *"Đọc tóm tắt bài giảng do AI tạo ra"*. Đây là lỗi kinh điển: biến app thành chatbot ChatGPT wrapper, nhầm thao tác giao diện hoặc output của hệ thống với hành vi tạo ra giá trị thật (Value Creation). User hỏi nhiều hay AI sinh nhiều nháp nhưng nếu bài sai hoặc user không đọc thì không hề có giá trị.
- **Ép Cadence Daily theo thói quen Dashboard (Vi phạm Nature vs Nurture):** AI tự động đề xuất đo `DAU` và `D7 Retention` với lý do *"để tối ưu hóa tần suất sử dụng mỗi ngày của học viên"*. Đây là tư duy rập khuôn tai hại: sinh viên học theo tín chỉ môn học (2–3 buổi/tuần), không ai ngày nào cũng nạp bài mới của cùng một môn. Ép Daily sẽ biến sản phẩm thành công cụ spam notification phiền toái.
- **North Star Metric thiếu Quality Threshold (Dễ bị Game):** AI đề xuất NSM là *"Số lượng câu hỏi AI giải đáp"* hoặc *"Số ghi chú được tạo"*. Đây là số lượng thuần túy (vanity metrics), hoàn toàn bị game bởi bot hoặc user click bừa mà không đo được chất lượng tiếp thu kiến thức.

---

## Tôi đã tự sửa hoặc quyết định lại điều gì?
- **Quyết định chọn Core Action là hành vi có kiểm chứng:** Tôi kiên quyết bác bỏ gợi ý của AI và chốt Core Action là **"Kiểm chứng nguồn và lưu ghi chú học tập gắn ngữ cảnh"** (`note_verified_and_saved`). Chỉ khi người học mở xem trích dẫn nguồn trên slide và bấm lưu, giá trị "tri thức tin cậy không hallucination" mới chính thức được xác lập.
- **Chuyển toàn bộ hệ thống Cadence sang Weekly:** Dựa trên thực tế lịch học đại học, tôi chốt nhịp tự nhiên là **Weekly (2–3 ngày học tích cực/tuần)**. Khung đo Retention chuyển sang **Weekly Brackets (W1 đến W8)** theo học kỳ, dứt khoát không dùng D7/D30.
- **Tái cấu trúc North Star Metric đúng công thức 3 vế:** Tôi tự xây dựng lại NSM = **Weekly Verified Notes Saved (WVNS)**, trong đó gắn chặt điều kiện kiểm chứng nguồn ($\ge 3$ giây) làm Quality Threshold, ngăn chặn việc bấm "Lưu hàng loạt" mà không đọc.
- **Bổ sung Counter-metrics nghiêm ngặt cho AI:** Tôi tự thiết lập 2 counter-metrics: *Tỷ lệ lưu nhanh không xem nguồn (Unverified Quick-Save Rate)* để chống lười đọc, và *Tỷ lệ báo lỗi trích dẫn (AI Citation Error Flag Rate)* để giám sát hallucination của model AI.
