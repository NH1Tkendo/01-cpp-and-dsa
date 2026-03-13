
### Tổng quan

Các kiểu dữ liệu nguyên thủy (còn gọi là kiểu cơ bản - fundamental data types) được triển khai trực tiếp bởi ngôn ngữ C++.

- Kích thước (size) và độ chính xác (precision) của chúng **phụ thuộc nhiều vào nền tảng (platform) và trình biên dịch (compiler)** bạn đang sử dụng.
    
- Kích thước được tính bằng **bit**. Số bit càng lớn, giá trị đại diện càng nhiều và bộ nhớ chiếm dụng càng cao. Công thức tính số giá trị phân biệt: $Số\ giá\ trị = 2^{Số\ bit}$.
    
- Thư viện `<climits>` trong C++ chứa thông tin về kích thước và giới hạn của các kiểu dữ liệu trên trình biên dịch của bạn.
    

---

### 1. Kiểu Ký tự (Character Types)

- Dùng để lưu trữ các ký tự đơn lẻ (ví dụ: 'a', 'X', '5').
    
- **Kiểu cơ bản:** `char`
    
- **Kích thước điển hình:** 8 bit (đại diện tối đa $2^{8} = 256$ ký tự), đủ dùng cho bảng mã ASCII/Latinh.
    
- C++ cũng hỗ trợ các kiểu ký tự rộng hơn (như Unicode) cho các ngôn ngữ phức tạp.
    
- **Cú pháp:** Đặt ký tự trong dấu nháy đơn `' '`. (Dùng nháy kép `" "` sẽ bị hiểu là chuỗi - string).
    

C++

```
char middle_initial = 'J'; 
```

---

### 2. Kiểu Số nguyên (Integer Types)

Dùng để biểu diễn các số nguyên (không có phần thập phân).

#### Phân loại theo dấu:

- **Signed (Có dấu):** Lưu được cả số âm, số 0 và số dương. Đây là mặc định trong C++.
    
- **Unsigned (Không dấu):** Chỉ lưu số 0 và số dương. Bắt buộc phải dùng từ khóa `unsigned` khi khai báo.
    

#### Phân loại theo kích thước (nhỏ đến lớn):

- `short` (hoặc `short int`)
    
- `int` (thông dụng nhất)
    
- `long` (hoặc `long int`)
    
- `long long` (hoặc `long long int`) - Dùng cho các số rất lớn.
    

_Mẹo đọc số lớn:_ Từ C++14, bạn có thể dùng dấu nháy đơn `'` để phân tách hàng nghìn cho dễ nhìn (trình biên dịch sẽ tự động bỏ qua chúng).

C++

```
unsigned short exam_score = 55;
int countries = 65;
long long people_on_earth = 7'600'000'000; // Cú pháp C++14
```

---

### 3. Kiểu Số thực dấu phẩy động (Floating-point Types)

Dùng để biểu diễn số thực (có phần thập phân) như $1.2$, $0.5$ hay $\pi$.

- Máy tính lưu trữ số thực dưới dạng xấp xỉ (mang phần định trị - mantissa và phần số mũ - exponent) vì bộ nhớ là hữu hạn.
    

#### Các loại cơ bản (độ chính xác tăng dần):

- `float`: Độ chính xác đơn.
    
- `double`: Độ chính xác kép (thông dụng nhất).
    
- `long double`: Dùng cho các số cực nhỏ hoặc cực lớn.
    

C++

```
double car_payment = 401.23;
long double large_amount = 2.7e120; // 2.7 * 10^120
```

---

### 4. Kiểu Logic (Boolean Type)

Dùng để biểu diễn các trạng thái đúng/sai.

- **Kiểu cơ bản:** `bool`
    
- **Giá trị:** - `true` (trong C++ in ra là `1`)
    
    - `false` (hoặc số `0`, trong C++ in ra là `0`)
        
    - Mọi giá trị khác `0` đều được C++ hiểu là `true`.
        

C++

```
bool game_over = false; 
```

---

### 5. Lỗi Tràn số (Overflow) & Lợi ích của Khởi tạo danh sách (List Initialization)

**Tràn số (Overflow):** Xảy ra khi bạn cố gắng lưu trữ một giá trị vượt quá giới hạn dung lượng của biến đó. C++ có thể sẽ sinh ra một giá trị rác (ví dụ số âm vô lý) mà không hề báo lỗi nếu bạn khởi tạo sai cách.

**Lỗi khó thấy với toán học:**

Ngay cả khi khai báo biến đủ lớn, kết quả của phép toán giữa chúng có thể gây tràn số nếu biến lưu kết quả (product/sum) có kiểu dữ liệu quá nhỏ.

C++

```
short value_1 = 30000;
short value_2 = 1000;
short product = value_1 * value_2; // GÂY TRÀN SỐ vì kết quả vượt quá giới hạn của short
```

**Cách phòng tránh:** Sử dụng cú pháp khởi tạo C++11 `{}`.

Khởi tạo bằng `{}` (List Initialization) là an toàn nhất vì nó kiểm tra lỗi "thu hẹp kiểu" (narrowing conversion) ngay lúc biên dịch (compile time) và sẽ **báo lỗi thay vì im lặng gây tràn số**.

C++

```
// ❌ Nguy hiểm (Gây tràn số nhưng không báo lỗi)
long people = 7600000000; 

// ✅ An toàn (Sẽ báo lỗi compiler: "narrowing conversion" để bạn sửa thành long long)
long people {7600000000}; 
```