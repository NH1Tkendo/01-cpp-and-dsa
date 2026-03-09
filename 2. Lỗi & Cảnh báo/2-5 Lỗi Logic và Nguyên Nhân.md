**Lỗi logic (logic errors)** hay còn gọi là "rệp" (bugs), là những sai sót khiến chương trình chạy không chính xác hoặc trả về kết quả sai, mặc dù chương trình vẫn có thể biên dịch và thực thi bình thường mà không báo lỗi. Đây hoàn toàn là những sai lầm bắt nguồn từ phía lập trình viên (programmer).

### 1. Nguyên nhân phổ biến

Lỗi logic có thể xuất phát từ rất nhiều lý do trong quá trình phát triển phần mềm:

- **Sự bất cẩn:** Những sai sót do thiếu tập trung trong lúc viết mã.
    
- **Thiếu thông tin:** Lập trình viên nắm bắt yêu cầu không đầy đủ hoặc hiểu sai thông tin bài toán.
    
- **Quá trình bảo trì/chỉnh sửa:** Khi một lập trình viên can thiệp, sửa chữa hoặc thêm tính năng mới vào luồng mã do người khác viết và vô tình đưa thêm lỗi mới vào hệ thống.
    

### 2. Ví dụ thực tế: Chương trình kiểm tra tuổi bầu cử

Giả sử yêu cầu bài toán là: _"Bạn phải từ 18 tuổi trở lên (>= 18) mới được quyền bầu cử."_

**Đoạn mã chứa lỗi logic:**

C++

```
if (age > 18) {
    // Thực thi các lệnh cho phép bầu cử
}
```

- **Phân tích vấn đề:** Đoạn mã trên có vẻ đúng khi đọc lướt qua. Tuy nhiên, nếu một người vừa tròn 18 tuổi (`age = 18`), phép thử `18 > 18` sẽ trả về sai (false). Hậu quả là người 18 tuổi sẽ bị từ chối quyền bầu cử. Trong thực tế, các lỗi này rất khó phát hiện vì chúng thường bị chôn vùi trong một khối lượng mã khổng lồ chứ không đứng tách biệt như ví dụ này.
    

**Cách khắc phục:** Cần điều chỉnh lại toán tử so sánh cho đúng với logic toán học và yêu cầu bài toán:

C++

```
// Cách 1: Sử dụng lớn hơn hoặc bằng
if (age >= 18) {
    // Thực thi các lệnh cho phép bầu cử
}

// Cách 2: Sử dụng lớn hơn 17
if (age > 17) {
    // Thực thi các lệnh cho phép bầu cử
}
```

### 3. Giải pháp phát hiện và xử lý

- Không giống như lỗi cú pháp được trình biên dịch chỉ điểm rõ ràng, lỗi logic đòi hỏi bạn phải tự đi tìm.
    
- **Cách duy nhất để khắc phục:** Bạn bắt buộc phải chủ động **kiểm thử mã (testing)** và **gỡ lỗi (debugging)** liên tục để đối chiếu kết quả thực tế với kết quả mong đợi. Các phương pháp kiểm thử (best practices) sẽ được áp dụng xuyên suốt vòng đời phát triển phần mềm.