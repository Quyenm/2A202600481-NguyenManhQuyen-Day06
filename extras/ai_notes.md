# AI usage notes — Vinmec Assistant

Trong quá trình làm bài, tôi có dùng nhiều công cụ AI khác nhau để hỗ trợ các phần khác nhau của dự án.

## 1. GPT
### Dùng để:
- Viết lại và cấu trúc hóa SPEC
- Hoàn thiện AI Product Canvas
- Rút gọn nội dung cho slide
- Chỉnh wording cho rõ và dễ trình bày hơn
- Hỗ trợ xử lý các vấn đề kỹ thuật nhỏ như Docker / compose / README

### Nhận xét:
- Mạnh ở việc tổ chức nội dung, viết lại cho rõ và nhanh.
- Hữu ích nhất ở phần product writing và biến ý tưởng thô thành bản trình bày dễ hiểu.

---

## 2. Claude
### Dùng để:
- Brainstorm failure modes
- Gợi ý trust risks
- Gợi ý cách nhìn product theo hướng an toàn hơn trong bối cảnh y tế

### Nhận xét:
- Mạnh ở phần phân tích và mở rộng góc nhìn.
- Hữu ích khi muốn nghĩ sâu hơn về case AI trả lời sai hoặc vượt scope.

### Điểm cần lưu ý:
- Có lúc gợi ý mở rộng sản phẩm sang những tính năng nghe hay nhưng quá lớn cho hackathon.

---

## 3. Gemini
### Dùng để:
- So sánh phản hồi prompt
- Test nhanh một số cách phrasing khác nhau
- Kiểm tra thêm hành vi ở các câu hỏi mơ hồ hoặc ngoài lề nhẹ

### Nhận xét:
- Hữu ích như một nguồn so sánh thứ ba để xem prompt behavior có ổn định không.
- Tốt cho việc đối chiếu cách các model khác nhau xử lý cùng một tình huống.

---

## 4. Bài học rút ra
- AI rất mạnh để brainstorm, viết nháp và tăng tốc suy nghĩ.
- Tuy nhiên, AI không tự biết giới hạn scope phù hợp với hackathon.
- Người làm sản phẩm vẫn phải quyết định:
  - cái gì là core value
  - cái gì nên bỏ
  - cái gì cần giữ an toàn trong ngữ cảnh y tế
# extras/docker_notes.md

# Docker notes — frontend demo support

## Mục tiêu
Chuẩn bị frontend chạy được bằng Docker để hỗ trợ demo sản phẩm.

## Vấn đề gặp phải
### 1. Sai build context
- Khi chạy trong thư mục `frontend/`, file `docker-compose.yml` ban đầu dùng:
  `context: ./frontend`
- Điều này khiến Docker tìm đến đường dẫn `frontend/frontend` và báo lỗi không tìm thấy path.

### 2. Cảnh báo version trong docker compose
- Docker báo `version` là obsolete.
- Đây không phải lỗi nghiêm trọng, chỉ cần bỏ dòng `version` là được.

### 3. Build frontend fail
- Sau khi sửa context, Docker build được bình thường.
- Lỗi còn lại đến từ source code frontend, không còn là lỗi Docker nữa.

## Kết luận
- Docker issue chính nằm ở build context.
- Sau khi sửa, phần còn lại là lỗi code frontend chứ không phải lỗi container configuration.