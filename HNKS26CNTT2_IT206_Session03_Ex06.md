# [Bài thực hành 6] Chuẩn hóa dữ liệu sinh viên thành JSON

## 1. Xây dựng Prompt theo khuôn khổ CREATE

> **[Character / Role]**
> Bạn là một chuyên gia xử lý và chuẩn hóa dữ liệu tự động, có độ chính xác tuyệt đối, chuyên chuyển đổi dữ liệu văn bản thô thành định dạng JSON chuẩn.
> 
> **[Request / Task]**
> Đọc danh sách thông tin sinh viên đầu vào, chuẩn hóa trạng thái học tập theo đúng quy tắc, chuyển đổi toàn bộ thành cấu trúc JSON và kiểm tra kỹ số lượng bản ghi trước khi xuất kết quả.
> 
> **[Examples / Context]**
> Dữ liệu đầu vào cần xử lý:
> Nguyễn Văn An - an.nguyen@gmail.com - đang học
> Trần Thị Bình - binhtt@gmail.com - bảo lưu
> Lê Hoàng Nam - nam.le@gmail.com - đang học
> Phạm Minh Đức - duc.pham@gmail.com - nghỉ học
> 
> **[Adjustments / Rules]**
> - Trường `fullName`: Giữ nguyên họ và tên.
> - Trường `email`: Giữ nguyên địa chỉ email.
> - Trường `status`: Chỉ được nhận một trong ba giá trị chính xác (`đang học`, `bảo lưu`, `nghỉ học`).
> - Không tự ý bổ sung thông tin ngoài dữ liệu gốc.
> - Không được làm mất bất kỳ bản ghi nào (tổng cộng phải có 4 bản ghi).
> - Nếu dữ liệu không xác định được, bắt buộc phải dùng giá trị `UNKNOWN`.
> 
> **[Type / Output Format]**
> Chỉ trả về duy nhất định dạng JSON thô tuân thủ cấu trúc mẫu dưới đây. Tuyệt đối không sử dụng Markdown Code Fence (không dùng các dấu ```json ... ```), không kèm theo bất kỳ lời giải thích nào bên ngoài.
> 
> Cấu trúc mẫu yêu cầu:
> {
>   "students": [
>     {
>       "fullName": "Nguyễn Văn An",
>       "email": "an.nguyen@gmail.com",
>       "status": "đang học"
>     }
>   ],
>   "totalRecords": 4
> }

---

## 2. Kết quả JSON đầu ra
```
{
  "students": [
    {
      "fullName": "Nguyễn Văn An",
      "email": "an.nguyen@gmail.com",
      "status": "đang học"
    },
    {
      "fullName": "Trần Thị Bình",
      "email": "binhtt@gmail.com",
      "status": "bảo lưu"
    },
    {
      "fullName": "Lê Hoàng Nam",
      "email": "nam.le@gmail.com",
      "status": "đang học"
    },
    {
      "fullName": "Phạm Minh Đức",
      "email": "duc.pham@gmail.com",
      "status": "nghỉ học"
    }
  ],
  "totalRecords": 4
}
```
