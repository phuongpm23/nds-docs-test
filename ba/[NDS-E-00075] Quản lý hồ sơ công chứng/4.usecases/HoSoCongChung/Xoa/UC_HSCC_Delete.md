# Use Case: UC_HSCC_Delete (Xóa hồ sơ công chứng)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể xóa hồ sơ công chứng để loại bỏ các hồ sơ không còn cần thiết hoặc được tạo nhầm.

## Acceptance Criteria
- Hệ thống yêu cầu xác nhận trước khi xóa hồ sơ.
- Hệ thống kiểm tra quyền xóa hồ sơ của người dùng.
- Hệ thống kiểm tra các điều kiện nghiệp vụ trước khi cho phép xóa.
- Hệ thống xóa toàn bộ thông tin liên quan đến hồ sơ (bên tham gia, tài sản, tài liệu).
- Hệ thống ghi nhận lịch sử xóa hồ sơ.
- Hệ thống hỗ trợ xóa một hoặc nhiều hồ sơ cùng lúc.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Xóa hồ sơ công chứng".
- Hồ sơ công chứng tồn tại trong hệ thống.
- Người dùng có quyền xóa hồ sơ này (thuộc cùng tổ chức).

## Luồng chính
1. Người dùng chọn chức năng **Xóa** từ danh sách hồ sơ (**UC_HSCC_List**) hoặc từ màn hình chi tiết (**UC_HSCC_Detail**).
2. Hệ thống kiểm tra quyền xóa hồ sơ của người dùng.
3. Hệ thống hiển thị hộp thoại xác nhận xóa hồ sơ với thông tin:
   - Mã hồ sơ công chứng
   - Tên giao dịch công chứng
   - Ngày công chứng
   - Cảnh báo: "Hành động này không thể hoàn tác. Toàn bộ thông tin liên quan đến hồ sơ sẽ bị xóa vĩnh viễn."
4. Người dùng xác nhận xóa hồ sơ.
5. Hệ thống kiểm tra các điều kiện nghiệp vụ:
   - Hồ sơ không đang trong quá trình xử lý
   - Hồ sơ không liên quan đến các vụ việc đang tranh chấp
   - Hồ sơ không bị khóa bởi người dùng khác
6. Nếu các điều kiện được đáp ứng:
   - Hệ thống ghi nhận thông tin xóa vào **ENT_LichSuCapNhatHoSo**
   - Xóa thông tin các bên tham gia trong **ENT_NguoiThamGiaGiaoDichCaNhan** và **ENT_NguoiThamGiaGiaoDichToChuc**
   - Xóa thông tin tài sản trong **ENT_TaiSan**
   - Xóa thông tin tài liệu đính kèm
   - Xóa thông tin hồ sơ trong **ENT_HoSoCongChung**
   - Hiển thị thông báo "Xóa hồ sơ công chứng thành công"
   - Cập nhật lại danh sách hồ sơ
7. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Đóng hộp thoại xác nhận, không xóa hồ sơ.
- Người dùng không có quyền: Hiển thị thông báo "Bạn không có quyền xóa hồ sơ này".
- Hồ sơ không tồn tại: Hiển thị thông báo "Hồ sơ không tồn tại hoặc đã bị xóa".
- Hồ sơ đang trong quá trình xử lý: Hiển thị thông báo "Không thể xóa hồ sơ đang trong quá trình xử lý".
- Hồ sơ liên quan đến vụ việc tranh chấp: Hiển thị thông báo "Không thể xóa hồ sơ liên quan đến vụ việc đang tranh chấp".
- Hồ sơ bị khóa bởi người dùng khác: Hiển thị thông báo "Hồ sơ đang bị khóa bởi người dùng khác. Không thể thực hiện thao tác xóa."
- Lỗi hệ thống: Hiển thị thông báo lỗi, không xóa hồ sơ.

## Hậu điều kiện
- Nếu thành công: Hồ sơ công chứng và toàn bộ thông tin liên quan bị xóa vĩnh viễn.
- Nếu thất bại: Không có thông tin nào bị xóa.

## Liên kết
- Activity Diagram: [AD_HSCC_Delete.puml]
- Form liên quan: [SCR_HSCC_Delete.md]
- Entity liên quan: ENT_HoSoCongChung, ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_TaiSan, ENT_LichSuCapNhatHoSo