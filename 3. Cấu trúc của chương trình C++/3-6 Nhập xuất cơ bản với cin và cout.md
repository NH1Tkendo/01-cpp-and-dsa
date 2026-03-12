### 1. Khái niệm cơ bản về Luồng (Streams)

Trong C++, việc nhập/xuất dữ liệu trên các thiết bị (như bàn phím, màn hình) được xử lý thông qua khái niệm **trừu tượng hóa luồng (stream abstraction)**. Để sử dụng các luồng này, bạn **bắt buộc** phải khai báo thư viện `#include <iostream>`.

Các luồng tiêu chuẩn bao gồm:

- **`cout`**: Luồng đầu ra (Output stream), mặc định hiển thị ra màn hình (console).
    
- **`cin`**: Luồng đầu vào (Input stream), mặc định nhận dữ liệu từ bàn phím.
    
- **`cerr`** và **`clog`**: Luồng đầu ra dành cho lỗi (standard error) và nhật ký (standard log).
    

### 2. Xuất dữ liệu với `cout`

- **Toán tử chèn (Insertion Operator) `<<`**: Dùng để chèn giá trị nằm ở bên phải nó vào luồng đầu ra `cout`.
    
- **Kéo dài chuỗi (Chaining)**: Bạn có thể nối nhiều toán tử `<<` trong cùng một câu lệnh để xuất nhiều dữ liệu liên tiếp.
    
    C++
    
    ```
    cout << "Hello" << " " << "World"; 
    ```
    
- **Xuống dòng**: `cout` **không** tự động xuống dòng. Bạn phải thực hiện việc này một cách tường minh qua 2 cách:
    
    - Dùng **`endl`** (Endline manipulator): Xuống dòng và đồng thời xóa bộ đệm (flush the stream) để đảm bảo dữ liệu hiển thị ngay lập tức.
        
    - Dùng **`\n`** (Ký tự dòng mới - Newline character): Chèn thẳng vào trong chuỗi ký tự (ví dụ: `"Hello\nWorld"`), giúp xuống dòng nhưng không xóa bộ đệm.
        

### 3. Nhập dữ liệu với `cin`

- **Toán tử trích xuất (Extraction Operator) `>>`**: Trích xuất dữ liệu từ luồng `cin` và lưu vào biến nằm ở bên phải nó.
    
- **Định dạng dữ liệu**: Trình biên dịch sẽ tự động nội suy cách đọc dữ liệu dựa trên kiểu của biến (ví dụ: số nguyên `int`, số thực `double`, hoặc chuỗi `string`).
    
- **Vai trò của khoảng trắng (Whitespace)**: `cin` sử dụng khoảng trắng (dấu cách, phím tab, phím enter) làm dấu hiệu kết thúc cho một giá trị. Mọi khoảng trắng thừa ở đầu sẽ bị bỏ qua.
    
- **Chaining với `cin`**: Bạn có thể yêu cầu người dùng nhập nhiều giá trị trên cùng một dòng, cách nhau bởi khoảng trắng.
    
    C++
    
    ```
    int num1, num2;
    cout << "Nhập hai số nguyên cách nhau bởi dấu cách: ";
    cin >> num1 >> num2; // Đọc lần lượt từng giá trị vào num1 và num2
    ```
    

### 4. Cơ chế hoạt động của Bộ đệm (Buffer) và Các lưu ý quan trọng

Dữ liệu bạn gõ từ bàn phím không đi thẳng vào biến mà được lưu tạm trong **bộ đệm (buffer)** cho đến khi bạn nhấn `Enter`. Điều này dẫn đến một số hành vi thú vị mà bạn cần nắm rõ:

- **Trường hợp nhập dư dữ liệu**:
    
    - Nếu chương trình yêu cầu 1 số nguyên nhưng bạn nhập `100 200` rồi nhấn `Enter`. `cin` sẽ lấy `100` gán cho biến đầu tiên.
        
    - Khi có lệnh `cin` tiếp theo, nó sẽ **không chờ** bạn gõ tiếp mà tự động lấy số `200` đang còn tồn đọng trong bộ đệm để gán luôn.
        
- **Trường hợp dữ liệu không khớp kiểu**:
    
    - Đọc số nguyên (`int num1`) và số thực (`double num3`). Nếu bạn nhập `10.5`:
        
    - `cin` đọc `int` đầu tiên: Nó thấy `1`, `0`, rồi đến dấu chấm `.` (không hợp lệ cho số nguyên). Nó dừng lại, lấy số `10` gán cho `num1`.
        
    - Bộ đệm lúc này còn dư chữ `.5`.
        
    - Tiếp theo `cin` đọc `double`: Nó lấy phần còn lại là `.5` gán cho `num3` (tương đương `0.5`). Kết quả: `num1 = 10`, `num3 = 0.5`.
        
- **Trạng thái lỗi (Fail State)**:
    
    - Nếu biến là `int` nhưng người dùng nhập chữ (ví dụ: `"Frank"`), quá trình trích xuất sẽ thất bại. Luồng `cin` rơi vào trạng thái lỗi (fail state). Biến sẽ nhận giá trị rác hoặc `0`, và các lệnh đọc `cin` sau đó sẽ hoạt động không đáng tin cậy.
        

### Ghi chú thêm từ giảng viên

Trong môi trường thực tế, lập trình viên thường đọc mọi thứ dưới dạng chuỗi (string) rồi mới chuyển đổi (parse) sang số để kiểm soát lỗi tốt hơn. Tuy nhiên, trong phạm vi khóa học cơ bản này, chúng ta sẽ tin tưởng nhập đúng kiểu dữ liệu được yêu cầu và chưa cần bận tâm đến việc xử lý lỗi (error handling).