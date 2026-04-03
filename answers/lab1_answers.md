# Lab 01 Answers
## CIA & Risk: Hệ thống lưu điểm

**Họ và tên:** Nguyễn Hữu Mạnh 

**MSSV:** 1871020381

**Lớp/Nhóm:** 18-02

---

## 1. Assets
Liệt kê ít nhất 2 assets cần bảo vệ.

- Asset 1: Dữ liệu điểm số của sinh viên: Đây là thông tin cốt lõi, phản ánh kết quả học tập và cần độ chính xác tuyệt đối.
- Asset 2: Thông tin xác thực người dùng (Account Credentials): Bao gồm username và password của giảng viên và sinh viên để kiểm soát quyền truy cập hệ thống.

---

## 2. Mapping CIA
Ghép từng sự cố với CIA.

- Sự cố A -> Availability (Tính khả dụng): Sinh viên không đăng nhập được vào tối trước ngày công bố điểm (hệ thống bị gián đoạn dịch vụ).
- Sự cố B -> Integrity (Tính toàn vẹn): Điểm bị thay đổi từ 8.0 thành 5.0 (dữ liệu bị sửa đổi trái phép, không còn chính xác).
- Sự cố C -> Confidentiality (Tính bảo mật): Danh sách điểm bị lộ ra nhóm chat ngoài lớp (thông tin riêng tư bị tiết lộ cho bên thứ ba không có thẩm quyền).

---

## 3. Phân tích sự cố B
- Threat (Mối đe dọa): Một sinh viên hoặc kẻ tấn công có ý đồ xấu thực hiện tấn công thay đổi dữ liệu (Data tampering) để phá hoại hoặc trục lợi.
- Vulnerability (Lỗ hổng): Hệ thống thiếu kiểm tra quyền hạn (Broken Access Control), cho phép người dùng bình thường có thể gửi request chỉnh sửa dữ liệu của người khác, hoặc thiếu cơ chế lưu vết (Logging).
- Mitigation (Biện pháp giảm thiểu): Triển khai cơ chế kiểm tra quyền (Authorization) chặt chẽ ở phía Server-side và sử dụng Digital Signatures hoặc Audit Logs để theo dõi mọi thay đổi đối với dữ liệu điểm.

---

## 4. Reflection
 Nếu là quản trị viên hệ thống, em sẽ ưu tiên xử lý sự cố B (Tính toàn vẹn - Integrity) trước. Lý do là vì điểm số là dữ liệu quan trọng nhất của hệ thống giáo dục; nếu tính toàn vẹn bị vi phạm, hệ thống sẽ mất đi sự tin cậy từ cả giảng viên lẫn sinh viên. Một hệ thống có thể chậm (Availability) hoặc lộ thông tin (Confidentiality), nhưng nếu dữ liệu bị sai lệch mà không thể truy vết, nó sẽ gây ra hệ lụy nghiêm trọng về công bằng và uy tín của tổ chức. Sau khi đảm bảo dữ liệu "sạch", em mới tiến hành vá lỗ hổng rò rỉ và tối ưu hiệu suất.

---

## 5. Bonus Flag
`FIT4012{A-?-B-?-C-?}`
Flag của em:
FIT4012{A-A-B-I-C-C}
A - Availability

B - Integrity

C - Confidentiality

