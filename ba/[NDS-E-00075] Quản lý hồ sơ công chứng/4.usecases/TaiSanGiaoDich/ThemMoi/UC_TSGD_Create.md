# Use Case: UC_TSGD_Create (Thêm mới tài sản giao dịch)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể thêm mới thông tin tài sản giao dịch để ghi nhận các tài sản liên quan trong giao dịch công chứng.

## Acceptance Criteria
- Hệ thống hiển thị form thêm mới tài sản giao dịch.
- Hệ thống cho phép chọn loại tài sản (đất ở, đất nông nghiệp, nhà ở, xe ô tô, xe máy, khác).
- Hệ thống hiển thị các trường thông tin phù hợp với từng loại tài sản.
- Hệ thống kiểm tra tính hợp lệ của dữ liệu trước khi lưu.
- Hệ thống cho phép liên kết tài sản với các bên liên quan.
- Hệ thống cho phép nhập thông tin về giá trị tài sản.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Thêm mới hồ sơ công chứng" hoặc "Chỉnh sửa hồ sơ công chứng".
- Người dùng đang trong quá trình tạo mới hoặc chỉnh sửa hồ sơ công chứng.

## Luồng chính
1. Người dùng chọn chức năng **Thêm mới tài sản** từ tab "Tài sản" trong form hồ sơ công chứng (**UC_HSCC_Create** hoặc **UC_HSCC_Update**).
2. Hệ thống hiển thị form thêm mới tài sản giao dịch với các trường:
   
   **Thông tin chung:**
   - Loại tài sản (Đất ở/Đất nông nghiệp/Nhà ở/Xe ô tô/Xe máy/Khác) - bắt buộc
   - Mục đích sử dụng - bắt buộc
   - Giá trị tài sản - bắt buộc
   
   **Thông tin chi tiết (hiển thị tùy theo loại tài sản):**
   
   *Đất ở/Đất nông nghiệp:*
   - Thửa đất số
   - Tờ bản đồ số
   - Địa chỉ thửa đất
   - Diện tích (m²) - bắt buộc
   - Hình thức sử dụng
   - Thời hạn sử dụng
   - Nguồn gốc sử dụng
   
   *Nhà ở:*
   - Địa chỉ nhà
   - Diện tích xây dựng (m²)
   - Diện tích sàn (m²)
   - Số tầng
   - Kết cấu nhà
   - Năm xây dựng
   
   *Xe ô tô/Xe máy:*
   - Số khung
   - Số máy
   - Biển số đăng ký
   - Nhãn hiệu
   - Model
   - Năm sản xuất
   
   *Tài sản khác:*
   - Mô tả chi tiết tài sản
   - Số serial/ID (nếu có)
   - Các đặc điểm nhận dạng khác
   
3. Người dùng nhập thông tin vào các trường tương ứng.
4. Người dùng có thể chọn liên kết tài sản với các bên liên quan đã có trong hồ sơ.
5. Người dùng bấm nút **Lưu**.
6. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Kiểm tra các trường bắt buộc đã được nhập
   - Kiểm tra định dạng dữ liệu (số, ngày tháng)
   - Kiểm tra logic nghiệp vụ
7. Nếu dữ liệu hợp lệ:
   - Hệ thống lưu thông tin vào **ENT_TaiSan**
   - Lưu thông tin chi tiết vào bảng tương ứng theo loại tài sản
   - Hiển thị thông báo "Thêm mới tài sản thành công"
   - Cập nhật danh sách tài sản trong tab "Tài sản" của hồ sơ công chứng
   - Đóng form thêm mới tài sản
8. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Nếu chưa điền thông tin bắt buộc, hiển thị thông báo yêu cầu điền thông tin bắt buộc.
- Nếu sai định dạng thông tin, hiển thị thông báo lỗi "Thông tin không hợp lệ".
- Nếu thông tin tài sản đã tồn tại trong hồ sơ, hệ thống thông báo lỗi "Tài sản này đã tồn tại trong hồ sơ".

## Hậu điều kiện
- Nếu thành công: Tài sản mới được thêm vào hồ sơ công chứng.
- Nếu thất bại: Không có dữ liệu mới nào được thêm.

## Liên kết
- Form liên quan: [SCR_TSGD_Create.md]
- Entity liên quan: ENT_TaiSan, ENT_TaiSanDat, ENT_TaiSanNha, ENT_TaiSanXe, ENT_TaiSanKhac
- Usecase gọi đến: UC_HSCC_Create, UC_HSCC_Update