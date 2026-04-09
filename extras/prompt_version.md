# Prompt versions — Vinmec Assistant

## Version 1
### Đặc điểm
- Scope khá chặt, chỉ cho trả lời đúng các chủ đề liên quan trực tiếp đến chuẩn bị khám tại Vinmec.
- Có checklist format rõ ràng.
- Có rule từ chối nếu câu hỏi ngoài scope.

### Vấn đề gặp phải
- Bot từ chối quá sớm khi user hỏi mơ hồ hoặc nói ngoài lề nhẹ.
- Một số câu như:
  - "Tôi hơi lo trước khi đi khám"
  - "Tôi đi lần đầu"
  - "Ở Hưng Yên có Vinmec không?"
  dễ bị trả lời khá cụt.

### Nhận xét
- An toàn nhưng thiếu tự nhiên.
- Trải nghiệm hội thoại chưa tốt.

---

## Version 2
### Thay đổi chính
- Giữ nguyên citation rules và tool routing.
- Nới phần scope để chấp nhận các câu hỏi liên quan gián tiếp đến hành trình khám.
- Thêm handling cho câu hỏi mơ hồ.
- Điều chỉnh out-of-scope reply theo hướng mềm hơn.

### Cải thiện
- Bot đỡ từ chối sớm hơn.
- Có xu hướng hỏi lại để làm rõ thay vì xin lỗi ngay.
- Hội thoại tự nhiên hơn.

### Hạn chế
- Một số câu vẫn còn hơi chung chung.
- Chưa tối ưu tốt cho case user hỏi ngắn kiểu 1 cụm từ.

---

## Version 3
### Thay đổi chính
- Thêm `conversation_style`
- Thêm `ambiguity_handling`
- Quy định rõ:
  - nếu user mơ hồ thì hỏi lại 1 câu ngắn
  - nếu ngoài lề nhẹ nhưng vẫn liên quan đến hành trình khám thì redirect mềm
  - chỉ từ chối khi thực sự ngoài scope

### Kết quả
- Bot tự nhiên hơn rõ rệt.
- Ít trả lời cụt.
- Phù hợp hơn với mục tiêu sản phẩm là hỗ trợ chuẩn bị trước khám, không chỉ trả lời FAQ cứng.

### Kết luận
- Chọn version 3 làm bản prompt chính để demo.