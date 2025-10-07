# Màn hình: Chi tiết công chứng viên
Hiển thị đầy đủ hồ sơ cá nhân,thông tin hành nghề của công chứng viên.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/G1GnG3ecpubkOPJjxrEiRo/CSDL.CC_V1?node-id=135-16264&t=AJ0R7XTWgx3u3lfZ-1]

## Thành phần

### Thông tin chung (ENT_CongChungVien)

<div style="overflow-x:auto">

| Trường thông tin                | Control  | Field           | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                                    |
|:--------------------------------|:---------|:----------------|:-----------|:---------------|:-------------------|:---------------------------------------------------------|
| Ảnh công chứng viên             | image    | anhDaiDien      | -          | -              | -                  | Ảnh công chứng viên (hiển thị ảnh mặc định nếu không có) |
| Họ và tên                       | text     | hoDem + ten     | -          | -              | -                  | Họ tên công chứng viên                                   |
| Ngày sinh                       | datetime | ngaySinh        | -          | -              | -                  | Ngày sinh                                                |
| Giới tính                       | text     | gioiTinh        | -          | -              | -                  | Giới tính                                                |
| Số điện thoại                   | text     | dienThoaiDiDong | -          | -              | -                  | Số điện thoại liên hệ                                    |
| Quốc tịch                       | text     | quocTich        | -          | -              | -                  | Quốc tịch                                                |
| Dân tộc                         | text     | danToc          | -          | -              | -                  | Dân tộc                                                  |
| Email                           | text     | email           | -          | -              | -                  | Email                                                    |
| Số giấy tờ (CMND/CCCD/Hộ chiếu) | text     | soGiayTo        | -          | -              | -                  | Thông tin giấy tờ định danh                              |
| Ngày cấp                        | datetime | ngayCap         | -          | -              | -                  | Ngày cấp giấy tờ định danh                               |
| Nơi cấp                         | text     | noiCap          | -          | -              | -                  | Nơi cấp giấy tờ định danh                                |
| Địa chỉ thường trú (cũ)         | text     | diaChiCu        | -          | -              | -                  | Địa chỉ thường trú                                       |
| Tỉnh/Thành phố thường trú (cũ)  | text     | tinhThanhPhoCu  | -          | -              | -                  | Thông tin cũ                                             |
| Phường/Xã thường trú (cũ)       | text     | phuongXaCu      | -          | -              | -                  | Thông tin cũ                                             |
| Địa chỉ thường trú              | text     | diaChiCu        | -          | -              | -                  | Địa chỉ thường trú                                       |
| Tỉnh/Thành phố thường trú (mới) | text     | tinhThanhPho    | -          | -              | -                  | Thông tin hiện tại                                       |
| Phường/Xã thường trú (mới)      | text     | phuongXa        | -          | -              | -                  | Thông tin hiện tại                                       |

</div>

### Thông tin tổ chức hành nghề (ENT_CongChungVien, ENT_ToChucCongChung)

<div style="overflow-x:auto">

| Trường thông tin           | Control | Field                                            | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                             |
|:---------------------------|:--------|:-------------------------------------------------|:-----------|:---------------|:-------------------|:----------------------------------|
| Tên tổ chức công chứng     | text    | tenDonVi                                         | -          | -              | -                  | Tổ chức công chứng đang hành nghề |
| Địa chỉ tổ chức công chứng | text    | diaChiChiTiet + diaChiPhuongXa + diaChiTinhThanh | -          | -              | -                  | Địa chỉ tổ chức công chứng        |
| Số thẻ công chứng viên     | text    | soThe                                            | -          | -              | -                  | Số hiệu thẻ hành nghề             |
| Trạng thái                 | text    | trangThai                                        | -          | -              | -                  | Trạng thái hoạt động              |

</div>

### Thông tin chứng chỉ hành nghề (ENT_ChungChiHanhNghe) *(nếu có quyền)*

<div style="overflow-x:auto">

| Trường thông tin | Control  | Field       | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                          |
|:-----------------|:---------|:------------|:-----------|:---------------|:-------------------|:-----------------------------------------------|
| Số chứng chỉ     | text     | soChungChi  | -          | -              | -                  | Hiển thị mã số chứng chỉ hành nghề             |
| Ngày cấp         | datetime | ngayCap     | -          | -              | -                  | Hiển thị ngày cấp chứng chỉ                    |
| Nơi cấp          | text     | noiCap      | -          | -              | -                  | Hiển thị nơi cấp chứng chỉ                     |
| Ngày hiệu lực    | datetime | ngayHieuLuc | -          | -              | -                  | Hiển thị ngày hiệu lực                         |
| Ngày hết hạn     | datetime | ngayHetHan  | -          | -              | -                  | Hiển thị ngày hết hạn                          |
| Đơn vị cấp       | text     | donViCap    | -          | -              | -                  | Hiển thị cơ quan cấp chứng chỉ                 |
| Trạng thái       | text     | trangThai   | -          | -              | -                  | Hiển thị trạng thái chứng chỉ                  |
| File đính kèm    | file     | fileDinhKem | -          | -              | -                  | Link file chứng chỉ, click vào mở preview file |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên                        | Loại   | Mô tả                                                                                  |
|:---------------------------|:-------|:---------------------------------------------------------------------------------------|
| Quay lại / Đóng            | Button | Trở về màn hình danh sách công chứng viên (**SCR_CCV_List**)                           |
| Chỉnh sửa                  | Button | Mở màn hình chỉnh sửa thông tin công chứng viên (**UC_CCV_Update**)                    |
| Lịch sử cập nhật chứng chỉ | Button | Hiển thị lịch sử cập nhật chứng chỉ (**UC_ChungChi_History**) (Hiển thị nếu có quyền)  |
| Lịch sử cập nhật           | Button | Hiển thị lịch sử cập nhật công chứng viên (**UC_CCV_History**) (Hiển thị nếu có quyền) |

</div>
