# Use Case: Đồng bộ danh mục giới tính qua API
## User Story
- Là **Quản trị viên**, tôi muốn xem được danh sách danh mục giới tính đã đồng bộ qua API.
- Là **Hệ thống khác**, khi có yêu cầu đồng bộ API danh mục giới tính sẽ trả về kết quả đồng bộ.

## Acceptance criteria
- Hệ thống kết nối với hệ thống khác cung cấp danh mục giới tính.
- Các trường thông tin bao gồm: 
   - Mã danh mục
   - Tên danh mục
- Người dùng có thể xem được danh sách danh mục sau khi đồng bộ
- Nếu không thực hiện đồng bộ được, hệ thống trả về thông báo **Đồng bộ không thành công.**.

## Tác nhân chính
- Quản trị viên
- Hệ thống khác

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem danh sách danh mục.
- Hệ thống khác có kết nối API.

## Luồng chính
1. Người dùng truy cập thành công màn hình danh sách danh mục giới tính (**SCR_DMGioitinh_List**)
2. Hệ thống gọi API hệ thống khác để lấy danh mục giới tính.
3. Hệ thống khác xử lý yêu cầu và trả về dữ liệu danh mục giới tính.
4. Hệ thống kiểm tra dữ liệu trả về:
 - Nếu hợp lệ → mapping, đồng bộ danh mục giới tính vào DB
 - Nếu không hợp lệ → ghi log lỗi + báo cáo lỗi
 - Ghi log kết quả (số bản ghi thành công, lỗi).
5. Kết thúc Use case

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không có danh mục giới tính được đồng bộ".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin"..

## Hậu điều kiện
- Nếu thành công: Người dùng xem được danh sách danh mục giới tính đã được đồng bộ.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_DMGioitinh_API.puml]
- Form/Screen: [SCR_DMGioitinh_API.md]
- Entity liên quan: DMGioitinh
