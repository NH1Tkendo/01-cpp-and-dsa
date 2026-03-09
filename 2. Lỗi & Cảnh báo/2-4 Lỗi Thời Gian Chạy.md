### 1. Đặc điểm cốt lõi

- **Tính khó lường:** Rất khó để lập trình viên dự đoán trước toàn bộ các tình huống gây ra lỗi này trong lúc viết mã nguồn (writing code).
    
- **Hậu quả:** Một số lỗi thời gian chạy nghiêm trọng có thể khiến chương trình của bạn bị sập (crash) ngay lập tức và thoát ra ngoài.
    

### 2. Các loại lỗi phổ biến

Dưới đây là những lỗi thời gian chạy điển hình nhất:

- Lỗi chia cho không `(divided by zero errors)`
    
- Lỗi không tìm thấy tệp dữ liệu `(file not found errors)`
    
- Lỗi cạn kiệt bộ nhớ `(out of memory errors)`
    

### 3. Giải pháp khắc phục

- **Xử lý ngoại lệ (Exception handling):** Đây là kỹ thuật/cơ chế lập trình thiết yếu. Nó giúp chúng ta "bắt" và nhận biết khi nào lỗi thời gian chạy xảy ra. Thay vì để chương trình sập đột ngột, việc xử lý ngoại lệ cho phép ứng dụng xử lý tình huống lỗi một cách an toàn và cố gắng phục hồi (recover) luồng chạy.