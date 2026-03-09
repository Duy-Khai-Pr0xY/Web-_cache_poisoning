# Web_cache_poisoning
#### Lợi dụng cách thức hoạt động của Web Cache để "lừa" hệ thống lưu trữ và phân phối nội dung độc hại đến những người dùng khác
#### Web Cache (thường nằm giữa người dùng và máy chủ gốc) có nhiệm vụ lưu lại các phản hồi (response) từ máy chủ. Khi có yêu cầu (request) tương tự gửi đến lần sau, Cache sẽ trả về nội dung đã lưu thay vì phải hỏi lại máy chủ gốc, giúp tăng tốc độ tải trang đáng kể
# Cách thức tấn công
#### 1.Gửi yêu cầu độc hại: Kẻ tấn công gửi một yêu cầu HTTP được thiết kế đặc biệt đến máy chủ.

#### 2.Máy chủ xử lý sai: Ứng dụng web xử lý yêu cầu này không đúng cách (ví dụ: phản hồi chứa dữ liệu do kẻ tấn công chèn vào, như các đoạn script độc hại, đường dẫn giả mạo) mà vẫn coi đó là một phản hồi hợp lệ.

#### 3.Lưu vào Cache: Hệ thống Cache nhận phản hồi từ máy chủ và lưu nó lại theo một Cache Key (thường là sự kết hợp của URL và một vài thông số khác).

#### 4.Phát tán: Những người dùng hợp pháp sau đó truy cập vào trang web đó. Thay vì nhận được dữ liệu gốc, Cache sẽ gửi cho họ nội dung "độc" đã bị đầu độc trước đó.
