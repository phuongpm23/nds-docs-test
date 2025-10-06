# Use Case: UC_DM_LoaiGDCC (Xem danh sách danh mục Loại giao dịch công chứng)

## User Story
- Với vai trò là **Quản trị viên**, tôi muốn xem danh sách danh mục Loại giao dịch công chứng.
- Với vai trò là **Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP**, tôi muốn xem danh sách danh mục Loại giao dịch công chứng.
- Với vai trò là **Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP**, tôi muốn xem danh sách danh mục Loại giao dịch công chứng.
- Với vai trò là **Công chứng viên tại các TCHNCC** tôi muốn xem danh sách danh mục Loại giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị danh sách danh mục Loại giao dịch công chứng với các trường: STT, Mã loại danh mục, tên danh mục, trạng thái danh mục.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Từ danh sách, người dùng có thể mở chi tiết, sửa , xóa, xem lịch sử (nếu có quyền và đúng trạng thái)
- Hiển thị thông báo lỗi nếu không tải được dữ liệu.
- Danh sách danh mục Loại giao dịch công chứng hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Hệ thống cho phép tìm kiếm danh mục Loại giao dịch công chứng (chi tiết tại UC_DM_LoaiGDCC_Search)
- Nếu không có danh mục Loại giao dịch công chứng nào trong hệ thống, hiển thị thông báo “Không có dữ liệu chữ ký số”. 

## Tác nhân chính
- Công chứng viên
- Chuyên viên STP
- Lãnh đạo STP
- Lãnh đạo phòng HCBTTP tại STP
- Lãnh đạo Bộ Tư pháp
- Lãnh đạo Cục BTTP
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền truy cập chức năng.

## Luồng chính
1. Người dùng mở menu chọn "Danh mục Loại giao dịch công chứng".
2. Hệ thống kiểm tra người dùng
3. Nếu người dùng thuộc Bộ, Hệ thống tải toàn bộ danh sách chữ ký số và lọc các bản ghi khác trạng thái "Tạo mới". (**ENT_ChuKySo**)
- Nếu người dùng thuộc Sở, Hệ thống tải danh sách chữ ký số của tất cả tổ chức công chứng thuộc Sở và lọc các chữ ký số khác trạng thái "Tạo mới".
- Nếu người dùng thuộc tổ chức công chứng, Hệ thống tải danh sách đăng ký chữ ký số theo tổ chức công chứng của người dùng.
4. Hệ thống hiển thị màn hình danh sách đăng theo thứ tự thời gian cập nhật từ mới tới cũ nhất **SCR_Sign_List** (lấy dữ liệu từ **ENT_CongChungVien**, **ENT_ChuKySo** và **ENT_ToChucCongChung**).
5. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
6. Người dùng có thể:
   - Chọn trang tiếp theo/ trước, hệ thống sẽ hiển thị 10 bản ghi của trang tương ứng
   - Export (UC_Sign_Export)
   - Tìm kiếm (UC_Sign__Search)
   - Đăng ký (UC_Sign__Create)
   - Xem chi tiết (UC_Sign__Detail)
   - Xóa (UC_Sign__Delete)
   - Chỉnh sửa (UC_Sign__Update)
   - Xem lịch sử cập nhật thông tin (UC_CCV_History)
5. Kết thúc.

## Luồng phụ/ Ngoại lệ
- Nếu có lỗi tải danh sách: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không có dữ liệu: hiển thị "Không có dữ liệu đăng ký chữ ký số của công chứng viên".
- Nếu không quyền truy cập: hiển thị "Không có quyền truy cập" và ẩn đi menu "Quản lý chữ ký số".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được danh sách chữ ký số.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Related
- AD_Sign_List.puml
- SCR_Sign_List.md
- ENT: **ENT_ChuKySo**, **ENT_CongChungVien**, **ENT_ToChucCongChung**