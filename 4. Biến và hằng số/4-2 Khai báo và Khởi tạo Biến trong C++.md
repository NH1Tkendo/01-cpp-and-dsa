### 1. Cú pháp khai báo cơ bản (Basic Syntax)

Để khai báo một biến trong C++, bạn cần cung cấp hai thông tin chính cho trình biên dịch (compiler) và kết thúc bằng dấu chấm phẩy `;`:

- **Kiểu dữ liệu (Type):** Xác định loại dữ liệu biến sẽ lưu trữ.
    
- **Tên biến (Name):** Định danh để gọi biến đó.
    

**Một số kiểu dữ liệu cơ bản:**

- `int`: Số nguyên (whole number).
    
- `double`: Số thực dấu phẩy động (floating point number).
    
- `string`: Chuỗi ký tự (sequence of characters).
    

_Ghi chú:_ Nhờ tính năng lập trình hướng đối tượng (Object-oriented programming), C++ cho phép bạn tạo ra các kiểu dữ liệu tùy chỉnh (custom types) như `Account` hay `Person`, giúp mã nguồn dễ đọc hơn rất nhiều.

### 2. Quy tắc đặt tên biến (Variable Naming Rules)

C++ có các quy tắc nghiêm ngặt bắt buộc phải tuân thủ khi đặt tên:

- **Ký tự cho phép:** Chỉ chứa chữ cái (letters), chữ số (numbers) và dấu gạch dưới (underscores `_`).
    
- **Ký tự bắt đầu:** Không được bắt đầu bằng chữ số (phải bắt đầu bằng chữ cái hoặc dấu gạch dưới).
    
- **Từ khóa dự trữ (Reserved keywords):** Không được sử dụng các từ khóa của C++ làm tên biến (ví dụ: không thể đặt tên biến là `int` hoặc `double`).
    
- **Phạm vi (Scope):** Không được khai báo lại một biến đã tồn tại trong cùng một phạm vi.
    
- **Phân biệt chữ hoa chữ thường (Case-sensitive):** Biến `Age` và `age` được hiểu là hai biến hoàn toàn khác nhau.
    
- **Ký tự đặc biệt và khoảng trắng:** Không được chứa khoảng trắng hoặc các ký tự đặc biệt (`$`, `+`, v.v.).
    

_Lưu ý về `cout`:_ `cout` là một tên hợp lệ theo quy tắc, nhưng nó đã được định nghĩa trong thư viện chuẩn (standard library). Không nên khai báo lại để tránh xung đột.

### 3. Phong cách đặt tên và Thực hành tốt (Naming Style & Best Practices)

Không chỉ cần đúng quy tắc, việc viết mã sạch (clean code) cũng rất quan trọng:

- **Tính nhất quán (Consistency):** Hãy chọn một phong cách đặt tên và tuân thủ nó xuyên suốt dự án (ví dụ: áp dụng theo hướng dẫn phong cách của Google).
    
- **Hai phong cách phổ biến:**
    
    - `CamelCase`: Viết hoa chữ cái đầu của mỗi từ, không dùng dấu gạch dưới (ví dụ: `RoomWidth`).
        
    - `Underscores`: Ngăn cách các từ bằng dấu gạch dưới (ví dụ: `room_width`).
        
- **Tên có ý nghĩa:** Sử dụng tên mô tả rõ chức năng, tránh viết tắt khó hiểu (ví dụ: dùng `mass_of_earth` thay vì `moe`).
    
- **Khai báo gần nơi sử dụng:** Đừng gom tất cả các biến lên đầu tệp (file). Hãy khai báo chúng ngay trước thời điểm bạn cần sử dụng.
    

### 4. Khởi tạo biến (Initializing Variables)

**Tuyệt đối không sử dụng biến chưa được khởi tạo (Uninitialized variables).** Nếu bạn khai báo `int age;` mà không gán giá trị, biến đó sẽ chứa các dữ liệu rác (chuỗi số 0 và 1 ngẫu nhiên) còn sót lại tại vị trí bộ nhớ đó. Điều này gây ra kết quả sai lệch và lỗi chương trình. Trình biên dịch thường sẽ phát ra cảnh báo (compiler warning) khi bạn mắc lỗi này.

**3 cách khởi tạo biến trong C++:**

1. **Sử dụng toán tử gán (Assignment operator):** Dùng dấu bằng `=`.
    
    - Cú pháp: `int age = 21;`
        
2. **Khởi tạo kiểu hàm tạo (Constructor-style):** Dùng dấu ngoặc đơn `()`.
    
    - Cú pháp: `int age (21);`
        
3. **Cú pháp khởi tạo C++11 (C++11 initialization syntax):** Khuyến nghị sử dụng vì tính nhất quán và an toàn.
    
    - Cú pháp: `int age {21};`
        

### 5. Ví dụ thực hành (Live Code Example)

Chương trình tính diện tích phòng (Square footage) áp dụng đầy đủ các quy tắc thực hành tốt:

C++

```
#include <iostream>

using namespace std;

int main() {
    // Yêu cầu nhập chiều rộng và khai báo biến ngay sát lúc dùng
    cout << "Enter the width of the room: ";
    int room_width = 0; // Khởi tạo giá trị mặc định là 0
    cin >> room_width;

    // Yêu cầu nhập chiều dài và khai báo biến ngay sát lúc dùng
    cout << "Enter the length of the room: ";
    int room_length = 0; // Khởi tạo giá trị mặc định là 0
    cin >> room_length;

    // Tính toán và in kết quả
    cout << "The area of the room is " << room_width * room_length << " square feet." << endl;

    return 0;
}
```