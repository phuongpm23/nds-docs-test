# Màn hình: Chi tiết tổ chức công chứng
Màn hình hiển thị chi tiết thông tin của một tổ chức hành nghề công chứng.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền xem thông tin chi tiết tổ chức công chứng.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=61-26989&t=D6KMt6aiRNAU7m7V-1]

## Thành phần

### Form hiển thị thông tin

<div style="overflow-x:auto">

| Trường thông tin       | Control | Field              | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                                   |
|:-----------------------|:--------|:-------------------|:-----------|:---------------|:-----------------|:-------------------|:----------------------------------------------------------------------------------------|
| Tên tổ chức công chứng | text    | tenToChucCongChung | -          | -              |                  | N                  | Tên của tổ chức hành nghề công chứng                                                    |
| Sở Tư pháp quản lý     | text    | soTuPhap           | -          | -              |                  | N                  | Tên Sở Tư pháp quản lý                                                                  |
| Địa chỉ                | text    | diaChi             | -          | -              |                  | N                  | Địa chỉ trụ sở chính                                                                    |
| Tỉnh/Thành phố         | text    | tinhThanhPho       | -          | -              |                  | N                  | Tỉnh/Thành phố nơi tổ chức công chứng hoạt động                                         |
| Phường/Xã              | text    | phuongXa           | -          | -              |                  | N                  | Phường/Xã thuộc địa chỉ tổ chức                                                         |
| Số điện thoại          | text    | soDienThoai        | -          | -              |                  | N                  | Thông tin số điện thoại liên hệ                                                         |
| Email                  | text    | email              | -          | -              |                  | N                  | Email liên hệ                                                                           |
| Họ và tên              | text    | hoVaTen            | -          | -              |                  | N                  | Hiển thị tên công chứng viên trưởng VP (tìm từ ENT_CongChungVien theo truongVanPhongId) |
| Số giấy tờ (CMND/CCCD/Hộ chiếu) | text     | soGiayTo       | -          | Y              | -                  | Thông tin giấy tờ định danh |
| Giới tính                       | text     | gioiTinh       | -          | -              | -                  | Giới tính                   |
| Ngày sinh                       | datetime | ngaySinh       | -          | -              | -                  | Ngày sinh                   |
| Số thẻ công chứng viên     | text    | soThe                 | -          | -              | -                  | Số hiệu thẻ hành nghề             |
| Trạng thái                 | text    | trangThai             | -          | -              | -                  | Trạng thái hoạt động của công chứng viên              |
| Trạng thái hoạt động   | dropdown | trangThai          | -          | -              | -                | N                  | Trạng thái: Đang hoạt động, Chờ thành lập, Giải thể, …                    |
| Ngày tạo               | datetime | createdAt          | -          | -              | -                | N                  | Ngày bản ghi được tạo                                                     |
| Ngày cập nhật          | datetime | updatedAt          | -          | -              | -                | N                  | Ngày cập nhật gần nhất                                                    |

</div>

### Chức năng
<div style="overflow-x:auto">

| Tên       | Loại   | Mô tả                                                                                       |
|:----------|:-------|:--------------------------------------------------------------------------------------------|
| Đóng      | Button | Đóng màn hình chi tiết, về trang danh sách                                                                         |
| Chỉnh sửa | Button | Mở form chỉnh sửa tổ chức công chứng (SCR_Org_Update), chỉ hiển thị khi người dùng có quyền |

</div>
