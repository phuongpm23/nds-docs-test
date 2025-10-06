# Use Case: DM_TenGDCC_Create (Thêm mới danh mục Tên giao dịch công chứng)

## User Story
- Với vai trò là **Quản trị viên**, tôi muốn thêm mới danh mục Tên giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị form thêm mới danh mục Tên giao dịch công chứng.
- Người dùng nhập thông tin: 
   - Mã danh mục **Tự sinh theo hệ thống**
   - Tên danh mục. 
- Hệ thống kiểm tra dữ liệu hợp lệ (mã danh mục không trùng lặp).
- Nếu hợp lệ: Lưu danh mục.
- Hiển thị thông báo "Thêm mới danh mục thành công".
- Người dùng có thể xóa danh mục ở thao tác Xóa (điều kiện: Danh mục chưa được sử dụng).

## Tác nhân chính
- Quản trị viên

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền đăng quản lý danh mục.

## Luồng chính
1. Người dùng chọn chức năng **Thêm mới danh mục Tên giao dịch công chứng** từ menu (**DM_TenGDCC_Create**).
2. Hệ thống hiển thị form thêm mới danh mục (**DM_TenGDCC_Create**).
3. Người dùng nhập các thông tin cần thiết.
4. Người dùng bấm nút **Lưu thông tin**.
5. Hệ thống kiểm tra dữ liệu:
   - Nếu hợp lệ: Lưu dữ liệu danh mục.
   - Hiển thị thông báo "Thêm mới danh mục thành công".
   - Quay về danh sách (**DM_TenGDCC_List**).
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Nhập thiếu thông tin bắt buộc: Hiển thị cảnh báo lỗi.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.

## Hậu điều kiện
- Nếu thành công: Danh mục Tên giao dịch công chứng được lưu trong hệ thống.
- Nếu thất bại: Không có dữ liệu nào được thêm.

## Liên kết
- Activity Diagram: [DM_TenGDCC_Create.puml]
- Form liên quan: [SCR_DM_TenGDCC_Create.md]
- Entity liên quan: DM_TenGDCC
