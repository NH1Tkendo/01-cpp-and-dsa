## Phạm vi của Biến: Biến Cục bộ và Biến Toàn cục (Variable Scope: Local vs Global Variables)

### Khái niệm cơ bản về Phạm vi (Scope)

Trong C++, vị trí bạn khai báo một biến sẽ quyết định **phạm vi (scope)** hoặc **tầm nhìn (visibility)** của biến đó. Điều này xác định phần nào của chương trình có thể nhìn thấy và sử dụng biến.

### 1. Biến Cục bộ (Local Variables)

- **Vị trí khai báo:** Bên trong cặp dấu ngoặc nhọn `{ }` của một hàm (ví dụ: hàm `main()`).
    
- **Phạm vi:** Chỉ có thể được truy cập và sử dụng bởi các câu lệnh nằm bên trong hàm đó (và phải sau dòng khai báo).
    
- **Thực hành tốt:** Đây là cách khai báo biến chuẩn mực và được khuyến nghị sử dụng trong hầu hết các trường hợp.
    

### 2. Biến Toàn cục (Global Variables)

- **Vị trí khai báo:** Nằm hoàn toàn bên ngoài mọi hàm.
    
- **Phạm vi:** Có thể được truy cập và thay đổi từ **bất kỳ phần nào** của chương trình.
    
- **Khởi tạo tự động:** Khác với biến cục bộ (chứa giá trị rác nếu không khởi tạo), biến toàn cục được tự động khởi tạo giá trị bằng `0`.
    

### 3. Vấn đề của Biến Toàn cục (Drawbacks of Global Variables)

Mặc dù bạn sẽ thường thấy biến toàn cục trong các bài hướng dẫn cho người mới bắt đầu (vì nó dễ viết), nhưng việc lạm dụng chúng **không phải là thực hành tốt (not a good practice)**.

- Vì bất kỳ hàm nào cũng có thể thay đổi biến toàn cục, việc theo dõi luồng dữ liệu trở nên cực kỳ phức tạp.
    
- Khi chương trình phình to lên hàng ngàn dòng mã, việc tìm kiếm lỗi (finding errors) và gỡ lỗi (debugging) liên quan đến biến toàn cục sẽ trở thành một "cơn ác mộng".
    

### 4. Hiện tượng Che khuất (Shadowing)

Bạn hoàn toàn có thể khai báo một biến cục bộ trùng tên với một biến toàn cục đã có.

- Khi trình biên dịch (compiler) đọc một biến, nó sẽ luôn **ưu tiên tìm kiếm ở phạm vi cục bộ (local scope) trước**.
    
- Nếu không tìm thấy, nó mới tìm ra phạm vi toàn cục (global scope).
    
- Nếu tìm thấy ở phạm vi cục bộ, biến cục bộ đó sẽ được sử dụng và **che khuất (shadow)** biến toàn cục bên ngoài.
    

### Ví dụ minh họa (Mã nguồn C++)

C++

```
#include <iostream>

using namespace std;

// 🌍 BIẾN TOÀN CỤC (Global Variable)
// Khai báo bên ngoài hàm main, mọi hàm đều có thể truy cập
int age = 18; 

int main() {
    // 🏠 BIẾN CỤC BỘ (Local Variable)
    // Khai báo bên trong hàm main, trùng tên với biến toàn cục
    int age = 16; 
    
    // Khi in ra, trình biên dịch tìm biến cục bộ trước.
    // Kết quả in ra sẽ là 16 (biến cục bộ đã che khuất biến toàn cục).
    cout << age << endl; 
    
    return 0;
}
```