# Màn hình: Lịch sử cập nhật công chứng viên
Popup hiển thị lịch sử cập nhật thông tin công chứng viên.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem lịch sử cập nhật công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/G1GnG3ecpubkOPJjxrEiRo/CSDL.CC_V1?node-id=135-16371&t=AJ0R7XTWgx3u3lfZ-1]

## Thành phần

### Bảng lịch sử

<div style="overflow-x:auto">

| Trường thông tin   | Control  | Field                 | Bắt buộc (Y/N) | Mô tả                            |
|:-------------------|:---------|:----------------------|:---------------|:---------------------------------|
| Thời gian          | datetime | updatedAt             | -              | Thời điểm thực hiện cập nhật     |
| Người thực hiện    | text     | updatedBy             | -              | Người thực hiện thay đổi         |
| Thao tác           | text     | thaoTac               | -              | Cập nhật                         |
| Thông tin thay đổi | text     | truongThongtinCapNhat | -              | Tên trường dữ liệu được thay đổi |
| Giá trị cũ         | text     | giaTriCu              | -              | Giá trị trước khi thay đổi       |
| Giá trị mới        | text     | giaTriMoi             | -              | Giá trị sau khi thay đổi         |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên             | Loại   | Mô tả                                                                    |
|:----------------|:-------|:-------------------------------------------------------------------------|
| Quay lại / Đóng | Button | Đóng popup, trở về màn hình danh sách công chứng viên (**SCR_CCV_List**) |

</div>

