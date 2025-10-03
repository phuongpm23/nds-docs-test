# Màn hình: Chi tiết công chứng viên
Hiển thị đầy đủ hồ sơ cá nhân,thông tin hành nghề của công chứng viên.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=31-34764&t=qhcu7sCD1S2A6kb5-1]
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=44-16244&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Thông tin chung (ENT_CongChungVien)

<div style="overflow-x:auto">

| Trường thông tin                | Control  | Field            | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                                    |
|:--------------------------------|:---------|:-----------------|:-----------|:---------------|:-------------------|:---------------------------------------------------------|
| Ảnh công chứng viên             | image    | anhCongChungVien | -          | -              | -                  | Ảnh công chứng viên (hiển thị ảnh mặc định nếu không có) |
| Họ và tên                       | text     | hoVaTen          | -          | -              | -                  | Họ tên công chứng viên                                   |
| Ngày sinh                       | datetime | ngaySinh         | -          | -              | -                  | Ngày sinh                                                |
| Giới tính                       | text     | gioiTinh         | -          | -              | -                  | Giới tính                                                |
| Số điện thoại                   | text     | soDienThoai      | -          | -              | -                  | Số điện thoại liên hệ                                    |
| Quốc tịch                       | text     | quocTich         | -          | -              | -                  | Quốc tịch                                                |
| Dân tộc                         | text     | danToc           | -          | -              | -                  | Dân tộc                                                  |
| Email                           | text     | email            | -          | -              | -                  | Email                                                    |
| Số giấy tờ (CMND/CCCD/Hộ chiếu) | text     | soGiayTo         | -          | Y              | -                  | Thông tin giấy tờ định danh                              |
| Ngày cấp                        | datetime | ngayCap          | -          | -              | -                  | Ngày cấp giấy tờ định danh                               |
| Nơi cấp                         | text     | noiCap           | -          | -              | -                  | Nơi cấp giấy tờ định danh                                |
| Địa chỉ thường trú (cũ)         | text     | diaChiCu         | -          | -              | -                  | Địa chỉ thường trú                                       |
| Tỉnh/Thành phố thường trú (cũ)  | text     | tinhThanhPhoCu   | -          | -              | -                  | Thông tin cũ                                             |
| Phường/Xã thường trú (cũ)       | text     | phuongXaCu       | -          | -              | -                  | Thông tin cũ                                             |
| Địa chỉ thường trú              | text     | diaChiCu         | -          | -              | -                  | Địa chỉ thường trú                                       |
| Tỉnh/Thành phố thường trú (mới) | text     | tinhThanhPho     | -          | -              | -                  | Thông tin hiện tại                                       |
| Phường/Xã thường trú (mới)      | text     | phuongXa         | -          | -              | -                  | Thông tin hiện tại                                       |

</div>

### Thông tin tổ chức hành nghề (ENT_CongChungVien, ENT_ToChucCongChung)

<div style="overflow-x:auto">

| Trường thông tin           | Control | Field                 | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                             |
|:---------------------------|:--------|:----------------------|:-----------|:---------------|:-------------------|:----------------------------------|
| Tên tổ chức công chứng     | text    | tenToChucCongChung    | -          | -              | -                  | Tổ chức công chứng đang hành nghề |
| Địa chỉ tổ chức công chứng | text    | diaChiToChucCongChung | -          | -              | -                  | Địa chỉ tổ chức công chứng        |
| Số thẻ công chứng viên     | text    | soThe                 | -          | -              | -                  | Số hiệu thẻ hành nghề             |
| Trạng thái                 | text    | trangThai             | -          | -              | -                  | Trạng thái hoạt động              |

</div>

### Thông tin chứng chỉ hành nghề (ENT_ChungChiHanhNghe) *(nếu có quyền)*

<div style="overflow-x:auto">

| Trường thông tin | Control  | Field         | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                                   |
|:-----------------|:---------|:--------------|:-----------|:---------------|:-------------------|:--------------------------------------------------------|
| Số chứng chỉ     | text     | licenseNo     | -          | -              | -                  | Hiển thị mã số chứng chỉ hành nghề                      |
| Ngày cấp         | datetime | issueDate     | -          | -              | -                  | Hiển thị ngày cấp chứng chỉ                             |
| Nơi cấp          | text     | issuePlace    | -          | -              | -                  | Hiển thị nơi cấp chứng chỉ                              |
| Ngày hiệu lực    | datetime | effectiveDate | -          | -              | -                  | Hiển thị ngày hiệu lực                                  |
| Ngày hết hạn     | datetime | expiryDate    | -          | -              | -                  | Hiển thị ngày hết hạn                                   |
| Đơn vị cấp       | text     | authority     | -          | -              | -                  | Hiển thị cơ quan cấp chứng chỉ                          |
| Trạng thái       | text     | status        | -          | -              | -                  | Hiển thị trạng thái chứng chỉ                           |
| File đính kèm    | file     | attachment    | -          | -              | -                  | Link file chứng chỉ, click vào mở tab mới hiển thị file |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên                        | Loại   | Mô tả                                                                            |
|:---------------------------|:-------|:---------------------------------------------------------------------------------|
| Quay lại / Đóng            | Button | Trở về màn hình danh sách công chứng viên (**SCR_CCV_List**)                     |
| Chỉnh sửa                  | Button | Mở màn hình chỉnh sửa thông tin công chứng viên (**UC_CCV_Update**)              |
| Lịch sử cập nhật chứng chỉ | Button | Xem lịch sử cập nhật chứng chỉ (**UC_ChungChi_History**) (Hiển thị nếu có quyền) |

</div>
