# Use Case: UC_BLQ_Delete (Xóa bên liên quan)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể xóa thông tin bên liên quan (cá nhân/tổ chức) khi có sai sót hoặc thay đổi trong giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị xác nhận trước khi xóa bên liên quan.
- Hệ thống kiểm tra các ràng buộc nghiệp vụ trước khi xóa.
- Hệ thống ghi nhận lịch sử xóa bên liên quan.
- Hệ thống cập nhật lại danh sách bên liên quan trong hồ sơ công chứng.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Chỉnh sửa hồ sơ công chứng".
- Bên liên quan tồn tại trong hồ sơ công chứng.
- Người dùng đang trong quá trình chỉnh sửa hồ sơ công chứng.

## Luồng chính
1. Người dùng chọn chức năng **Xóa** bên liên quan từ tab "Bên tham gia" trong form hồ sơ công chứng (**UC_HSCC_Update**).
2. Hệ thống hiển thị hộp thoại xác nhận xóa với thông tin:
   - Tên bên liên quan (cá nhân/tổ chức)
   - Vai trò trong giao dịch
   - Cảnh báo: "Bạn có chắc chắn muốn xóa bên liên quan này không?"
3. Người dùng xác nhận xóa.
4. Hệ thống kiểm tra các ràng buộc nghiệp vụ:
   - Kiểm tra xem bên liên quan có liên quan đến tài sản trong giao dịch không
   - Kiểm tra xem hồ sơ đã được công chứng chưa
5. Nếu không có ràng buộc nào vi phạm:
   - Hệ thống ghi nhận thông tin xóa vào lịch sử
   - Xóa thông tin bên liên quan khỏi **ENT_NguoiThamGiaGiaoDichCaNhan** hoặc **ENT_NguoiThamGiaGiaoDichToChuc**
   - Hiển thị thông báo "Xóa bên liên quan thành công"
   - Cập nhật lại danh sách bên liên quan trong tab "Bên tham gia" của hồ sơ công chứng
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy** trong hộp thoại xác nhận: Hộp thoại đóng, không xóa dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không xóa dữ liệu.
- Nếu bên liên quan có liên quan đến tài sản trong giao dịch: Hệ thống thông báo lỗi "Không thể xóa bên liên quan này vì đã liên quan đến tài sản trong giao dịch".
- Nếu hồ sơ đã được công chứng: Hệ thống thông báo lỗi "Không thể xóa bên liên quan vì hồ sơ đã được công chứng. Vui lòng tạo phụ lục hồ sơ".

## Hậu điều kiện
- Nếu thành công: Bên liên quan được xóa khỏi hồ sơ công chứng.
- Nếu thất bại: Không có thay đổi nào được thực hiện.

## Liên kết
- Form liên quan: [SCR_BLQ_Delete.md]
- Entity liên quan: ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_LichSuXoaBenLienQuan
- Usecase gọi đến: UC_HSCC_Update