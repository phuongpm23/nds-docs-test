# Use Case: UC_HSCC_List (Xem danh sách hồ sơ công chứng)

## User Story
- Với vai trò là **Chuyên viên tại Sở Tư pháp/Lãnh đạo Sở Tư pháp/Lãnh đạo Phòng HCBTTP tại Sở TP**, tôi muốn có thể xem danh sách hồ sơ công chứng của các tổ chức công chứng thuộc phạm vi quản lý của Sở Tư pháp để nắm được thông tin tổng quan về các hồ sơ công chứng.
- Với vai trò là **Lãnh đạo Bộ Tư pháp/Lãnh đạo Cục Bổ trợ tư pháp/Chuyên viên Cục Bổ trợ tư pháp**, tôi muốn có thể xem danh sách hồ sơ công chứng của toàn bộ hệ thống để nắm được thông tin tổng quan về các hồ sơ công chứng.
- Với vai trò là **Công chứng viên/Nhân viên TCHNCC**, tôi muốn có thể xem danh sách hồ sơ công chứng của tổ chức mình để nắm được thông tin tổng quan về các hồ sơ công chứng.

## Acceptance Criteria
- Hệ thống hiển thị danh sách hồ sơ công chứng theo phạm vi quyền hạn của người dùng.
- Danh sách hiển thị các thông tin cơ bản của hồ sơ công chứng.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Hỗ trợ xuất (Export) danh sách theo điều kiện đã tìm  (chi tiết trong UC_HSCC_Export).
- Mỗi dòng có action: Xem chi tiết, Sửa, Xóa, Xem lịch sử (tuỳ quyền).  
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
<!-- - Danh sách hồ sơ công chứng hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất. -->
- Hệ thống cho phép tìm kiếm hồ sơ công chứng (chi tiết trong UC_HSCC_Search).    
- Nếu không có công chứng viên nào trong hệ thống, hiển thị thông báo “Không có dữ liệu hồ sơ công chứng”.

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
1. Người dùng chọn chức năng **Quản lý hồ sơ công chứng** từ menu chính.
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