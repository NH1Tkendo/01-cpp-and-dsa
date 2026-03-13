### Kiến thức nền tảng

Để hiểu về biến, cần nắm rõ cấu trúc cơ bản của một hệ thống máy tính bao gồm:

- **Bộ nhớ (Memory):** Điển hình là **Bộ nhớ truy cập ngẫu nhiên (Random Access Memory - RAM)**. Đây là một khối lưu trữ liền kề được máy tính sử dụng để chứa cả dữ liệu và các lệnh (instructions).
    
- **Bộ vi xử lý trung tâm (CPU)** và **Bus dữ liệu (Bus):** Chịu trách nhiệm di chuyển dữ liệu giữa CPU và bộ nhớ.
    
- RAM bao gồm nhiều **ô nhớ (memory cells)**, mỗi ô có một vị trí/địa chỉ cụ thể.
    

### Vấn đề và Giải pháp trong Lập trình

- **Vấn đề:** Nếu phải lập trình trực tiếp bằng các địa chỉ bộ nhớ cụ thể (ví dụ: `move 21 to memory location 1002` - chuyển giá trị 21 vào vị trí bộ nhớ 1002), việc viết mã sẽ rất khó khăn, khó đọc và dễ sinh ra lỗi lập trình (programmer errors).
    
- **Giải pháp:** Hầu hết các ngôn ngữ lập trình cho phép liên kết một tên gọi với một vị trí bộ nhớ.
    

### Khái niệm cốt lõi

- **Biến (Variable):** Là một sự **trừu tượng hóa (abstraction)** cho một vị trí bộ nhớ. Nó cho phép chúng ta sử dụng một tên gọi có ý nghĩa để đại diện cho một giá trị.
    
- **Sự gắn kết (Binding):** Là quá trình liên kết địa chỉ bộ nhớ với tên biến. Ví dụ: vị trí bộ nhớ `1002` được gắn với tên biến `age`. Chúng ta chỉ cần gán giá trị `21` cho `age` mà không cần nhớ địa chỉ `1002`.
    
- **Lợi ích:** - Mỗi lần chạy chương trình, biến có thể được gắn với một địa chỉ bộ nhớ khác nhau, nhưng đoạn mã (code) vẫn hoạt động chính xác.
    
    - Sử dụng tên biến có ý nghĩa giúp việc đọc và viết chương trình dễ dàng hơn nhiều.
        
- **Tính thay đổi:** Đúng như tên gọi, nội dung lưu trữ bên trong biến có thể thay đổi trong quá trình chương trình thực thi (ví dụ: thay đổi giá trị của `age` từ $21$ sang $22$).
    

### Khai báo và Kiểu dữ liệu (Declaration & Typing)

Biến có hai thuộc tính quan trọng, trong đó thuộc tính đầu tiên là **Kiểu (Type)**:

- **Trình biên dịch (Compiler):** Cần phải biết loại dữ liệu (giá trị) nào là hợp lệ để có thể lưu trữ vào một biến cụ thể.
    
- **Kiểu tĩnh (Static typing):** Trình biên dịch sẽ thực thi các quy tắc về kiểu dữ liệu ngay tại thời điểm biên dịch chương trình (compile time) thay vì lúc chương trình đang chạy (execution time).
    
- **Khai báo (Declare):** Trong các ngôn ngữ như C++, bạn **bắt buộc** phải khai báo biến trước khi sử dụng. Nếu bạn gán giá trị cho một biến chưa được khai báo, bạn sẽ nhận được **lỗi trình biên dịch (compiler error)**.
    

### Ví dụ minh họa (Mã giả/C++)

C++

```
// ❌ SAI: Biến chưa được khai báo
age = 21; // Sẽ gây ra lỗi trình biên dịch (compiler error) vì 'age' chưa được định nghĩa kiểu.

// ✅ ĐÚNG: Khai báo biến trước khi sử dụng
int age;  // Khai báo biến 'age' có kiểu dữ liệu là số nguyên (integer)
age = 21; // Hợp lệ: Trình biên dịch đã biết 'age' chỉ chứa số nguyên
	```