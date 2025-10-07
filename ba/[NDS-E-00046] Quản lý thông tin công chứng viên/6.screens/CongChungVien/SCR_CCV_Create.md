# Màn hình: Thêm mới công chứng viên
Form cho phép nhập và lưu thông tin công chứng viên mới vào hệ thống.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền thêm mới công chứng viên.
 
## Nguyên mẫu
[https://www.figma.com/design/G1GnG3ecpubkOPJjxrEiRo/CSDL.CC_V1?node-id=135-16133&t=AJ0R7XTWgx3u3lfZ-1]

## Thành phần

### Thông tin cá nhân

<div style="overflow-x:auto">

| Trường thông tin                | Control         | Field           | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                             |
|:--------------------------------|:----------------|:----------------|:-----------|:---------------|:-----------------|:-------------------|:------------------------------------------------------------------|
| Ảnh                             | upload file     | anhDaiDien      | -          | N              | -                | -                  | Upload ảnh công chứng viên, chỉ chấp nhận định dạng ảnh dưới 10MB |
| Họ và tên                       | text            | hoDem + ten     | 250        | Y              | -                | -                  | Điền họ và tên công chứng viên                                    |
| Ngày sinh                       | date            | ngaySinh        | -          | Y              | -                | -                  | **BR9.3**                                                         |
| Giới tính                       | dropdown        | gioiTinh        | -          | Y              | -                | -                  | Chọn 1 Nam/Nữ                                                     |
| Quốc tịch                       | combobox search | quocTich        | -          | Y              | Việt Nam         | Y                  | Chọn 1 từ danh mục quốc tịch                                      |
| Dân tộc                         | combobox search | danToc          | -          | N              | -                | -                  | Chọn 1 từ danh mục dân tộc                                        |
| Số điện thoại                   | text            | dienThoaiDiDong | 20         | N              | -                | -                  | **BR9.4**                                                         |
| Email                           | text            | email           | 250        | N              | -                | -                  |                                                                   |
| Số giấy tờ (CMND/CCCD/Hộ chiếu) | text            | soGiayTo        | 20         | Y              | -                | -                  | **BR9.10**                                                        |
| Ngày cấp                        | datetime        | ngayCap         | -          | Y              | -                | -                  | **BR9.3**                                                         |
| Nơi cấp                         | text            | noiCap          | 500        | Y              | -                | -                  |                                                                   |
| Địa chỉ thường trú (cũ)         | text            | diaChiCu        | 500        | N              | -                | -                  | Placeholder: Nhập địa chỉ số nhà, tổ, thôn, xóm                   |
| Tỉnh/Thành phố thường trú (cũ)  | combobox search | tinhThanhPhoCu  | -          | N              | -                | -                  | Chọn 1 từ danh mục tỉnh thành phố cũ. **BR9.7**                   |
| Phường/Xã thường trú (cũ)       | combobox search | phuongXaCu      | -          | N              | -                | -                  | Chọn 1 từ danh mục phường xã cũ. **BR9.8**                        |
| Địa chỉ thường trú (mới)        | text            | diaChi          | 500        | Y              | -                | -                  | Placeholder: Nhập địa chỉ số nhà, tổ, thôn, xóm                   |
| Tỉnh/Thành phố thường trú (mới) | combobox search | tinhThanhPho    | -          | Y              | -                | -                  | Chọn 1 từ danh mục tỉnh thành phố mới. **BR9.7**                  |
| Phường/Xã thường trú (mới)      | combobox search | phuongXa        | -          | Y              | -                | -                  | Chọn 1 từ danh mục phường xã mới. **BR9.8**                       |
| Trạng thái                      | combobox search | trangThai       | -          | Y              | Đang hành nghề   | Y                  | Chọn 1 từ danh sách lấy trong entity                              |

</div>

### Thông tin hành nghề

<div style="overflow-x:auto">

| Trường thông tin           | Control         | Field                                            | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                |
|:---------------------------|:----------------|:-------------------------------------------------|:-----------|:---------------|:-----------------|:-------------------|:---------------------------------------------------------------------|
| Tên tổ chức công chứng     | combobox search | donViId                                          | -          | Y              | -                | -                  | Chọn từ danh sách tổ chức công chứng thuộc Sở Tư pháp của người dùng |
| Địa chỉ tổ chức công chứng | text            | diaChiChiTiet + diaChiTinhThanh + diaChiPhuongXa | 500        | N              | -                | N                  | Tự động điền từ tổ chức chọn, disable                                |
| Số thẻ công chứng viên     | text            | soThe                                            | 50         | Y              | -                | -                  | Số hiệu thẻ hành nghề                                                |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên | Loại   | Mô tả                                                                  |
|:----|:-------|:-----------------------------------------------------------------------|
| Lưu | Button | Kiểm tra hợp lệ, lưu dữ liệu vào ENT_CongChungVien (**UC_CCV_Create**) |
| Hủy | Button | Hiển thị popup xác nhận hủy thao tác                                   |

</div>
