# Use Case: Tìm kiếm danh mục phường xã (mới)

## User Story
- Là **Quản trị viên**, tôi muốn xem được danh sách và tìm kiếm được danh mục phường xã (mới).
- Là **Chuyên viên cục BTTP**, tôi muốn xem được danh sách và tìm kiếm được danh mục phường xã (mới).

## Acceptance criteria
- Hệ thống hiển thị form tìm kiếm với các tiêu chí.
- Ô điền thông tin tìm kiếm theo "Tên danh mục", "Mã danh mục".
- Hiển thị bảng danh sách danh mục phường xã (mới) theo tiêu chí đã tìm kiếm.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tìm kiếm, thông báo "Không tìm thấy dữ liệu danh mục phường xã (mới)"
- Danh sách danh mục phường xã (mới) hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Quản trị viên
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tìm kiếm thông tin danh mục phường xã (mới)

## Luồng chính
1. Người dùng truy cập màn hình danh sách danh mục phường xã (mới) (**UC_DMPhuongxa_new_List**).
2. Người dùng điền thông tin tìm kiếm (theo "Tên danh mục", "Mã danh mục")
3. Người dùng chọn tiêu chí tìm kiếm khác
4. Người dùng bấm nút "Tìm kiếm"
5. Hệ thống truy vấn thông tin danh mục phường xã (mới)
    - Truy vấn theo tên danh mục
    - Truy vấn chính xác mã danh mục
6. Hệ thống hiển thị danh sách thông tin danh mục đã truy vấn được
7. Hệ thống hiển thị danh sách danh mục phường xã (mới) theo thứ tự thời gian cập nhật từ mới tới cũ nhất
8. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
9. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tìm kiếm: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu danh mục".

## Hậu điều kiện
- Nếu thành công: Người dùng tìm kiếm thành công danh mục phường xã (mới).
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_DMPhuongxa_new.puml]
- Form/Screen: [SCR_DMPhuongxa_new.md]
- Entity liên quan: DMPhuongxa_new
