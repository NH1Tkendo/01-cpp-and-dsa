### 1. Nguyên lý cơ bản (Basic Principles)

- Máy tính thực chất không thông minh; nó chỉ thực thi chính xác những mệnh lệnh mà lập trình viên `(programmer)` giao phó.
    
- Một chương trình máy tính giống như một công thức nấu ăn `(recipe)`. Các bước phải được định nghĩa cực kỳ chi tiết và rõ ràng.
    
    - _Ví dụ:_ Nếu công thức yêu cầu "cho 4 quả trứng vào bát và khuấy", con người sẽ tự hiểu là phải đập vỏ và chỉ lấy phần bên trong. Nhưng nếu không được hướng dẫn cụ thể, máy tính có thể sẽ bỏ cả vỏ trứng vào bát. Đó là lý do mã code phải cực kỳ tường minh `(explicit)`.
        

### 2. Mã nguồn và Trình biên dịch (Source Code & Compiler)

- **Mã nguồn `(Source code)`:** Là những dòng lệnh do con người viết ra bằng ngôn ngữ lập trình (C++). Con người không giỏi đọc các chuỗi số 0 và 1, nên mã nguồn được thiết kế ở bậc cao hơn để dễ đọc hiểu. Trong khóa học này, chúng ta sẽ sử dụng các tệp có phần mở rộng là `.cpp` và `.h`.
    
- **Trình biên dịch `(Compiler)`:** Vì máy tính không hiểu mã nguồn, chúng ta cần một "người phiên dịch". Trình biên dịch C++ sẽ nhận đầu vào là mã nguồn và xuất ra **mã đối tượng/mã máy `(object code)`**.
    
    - _Lưu ý:_ Nếu mã nguồn có lỗi cú pháp `(syntax errors)`, quá trình biên dịch sẽ thất bại và không có tệp object nào được tạo ra.
        

### 3. Quá trình Xây dựng chương trình (The Build Process)

Quá trình biến mã code thành một chương trình có thể chạy được diễn ra qua các bước sau:

1. **Soạn thảo `(Editing)`:** Viết mã C++ bằng trình soạn thảo văn bản `(editor)`. (Bắt đầu với tệp `main.cpp`).
    
2. **Biên dịch `(Compiling)`:** Trình biên dịch chuyển đổi mã nguồn thành tệp mã đối tượng `(object code file)`.
    
    - Trên Windows: tệp có đuôi `.obj`.
        
    - Trên UNIX / Mac: tệp có đuôi `.o`.
        
3. **Liên kết `(Linking)`:** Trình liên kết `(Linker)` sẽ kết hợp các tệp object của bạn cùng với các thư viện có sẵn `(libraries)` để tạo thành một tệp thực thi duy nhất `(executable program)`.
    
    - Trên Windows: tệp có đuôi `.exe`.
        
    - Trên UNIX / Mac: thường không có đuôi mở rộng.
        
4. **Kiểm thử và Gỡ lỗi `(Testing & Debugging)`:** Chạy thử chương trình để phát hiện lỗi logic `(logic errors)` và dùng trình gỡ lỗi để khắc phục.
    

### 4. Môi trường Phát triển Tích hợp (IDE - Integrated Development Environment)

- **Khái niệm:** IDE là một phần mềm kết hợp tất cả các công cụ nêu trên (trình soạn thảo, trình biên dịch, trình liên kết, trình gỡ lỗi) vào chung một giao diện. IDE giúp tự động hóa quá trình build chỉ bằng một cú click chuột và hỗ trợ kết nối với các hệ thống quản lý phiên bản (như Git).
    
- **IDE được sử dụng trong khóa học:** **CodeLite**.
    
    - _Ưu điểm:_ Miễn phí, hoạt động đa nền tảng `(cross-platform)`, tốc độ nhanh và yêu cầu cấu hình phần cứng/bộ nhớ rất thấp.
        
- **Các IDE phổ biến khác:**
    
    - **Code::Blocks:** Đa nền tảng, nhưng phiên bản trên Mac khá nhiều lỗi `(buggy)`.
        
    - **NetBeans / Eclipse:** Hỗ trợ chéo nền tảng rất tốt, nhưng yêu cầu cài đặt Java JRE và ngốn khá nhiều RAM.
        
    - **CLion (JetBrains):** Một IDE vô cùng xuất sắc nhưng phải trả phí (có bản dùng thử 30 ngày).
        
    - **Dev-C++:** Nhanh, nhẹ nhưng chỉ hoạt động trên Windows.
        
    - **KDevelop:** Đa nền tảng nhưng không có bản cài sẵn cho Mac (phải tự build từ source).
        
    - **Visual Studio (Microsoft):** Môi trường phát triển tuyệt vời, nhưng phiên bản hỗ trợ C++ chỉ có trên Windows.
        
    - **Xcode (Apple):** IDE cực kỳ mạnh mẽ nhưng chỉ độc quyền cho hệ điều hành Mac.