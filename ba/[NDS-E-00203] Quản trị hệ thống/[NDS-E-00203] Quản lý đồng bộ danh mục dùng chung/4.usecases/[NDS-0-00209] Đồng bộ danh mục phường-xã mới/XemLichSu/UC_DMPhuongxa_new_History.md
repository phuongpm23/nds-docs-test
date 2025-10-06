# Use Case: Xem lịch sử đồng bộ danh mục phường xã (mới)

## User Story
- Là **Quản trị viên**, tôi muốn xem được lịch sử đồng bộ danh mục phường xã (mới) để có thể truy vết và xem các thay đổi của thông tin.

## Acceptance criteria
- Hệ thống hiển thị lịch sử đồng bộ dưới dạng danh sách
- Các trường thông tin trong danh sách bao gồm: 
    - Thời gian
    - Người thực hiện
    - Thao tác
    - Trường thay đổi
    - Giá trị cũ
    - Giá trị mới
- Người dùng có thể quay lại trang danh sách danh mục phường xã (mới)
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy lịch sử đồng bộ danh mục".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Quản trị viên
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem lịch sử đồng bộ danh mục phường xã (mới)

## Luồng chính
1. Người dùng truy cập thành công màn hình danh sách danh mục phường xã (mới) (**SCR_DMPhuongxa_new_List**)
2. Người dùng truy cập trang lịch sử đồng bộ danh mục phường xã (mới) 
3. Hệ thống truy vấn lịch sử đồng bộ thông tin đăng ký chữ ký số theo ID (**DMPhuongxa_new**).
4. Hệ thống hiển thị popup lịch sử đồng bộ thông tin đăng ký chữ ký số (**SCR_DMPhuongxa_new_History**) bao gồm các thông tin
    - Thời gian
    - Người thực hiện
    - Thao tác
    - Trường thay đổi
    - Giá trị cũ
    - Giá trị mới
5. Hệ thống hiển thị các nút chức năng.
- Biểu tượng quay lại và nút đóng => Bấm vào đóng popup, chuyển về màn hình danh sách danh mục phường xã (mới) (**SCR_DMPhuongxa_new_List**)
6. Kết thúc

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy lịch sử đồng bộ danh mục phường xã (mới)".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được lịch sử đồng bộ danh mục phường xã (mới).
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_DMPhuongxa_new_History.puml]
- Form/Screen: [SCR_DMPhuongxa_new_History.md]
- Entity liên quan: DMPhuongxa_new
