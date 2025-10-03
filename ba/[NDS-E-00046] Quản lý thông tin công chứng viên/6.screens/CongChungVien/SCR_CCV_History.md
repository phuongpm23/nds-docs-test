# Màn hình: Lịch sử cập nhật công chứng viên
Popup hiển thị lịch sử cập nhật thông tin công chứng viên.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem lịch sử cập nhật công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=32-35913&t=qhcu7sCD1S2A6kb5-1]

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

