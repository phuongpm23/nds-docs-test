# Màn hình: Thêm mới công chứng viên
Form cho phép nhập và lưu thông tin công chứng viên mới vào hệ thống.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền thêm mới công chứng viên.
 
## Nguyên mẫu
[https://www.figma.com/design/G1GnG3ecpubkOPJjxrEiRo/CSDL.CC_V1?node-id=135-16133&t=AJ0R7XTWgx3u3lfZ-1]

## Thành phần

### Thông tin cá nhân

<div style="overflow-x:auto">

| Trường thông tin                | Control  | Field          | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                          |
|:--------------------------------|:---------|:---------------|:-----------|:---------------|:-----------------|:-------------------|:-----------------------------------------------|
| Ảnh                       | upload file     | anhDaiDien        | -        | N              | -                | Y                  | Upload ảnh công chứng viên, chỉ chấp nhận định dạng ảnh dưới 10MB                 |
| Họ và tên đệm                       | text     | hoDem        | 250        | Y              | -                | Y                  | Điền họ và tên đệm công chứng viên                 |
| Tên                       | text     | ten        | 250        | Y              | -                | Y                  | Điền tên công chứng viên                 |
| Ngày sinh                       | date     | ngaySinh       | -          | Y              | -                | Y                  | **BR9.3**                                      |
| Giới tính                       | dropdown | gioiTinh       | -          | Y              | -                | Y                  | Nam/Nữ                                         |
| Quốc tịch                       | text     | quocTich       | 20         | Y              | Việt Nam         | N                  |                                                |
| Dân tộc                         | dropdown | danToc         | 20         | N              | -                | Y                  | Chọn từ danh mục dân tộc                       |
| Số điện thoại                   | text     | dienThoaiDiDong    | 20         | N              | -                | Y                  | **BR9.4**                                      |
| Email                           | text     | email          | 250        | N              | -                | Y                  |                                                |
| Số giấy tờ (CMND/CCCD/Hộ chiếu) | text     | soGiayTo       | 50         | Y              | -                | Y                  | **BR9.10**                                     |
| Ngày cấp                        | datetime | ngayCap        | -          | Y              | -                | Y                  | **BR9.3**                                      |
| Nơi cấp                         | text     | noiCap         | 500        | Y              | -                | Y                  |                                                |
| Địa chỉ thường trú (cũ)         | text     | diaChiCu       | 500        | N              | -                | Y                  |                                                |
| Tỉnh/Thành phố thường trú (cũ)  | dropdown | tinhThanhPhoCu | 250        | N              | -                | Y                  | Chọn từ danh mục tỉnh thành phố cũ. **BR9.7**  |
| Phường/Xã thường trú (cũ)       | dropdown | phuongXaCu     | 250        | N              | -                | Y                  | Chọn từ danh mục phường xã cũ. **BR9.8**       |
| Địa chỉ thường trú              | text     | diaChi         | 500        | Y              | -                | Y                  |                                                |
| Tỉnh/Thành phố thường trú       | dropdown | tinhThanhPho   | 250        | Y              | -                | Y                  | Chọn từ danh mục tỉnh thành phố mới. **BR9.7** |
| Phường/Xã thường trú            | dropdown | phuongXa       | 250        | Y              | -                | Y                  | Chọn từ danh mục phờng xã mới. **BR9.8**       |
| Trạng thái                      | dropdown | trangThai      | 50         | Y              | Đang hành nghề   | Y                  | Lấy trong entity                               |

</div>

### Thông tin hành nghề

<div style="overflow-x:auto">

| Trường thông tin           | Control  | Field                            | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                |
|:---------------------------|:---------|:---------------------------------|:-----------|:---------------|:-----------------|:-------------------|:---------------------------------------------------------------------|
| Tên tổ chức công chứng     | dropdown | donViId               | 250        | Y              | -                | Y                  | Chọn từ danh sách tổ chức công chứng thuộc Sở Tư pháp của người dùng |
| Địa chỉ tổ chức công chứng | text     | diaChiChiTiet + diaChiTinhThanh + diaChiPhuongXa | 500        | N              | -                | N                  | Tự động điền từ tổ chức chọn, disable                                |
| Số thẻ công chứng viên     | text     | soThe                            | 50         | Y              | -                | Y                  | Số hiệu thẻ hành nghề                                                |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên  | Loại   | Mô tả                                                                  |
|:-----|:-------|:-----------------------------------------------------------------------|
| Lưu  | Button | Kiểm tra hợp lệ, lưu dữ liệu vào ENT_CongChungVien (**UC_CCV_Create**) |
| Đóng | Button | Hiển thị popup xác nhận hủy thao tác                                   |

</div>
