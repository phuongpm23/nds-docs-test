# Use Case: UC_BLQ_Create (Thêm mới bên liên quan)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể thêm mới thông tin bên liên quan (cá nhân/tổ chức) để ghi nhận các bên tham gia trong giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị form thêm mới bên liên quan.
- Hệ thống cho phép chọn loại bên liên quan (cá nhân/tổ chức).
- Hệ thống cho phép nhập thông tin chi tiết về bên liên quan.
- Hệ thống kiểm tra tính hợp lệ của dữ liệu trước khi lưu.
- Hệ thống hỗ trợ tra cứu thông tin bên liên quan đã có trong hệ thống.
- Hệ thống cho phép xác định vai trò của bên liên quan trong giao dịch.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Thêm mới hồ sơ công chứng" hoặc "Chỉnh sửa hồ sơ công chứng".
- Người dùng đang trong quá trình tạo mới hoặc chỉnh sửa hồ sơ công chứng.

## Luồng chính
1. Người dùng chọn chức năng **Thêm mới bên liên quan** từ tab "Bên tham gia" trong form hồ sơ công chứng (**UC_HSCC_Create** hoặc **UC_HSCC_Update**).
2. Hệ thống hiển thị form thêm mới bên liên quan với các trường:
   
   **Thông tin chung:**
   - Loại bên liên quan (Cá nhân/Tổ chức) - bắt buộc
   - Vai trò trong giao dịch (Bên A/Bên B/Bên liên quan khác) - bắt buộc
   
   **Thông tin cá nhân (hiển thị khi chọn loại là Cá nhân):**
   - Họ và tên - bắt buộc
   - Ngày sinh
   - Số CMND/CCCD - bắt buộc
   - Ngày cấp CMND/CCCD
   - Nơi cấp CMND/CCCD
   - Số điện thoại
   - Email
   - Địa chỉ thường trú
   - Địa chỉ hiện tại
   
   **Thông tin tổ chức (hiển thị khi chọn loại là Tổ chức):**
   - Tên tổ chức - bắt buộc
   - Mã số thuế - bắt buộc
   - Địa chỉ trụ sở
   - Số điện thoại
   - Email
   - Người đại diện theo pháp luật
   - Chức vụ người đại diện
   
3. Người dùng nhập thông tin vào các trường tương ứng.
4. Người dùng có thể chọn **Tra cứu** để kiểm tra thông tin bên liên quan đã tồn tại trong hệ thống.
5. Người dùng bấm nút **Lưu**.
6. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Kiểm tra các trường bắt buộc đã được nhập
   - Kiểm tra định dạng dữ liệu (email, số điện thoại, CMND/CCCD, mã số thuế)
   - Kiểm tra logic nghiệp vụ
7. Nếu dữ liệu hợp lệ:
   - Hệ thống lưu thông tin vào **ENT_NguoiThamGiaGiaoDichCaNhan** (đối với cá nhân) hoặc **ENT_NguoiThamGiaGiaoDichToChuc** (đối với tổ chức)
   - Hiển thị thông báo "Thêm mới bên liên quan thành công"
   - Cập nhật danh sách bên liên quan trong tab "Bên tham gia" của hồ sơ công chứng
   - Đóng form thêm mới bên liên quan
8. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Nếu chưa điền thông tin bắt buộc, hiển thị thông báo yêu cầu điền thông tin bắt buộc.
- Nếu sai định dạng thông tin, hiển thị thông báo lỗi "Thông tin không hợp lệ".
- Nếu thông tin bên liên quan đã tồn tại trong hồ sơ, hệ thống thông báo lỗi "Bên liên quan này đã tồn tại trong hồ sơ".

## Hậu điều kiện
- Nếu thành công: Bên liên quan mới được thêm vào hồ sơ công chứng.
- Nếu thất bại: Không có dữ liệu mới nào được thêm.

## Liên kết
- Form liên quan: [SCR_BLQ_Create.md]
- Entity liên quan: ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc
- Usecase gọi đến: UC_HSCC_Create, UC_HSCC_Update