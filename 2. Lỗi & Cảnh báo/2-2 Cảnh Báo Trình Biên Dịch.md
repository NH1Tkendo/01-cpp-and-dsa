Khác với lỗi (errors), **cảnh báo trình biên dịch (compiler warnings)** xảy ra khi trình biên dịch (compiler) phát hiện ra một _vấn đề tiềm ẩn_ trong mã nguồn của bạn, nhưng nó vẫn có thể hiểu và dịch mã đó thành mã đối tượng (object code).

**Nguyên tắc cốt lõi:** - **Tuyệt đối không bỏ qua cảnh báo!** Đừng vì chương trình vẫn chạy được mà ngó lơ chúng.

- Nhiều lập trình viên chuyên nghiệp xử lý các cảnh báo này khắt khe như đối với lỗi (errors) và luôn khắc phục chúng ngay từ đầu.
    
- Nên áp dụng **Chính sách Không cảnh báo (No warnings policy)**: Mục tiêu luôn là biên dịch sạch (clean compile) mà không có bất kỳ cảnh báo nào.
    

### 1. Các trường hợp gây cảnh báo phổ biến

Dưới đây là những ví dụ thường gặp khi làm việc với biến (variables), được minh họa trên CodeLite:

#### A. Sử dụng biến chưa được khởi tạo (Uninitialized Variable)

Nếu bạn khai báo một biến nhưng không gán giá trị ban đầu (hoặc không yêu cầu người dùng nhập) mà đã mang ra sử dụng (như in ra màn hình), trình biên dịch sẽ cảnh báo.

- **Hậu quả:** Giá trị in ra sẽ là một con số "rác" ngẫu nhiên đang tồn tại trong bộ nhớ (Ví dụ: `4200971`), hoàn toàn không như bạn mong đợi.
    
- **Mã nguồn minh họa:**
    

C++

```
int favorite_number;
// Chưa gán giá trị cho biến
cout << favorite_number; 

// Cảnh báo: 'favorite_number' is used uninitialized in this function
```

#### B. Biến được khai báo/gán nhưng không sử dụng (Unused Variable)

Bạn tạo ra một biến, thậm chí gán giá trị cho nó, nhưng lại không sử dụng nó ở bất kỳ đâu trong phần còn lại của chương trình. Trình biên dịch sẽ nhắc nhở: _"Tại sao lại tạo một biến nếu không dùng đến nó?"_

- **Mã nguồn minh họa:**
    

C++

```
int favorite_number = 100;
cout << "Hello World";

// Cảnh báo: variable 'favorite_number' set but not used
// Hoặc nếu không gán giá trị: unused variable 'favorite_number'
```
