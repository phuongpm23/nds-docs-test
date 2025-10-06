# Màn hình: Danh sách danh mục trạng thái giao dịch công chứng
Form cho phép tìm kiếm thông tin danh mục trạng thái giao dịch công chứng.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền tìm kiếm thông tin danh mục trạng thái giao dịch công chứng.

## Nguyên mẫu
[]

## Thành phần

### Form tìm kiếm (DM_TTGiaodich)
- Tự động hiển thị danh sách danh mục 
- Ô tìm kiếm tự luôn xuất hiện trên top trang

<div style="overflow-x:auto">

| Trường thông tin | Control  | Field           | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                           |
|:-----------------|:---------|:----------------|:-----------|:---------------|:-----------------|:-------------------|:------------------------------------------------|
| Mã danh mục      | Text     | MaDM_TTGiaodich | -          | Y              | -                | N                  | Mã danh mục tự tăng trong danh sách             |
| Tên danh mục     | Text     | TenDM_TTGiaodich| 250        | Y              | -                | Y                  |                                                 |
| Trạng thái       | Boolean  | TT_DM_TTGiaodich| -          | Y              | Active           | Y                  |                                                 |

</div>

### Chức năng

<div style="overflow-x:auto">

| Tên          | Tên   | Mô tả                                                                                                              |
|:-------------|:-------|:------------------------------------------------------------------------------------------------------------------|
| Tìm kiếm     | Button | Kiểm tra hợp lệ và hiển thị danh sách thông tin danh mục trạng thái giao dịch công chứng theo từ khóa tìm kiếm           |
| Làm mới      | Button | Làm mới lại thông tin tìm kiếm                                                                                    |
