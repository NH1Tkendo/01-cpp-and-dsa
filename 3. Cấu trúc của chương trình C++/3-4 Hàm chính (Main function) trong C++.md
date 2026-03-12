### 1. Vai trò và Đặc điểm cốt lõi

- **Quy tắc bắt buộc**: Mỗi chương trình C++ phải có **duy nhất một** hàm `main`. Một dự án có thể bao gồm hàng trăm tệp (files), nhưng hàm `main` chỉ được phép tồn tại ở một vị trí duy nhất.
    
- **Định dạng**: Tên hàm bắt buộc phải viết chữ thường hoàn toàn (`main`, không phải `Main` hay `MAIN`).
    
- **Quá trình thực thi**:
    
    - Khi chạy chương trình, hàm `main` sẽ được gọi tự động bởi Hệ điều hành (Operating System).
        
    - Mã nguồn (code) nằm giữa hai dấu ngoặc nhọn `{ }` của hàm `main` sẽ bắt đầu được thực thi.
        
- **Giá trị trả về (Return value)**: Hàm `main` luôn phải trả về một số nguyên (integer) cho Hệ điều hành khi kết thúc bằng câu lệnh `return`.
    
    - Nếu trả về `0`: Tín hiệu cho biết chương trình đã kết thúc thành công.
        
    - Nếu trả về một số khác `0`: Tín hiệu cho biết đã xảy ra lỗi, Hệ điều hành có thể dựa vào mã số này để xác định nguyên nhân.
        

### 2. Hai phiên bản của hàm `main`

Cả hai phiên bản dưới đây đều hoàn toàn hợp lệ theo tiêu chuẩn của C++ (C++ specification).

#### Phiên bản 1: Không có đối số

Đây là phiên bản cơ bản nhất và sẽ được sử dụng chủ yếu trong phần đầu của khóa học.

- **Cú pháp**: Không có gì nằm trong dấu ngoặc đơn `()`.
    
- **Đặc điểm**: Hàm `main` không mong đợi hay yêu cầu bất kỳ thông tin đầu vào nào từ Hệ điều hành để có thể chạy.
    

C++

```
int main() {
    // Mã lệnh của bạn
    return 0;
}
```

#### Phiên bản 2: Có đối số dòng lệnh (Command-line arguments)

Phiên bản này rất phổ biến khi xây dựng các ứng dụng dòng lệnh (command line applications), nơi người dùng cần truyền dữ liệu vào ngay lúc khởi chạy chương trình.

- **Đặc điểm**: Hàm `main` yêu cầu nhận thông tin từ Hệ điều hành. Trình biên dịch cần hai mẩu thông tin:
    
    1. **`argc` (Argument Count)**: Số lượng đối số (thông tin) được truyền vào.
        
    2. **`argv` (Argument Vector)**: Tập hợp các đối số thực tế được truyền vào (thường dưới dạng một danh sách chuỗi văn bản - strings). _Ví dụ: tên chương trình `program.exe`, `argument1`, `argument2`._
        
- **Ghi chú**: Mặc dù bạn có thể đặt bất kỳ tên biến nào, nhưng `argc` và `argv` là những quy ước mang tính lịch sử và tiêu chuẩn.
    

C++

```
int main(int argc, char *argv[]) {
    // Mã lệnh xử lý đối số dòng lệnh
    return 0;
}
```

### 3. Hiểu thêm về Hàm (Function)

- **Định nghĩa**: Hàm (function) về cơ bản là một cái tên được sử dụng để tham chiếu đến một khối mã nguồn (block of code).
    
- `main` chính là một hàm đặc biệt. Trong giai đoạn đầu học C++, toàn bộ chương trình của chúng ta sẽ được viết bên trong hàm này.
    
- Khi chương trình trở nên phức tạp hơn, chúng ta sẽ tự viết các hàm riêng và các lớp (classes) để mô-đun hóa (modularize) và tổ chức mã nguồn một cách khoa học.