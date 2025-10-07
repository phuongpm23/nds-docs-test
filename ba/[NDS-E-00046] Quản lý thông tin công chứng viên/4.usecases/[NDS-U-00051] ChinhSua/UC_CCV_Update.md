# Use Case: UC_CCV_Update (Chỉnh sửa công chứng viên)

## User Story
- Với vai trò là **Chuyên viên STP**, tôi muốn có thể Chỉnh sửa công chứng viên, để đảm bảo dữ liệu công chứng viên luôn đầy đủ và chính xác.

## Acceptance Criteria
- Hệ thống hiển thị form Chỉnh sửa công chứng viên và điền sẵn thông tin đã lưu.
- Hệ thống kiểm tra dữ liệu hợp lệ trước khi lưu thông tin công chứng viên.
- Nếu dữ liệu hợp lệ, hệ thống lưu công chứng viên mới vào danh sách và hiển thị thông báo thành công.
- Nếu dữ liệu không hợp lệ, hiển thị thông báo lỗi cụ thể (VD: "Số thẻ đã tồn tại").
- Người dùng có thể hủy thao tác Chỉnh sửa.

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Chỉnh sửa công chứng viên".

## Luồng chính
1. Người dùng chọn chức năng **Chỉnh sửa công chứng viên** từ danh sách (**SCR_CCV_List**) hoặc màn hình chi tiết (**SCR_CCV_Detail**).
2. Hệ thống hiển thị form Chỉnh sửa (**SCR_CCV_Update**).
3. Người dùng nhập các thông tin cần thiết.
4. Người dùng bấm nút **Lưu**.
5. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Nếu hợp lệ: Cập nhật dữ liệu vào bảng **CongChungVien**
   - Thông báo "Chỉnh sửa công chứng viên thành công".
   - Mở màn hình chi tiết công chứng viên vừa cập nhật (**UC_CCV_Detail**).
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Hiển thị popup xác nhận hủy thao tác. Nếu xác nhận, form đóng, không lưu dữ liệu, chuyển về màn danh sách. Nếu hủy xác nhận, đóng popup xác nhận
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Nếu Ngày Sinh/Ngày cấp giấy tờ > Ngày hôm nay: thông báo lỗi "Thông tin không hợp lệ"
- Nếu chưa điền thông tin bắt buộc, hiển thị thông báo yêu cầu điền thông tin bắt buộc
- Nếu sai định dạng thông tin, hiển thị thông báo lỗi "Thông tin không hợp lệ"
- Nếu số thẻ bị trùng với công chứng viên khác trong hệ thống, hệ thống thông báo lỗi "Số thẻ đã tồn tại". 
- Nếu số giấy tờ cá nhân bị trùng với công chứng viên khác trong hệ thống, hệ thống thông báo lỗi "Số CCCD/CMND/Hộ chiếu đã tồn tại". 

## Hậu điều kiện
- Nếu thành công: Công chứng viên được cập nhật thông tin.
- Nếu thất bại: Không có dữ liệu mới nào được thêm.

## Liên kết
- Activity Diagram: [AD_CCV_Update.puml]
- Form liên quan: [SCR_CCV_Update.md]
- Entity liên quan: **ENT_CongChungVien**, **ENT_ToChucCongChung**
