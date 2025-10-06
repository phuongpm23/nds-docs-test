# Use Case: UC_TSGD_Update (Chỉnh sửa tài sản giao dịch)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể chỉnh sửa thông tin tài sản giao dịch để cập nhật các thay đổi hoặc sửa lỗi thông tin trong giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị form chỉnh sửa thông tin tài sản với dữ liệu đã có.
- Hệ thống cho phép chỉnh sửa thông tin chi tiết về tài sản.
- Hệ thống kiểm tra tính hợp lệ của dữ liệu trước khi lưu.
- Hệ thống ghi nhận lịch sử các thay đổi trên thông tin tài sản.
- Hệ thống cho phép thay đổi loại tài sản (với các ràng buộc phù hợp).

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Chỉnh sửa hồ sơ công chứng".
- Tài sản tồn tại trong hồ sơ công chứng.
- Người dùng đang trong quá trình chỉnh sửa hồ sơ công chứng.

## Luồng chính
1. Người dùng chọn chức năng **Chỉnh sửa** tài sản từ tab "Tài sản" trong form hồ sơ công chứng (**UC_HSCC_Update**).
2. Hệ thống hiển thị form chỉnh sửa thông tin tài sản với các trường dữ liệu đã có:
   
   **Thông tin chung:**
   - Loại tài sản (Đất ở/Đất nông nghiệp/Nhà ở/Xe ô tô/Xe máy/Khác) - có thể thay đổi với ràng buộc
   - Mục đích sử dụng - có thể chỉnh sửa
   - Giá trị tài sản - có thể chỉnh sửa
   
   **Thông tin chi tiết (hiển thị tùy theo loại tài sản):**
   
   *Đất ở/Đất nông nghiệp:*
   - Thửa đất số - có thể chỉnh sửa
   - Tờ bản đồ số - có thể chỉnh sửa
   - Địa chỉ thửa đất - có thể chỉnh sửa
   - Diện tích (m²) - có thể chỉnh sửa
   - Hình thức sử dụng - có thể chỉnh sửa
   - Thời hạn sử dụng - có thể chỉnh sửa
   - Nguồn gốc sử dụng - có thể chỉnh sửa
   
   *Nhà ở:*
   - Địa chỉ nhà - có thể chỉnh sửa
   - Diện tích xây dựng (m²) - có thể chỉnh sửa
   - Diện tích sàn (m²) - có thể chỉnh sửa
   - Số tầng - có thể chỉnh sửa
   - Kết cấu nhà - có thể chỉnh sửa
   - Năm xây dựng - có thể chỉnh sửa
   
   *Xe ô tô/Xe máy:*
   - Số khung - có thể chỉnh sửa
   - Số máy - có thể chỉnh sửa
   - Biển số đăng ký - có thể chỉnh sửa
   - Nhãn hiệu - có thể chỉnh sửa
   - Model - có thể chỉnh sửa
   - Năm sản xuất - có thể chỉnh sửa
   
   *Tài sản khác:*
   - Mô tả chi tiết tài sản - có thể chỉnh sửa
   - Số serial/ID (nếu có) - có thể chỉnh sửa
   - Các đặc điểm nhận dạng khác - có thể chỉnh sửa
   
3. Người dùng thực hiện các thay đổi cần thiết.
4. Nếu người dùng thay đổi loại tài sản, hệ thống hiển thị cảnh báo và yêu cầu xác nhận.
5. Người dùng bấm nút **Lưu**.
6. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Kiểm tra các trường bắt buộc đã được nhập
   - Kiểm tra định dạng dữ liệu (số, ngày tháng)
   - Kiểm tra logic nghiệp vụ
7. Nếu dữ liệu hợp lệ:
   - Hệ thống ghi nhận các thay đổi vào lịch sử
   - Cập nhật thông tin vào **ENT_TaiSan**
   - Cập nhật thông tin chi tiết vào bảng tương ứng theo loại tài sản
   - Hiển thị thông báo "Cập nhật thông tin tài sản thành công"
   - Cập nhật danh sách tài sản trong tab "Tài sản" của hồ sơ công chứng
   - Đóng form chỉnh sửa thông tin tài sản
8. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Nếu chưa điền thông tin bắt buộc, hiển thị thông báo yêu cầu điền thông tin bắt buộc.
- Nếu sai định dạng thông tin, hiển thị thông báo lỗi "Thông tin không hợp lệ".
- Nếu thông tin tài sản bị trùng với tài sản khác trong hồ sơ, hệ thống thông báo lỗi "Thông tin này đã tồn tại cho tài sản khác trong hồ sơ".
- Nếu thay đổi loại tài sản, hệ thống yêu cầu xác nhận và có thể xóa các trường thông tin không còn phù hợp.

## Hậu điều kiện
- Nếu thành công: Thông tin tài sản được cập nhật.
- Nếu thất bại: Không có thay đổi nào được lưu.

## Liên kết
- Form liên quan: [SCR_TSGD_Update.md]
- Entity liên quan: ENT_TaiSan, ENT_TaiSanDat, ENT_TaiSanNha, ENT_TaiSanXe, ENT_TaiSanKhac, ENT_LichSuCapNhatTaiSan
- Usecase gọi đến: UC_HSCC_Update