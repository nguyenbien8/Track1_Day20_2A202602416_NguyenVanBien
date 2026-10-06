# AI Support Log

**Học viên:** Nguyễn Văn Biển · **MHV:** 2A202602416 · **Dự án:** AI Notes (ghi chú học tập gắn ngữ cảnh nguồn)

---

## AI đã giúp tôi ở đâu?

- **Brainstorm ứng viên core action:** AI liệt kê nhanh các hành vi có thể chọn (upload slide, hỏi chatbot, đọc tóm tắt AI, mở nguồn trích dẫn, lưu ghi chú) để tôi tự chấm bằng 5 tiêu chí.
- **Gợi ý tên event dạng `object_action`:** ví dụ `material_uploaded`, `source_citation_viewed`, `note_saved`.
- **Gợi ý tình huống biên cho acceptance criteria:** AI đóng vai QA/data engineer, nêu các bẫy như reload trang, rớt mạng rồi retry, autosave bản nháp, bấm nút trước khi server xác nhận.
- **Rà soát tính nhất quán trước khi nộp:** tôi nhờ AI (Claude) đọc lại toàn bộ Metrics Pack theo checklist của lab. AI chỉ ra các chỗ lệch nhau (ngưỡng 3s / 1s / 0ms, hai tên endpoint khác nhau), các counter-metric chưa có event để tính, link anchor trong README bị hỏng, và các con số không có nguồn.

---

## AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?

- **Core action sai bản chất:** ban đầu AI gợi ý core action là *"hỏi AI về bài giảng"* hoặc *"đọc tóm tắt do AI tạo"*. Cái đầu là thao tác giao diện, cái sau là output hệ thống. User hỏi nhiều hay AI sinh nhiều nháp không có nghĩa là user đã hiểu bài.
- **Ép cadence daily:** AI đề xuất đo `DAU` và `D7 retention` "để tối ưu tần suất sử dụng mỗi ngày". Sinh viên học theo lịch tín chỉ, mỗi môn 1–2 buổi/tuần; ép daily chỉ dẫn tới notification phiền và số ảo.
- **NSM thiếu quality threshold:** AI đề xuất NSM là *"số câu hỏi AI trả lời"* hoặc *"số ghi chú được tạo"*. Đây là số lượng thuần, bấm "lưu tất cả" là game được ngay.
- **Bịa số liệu:** trong bản nháp có những con số "tham khảo" như benchmark W4 retention ngành EdTech, "tăng gấp 3.2 lần", "tiết kiệm 70% thời gian" mà không có nguồn nào. Lab cấm điều này, nên tôi đã bỏ hết.

---

## Tôi đã tự sửa hoặc quyết định lại điều gì?

- **Chốt core action là hành vi có kiểm chứng:** tôi bác gợi ý "hỏi AI" và chọn **"lưu một ghi chú đã đối chiếu nguồn"**. Chỉ khi learner mở nguồn đối chiếu rồi mới lưu thì giá trị "tri thức đáng tin, không bị AI bịa" mới xảy ra.
- **Chuyển cadence sang weekly:** dựa trên lịch học thật (2–3 buổi có nội dung mới/tuần), tôi chốt nhịp đo weekly ở cấp user. Retention đo theo tuần lịch W1–W8, segment in-semester, không dùng D7/D30.
- **Dựng lại NSM đủ 3 vế:** **Weekly Verified Notes Saved**, với quality threshold là có nguồn hợp lệ, nội dung ≥ 20 ký tự và đã mở nguồn ≥ 3 giây. Mỗi note chỉ đếm một lần.
- **Thêm counter-metric riêng cho sản phẩm AI:** tỉ lệ lưu không xem nguồn (UQSR), tỉ lệ báo lỗi trích dẫn (CERR) và chi phí LLM mỗi verified note (ICPVN).
- **Sửa sau lượt rà soát cuối:** đổi event thành `note_saved` + thuộc tính `is_verified`, để đếm được cả các lần lưu *không* verify cho UQSR. Thống nhất ngưỡng 3 giây ở mọi nơi. Thêm event `citation_error_reported`. Bỏ toàn bộ số không có nguồn và viết lại metric hypothesis thành phép so sánh hai nhóm learner, baseline lấy từ cohort học kỳ đầu. Lý do từng thay đổi được ghi trong revision log ở cuối Metrics Pack.
