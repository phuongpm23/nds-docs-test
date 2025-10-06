# Use Case: UC_TSGD_Delete (Xóa tài sản giao dịch)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể xóa thông tin tài sản giao dịch khi có sai sót hoặc thay đổi trong giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị xác nhận trước khi xóa tài sản.
- Hệ thống kiểm tra các ràng buộc nghiệp vụ trước khi xóa.
- Hệ thống ghi nhận lịch sử xóa tài sản.
- Hệ thống cập nhật lại danh sách tài sản trong hồ sơ công chứng.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Chỉnh sửa hồ sơ công chứng".
- Tài sản tồn tại trong hồ sơ công chứng.
- Người dùng đang trong quá trình chỉnh sửa hồ sơ công chứng.

## Luồng chính
1. Người dùng chọn chức năng **Xóa** tài sản từ tab "Tài sản" trong form hồ sơ công chứng (**UC_HSCC_Update**).
2. Hệ thống hiển thị hộp thoại xác nhận xóa với thông tin:
   - Loại tài sản
   - Mô tả ngắn gọn về tài sản
   - Giá trị tài sản
   - Cảnh báo: "Bạn có chắc chắn muốn xóa tài sản này không?"
3. Người dùng xác nhận xóa.
4. Hệ thống kiểm tra các ràng buộc nghiệp vụ:
   - Kiểm tra xem tài sản có liên quan đến bên liên quan nào không
   - Kiểm tra xem hồ sơ đã được công chứng chưa
5. Nếu không có ràng buộc nào vi phạm:
   - Hệ thống ghi nhận thông tin xóa vào lịch sử
   - Xóa thông tin tài sản khỏi **ENT_TaiSan** và bảng chi tiết tương ứng
   - Hiển thị thông báo "Xóa tài sản thành công"
   - Cập nhật lại danh sách tài sản trong tab "Tài sản" của hồ sơ công chứng
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy** trong hộp thoại xác nhận: Hộp thoại đóng, không xóa dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không xóa dữ liệu.
- Nếu tài sản có liên quan đến bên liên quan: Hệ thống thông báo lỗi "Không thể xóa tài sản này vì đã liên quan đến bên liên quan trong giao dịch".
- Nếu hồ sơ đã được công chứng: Hệ thống thông báo lỗi "Không thể xóa tài sản vì hồ sơ đã được công chứng. Vui lòng tạo phụ lục hồ sơ".

## Hậu điều kiện
- Nếu thành công: Tài sản được xóa khỏi hồ sơ công chứng.
- Nếu thất bại: Không có thay đổi nào được thực hiện.

## Liên kết
- Form liên quan: [SCR_TSGD_Delete.md]
- Entity liên quan: ENT_TaiSan, ENT_TaiSanDat, ENT_TaiSanNha, ENT_TaiSanXe, ENT_TaiSanKhac, ENT_LichSuXoaTaiSan
- Usecase gọi đến: UC_HSCC_Update