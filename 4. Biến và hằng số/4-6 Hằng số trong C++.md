### Khái niệm chung

- **Hằng số (Constants)** rất giống với biến (variables): chúng có tên, tuân thủ các quy tắc đặt tên, chiếm dụng bộ nhớ và thường có kiểu dữ liệu (typed).
    
- **Điểm khác biệt cốt lõi:** Giá trị của hằng số **không thể thay đổi** (read-only) sau khi đã được khai báo. Bất kỳ nỗ lực nào nhằm thay đổi giá trị này đều sẽ dẫn đến lỗi trình biên dịch (compiler error).
    
- **Tại sao nên sử dụng hằng số?**
    
    - Tránh việc mã hóa cứng (hard coding) các "con số ma thuật" (magic numbers) như `12`, `3.14`, v.v.
        
    - Thay vì dùng số `12` rải rác khắp mã nguồn mà không rõ ý nghĩa, việc tạo một hằng số `months_in_year = 12` giúp mã nguồn dễ đọc, dễ hiểu cho các lập trình viên khác.
        
    - Tránh được các lỗi vô ý thay đổi giá trị so với việc dùng biến thông thường.
        

Có một số cách để tạo hằng số trong C++, bao gồm: Hằng số dạng chữ (Literal constants), Hằng số được khai báo (Declared constants), Hằng số định nghĩa (Defined constants), Biểu thức hằng (Constant expressions) và Hằng số liệt kê (Enumerated constants). Bài này sẽ tập trung vào 3 loại đầu tiên.

---

### 1. Hằng số dạng chữ (Literal Constants)

Đây là loại hằng số rõ ràng và phổ biến nhất, được sử dụng trực tiếp để biểu đạt một giá trị cụ thể trong mã nguồn.

- **Ví dụ:** `12`, `1.56`, `"Frank"`, ký tự `'J'`.
    
- **Hậu tố chỉ định kiểu (Suffixes):** Bạn có thể thêm hậu tố vào sau hằng số để báo cho trình biên dịch biết chính xác kiểu dữ liệu của nó (có thể viết hoa hoặc viết thường).
    
    - Đối với số nguyên: `U` (unsigned - không dấu), `L` (long). Ví dụ: `12U`, `12L`, `12UL`.
        
    - Đối với số thực: `F` (float), `L` (long double). Ví dụ: `1.56F`.
        
- **Mã thoát (Escape Codes):** Là các hằng số ký tự đặc biệt, bắt đầu bằng dấu gạch chéo ngược `\`, thường được nhúng bên trong các chuỗi ký tự (string literals) để định dạng đầu ra.
    
    - `\n`: Xuống dòng mới (newline).
        
    - `\t`: Dấu tab.
        

C++

```
// Ví dụ về sử dụng mã thoát trong cout
cout << "Hello\tthere\nmy friend\n"; 
// Kết quả in ra: 
// Hello   there
// my friend
```

---

### 2. Hằng số được khai báo (Declared Constants)

Đây là cách phổ biến nhất và được khuyến nghị sử dụng nhất trong C++ hiện đại để khai báo hằng số.

- Sử dụng từ khóa `const` ở ngay đầu phần khai báo. Cú pháp hoàn toàn giống với khai báo biến.
    
- **Bắt buộc phải khởi tạo (Initialize):** Bạn phải gán giá trị ngay khi khai báo. Nếu không, trình biên dịch sẽ báo lỗi "uninitialized const".
    

C++

```
// ✅ ĐÚNG: Khai báo và khởi tạo ngay lập tức
const int months_in_year {12}; // Khuyên dùng cú pháp khởi tạo danh sách C++11
const double pi = 3.14159;

// ❌ SAI: Sẽ gây lỗi trình biên dịch (compiler error)
const int days_in_week; // Lỗi vì chưa khởi tạo
months_in_year = 13;    // Lỗi vì cố gắng thay đổi giá trị của hằng số
```

---

### 3. Hằng số định nghĩa qua tiền xử lý (Defined Constants)

Đây là cách khai báo hằng số thường thấy trong các mã nguồn C/C++ cũ (legacy code).

- Sử dụng chỉ thị tiền xử lý (preprocessor directive) `#define`.
    
- **Cơ chế hoạt động:** Nó hoạt động như một công cụ "Tìm kiếm và Thay thế mù quáng" (blind find-and-replace) của bộ tiền xử lý trước khi mã thực sự được biên dịch. Nơi nào có chữ `pi`, nó sẽ thay bằng `3.1415926`.
    
- **Nhược điểm chí mạng:** Bộ tiền xử lý không hiểu C++, do đó nó **không kiểm tra kiểu dữ liệu (no type check)**. Điều này có thể dẫn đến những lỗi logic cực kỳ khó tìm.
    
- **Lưu ý:** Tuyệt đối **không nên sử dụng** cách này trong mã C++ hiện đại.
    

C++

```
// Ví dụ về Defined Constants (KHÔNG KHUYẾN NGHỊ DÙNG)
#define pi 3.1415926
```