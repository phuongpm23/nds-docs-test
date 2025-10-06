# Use Case: UC_DM_Giayto_List (Xem danh sách danh mục giấy tờ )

## User Story
- Với vai trò là **Quản trị viên**, tôi muốn xem danh sách danh mục giấy tờ .
- Với vai trò là **Chuyên viên Cục BTTP**, tôi muốn xem danh sách danh mục giấy tờ .


## Acceptance Criteria
- Hệ thống hiển thị danh sách danh mục giấy tờ  với các trường: STT, Mã Tên danh mục, tên danh mục, trạng thái danh mục.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Từ danh sách, người dùng có thể mở chi tiết, sửa , xóa, xem lịch sử (nếu có quyền và đúng trạng thái)
- Hiển thị thông báo lỗi nếu không tải được dữ liệu.
- Danh sách danh mục giấy tờ  hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Hệ thống cho phép tìm kiếm danh mục giấy tờ  (chi tiết tại UC_DM_Giayto_Search)
- Nếu không có danh mục giấy tờ  nào trong hệ thống, hiển thị thông báo “Không có dữ liệu chữ ký số”. 

## Tác nhân chính
- Quản trị viên
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền truy cập chức năng.

## Luồng chính
1. Người dùng mở menu chọn "Danh mục giấy tờ ".
2. Hệ thống kiểm tra người dùng
3. Nếu có quyền truy cập
- Hệ thống hiển thị danh sách danh mục giấy tờ .
- Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
4. Nếu không có quyền truy cập
- Hệ thống hiển thị thông báo "Không có quyền truy cập".
5. Kết thúc.

## Luồng phụ/ Ngoại lệ
- Nếu có lỗi tải danh sách: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không có dữ liệu: hiển thị "Không có dữ liệu đăng ký chữ ký số của công chứng viên".
- Nếu không quyền truy cập: hiển thị "Không có quyền truy cập" và ẩn đi menu "Quản lý danh mục giấy tờ ".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được danh sách danh mục giấy tờ .
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [DM_Giayto_List.puml]
- Form liên quan: [SCR_DM_Giayto_List.md]
- Entity liên quan: DM_Giayto
