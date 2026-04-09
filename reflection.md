# Individual reflection — Nguyễn Mạnh Quyền - 2A202600481
## 1. Role
Product/spec writer + prompt designer + technical integration support.  
Phụ trách chính phần SPEC, AI Product Canvas, định hướng luồng sản phẩm, chỉnh system prompt cho Vinmec assistant, và hỗ trợ phần cấu hình frontend / Docker trong quá trình demo.

## 2. Đóng góp cụ thể
- Viết bản SPEC chính của nhóm cho bài toán **VinmecPrep AI**: problem statement, AI Product Canvas, user flow, metrics, failure modes, ROI.
- Chỉnh và hoàn thiện phần **AI Product Canvas** để làm rõ 3 ý chính: **Value, Trust, Feasibility**.
- Xây dựng và refine **system prompt** cho Vinmec assistant, đặc biệt ở các phần:
  - scope / out-of-scope
  - checklist format
  - citation rules
  - cách xử lý câu hỏi mơ hồ để bot không từ chối quá sớm
- Hỗ trợ chuyển hóa SPEC thành nội dung ngắn gọn để đưa lên slide thuyết trình.
- Hỗ trợ nhóm ở phần kỹ thuật demo: chỉnh Dockerfile, docker-compose cho frontend và xử lý một số lỗi build / path trong lúc chạy thử.

## 3. SPEC mạnh/yếu
- **Mạnh nhất:** phần **Value – Trust – Feasibility** khá rõ. Nhóm xác định đúng đây là bài toán augmentation chứ không phải automation, nên hợp với bối cảnh y tế và an toàn hơn cho người dùng.
- **Mạnh nhất nữa:** phần failure modes và prompt behavior khá thực tế, đặc biệt là case user hỏi mơ hồ hoặc nói ngoài lề nhẹ nhưng vẫn liên quan đến hành trình khám.
- **Yếu nhất:** phần ROI vẫn còn mang tính giả định khá nhiều. Chi phí inference thì ước lượng được, nhưng phần benefit thực tế như giảm bao nhiêu cuộc gọi hotline hay tiết kiệm bao nhiêu thời gian hỗ trợ vẫn chưa có dữ liệu thật để chứng minh.
- **Yếu nữa:** phần eval mới dừng ở mức logic sản phẩm và test case nhỏ, chưa có bộ dữ liệu đủ lớn để validate ổn định.

## 4. Đóng góp khác
- Dùng **GPT, Claude và Gemini** để so sánh nhiều hướng triển khai:
  - GPT: hỗ trợ viết lại SPEC, Canvas, slide content và chỉnh wording cho rõ hơn
  - Claude: brainstorm failure modes, trust issues, product framing
  - Gemini: hỗ trợ test ý tưởng prompt và so sánh phản hồi trong các tình huống user hỏi mơ hồ
- Hỗ trợ viết lại nội dung slide giới thiệu sản phẩm bằng tiếng Anh và tiếng Việt theo bản ngắn gọn, dễ thuyết trình.
- Hỗ trợ nhóm rà lại cách đặt scope để tránh bị “scope creep”, ví dụ không đẩy sản phẩm đi quá xa sang đặt lịch thật hoặc tư vấn y khoa chuyên sâu.

## 5. Điều học được
Trước hackathon, em nghĩ làm AI product chủ yếu là nghĩ ra feature rồi gắn model vào.  
Sau khi làm bài này, em hiểu rõ hơn rằng phần khó nhất không phải chỉ là model, mà là:
- xác định scope đủ hẹp để làm được,
- thiết kế trust cho đúng ngữ cảnh,
- và viết prompt sao cho bot vừa hữu ích vừa không đi quá giới hạn.

Em cũng học được rằng **prompt design là một phần của product design**.  
Ví dụ cùng một assistant, nếu scope quá cứng thì bot sẽ trả lời rất cụt; nhưng nếu nới quá nhiều thì lại dễ vượt phạm vi và tăng rủi ro.  
Nên việc chỉnh prompt không chỉ là kỹ thuật, mà là quyết định UX và product.

## 6. Nếu làm lại
- Em sẽ test prompt sớm hơn, thay vì viết SPEC khá kỹ rồi mới quay lại refine behavior của bot.
- Em cũng sẽ tách sớm hơn giữa:
  - phần nào là core value thật sự của sản phẩm,
  - phần nào chỉ là “nice-to-have”.
- Ngoài ra, nếu có thêm thời gian, em sẽ chuẩn bị một bộ test conversation chuẩn hơn để đo consistency của assistant, thay vì chỉ test thủ công theo từng case.

## 7. AI giúp gì / AI sai gì
- **Giúp:**  
  - GPT giúp em viết lại và cấu trúc hóa SPEC, Canvas, và slide content nhanh hơn rất nhiều.
  - Claude giúp brainstorm failure modes, trust risks, và cách diễn đạt product rõ hơn.
  - Gemini hữu ích khi muốn kiểm tra thêm một góc nhìn khác về prompt behavior và cách bot phản hồi trong các tình huống mơ hồ.
- **Sai / mislead:**  
  - Có lúc AI gợi ý mở rộng scope sang những hướng nghe rất hay như chatbot tư vấn sâu hơn, đặt lịch trực tiếp, hoặc xử lý quá nhiều loại câu hỏi ngoài bài toán chính.
  - Một số gợi ý nhìn bề ngoài khá thuyết phục nhưng nếu đưa hết vào thì sẽ làm sản phẩm bị phình to, khó làm trong thời gian hackathon.
- **Bài học:**  
  AI rất mạnh để brainstorm, viết nháp và tăng tốc suy nghĩ, nhưng mình vẫn phải là người quyết định scope, chọn đúng cái cần làm, và bỏ bớt những thứ “nghe hay nhưng không cần thiết”.