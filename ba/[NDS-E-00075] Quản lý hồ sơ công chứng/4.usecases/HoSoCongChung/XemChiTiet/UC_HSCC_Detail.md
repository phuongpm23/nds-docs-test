# Use Case: UC_HSCC_Detail (Xem chi tiết hồ sơ công chứng)

## User Story
- Với vai trò là **Chuyên viên tại Sở Tư pháp/Lãnh đạo Sở Tư pháp/Lãnh đạo Bộ Tư pháp/Công chứng viên/Nhân viên TCHNCC**, tôi muốn có thể xem chi tiết thông tin của một hồ sơ công chứng để nắm được đầy đủ thông tin về giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị đầy đủ thông tin chi tiết của hồ sơ công chứng.
- Hệ thống kiểm tra quyền truy cập của người dùng trước khi hiển thị thông tin.
- Hệ thống hiển thị thông tin về các bên tham gia giao dịch.
- Hệ thống hiển thị thông tin chi tiết về tài sản liên quan.
- Hệ thống hiển thị các tài liệu đính kèm liên quan đến hồ sơ.
- Người dùng có thể thực hiện các thao tác liên quan dựa trên quyền hạn.

## Tác nhân chính
- Chuyên viên tại Sở Tư pháp
- Lãnh đạo Sở Tư pháp/Lãnh đạo Phòng HCBTTP tại Sở TP
- Lãnh đạo Bộ Tư pháp/Lãnh đạo Cục Bổ trợ tư pháp/Chuyên viên Cục Bổ trợ tư pháp
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Xem chi tiết hồ sơ công chứng".
- Hồ sơ công chứng tồn tại trong hệ thống.

## Luồng chính
1. Người dùng chọn chức năng **Xem chi tiết** từ danh sách hồ sơ công chứng (**UC_HSCC_List**).
2. Hệ thống kiểm tra quyền truy cập hồ sơ của người dùng:
   - Chuyên viên/Lãnh đạo Sở Tư pháp: Xem hồ sơ trên địa bàn tỉnh/thành phố
   - Lãnh đạo Bộ Tư pháp/Cục BTP: Xem hồ sơ toàn quốc hoặc theo địa phương được chỉ định
   - Công chứng viên/Nhân viên TCHNCC: Xem hồ sơ tại tổ chức của mình
3. Hệ thống hiển thị thông tin chi tiết hồ sơ công chứng:
   
   **Thông tin chung:**
   - Mã hồ sơ công chứng
   - Tên giao dịch công chứng
   - Ngày công chứng
   - Số công chứng
   - Nội dung giao dịch
   - Giá trị hợp đồng
   - Tên tổ chức công chứng
   - Tên công chứng viên thực hiện
   
   **Thông tin các bên tham gia:**
   - Danh sách bên tham gia cá nhân (Họ tên, CMND/CCCD, Địa chỉ, Số điện thoại)
   - Danh sách bên tham gia tổ chức (Tên tổ chức, Mã số thuế, Địa chỉ, Người đại diện)
   
   **Thông tin tài sản:**
   - Loại tài sản
   - Thông tin chi tiết về tài sản (tùy theo loại tài sản)
   - Giá trị tài sản
   
   **Tài liệu đính kèm:**
   - Văn bản công chứng giấy
   - Hồ sơ lưu trữ điện tử
   - Các tài liệu khác liên quan
4. Hệ thống hiển thị các chức năng thao tác dựa trên quyền hạn:
   - Chỉnh sửa hồ sơ (nếu có quyền)
   - In/In lại văn bản công chứng (nếu có quyền)
   - Tạo phụ lục hồ sơ (nếu có quyền)
   - Xóa hồ sơ (nếu có quyền)
5. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Hồ sơ không tồn tại: Hiển thị thông báo "Hồ sơ không tồn tại hoặc đã bị xóa".
- Người dùng không có quyền: Hiển thị thông báo "Bạn không có quyền truy cập hồ sơ này".
- Lỗi hệ thống: Hiển thị thông báo lỗi, không hiển thị chi tiết hồ sơ.

## Hậu điều kiện
- Nếu thành công: Hiển thị đầy đủ thông tin chi tiết hồ sơ công chứng.
- Nếu thất bại: Hiển thị thông báo lỗi tương ứng.

## Liên kết
- Activity Diagram: [AD_HSCC_Detail.puml]
- Form liên quan: [SCR_HSCC_Detail.md]
- Entity liên quan: ENT_HoSoCongChung, ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_TaiSan