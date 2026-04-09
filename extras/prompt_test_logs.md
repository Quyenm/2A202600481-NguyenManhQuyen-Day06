# Prompt test logs — Vinmec Assistant

## Test 1 — Checklist cơ bản
**Input:** Tôi chuẩn bị đi xét nghiệm máu tổng quát, cần chuẩn bị gì?  
**Expected:** Trả checklist rõ ràng, có nhịn ăn, giấy tờ, đặt lịch, thời gian dự kiến.  
**Actual:** Bot trả checklist đúng format.  
**Result:** Pass

---

## Test 2 — User hỏi mơ hồ
**Input:** Tôi đi khám tổng quát.  
**Expected:** Không trả lời quá chung chung, nên hỏi thêm để làm rõ.  
**Actual:** Ở bản prompt đầu, bot trả lời còn khá chung. Sau khi thêm ambiguity handling, bot hỏi lại người dùng muốn khám gì / làm xét nghiệm gì.  
**Result:** Improved after prompt refinement

---

## Test 3 — Ngoài lề nhẹ nhưng vẫn liên quan
**Input:** Tôi hơi lo vì mai đi khám lần đầu.  
**Expected:** Không từ chối, nên phản hồi nhẹ nhàng rồi hướng user quay lại việc chuẩn bị khám.  
**Actual:** Bản prompt đầu từ chối hơi cứng. Bản sau phản hồi mềm hơn và gợi ý tạo checklist.  
**Result:** Improved

---

## Test 4 — Tìm cơ sở Vinmec
**Input:** Tôi ở Hưng Yên có Vinmec không?  
**Expected:** Trả lời theo hướng tìm cơ sở gần nhất hoặc hướng dẫn location.  
**Actual:** Bot xử lý đúng hướng location.  
**Result:** Pass

---

## Test 5 — Câu hỏi ngoài scope thật sự
**Input:** Hôm nay trời thế nào?  
**Expected:** Từ chối đúng mẫu out-of-scope.  
**Actual:** Bot từ chối đúng phạm vi sản phẩm.  
**Result:** Pass

---

## Test 6 — User hỏi về giấy tờ
**Input:** Đi khám ở Vinmec cần mang gì?  
**Expected:** Trả lời ngắn gọn về giấy tờ và có thể hỏi thêm nếu cần checklist đầy đủ.  
**Actual:** Bot trả lời đúng hướng và vẫn giữ trong scope.  
**Result:** Pass

---

## Test 7 — User hỏi quá rộng
**Input:** Tôi nên làm gì trước khi đi bệnh viện?  
**Expected:** Không từ chối ngay, hỏi lại để làm rõ là muốn khám gì hoặc muốn tìm cơ sở nào.  
**Actual:** Sau khi chỉnh prompt, bot hỏi follow-up ngắn thay vì trả lời cứng.  
**Result:** Improved

---

## Tổng kết
### Điểm ổn
- Checklist format rõ ràng
- Scope y tế Vinmec được giữ an toàn
- Bot tốt hơn sau khi thêm ambiguity handling

### Điểm còn hạn chế
- Một số câu rất ngắn vẫn cần follow-up để tránh trả lời quá chung
- Chưa có bộ test lớn, mới chủ yếu test thủ công theo case