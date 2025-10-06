# Màn hình: Thêm mới thông tin danh mục loại tài sản
Form cho phép Thêm mới thông tin danh mục loại tài sản.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền Thêm mới thông tin danh mục loại tài sản.

## Nguyên mẫu
[]

## Thành phần

### Form Thêm mới (DM_Loaitaisan)
- Hiển thị form thêm mới
<div style="overflow-x:auto">

| Trường thông tin | Control  | Field        -   | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                          |
|:-----------------|:---------|:-----------------|:-----------|:---------------|:-----------------|:-------------------|:-----------------------------------------------|
| Mã danh mục      | Text     | MaDM_Loaitaisan  | -          | Y              | -                | N                  | Mã danh mục tự tăng trong danh sách            |
| Tên danh mục     | Text     | TenDM_Loaitaisan | 250        | Y              | -                |                    |                                                |
| Trạng thái       | Boolean  | TT_DM_Loaitaisan | -          | Y              | Active           |                    |                                                |

</div>

### Chức năng

<div style="overflow-x:auto">

| Tên          | Tên   | Mô tả                                                                                            |
|:-------------|:-------|:------------------------------------------------------------------------------------------------|
| Lưu thông tin| Button | Kiểm tra hợp lệ, lưu dữ liệu vào DM_Loaitaisan với trạng thái = "Active"                           |
| Đóng         | Button | Đóng popup                                                                                      |
