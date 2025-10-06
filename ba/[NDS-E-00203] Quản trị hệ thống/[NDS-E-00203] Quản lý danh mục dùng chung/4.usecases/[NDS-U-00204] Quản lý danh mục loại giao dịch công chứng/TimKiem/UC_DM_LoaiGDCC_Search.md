# Use Case: DM_LoaiGDCC_Search (Tìm kiếm danh mục Loại giao dịch công chứng)

## User Story
- Với vai trò là **Quản trị viên**, tôi muốn tìm kiếm thông tin danh mục Loại giao dịch công chứng.
- Với vai trò là **Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP**, tôi muốn tìm kiếm thông tin danh mục Loại giao dịch công chứng.
- Với vai trò là **Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP**, tôi muốn tìm kiếm thông tin danh mục Loại giao dịch công chứng.
- Với vai trò là **Công chứng viên tại các TCHNCC** tôi muốn tìm kiếm thông tin danh mục Loại giao dịch công chứng.

## Acceptance criteria
- Hệ thống hiển thị form tìm kiếm với các tiêu chí
    - Tên danh mục loại giao dịch công chứng theo từ khóa tìm kiếm
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tìm kiếm, thông báo "Không tìm thấy dữ liệu danh mục Loại giao dịch công chứng theo từ khóa tìm kiếm"
- Danh sách danh mục Loại giao dịch công chứng hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Công chứng viên
- Chuyên viên STP
- Lãnh đạo STP
- Lãnh đạo phòng HCBTTP tại STP
- Lãnh đạo Bộ Tư pháp
- Lãnh đạo Cục BTTP
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tìm kiếm danh mục Loại giao dịch công chứng

## Luồng chính
1. Người dùng truy cập màn hình danh sách danh mục Loại giao dịch công chứng (**DM_LoaiGDCC_List**).
2. Người dùng điền thông tin tìm kiếm (theo "Tên danh mục loại giao dịch công chứng", "mã danh mục")
3. Người dùng bấm nút "Tìm kiếm"
4. Hệ thống truy vấn thông tin danh mục Loại giao dịch công chứng
    - Truy vấn tên danh mục
    - Truy vấn đến mã danh mục
5. Hệ thống hiển thị danh sách thông tin danh mục Loại giao dịch công chứng theo từ khóa tìm kiếm
6. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
7. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tìm kiếm: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu danh mục".

## Hậu điều kiện
- Nếu thành công: Người dùng tìm kiếm thành công danh mục Loại giao dịch công chứng
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [DM_LoaiGDCC_Search.puml]
- Form/Screen:
- Entity liên quan: 
