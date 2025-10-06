# Use Case: UC_BLQ_Update (Chỉnh sửa bên liên quan)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể chỉnh sửa thông tin bên liên quan (cá nhân/tổ chức) để cập nhật các thay đổi hoặc sửa lỗi thông tin trong giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị form chỉnh sửa thông tin bên liên quan với dữ liệu đã có.
- Hệ thống cho phép chỉnh sửa thông tin chi tiết về bên liên quan.
- Hệ thống kiểm tra tính hợp lệ của dữ liệu trước khi lưu.
- Hệ thống ghi nhận lịch sử các thay đổi trên thông tin bên liên quan.
- Hệ thống cho phép thay đổi vai trò của bên liên quan trong giao dịch.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Chỉnh sửa hồ sơ công chứng".
- Bên liên quan tồn tại trong hồ sơ công chứng.
- Người dùng đang trong quá trình chỉnh sửa hồ sơ công chứng.

## Luồng chính
1. Người dùng chọn chức năng **Chỉnh sửa** bên liên quan từ tab "Bên tham gia" trong form hồ sơ công chứng (**UC_HSCC_Update**).
2. Hệ thống hiển thị form chỉnh sửa thông tin bên liên quan với các trường dữ liệu đã có:
   
   **Thông tin chung:**
   - Loại bên liên quan (Cá nhân/Tổ chức) - không thể thay đổi
   - Vai trò trong giao dịch (Bên A/Bên B/Bên liên quan khác) - có thể thay đổi
   
   **Thông tin cá nhân (hiển thị khi loại là Cá nhân):**
   - Họ và tên - có thể chỉnh sửa
   - Ngày sinh - có thể chỉnh sửa
   - Số CMND/CCCD - có thể chỉnh sửa
   - Ngày cấp CMND/CCCD - có thể chỉnh sửa
   - Nơi cấp CMND/CCCD - có thể chỉnh sửa
   - Số điện thoại - có thể chỉnh sửa
   - Email - có thể chỉnh sửa
   - Địa chỉ thường trú - có thể chỉnh sửa
   - Địa chỉ hiện tại - có thể chỉnh sửa
   
   **Thông tin tổ chức (hiển thị khi loại là Tổ chức):**
   - Tên tổ chức - có thể chỉnh sửa
   - Mã số thuế - có thể chỉnh sửa
   - Địa chỉ trụ sở - có thể chỉnh sửa
   - Số điện thoại - có thể chỉnh sửa
   - Email - có thể chỉnh sửa
   - Người đại diện theo pháp luật - có thể chỉnh sửa
   - Chức vụ người đại diện - có thể chỉnh sửa
   
3. Người dùng thực hiện các thay đổi cần thiết.
4. Người dùng bấm nút **Lưu**.
5. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Kiểm tra các trường bắt buộc đã được nhập
   - Kiểm tra định dạng dữ liệu (email, số điện thoại, CMND/CCCD, mã số thuế)
   - Kiểm tra logic nghiệp vụ
6. Nếu dữ liệu hợp lệ:
   - Hệ thống ghi nhận các thay đổi vào lịch sử
   - Cập nhật thông tin vào **ENT_NguoiThamGiaGiaoDichCaNhan** (đối với cá nhân) hoặc **ENT_NguoiThamGiaGiaoDichToChuc** (đối với tổ chức)
   - Hiển thị thông báo "Cập nhật thông tin bên liên quan thành công"
   - Cập nhật danh sách bên liên quan trong tab "Bên tham gia" của hồ sơ công chứng
   - Đóng form chỉnh sửa thông tin bên liên quan
7. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Nếu chưa điền thông tin bắt buộc, hiển thị thông báo yêu cầu điền thông tin bắt buộc.
- Nếu sai định dạng thông tin, hiển thị thông báo lỗi "Thông tin không hợp lệ".
- Nếu thông tin bên liên quan bị trùng với bên liên quan khác trong hồ sơ, hệ thống thông báo lỗi "Thông tin này đã tồn tại cho bên liên quan khác trong hồ sơ".

## Hậu điều kiện
- Nếu thành công: Thông tin bên liên quan được cập nhật.
- Nếu thất bại: Không có thay đổi nào được lưu.

## Liên kết
- Form liên quan: [SCR_BLQ_Update.md]
- Entity liên quan: ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_LichSuCapNhatBenLienQuan
- Usecase gọi đến: UC_HSCC_Update