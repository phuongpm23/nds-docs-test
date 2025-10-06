# Màn hình: Tra cứu công chứng viên
Form cho phép người dùng nhập tiêu chí tra cứu và hiển thị danh sách công chứng viên phù hợp.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền tra cứu thông tin công chứng viên và chứng chỉ hành nghề.

## Nguyên mẫu
[]

## Thành phần

### Form tra cứu

<div style="overflow-x:auto">

| Trường thông tin             | Control  | Field             | Max length | Bắt buộc (Y/N) | Mô tả                                                                                                                         |
|:-----------------------------|:---------|:------------------|:-----------|:---------------|:------------------------------------------------------------------------------------------------------------------------------|
| Ô điền thông tin tra cứu     | text     | hoVaTen           | -          | -              | Hiển thị khi có quyền tra cứu công chứng viên, placeholder: "Điền tên công chứng viên, số thẻ CCV hoặc số chứng chỉ hành nghề |
| Trạng thái                   | dropdown | trangThai         | -          | -              | Hiển thị khi có quyền tra cứu công chứng viên,Lọc theo trạng thái hành nghề trong entity                     |
| Sở Tư Pháp                   | dropdown | soTuPhap          | -          | -              | Hiển thị khi có quyền tra cứu công chứng viên, Lấy từ danh sách Sở Tư pháp                                                    |
| Tổ chức hành nghề công chứng | dropdown | toChucCongChungID | -          | -              | Hiển thị khi có quyền tra cứu công chứng viên, Danh sách hiển thị theo Sở Tư pháp đã chọn                                     |

</div>

### Bảng kết quả

<div style="overflow-x:auto">

| Trường thông tin             | Control | Field                                            | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                                         |
|:-----------------------------|:--------|:-------------------------------------------------|:-----------|:---------------|:-------------------|:--------------------------------------------------------------|
| Họ và tên                    | text    | hoDem + ten                                      | -          | -              | -                  | Họ và tên công chứng viên                                     |
| Số thẻ CCV                   | text    | soThe                                            | -          | -              | -                  | Số hiệu thẻ hành nghề công chứng viên                         |
| Số chứng chỉ hành nghề       | text    | soChungChi                                       | -          | -              | -                  | Bấm vào hiển thị popup chi tiết chứng chỉ                     |
| Tổ chức công chứng hành nghề | text    | tenDonVi                                         | -          | -              | -                  | Tổ chức công chứng đang hành nghề                             |
| Địa chỉ trụ sở               | text    | diaChiChiTiet + diaChiTinhThanh + diaChiPhuongXa | -          | -              | -                  | Hiển thị địa chỉ chi tiết của tổ chức + Phường xã, Tỉnh/Thành |
| Trạng thái hoạt động         | text    | trangThai                                        | -          | -              | -                  | Trạng thái công chứng viên                                    |

</div>

### Popup chi tiết chứng chỉ hành nghề

<div style="overflow-x:auto">

| Trường thông tin | Control  | Field       | Max length | Bắt buộc (Y/N) | Mô tả                       |
|:-----------------|:---------|:------------|:-----------|:---------------|:----------------------------|
| Số chứng chỉ     | text     | soChungChi  | -          | -              | Mã số chứng chỉ hành nghề   |
| Ngày cấp         | datetime | ngayCap     | -          | -              | Ngày cấp chứng chỉ          |
| Nơi cấp          | text     | noiCap      | -          | -              | Nơi cấp chứng chỉ           |
| Ngày hiệu lực    | datetime | ngayHieuLuc | -          | -              | Ngày bắt đầu có hiệu lực    |
| Ngày hết hạn     | datetime | ngayHetHan  | -          | -              | Ngày chứng chỉ hết hiệu lực |
| Đơn vị cấp       | text     | tenDonVi    | -          | -              | Cơ quan cấp chứng chỉ       |
| Trạng thái       | text     | trangThai   | -          | -              | Trạng thái chứng chỉ        |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên        | Loại    | Mô tả                                                              |
|:-----------|:--------|:-------------------------------------------------------------------|
| Tra cứu    | Button  | Thực hiện tra cứu theo tiêu chí đã nhập                            |
| Phân trang | Control | Hiển thị danh sách theo trang (10 bản ghi/trang)                   |
| Đóng popup | Button  | Đóng popup chi tiết chứng chỉ hành nghề, quay lại màn hình tra cứu |
| Reset      | Button  | Reset màn hình tra cứu                                             |

</div>
