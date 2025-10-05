# Màn hình: Thêm mới công chứng viên
Form cho phép nhập và lưu thông tin công chứng viên mới vào hệ thống.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền thêm mới công chứng viên.
 
## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=31-17112&t=qhcu7sCD1S2A6kb5-1]
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=31-21596&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Thông tin cá nhân

<div style="overflow-x:auto">

| Trường thông tin                | Control  | Field          | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                          |
|:--------------------------------|:---------|:---------------|:-----------|:---------------|:-----------------|:-------------------|:-----------------------------------------------|
| Họ và tên                       | text     | hoVaTen        | 250        | Y              | -                | Y                  | Điền họ và tên công chứng viên                 |
| Ngày sinh                       | date     | ngaySinh       | -          | Y              | -                | Y                  | **BR9.3**                                      |
| Giới tính                       | dropdown | gioiTinh       | -          | Y              | -                | Y                  | Nam/Nữ                                         |
| Quốc tịch                       | text     | quocTich       | 20         | Y              | Việt Nam         | N                  |                                                |
| Dân tộc                         | dropdown | danToc         | 20         | N              | -                | Y                  | Chọn từ danh mục dân tộc                       |
| Số điện thoại                   | text     | soDienThoai    | 20         | N              | -                | Y                  | **BR9.4**                                      |
| Email                           | text     | email          | 250        | N              | -                | Y                  |                                                |
| Loại giấy tờ                    | dropdown | loaiGiayTo     | 50         | Y              | -                | Y                  | Chọn CMND/Căn cước/Căn cước công dân/Hộ chiếu  |
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

| Trường thông tin           | Control  | Field                 | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                |
|:---------------------------|:---------|:----------------------|:-----------|:---------------|:-----------------|:-------------------|:---------------------------------------------------------------------|
| Tên tổ chức công chứng     | dropdown | tenToChucCongChung    | 250        | Y              | -                | Y                  | Chọn từ danh sách tổ chức công chứng thuộc Sở Tư pháp của người dùng |
| Địa chỉ tổ chức công chứng | text     | diaChiToChucCongChung | 500        | N              | -                | N                  | Tự động điền từ tổ chức chọn                                         |
| Số thẻ công chứng viên     | text     | soThe                 | 50         | Y              | -                | Y                  | Số hiệu thẻ hành nghề                                                |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên   | Loại   | Mô tả                                                         |
|:------|:-------|:--------------------------------------------------------------|
| Lưu   | Button | Kiểm tra hợp lệ, lưu dữ liệu vào ENT_CongChungVien (**UC_CCV_Create**) |
| Hủy   | Button | Đóng form, không lưu dữ liệu                                  |
| Reset | Button | Xóa dữ liệu đang nhập và trả về trạng thái ban đầu            |

</div>
