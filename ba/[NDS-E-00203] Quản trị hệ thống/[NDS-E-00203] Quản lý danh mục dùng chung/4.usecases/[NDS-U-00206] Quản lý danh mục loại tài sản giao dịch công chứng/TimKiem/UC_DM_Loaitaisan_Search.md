# Use Case: DM_Loaitaisan_Search (Tìm kiếm danh mục Loại tài sản)

## User Story
- Với vai trò là **Quản trị viên**, tôi muốn tìm kiếm thông tin danh mục Loại tài sản.
- Với vai trò là **Chuyên viên Cục BTTP**, tôi muốn tìm kiếm thông tin danh mục Loại tài sản.


## Acceptance criteria
- Hệ thống hiển thị form tìm kiếm với các tiêu chí
    - Tên danh mục Loại tài sản theo từ khóa tìm kiếm
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tìm kiếm, thông báo "Không tìm thấy dữ liệu danh mục Loại tài sản theo từ khóa tìm kiếm"
- Danh sách danh mục Loại tài sản hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Quản trị viên
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tìm kiếm danh mục Loại tài sản

## Luồng chính
1. Người dùng truy cập màn hình danh sách danh mục Loại tài sản (**DM_Loaitaisan_List**).
2. Người dùng điền thông tin tìm kiếm (theo "Tên danh mục Loại tài sản", "mã danh mục")
3. Người dùng bấm nút "Tìm kiếm"
4. Hệ thống truy vấn thông tin danh mục Loại tài sản
    - Truy vấn tên danh mục
    - Truy vấn đến mã danh mục
5. Hệ thống hiển thị danh sách thông tin danh mục Loại tài sản theo từ khóa tìm kiếm
6. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
7. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tìm kiếm: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu danh mục".

## Hậu điều kiện
- Nếu thành công: Người dùng tìm kiếm thành công danh mục Loại tài sản
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [DM_Loaitaisan_Search.puml]
- Form/Screen: [SCR_DM_Loaitaisan_Search.md]
- Entity liên quan: DM_Loaitaisan
