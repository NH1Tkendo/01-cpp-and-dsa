### 1. Từ khóa (Keywords) và Từ dự phòng (Reserved Words)

- **Định nghĩa**: Từ khóa là một phần trong "từ vựng" của ngôn ngữ lập trình. Trong C++, hầu hết các từ khóa đều là **từ dự phòng (reserved words)**.
    
- **Đặc điểm**:
    
    - Lập trình viên **không được phép** định nghĩa lại ý nghĩa của chúng.
        
    - Không được sử dụng chúng cho các mục đích khác ngoài mục đích đã được ngôn ngữ quy định (ví dụ: không dùng làm tên biến).
        
- **Số lượng**: C++ có khoảng **90 từ khóa**, nhiều hơn đáng kể so với Java (~50), C (32) hay Python (33).
    
- **Lưu ý**: Số lượng từ khóa càng nhiều thì ngữ pháp của ngôn ngữ càng phức tạp. Tuy nhiên, bạn không cần học thuộc lòng tất cả; chúng ta sẽ làm quen dần trong quá trình thực hành.
    
- **Ví dụ**: `int`, `return` là các từ khóa đã xuất hiện trong chương trình đầu tiên.
    

### 2. Định danh (Identifiers)

- **Định nghĩa**: **Định danh (Identifiers)** là những tên gọi do lập trình viên tự đặt để đại diện cho một thành phần có ý nghĩa trong chương trình (biến, hàm, lớp...).
    
- **Phân biệt với Từ khóa**:
    
    - Các từ như `main`, `favorite_number`, `cout`, `cin`, `endl` **không phải** là từ khóa, chúng là các định danh.
        
    - Có những quy tắc cụ thể để đặt tên định danh (sẽ được học chi tiết ở các phần sau).
        

### 3. Toán tử (Operators)

C++ sở hữu hệ thống toán tử phong phú, bao gồm các toán tử toán học cơ bản và các toán tử chuyên dụng cho luồng dữ liệu:

- **Toán tử toán học**: Cộng (+), trừ (-), nhân (*), chia (/)...
    
- **Toán tử chèn luồng (Stream Insertion Operator) `<<`**: Dùng để đưa dữ liệu từ phía bên phải vào luồng đầu ra (ví dụ: hiển thị ra màn hình qua `cout`).
    
- **Toán tử trích xuất luồng (Stream Extraction Operator) `>>`**: Dùng để lấy dữ liệu từ luồng đầu vào (ví dụ: nhập từ bàn phím qua `cin`) và lưu vào một biến.
    
- **Toán tử phân giải phạm vi (Scope Resolution Operator) `::`**: Ví dụ trong `std::cout`, dấu `::` giúp xác định `cout` thuộc phạm vi (namespace) `std`.
    

### 4. Dấu câu (Punctuation) và Cú pháp (Syntax)

- **Dấu câu (Punctuation)**: Là các ký tự dùng để cấu trúc hóa mã nguồn, bao gồm:
    
    - Dấu chấm phẩy `;`: Kết thúc một câu lệnh.
        
    - Dấu ngoặc nhọn `{ }`: Bao quanh một khối mã.
        
    - Dấu ngoặc đơn `( )`: Dùng trong hàm hoặc biểu thức.
        
    - Dấu ngoặc kép `" "`: Bao quanh chuỗi ký tự.
        
- **Cú pháp (Syntax)**: Là sự kết hợp của từ khóa, định danh, toán tử và dấu câu theo một quy tắc nhất định.
    
    - **Vai trò**: Tạo nên cấu trúc và ý nghĩa mà trình biên dịch (compiler) có thể hiểu được.
        
    - **Lưu ý**: Trình biên dịch sẽ chuyển đổi mã nguồn sang mã máy dựa trên đúng những gì bạn viết, nó không tự "đoán" ý định của lập trình viên. Do đó, viết đúng cú pháp là bắt buộc.
        

### Ghi chú thêm

- **Tiền xử lý (Preprocessor)**: Các dòng bắt đầu bằng dấu `#` như `#include` là các chỉ thị tiền xử lý, không phải là từ khóa của ngôn ngữ C++ nhưng đóng vai trò quan trọng trong việc chuẩn bị mã nguồn trước khi biên dịch.