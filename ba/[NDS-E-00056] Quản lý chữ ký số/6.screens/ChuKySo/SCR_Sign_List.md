# Màn hình: Danh sách chữ ký số
Nơi tập trung để xem và quản lý các chữ ký số.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền truy cập chức năng quản lý chữ ký số.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=31-16209&t=rbUdgRjssoRY3o5T-1]
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=31-16571&t=rbUdgRjssoRY3o5T-1]

## Thành phần

### Bảng chính (ENT_ChuKySo, ENT_CongChungVien, ENT_ToChucCongChung)

<div style="overflow-x:auto">

| Trường thông tin       | Control | Field              | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                                                 |
|:-----------------------|:--------|:-------------------|:-----------|:---------------|:-------------------|:----------------------------------------------------------------------|
| Tên tổ chức công chứng | text    | tenToChucCongChung | -          | -              | -                  | Chỉ hiển thị trong trường hợp người dùng cấp Sở và cấp Bộ             |
| Số serial              | text    | soSerial           | -          | -              | -                  | Số Serial                                                             |
| Nhà cung cấp dịch vụ   | text    | nhaCungCap         | -          | -              | -                  | Nhà cung cấp chữ ký số                                                |
| Loại chữ ký số         | text    | loaiChuKySo        | -          | -              | -                  | Cá nhân / Tổ chức                                                     |
| Tên công chứng viên    | text    | hoVaTen            | -          | -              | -                  | Hiển thị tên công chứng viên đã chọn nếu là chữ ký số cá nhân         |
| Trạng thái             | text    | trangThai          | -          | -              | -                  | Mới tạo / Chờ duyệt / Đã duyệt / Từ chối                              |
| Chức năng              | icon    | -                  | -          | -              | -                  | Xem chi tiết, Chỉnh sửa, Xóa, xem lịch sử (tuỳ quyền, tuỳ trạng thái) |

</div>

### Khác
- Phân trang 10 bản ghi/trang.  
- Sắp xếp theo thứ tự thời gian cập nhật từ mới tới cũ nhất.  
- Nếu không có dữ liệu: hiển thị **"Không có dữ liệu chữ ký số"**.  
- Nếu có lỗi tải dữ liệu: hiển thị **"Không tải được danh sách, vui lòng thử lại"**.  

### Chức năng

<div style="overflow-x:auto">

| Tên                        | Loại   | Mô tả                                                                                                       |
|:---------------------------|:-------|:------------------------------------------------------------------------------------------------------------|
| Tìm kiếm                   | Input  | Nhập tiêu chí để tìm kiếm (**UC_Sign_Search**)                                                               |
| Ô điền tên tổ chức         | Input  | Nhập tên tổ chức để tìm kiếm (**UC_Sign_Search**)                                                            |
| Ô điền số serial           | Input  | Nhập số serial để tìm kiếm (**UC_Sign_Search**)                                                              |
| Ô chọn nhà cung cấp        | Input  | Chọn nhà cung cấp để tìm kiếm (**UC_Sign_Search**)                                                           |
| Ô chọn loại chữ ký số      | Input  | Chọn loại chữ ký số (cá nhân/tổ chức) để tìm kiếm (**UC_Sign_Search**)                                       |
| Ô điền tên công chứng viên | Input  | Điền tên công chứng viên để tìm kiếm (**UC_Sign_Search**)                                                    |
| Ô chọn trạng thái          | Input  | Chọn trạng thái (Chờ duyệt, tạo mới, đã duyệt, từ chối) để tìm kiếm (**UC_Sign_Search**)                     |
| Tìm kiếm                   | Input  | Nhập tiêu chí để tìm kiếm (**UC_Sign_Search**)                                                               |
| Tìm kiếm                   | Button | Thực hiện tìm kiếm theo tiêu chí đã nhập và chọn                                                            |
| Export                     | Button | Xuất danh sách đăng ký chữ ký số theo điều kiện tìm kiếm (**UC_Sign_Export**)                                |
| Xem chi tiết               | Button | Hiển thị nếu có quyền xem chi tiết, click mở màn hình chi tiết thông tin đăng ký chữ ký số (**UC_Sign_Detail**) |
| Đăng ký                    | Button | Hiển thị nếu có quyền thêm mới, click mở màn hình thêm mới đăng ký chữ ký số (**UC_Sign_Create**)               |
| Sửa                        | Button | Hiển thị nếu có quyền chỉnh sửa, click mở màn hình chỉnh sửa đăng ký chữ ký số (**UC_Sign_Update**)             |
| Xóa                        | Button | Hiển thị nếu có quyền xóa, click mở popup xác nhận xoá (**UC_Sign_Delete**)                                  |
| Xem lịch sử                | Button | Hiển thị nếu có quyền, click mở popup lịch sử thay đổi (**UC_Sign_History**)                                 |

</div>