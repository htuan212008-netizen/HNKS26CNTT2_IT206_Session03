# [Bài thực hành 5] Phân loại phản hồi của khách hàng

## 1. Xây dựng Prompt

### Prompt 1: Zero-shot Prompting
> Phân loại 5 phản hồi sau thành 3 nhãn (`Tích cực`, `Tiêu cực`, `Yêu cầu hỗ trợ`). Xuất kết quả dạng bảng gồm các cột: `STT`, `Phản hồi`, `Nhãn phân loại`, `Lý do`:
> 1. "Sản phẩm đẹp, giao hàng nhanh, rất hài lòng."
> 2. "Tôi đã đặt hàng 5 ngày nhưng chưa nhận được."
> 3. "Tai nghe không kết nối được Bluetooth."
> 4. "Nhân viên tư vấn rất nhiệt tình."
> 5. "Tôi muốn hoàn tiền vì sản phẩm bị lỗi."

### Prompt 2: Few-shot Prompting
> Phân loại 5 phản hồi trên thành 3 nhãn (`Tích cực`, `Tiêu cực`, `Yêu cầu hỗ trợ`).
> 
> **Ví dụ mẫu:**
> - "Chất lượng máy rất tốt." -> **Nhãn phân loại:** Tích cực | **Lý do:** Khen ngợi sản phẩm.
> - "Shop làm ăn chán quá." -> **Nhãn phân loại:** Tiêu cực | **Lý do:** Phàn nàn thái độ.
> - "Hướng dẫn giúp mình cài đặt." -> **Nhãn phân loại:** Yêu cầu hỗ trợ | **Lý do:** Cần giải quyết vấn đề kỹ thuật.
> 
> Xuất kết quả dạng bảng gồm các cột: `STT`, `Phản hồi`, `Nhãn phân loại`, `Lý do`.

---

## 2. Kết quả phân loại

| STT | Phản hồi | Nhãn phân loại | Lý do |
| :---: | :--- | :--- | :--- |
| 1 | "Sản phẩm đẹp, giao hàng nhanh, rất hài lòng." | Tích cực | Khách hàng khen ngợi sản phẩm và dịch vụ. |
| 2 | "Tôi đã đặt hàng 5 ngày nhưng chưa nhận được." | Yêu cầu hỗ trợ | Đơn hàng chậm, cần xử lý nghiệp vụ. |
| 3 | "Tai nghe không kết nối được Bluetooth." | Yêu cầu hỗ trợ | Sự cố kỹ thuật cần hướng dẫn khắc phục. |
| 4 | "Nhân viên tư vấn rất nhiệt tình." | Tích cực | Khen ngợi thái độ nhân viên. |
| 5 | "Tôi muốn hoàn tiền vì sản phẩm bị lỗi." | Yêu cầu hỗ trợ | Yêu cầu đổi trả do lỗi sản phẩm. |

---

## 3. So sánh Zero-shot vs Few-shot
* **Zero-shot:** Dễ nhầm lẫn các câu khiếu nại/sự cố (như đơn hàng chậm, lỗi sản phẩm) thành nhãn "Tiêu cực" thuần túy do chỉ dựa vào từ khóa cảm xúc.
* **Few-shot:** Độ chính xác và nhất quán cao hơn hẳn nhờ các ví dụ mẫu giúp AI hiểu đúng ngữ cảnh nghiệp vụ cần xử lý (`Yêu cầu hỗ trợ`).
