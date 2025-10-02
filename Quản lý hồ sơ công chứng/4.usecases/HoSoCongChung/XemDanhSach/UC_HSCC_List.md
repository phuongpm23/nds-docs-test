# Use Case: UC_HSCC_List (Xem danh sách hồ sơ công chứng)

## User Story
- Với vai trò là **Chuyên viên tại Sở Tư pháp/Lãnh đạo Sở Tư pháp/Lãnh đạo Bộ Tư pháp/Công chứng viên/Nhân viên TCHNCC**, tôi muốn có thể xem danh sách hồ sơ công chứng theo phạm vi quyền hạn của mình để nắm được thông tin tổng quan về các hồ sơ công chứng.

## Acceptance Criteria
- Hệ thống hiển thị danh sách hồ sơ công chứng theo phạm vi quyền hạn của người dùng.
- Danh sách hiển thị các thông tin cơ bản của hồ sơ công chứng.
- Hệ thống hỗ trợ phân trang danh sách hồ sơ.
- Hệ thống hỗ trợ sắp xếp theo các cột thông tin.
- Người dùng có thể truy cập chi tiết từng hồ sơ từ danh sách.

## Tác nhân chính
- Chuyên viên tại Sở Tư pháp
- Lãnh đạo Sở Tư pháp/Lãnh đạo Phòng HCBTTP tại Sở TP
- Lãnh đạo Bộ Tư pháp/Lãnh đạo Cục Bổ trợ tư pháp/Chuyên viên Cục Bổ trợ tư pháp
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Xem danh sách hồ sơ công chứng".

## Luồng chính
1. Người dùng chọn chức năng **Danh sách hồ sơ công chứng** từ menu chính.
2. Hệ thống xác định phạm vi dữ liệu hiển thị theo quyền của người dùng:
   - Chuyên viên/Lãnh đạo Sở Tư pháp: Xem hồ sơ trên địa bàn tỉnh/thành phố
   - Lãnh đạo Bộ Tư pháp/Cục BTP: Xem hồ sơ toàn quốc hoặc theo địa phương được chỉ định
   - Công chứng viên/Nhân viên TCHNCC: Xem hồ sơ tại tổ chức của mình
3. Hệ thống hiển thị danh sách hồ sơ công chứng với các thông tin:
   - Mã hồ sơ công chứng
   - Tên giao dịch công chứng
   - Ngày công chứng
   - Số công chứng
   - Giá trị hợp đồng
   - Tên tổ chức công chứng
   - Tên công chứng viên
   - Trạng thái hồ sơ
4. Hệ thống hỗ trợ các chức năng trên danh sách:
   - Phân trang (mặc định 10 bản ghi/trang)
   - Sắp xếp theo các cột
   - Tìm kiếm nhanh theo từ khóa
5. Người dùng có thể chọn một hồ sơ để xem chi tiết.
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Không có dữ liệu: Hiển thị thông báo "Không có dữ liệu hồ sơ công chứng".
- Lỗi hệ thống: Hiển thị thông báo lỗi, không hiển thị dữ liệu.
- Người dùng không có quyền: Hiển thị thông báo "Bạn không có quyền truy cập chức năng này".

## Hậu điều kiện
- Nếu thành công: Hiển thị danh sách hồ sơ công chứng theo phạm vi quyền hạn.
- Nếu thất bại: Hiển thị thông báo lỗi tương ứng.

## Liên kết
- Activity Diagram: [AD_HSCC_List.puml]
- Form liên quan: [SCR_HSCC_List.md]
- Entity liên quan: ENT_HoSoCongChung