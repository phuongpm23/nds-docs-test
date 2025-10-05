# Màn hình: Chỉnh sửa tổ chức công chứng
Form cho phép chỉnh sửa thông tin một tổ chức hành nghề công chứng.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền chỉnh sửa tổ chức công chứng.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=61-25542&t=D6KMt6aiRNAU7m7V-1]

## Thành phần

### Form chỉnh sửa thông tin
- Đổ ra dữ liệu đã lưu
<div style="overflow-x:auto">

| Trường thông tin       | Control  | Field              | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                                                                                                                                                           |
|:-----------------------|:---------|:-------------------|:-----------|:---------------|:-----------------|:-------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tên tổ chức công chứng | text     | tenToChucCongChung | 250        | Y              |                  | Y                  | Điền tên của tổ chức hành nghề công chứng                                                                                                                                                                       |
| Sở Tư pháp quản lý     | text     | soTuPhap           | 250        | Y              |                  | N                  | Tự động chọn Sở Tư pháp giống với người dùng. Disable, không cho phép thay đổi                                                                                                                                  |
| Địa chỉ                | text     | diaChi             | 500        | Y              |                  | Y                  | Điền địa chỉ trụ sở chính                                                                                                                                                                                       |
| Tỉnh/Thành phố         | dropdown | tinhThanhPho       | 250        | Y              |                  | Y                  | Chọn từ danh mục tỉnh/thành phố mới, **BR9.7**                                                                                                                                                                  |
| Phường/Xã              | dropdown | phuongXa           | 250        | Y              |                  | Y                  | Chọn từ danh mục phường xã mới **BR9.8**,                                                                                                                                                                       |
| Số điện thoại          | text     | soDienThoai        | 10         | N              |                  | Y                  | **BR9.1**,**BR9.4**                                                                                                                                                                                             |
| Email                  | text     | email              | 255        | N              |                  | Y                  | **BR9.9**                                                                                                                                                                                                       |
| Trưởng văn phòng       | dropdown | truongVanPhongId   | 50         | Y              |                  | Y                  | Click vào cho phép chọn công chứng viên từ danh sách (entity CongChungVien), cho phép điền và tìm kiếm theo số giấy tờ/tên công chứng viên, danh sách hiển thị theo cấu trúc "Số giấy tờ - Tên công chứng viên" |
| Trạng thái hoạt động   | dropdown | trangThai          | 50         | Y              | Đang hoạt động   | Y                  | Chọn trạng thái hoạt động theo danh sách đã liệt kê trong entity                                                                                                                                                |

</div>

### Chức năng
<div style="overflow-x:auto">

| Tên | Loại   | Mô tả                                                                                                 |
|:----|:-------|:------------------------------------------------------------------------------------------------------|
| Lưu | Button | Lưu dữ liệu nhập vào. Nếu hợp lệ thì cập nhật dữ liệu và đóng màn hình. Chi tiết trong **UC_Org_Update** |
| Hủy | Button | Hủy thao tác, đóng màn hình mà không lưu dữ liệu, về trang danh sách                                                         |
