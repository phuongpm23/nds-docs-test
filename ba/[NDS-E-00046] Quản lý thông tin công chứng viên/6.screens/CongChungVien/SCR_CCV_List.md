# Màn hình: Danh sách công chứng viên
Nơi tập trung để xem và quản lý công chứng viên trên hệ thống.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền xem danh sách công chứng viên.

## Nguyên mẫu
[]

## Thành phần

### Bảng chính
- Các cột trong bảng danh sách công chứng viên hiển thị theo thứ tự bên dưới

<div style="overflow-x:auto">

| Trường thông tin     | Control | Field                                            | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                           |
|:---------------------|:--------|:-------------------------------------------------|:-----------|:---------------|:-----------------|:-------------------|:------------------------------------------------|
| Họ và tên            | text    | hoDem + ten                                      | -          | Y              | -                | -                  | Họ và tên công chứng viên                       |
| Số thẻ               | text    | soThe                                            | -          | Y              | -                | -                  | Số hiệu thẻ hành nghề công chứng                |
| Tổ chức công chứng   | text    | tenDonVi                                         | -          | Y              | -                | -                  | Tên tổ chức công chứng đang hành nghề           |
| Địa chỉ tổ chức      | text    | diaChiChiTiet + diaChiTinhThanh + diaChiPhuongXa | -          | Y              | -                | -                  | Địa chỉ tổ chức công chứng                      |
| Trạng thái hoạt động | text    | trangThai                                        | -          | Y              | -                | -                  | Trạng thái hoạt động                            |
| Chức năng            | icon    | -                                                | -          | -              | -                | -                  | Xem chi tiết, Sửa, Xóa, Xem lịch sử (tùy quyền) |

</div>

### Chức năng

<div style="overflow-x:auto">

| Tên                           | Loại     | Mô tả                                                                                                                            |
|:------------------------------|:---------|:---------------------------------------------------------------------------------------------------------------------------------|
| Ô tìm kiếm                    | Input    | Chỉ hiển thị khi người dùng có quyền tìm kiếm công chứng viên, nhập tên công chứng viên hoặc số thẻ để tìm kiếm                  |                                                        |
| Ô chọn trạng thái             | dropdown | Chỉ hiển thị khi người dùng có quyền tìm kiếm công chứng viên, Chọn trạng thái từ danh sách trạng thái hoạt động của công chứng viên (Giống với SCR_CCV_Create) để tìm kiếm (**UC_CCV_Search**) |
| Ô chọn Sở Tư pháp            | dropdown | Chỉ hiển thị khi người dùng có quyền tìm kiếm công chứng viên, Chọn Sở Tư pháp từ danh sách Sở Tư pháp để tìm kiếm (**UC_CCV_Search**) |
| Ô chọn Tổ chức công chứng            | dropdown | Chỉ hiển thị khi người dùng có quyền tìm kiếm công chứng viên, Chọn tổ chức công chứng theo Sở Tư Pháp đã chọn (**UC_CCV_Search**) |
| Biểu tượng tìm kiếm           | Button   | Bấm vào thực hiện tìm kiếm theo thông tin đã nhập/chọn (UC_CCV_Search)   
| Nút xuất danh sách            | Button   | Hiển thị nếu có quyền, click sẽ xuất danh sách theo điều kiện đã tìm (UC_CCV_Export)                                             |
| Nút thêm mới                  | Button   | Hiển thị nếu có quyền, click sẽ mở màn hình thêm công chứng viên (UC_CCV_Create)                                                    |
| Biểu tượng xem chi tiết       | Button   | Hiển thị nếu có quyền, click sẽ mở màn hình xem chi tiết công chứng viên (UC_CCV_Detail)                                            |
| Biểu tượng sửa                | Button   | Hiển thị nếu có quyền, click sẽ mở màn hình chỉnh sửa công chứng viên (UC_CCV_Update)                                               |
| Biểu tượng xóa                | Button   | Hiển thị nếu có quyền, click sẽ mở popup xác nhận xóa công chứng viên (UC_CCV_Delete)                                            |
| Biểu tượng lịch sử cập nhật   | Button   | Hiển thị nếu có quyền, click sẽ mở popup xem lịch sử cập nhật thông tin công chứng viên (UC_CCV_History)                         |

</div>
