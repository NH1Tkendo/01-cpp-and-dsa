### 1. Khái niệm cơ bản

- **Bộ tiền xử lý (Preprocessor)**: Là một chương trình thực hiện nhiệm vụ xử lý mã nguồn (source code) **trước khi** nó được chuyển đến trình biên dịch (compiler).
    
- **Lưu ý cực kỳ quan trọng**: Bộ tiền xử lý C++ **hoàn toàn không hiểu ngôn ngữ C++**. Nó chỉ tuân theo các chỉ thị để chuẩn bị sẵn sàng mã nguồn. Trình biên dịch (compiler) mới là thành phần thực sự hiểu cú pháp và ngữ nghĩa của C++.
    

### 2. Trình tự và Cách thức hoạt động

Khi chạy chương trình, bộ tiền xử lý sẽ thực hiện các bước sau:

1. **Dọn dẹp mã nguồn**: Loại bỏ tất cả các chú thích (comments) trong tệp mã nguồn và thay thế mỗi đoạn chú thích bằng một khoảng trắng (space) duy nhất.
    
2. **Xử lý chỉ thị**: Tìm kiếm và thực thi các **chỉ thị tiền xử lý (preprocessor directives)**. Đây là những dòng mã bắt đầu bằng ký hiệu dấu thăng `#` (hashtag).
    
3. **Kết quả đầu ra**: Đưa cho trình biên dịch một bản mã nguồn "sạch", nơi toàn bộ chú thích đã bị xóa và các chỉ thị tiền xử lý đã được thực thi và loại bỏ khỏi mã.
    

### 3. Các chỉ thị tiền xử lý phổ biến

#### Chỉ thị bao gồm (`#include`)

- Đây là chỉ thị tiền xử lý được sử dụng thường xuyên nhất.
    
- **Cách hoạt động**: Khi gặp `#include`, bộ tiền xử lý sẽ sao chép toàn bộ nội dung của tệp được tham chiếu và dán trực tiếp để thay thế cho dòng `#include` đó. Quá trình này được thực hiện một cách đệ quy (recursively), tức là nếu tệp được gọi cũng chứa các chỉ thị khác, chúng cũng sẽ được xử lý tiếp.
    

#### Biên dịch có điều kiện (Conditional Compilation)

- Chỉ thị tiền xử lý thường được dùng để chỉ định trình biên dịch bỏ qua hoặc bao gồm một đoạn mã dựa trên điều kiện nhất định.
    
- **Ví dụ**: Bạn có thể dùng chỉ thị để kiểm tra xem chương trình đang chạy trên hệ điều hành Windows hay macOS. Nếu là Windows, hệ thống sẽ chèn các thư viện (libraries) dành riêng cho Windows. Ngược lại, nếu là macOS, nó sẽ gọi thư viện của macOS, hoặc sử dụng chỉ thị lỗi (error directive) để hủy quá trình biên dịch và báo lỗi.