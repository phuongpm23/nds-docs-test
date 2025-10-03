# Use Case: UC_HSCC_Update (Chỉnh sửa hồ sơ công chứng)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể chỉnh sửa thông tin hồ sơ công chứng để cập nhật các thay đổi hoặc sửa lỗi kỹ thuật.

## Acceptance Criteria
- Hệ thống hiển thị form chỉnh sửa thông tin hồ sơ công chứng với dữ liệu đã có.
- Hệ thống cho phép chỉnh sửa thông tin chung của hồ sơ.
- Hệ thống cho phép chỉnh sửa thông tin các bên tham gia giao dịch.
- Hệ thống cho phép chỉnh sửa thông tin chi tiết về tài sản.
- Hệ thống cho phép cập nhật tài liệu đính kèm.
- Hệ thống kiểm tra tính hợp lệ của dữ liệu trước khi lưu.
- Hệ thống ghi nhận lịch sử các thay đổi trên hồ sơ.
- Hệ thống hỗ trợ tạo phụ lục hồ sơ công chứng.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Chỉnh sửa hồ sơ công chứng".
- Hồ sơ công chứng tồn tại trong hệ thống.
- Người dùng có quyền chỉnh sửa hồ sơ này (thuộc cùng tổ chức).

## Luồng chính
1. Người dùng chọn chức năng **Chỉnh sửa** từ danh sách hồ sơ (**UC_HSCC_List**) hoặc từ màn hình chi tiết (**UC_HSCC_Detail**).
2. Hệ thống kiểm tra quyền chỉnh sửa hồ sơ của người dùng.
3. Hệ thống hiển thị form chỉnh sửa thông tin hồ sơ công chứng với các tab:
   
   **Tab Thông tin chung:**
   - Tên giao dịch công chứng
   - Ngày công chứng
   - Số công chứng
   - Nội dung giao dịch
   - Giá trị hợp đồng
   - Tổ chức công chứng
   - Công chứng viên thực hiện
   
   **Tab Bên tham gia:**
   - Danh sách bên tham gia cá nhân (có thể chỉnh sửa, xóa, thêm mới)
   - Danh sách bên tham gia tổ chức (có thể chỉnh sửa, xóa, thêm mới)
   
   **Tab Tài sản:**
   - Thông tin chi tiết về tài sản (có thể chỉnh sửa)
   
   **Tab Tài liệu đính kèm:**
   - Danh sách tài liệu đính kèm (có thể xóa, thêm mới)
4. Người dùng thực hiện các thay đổi cần thiết.
5. Người dùng bấm nút **Lưu**.
6. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Kiểm tra các trường bắt buộc đã được nhập
   - Kiểm tra định dạng dữ liệu
   - Kiểm tra logic nghiệp vụ
7. Nếu dữ liệu hợp lệ:
   - Hệ thống ghi nhận các thay đổi vào **ENT_LichSuCapNhatHoSo**
   - Cập nhật thông tin hồ sơ vào **ENT_HoSoCongChung**
   - Cập nhật thông tin các bên tham gia vào **ENT_NguoiThamGiaGiaoDichCaNhan** và **ENT_NguoiThamGiaGiaoDichToChuc**
   - Cập nhật thông tin tài sản vào **ENT_TaiSan**
   - Cập nhật thông tin tài liệu đính kèm
   - Hiển thị thông báo "Cập nhật hồ sơ công chứng thành công"
   - Chuyển hướng về màn hình chi tiết hồ sơ (**UC_HSCC_Detail**)
8. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Nếu ngày công chứng > Ngày hôm nay: thông báo lỗi "Ngày công chứng không được lớn hơn ngày hiện tại".
- Nếu chưa điền thông tin bắt buộc, hiển thị thông báo yêu cầu điền thông tin bắt buộc.
- Nếu sai định dạng thông tin, hiển thị thông báo lỗi "Thông tin không hợp lệ".
- Nếu số công chứng bị trùng với hồ sơ khác trong cùng tổ chức, hệ thống thông báo lỗi "Số công chứng đã tồn tại".
- Người dùng không có quyền chỉnh sửa: Hiển thị thông báo "Bạn không có quyền chỉnh sửa hồ sơ này".

## Hậu điều kiện
- Nếu thành công: Hồ sơ công chứng được cập nhật thông tin.
- Nếu thất bại: Không có thay đổi nào được lưu.

## Liên kết
- Activity Diagram: [AD_HSCC_Update.puml]
- Form liên quan: [SCR_HSCC_Update.md]
- Entity liên quan: ENT_HoSoCongChung, ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_TaiSan, ENT_LichSuCapNhatHoSo