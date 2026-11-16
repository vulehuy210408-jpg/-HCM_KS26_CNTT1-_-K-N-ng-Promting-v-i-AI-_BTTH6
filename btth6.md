# [Bài thực hành 6] Chuẩn hóa dữ liệu sinh viên thành JSON
### C - Context (Bối cảnh)
Phòng đào tạo nhận danh sách thông tin sinh viên từ nhiều nguồn khác nhau. Dữ liệu thô hiện không đồng nhất về cách viết họ tên, email và trạng thái học tập. Cần sử dụng AI để chuẩn hóa dữ liệu và chuyển đổi thành định dạng JSON trước khi đưa vào hệ thống quản lý.

### R - Role (Vai trò)
Hãy đóng vai một chuyên gia Kỹ thuật dữ liệu (Data Engineer) và chuyên gia Prompt Engineering chuyên nghiệp, có nhiệm vụ xử lý và chuẩn hóa dữ liệu đầu vào theo đúng định dạng cấu trúc nghiêm ngặt.

### E - Explicit Instructions (Yêu cầu cụ thể)
Hãy đọc dữ liệu đầu vào, thực hiện chuẩn hóa trạng thái sinh viên và chuyển đổi thành định dạng JSON tuân thủ các quy tắc sau:
1. **Trường `fullName`:** Lưu họ và tên sinh viên (viết hoa chữ cái đầu, giữ nguyên dấu tiếng Việt).
2. **Trường `email`:** Lưu địa chỉ email chính xác của sinh viên.
3. **Trường `status`:** Chỉ được nhận một trong ba giá trị chuẩn: `đang học`, `bảo lưu`, hoặc `nghỉ học`. Nếu dữ liệu không xác định được, bắt buộc sử dụng `UNKNOWN`.
4. **Kiểm tra bản ghi:** Đếm chính xác tổng số bản ghi và gán vào trường `totalRecords`. Tuyệt đối không tự ý bổ sung hoặc làm mất bất kỳ bản ghi nào từ dữ liệu đầu vào.
5. **Định dạng đầu ra:** Chỉ trả về JSON thô, không có Markdown Code Fence (không dùng cặp dấu ```json ... ```), tuyệt đối không kèm theo bất kỳ lời giải thích hay chú thích nào bên ngoài JSON.

### A - Audience & Constraints (Đối tượng & Ràng buộc dữ liệu)
- **Dữ liệu đầu vào cần xử lý:**
  - Nguyễn Văn An - an.nguyen@gmail.com - đang học
  - Trần Thị Bình - binhtt@gmail.com - bảo lưu
  - Lê Hoàng Nam - nam.le@gmail.com - đang học
  - Phạm Minh Đức - duc.pham@gmail.com - nghỉ học
- **Ràng buộc nghiêm ngặt:** Đầu ra phải là chuỗi JSON thuần túy (raw JSON) theo đúng cấu trúc mẫu quy định.

### T - Tone & Format (Giọng văn & Định dạng đầu ra)
- **Giọng văn:** Khách quan, chuẩn xác, tuân thủ tuyệt đối logic lập trình.
- **Định dạng đầu ra bắt buộc:**
  ```json
  {
    "students": [
      {
        "fullName": "...",
        "email": "...",
        "status": "..."
      }
    ],
    "totalRecords": 4
  }