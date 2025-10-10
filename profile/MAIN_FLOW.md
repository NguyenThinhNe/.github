## Main Flow
### 🟢 Luồng 1: Bảo hành xe
#### 🔹 Giai đoạn 1: Tạo yêu cầu bảo hành (Service Center)
**👨‍🔧 SC Technician**
+ Tạo mới một yêu cầu bảo hành (Claim Request).
+ Thông tin bao gồm:
    + 📌 Mã lập đơn, Ngày lập đơn, Trung tâm, Người lập
    + 🚗 Hãng xe, Mã VIN, Số km, Ngày mua xe
    + 🔧 Tên & mã phụ tùng, Ngày thay thế
    + 📝 Mô tả sự cố, điều kiện vận hành
    + 📷 Ảnh/Video minh chứng
    + 📨 Yêu cầu từ trung tâm:
        + Cung cấp phụ tùng thay thế / phê duyệt sửa chữa
        + Hoàn chi phí sửa chữa (nếu trung tâm đã thay trước)

**👩‍💼 SC Staff**
+ Nhận claim mới → xem danh sách claim (theo ngày, trạng thái).
+ 🔍 Xác minh lại thông tin.
+ 📤 Gửi claim lên hãng (EVM Staff).

#### 🔹 Giai đoạn 2: Xử lý yêu cầu bảo hành (EVM Staff)

**👨‍💼 EVM Staff**
+ Mở claim request → kiểm tra thông tin: xe, phụ tùng, ảnh/video...
+ ⏳ Đánh giá thời hạn & điều kiện bảo hành.

**🛑 Nếu không đạt → Reject claim**
+ Lý do: phụ tùng hết hạn, hư hỏng do người dùng, v.v.
+ 📩 Trả lại thông báo cho SC Staff.

**✅ Nếu đạt → Approve claim**
+ Cung cấp phụ tùng / phê duyệt sửa chữa.
+ 📩 Gửi thông báo approved về SC Staff.

#### 🔹 Giai đoạn 3: Thực hiện bảo hành (Service Center)
**👩‍💼 SC Staff**
+ Assign cho một Technician để thực hiện case.

**👨‍🔧 SC Technician**
+ Thay thế hoặc sửa chữa phụ tùng.
+ Ghi nhận: Ngày thay thế, Người thực hiện, Ảnh chứng minh, Số seri phụ tùng mới.
+ 🖱️ Bấm Complete → xuất hóa đơn bảo hành (chi phí dựa trên phụ tùng/sửa chữa).

**🏢 EVM Staff**
+ Nhận hóa đơn.
+ 💳 Bấm Thanh toán (chỉ hiển thị “Thanh toán thành công”).

### 🟡 Luồng 2: Chiến dịch (Service Campaign / Recall)
#### 📝 Giai đoạn Khởi tạo & Phê duyệt (Manufacturer)
+ Hãng xác định vấn đề kỹ thuật/an toàn.
+ Tạo chiến dịch:
    + 🔖 Loại: Service Campaign hoặc Safety Recall.
    + 📜 Mô tả chi tiết, biện pháp khắc phục.
    + ⏰ Thời gian hiệu lực.
    + 🧩 Linh kiện/Phần mềm liên quan.
+ 👨‍💼 Quản lý hãng phê duyệt → hệ thống kích hoạt:
    + Đánh dấu các xe bị ảnh hưởng = Campaign Pending.
    + 📩 Gửi thông báo đến Service Center.

#### 🛠️ Giai đoạn Triển khai (Service Center)
+ Nhận thông tin chiến dịch.
+ Kiểm tra kho phụ tùng → đặt hàng nếu cần.
+ Lập lịch dịch vụ cho khách hàng:
    + Nhập VIN → hệ thống báo xe có nằm trong campaign không.
    + Lên lịch hẹn & thông báo khách.
+ Khi xe tới:
    + Tạo Repair/Warranty Order (RO/WO).
    + Gán mã chiến dịch.
    + 👨‍🔧 Technician thực hiện công việc (thay linh kiện, update phần mềm).
    + Ghi lại thời gian & phụ tùng đã sử dụng.
+ Sau khi xong:
    + Đóng RO/WO → gửi claim bồi thường đến hãng.
+ Hệ thống tự động cập nhật:
    + 🚘 VIN = Campaign Completed / Claim Submitted.
    + 📅 Lưu ngày & trung tâm thực hiện.
