### 1. Khái niệm cơ bản

- **Định nghĩa**: Chú thích (comments) là các lời giải thích, ghi chú hoặc văn bản chú giải có thể đọc được bởi con người (human-readable) được chèn vào mã nguồn (source code) để làm rõ ý nghĩa của chương trình.
    
- **Cơ chế hoạt động**: Trình biên dịch (compiler) **không bao giờ** nhìn thấy chú thích. Bộ tiền xử lý (preprocessor) sẽ tự động loại bỏ tất cả các chú thích và thay thế chúng bằng một khoảng trắng duy nhất trước khi tiến hành biên dịch.
    
- **Mục đích**: Chú thích không dành cho máy tính, mà dành cho **con người** (chính bạn trong tương lai hoặc các lập trình viên khác tiếp quản dự án) để hiểu rõ bối cảnh, lý do và cách thức hoạt động của đoạn mã.
    

### 2. Phân loại chú thích

C++ hỗ trợ 2 cú pháp để viết chú thích:

#### Chú thích một dòng (Single-line comment)

- Sử dụng hai dấu gạch chéo tiến `//`.
    
- Toàn bộ nội dung từ `//` cho đến cuối dòng sẽ bị bỏ qua.
    

C++

```
int favorite_number; // Đây là biến lưu trữ con số yêu thích của tôi
```

#### Chú thích nhiều dòng (Multi-line comment)

- Nội dung được đặt giữa `/*` và `*/`.
    
- Có thể trải dài qua nhiều dòng mà không bị ngắt. Thường được sử dụng ở đầu tệp (file header) để ghi thông tin tác giả, ngày tháng, bản quyền, hoặc giấy phép (license).
    

C++

```
/* ****************************************
* Tác giả: Frank
* Ngày tạo: 11/11/2017
* Mô tả: Khởi tạo dữ liệu người dùng
****************************************
*/
```

### 3. Nguyên tắc viết chú thích hiệu quả (Best Practices)

#### Những điều NÊN làm:

- **Hướng tới mã tự tài liệu hóa (Self-documenting code)**: Hãy viết mã nguồn rõ ràng, biến và hàm được đặt tên có ý nghĩa để tự nó nói lên chức năng, giảm thiểu sự phụ thuộc vào chú thích.
    
- **Giải thích những đoạn mã phức tạp**: Sử dụng chú thích để làm rõ các thuật toán khó hoặc các thủ thuật tối ưu hóa.
    
    - _Ví dụ tốt_: `// Sử dụng phiên bản sửa đổi của thuật toán Dijkstra để tối ưu hóa không gian lưu trữ (space efficiency)`
        
- **Giữ tính nhất quán (Consistency)**: Tuân thủ một phong cách viết chú thích đồng nhất xuyên suốt tệp mã nguồn hoặc dự án.
    
- **Cập nhật chú thích liên tục**: Khi sửa đổi mã nguồn, **bắt buộc** phải chỉnh sửa chú thích đi kèm nếu cần. Một chú thích sai lệch với mã nguồn thực tế còn gây hại nhiều hơn là không có chú thích.
    

#### Những điều KHÔNG NÊN làm (Anti-patterns):

- **Không chú thích những điều hiển nhiên**: Đừng viết những dòng vô nghĩa chỉ để dịch lại mã nguồn sang ngôn ngữ tự nhiên.
    
    - _Ví dụ xấu_: `return 0; // trả về 0` hoặc `a + b; // cộng a và b`.
        
- **Không dùng chú thích để kiểm soát phiên bản (Version Control)**:
    
    - Đừng ghi chú lịch sử chỉnh sửa vào mã nguồn (ví dụ: `// Joe đã thêm tính năng X vào ngày 13/11`).
        
    - Thói quen này làm rác mã nguồn. Thay vào đó, hãy sử dụng các hệ thống quản lý phiên bản (Version Control Systems) chuyên dụng và tiêu chuẩn như **Git** hoặc **Subversion (SVN)**.
        
- **Không dùng chú thích để bao biện cho mã tệ**: Một đoạn mã viết cẩu thả không thể được "cứu vớt" bằng một đoạn chú thích hay. Hãy ưu tiên việc tái cấu trúc (refactoring) mã nguồn cho tốt thay vì cố gắng giải thích nó.