- Context: Đóng vai trò Chuyên viên xử lý dữ liệu nhân sự.
- Request: Trích xuất các trường từ email ứng tuyển thô: Họ tên, Số điện thoại, Email, Vị trí ứng tuyển, Năm kinh nghiệm, Kỹ năng chính.
- Explanation: Dữ liệu dùng để import vào database tuyển dụng, yêu cầu chính xác 100%.
- Action: Quét email, trích xuất đúng trường thông tin, chuẩn hóa kỹ năng thành danh sách không trùng lặp, trả về đồng thời 1 bảng Markdown và 1 mảng JSON thô.
- Tone: Khách quan, chính xác.
- Extras (Ví dụ):
  * Input: "Chào HR, em là Hồ Anh Tuấn, ứng tuyển Backend Developer. 2 năm kinh nghiệm Python, SQL, FastAPI. SĐT: 0359223336, mail: htuan@gmail.com"
  * Output (Markdown): 
    | Họ tên | SĐT | Email | Vị trí | Kinh nghiệm | Kỹ năng |
    | :--- | :--- | :--- | :--- | :--- | :--- |
    | Hồ Anh Tuấn | 0359223336 | htuan@gmail.com | Backend Developer | 2 | Python, SQL, FastAPI |
  * Output (JSON):
```
    {
      "name": "Hồ Anh Tuấn",
      "phone": "0359223336",
      "email": "htuan@gmail.com",
      "position": "Backend Developer",
      "experience_years": 2,
      "skills": ["Python", "SQL", "FastAPI"]
    }
```
