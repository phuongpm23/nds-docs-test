# Use Case: UC_DMPhuongxa_new (Xem danh sách danh mục phường xã (mới))

## User Story
- Với vai trò là **Quản trị viên**, tôi muốn xem danh sách danh mục phường xã (mới).
- Với vai trò là **Chuyên viên Cục BTTP**, tôi muốn xem danh sách danh mục phường xã (mới).

## Acceptance Criteria
- Hệ thống hiển thị danh sách danh mục phường xã (mới) với các trường: STT, Mã danh mục, tên danh mục, trạng thái danh mục.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Từ danh sách, người dùng có thể mở chi tiết, sửa , xóa, xem lịch sử (nếu có quyền và đúng trạng thái)
- Hiển thị thông báo lỗi nếu không tải được dữ liệu.
- Danh sách danh mục phường xã (mới) hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Hệ thống cho phép tìm kiếm danh mục phường xã (mới) (chi tiết tại UC_DMPhuongxa_new_Search)
- Nếu không có danh mục phường xã (mới) nào trong hệ thống, hiển thị thông báo “Không có dữ liệu chữ ký số”. 

## Tác nhân chính
- Quản trị viên
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền truy cập chức năng.

## Luồng chính
1. Người dùng truy cập vào màn hình danh mục phường xã (mới).
2. Hệ thống thực hiện kiểm tra quyền truy cập.
- Nếu người dùng có quyền:
- Hệ thống tải danh sách dữ liệu phường xã (mới) từ CSDL.
3. Hệ thống kiểm tra dữ liệu trả về.
- Nếu có dữ liệu:
- Sắp xếp danh sách theo thời gian cập nhật (mới nhất → cũ).
4. Hiển thị danh sách trên giao diện (SCR_DMPhuongxa_new_List).
- Nếu không có dữ liệu: hiển thị thông báo “Không có dữ liệu danh mục”.
- Nếu người dùng không có quyền: hệ thống hiển thị thông báo lỗi “Không có quyền truy cập”.
5. Kết thúc

## Luồng phụ/ Ngoại lệ
- Nếu không có dữ liệu: Hệ thống hiển thị thông báo “Không có dữ liệu danh mục” thay vì danh sách.
- Nếu không quyền truy cập: Hệ thống chặn truy cập và thông báo lỗi “Không có quyền truy cập”.

## Hậu điều kiện
- Nếu thành công: Người dùng xem được danh sách danh mục phường xã (mới)
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_DMPhuongxa_new_List.puml]
- Form/Screen: [SCR_DMPhuongxa_new_List.md]
- Entity liên quan: DMPhuongxa_new