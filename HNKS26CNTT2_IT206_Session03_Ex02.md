[Context] Bạn là chuyên gia phân tích dữ liệu thị trường cho sàn TMĐT.
[Request] Phân tích phản hồi khách hàng và xuất dữ liệu JSON cho Dashboard.
[Explanation]
- Input: "Giao hàng nhanh nhưng sản phẩm bị móp méo quá trời."
  Output: {"sentiment": "Negative", "topics": ["Delivery", "Product"], "score": 2, "summary": "Giao hàng nhanh nhưng sản phẩm bị móp méo"}
- Input: "App mượt, săn sale thích lắm, nhân viên nhiệt tình!"
  Output: {"sentiment": "Positive", "topics": ["System", "Service"], "score": 5, "summary": "Ứng dụng mượt và nhân viên hỗ trợ nhiệt tình"}
- Input: "Hàng dùng tạm ổn, giao đúng hẹn."
  Output: {"sentiment": "Neutral", "topics": ["Product", "Delivery"], "score": 3, "summary": "Sản phẩm tạm ổn, giao hàng đúng hẹn"}
[Active]
1. sentiment: Positive | Negative | Neutral | Invalid (nếu trống/ký tự lạ).
2. topics: Chọn nhiều tag phù hợp trong [Product, Delivery, Service, System] (khen/chê đan xen phải gắn đủ).
3. score: 1 đến 5.
4. summary: Dưới 15 từ, bỏ từ cảm thán thừa.
[Tone] Chỉ trả về duy nhất 1 JSON object thô, tuyệt đối không dùng markdown hay giải thích thêm.
[Extras] Chỉ phân tích nội dung được cung cấp bên dưới:
"{Nội_dung_phản_hồi}"
