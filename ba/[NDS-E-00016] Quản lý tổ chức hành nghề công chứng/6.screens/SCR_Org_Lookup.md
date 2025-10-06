# Màn hình: Tra cứu tổ chức công chứng
Màn hình tra cứu tổ chức công chứng

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền tra cứu tổ chức công chứng.

## Nguyên mẫu
[]

## Thành phần

### Bảng kết quả tra cứu

<div style="overflow-x:auto">

| Trường thông tin       | Control | Field                                            | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                |
|:-----------------------|:--------|:-------------------------------------------------|:-----------|:---------------|:-----------------|:-------------------|:---------------------------------------------------------------------|
| Tên tổ chức công chứng | text    | tenDonVi                                         | -          | -              |                  | -                  | Tên của tổ chức hành nghề công chứng                                 |
| Sở Tư pháp             | text    | tenDonVi                                         | -          | -              |                  | -                  | Tên Sở Tư pháp quản lý (Chỉ hiển thị cột này cho người dùng cấp bộ)  |
| Trưởng văn phòng       | text    | hoDem + ten                                      | -          | -              |                  | -                  | Tên trưởng văn phòng                                                 |
| Địa chỉ trụ sở         | text    | diaChiChiTiet + diaChiTinhThanh + diaChiPhuongXa | -          | -              |                  | -                  | Địa chỉ trụ sở hiện tại: Địa chỉ - Phường/xã - Tỉnh/Thành phố        |
| Trạng thái hoạt động   | text    | trangThai                                        | -          | -              |                  | -                  | Trạng thái: Đang hoạt động, Chờ thành lập, Giải thể, … (theo entity) |

</div>

### Chức năng

<div style="overflow-x:auto">

| Tên                 | Loại            | Mô tả                                                                                                 |
|:--------------------|:----------------|:------------------------------------------------------------------------------------------------------|
| Ô tìm kiếm          | Input           | Nhập tên tổ chức công chứng để tìm kiếm                                                               |
| Biểu tượng tìm kiếm | Button          | Bấm vào thực hiện tra cứu theo thông tin đã nhập/chọn (**UC_Org_Lookup**)                             |
| Ô chọn Sở Tư pháp   | combobox search | Chọn 1 từ danh sách Sở Tư pháp                                                                        |
| Ô chọn trạng thái   | dropdown        | Chọn 1 trạng thái từ danh sách trạng thái hoạt động của tổ chức công chứng (Giống với SCR_Org_Create) |

</div>
