# Use Case: UC_HSCC_Create (Thêm mới hồ sơ công chứng)

## User Story
- Với vai trò là **Công chứng viên/Nhân viên tại các TCHNCC**, tôi muốn có thể tạo mới hồ sơ công chứng để ghi nhận thông tin về giao dịch công chứng được thực hiện.

## Acceptance Criteria
- Hệ thống hiển thị form tạo mới hồ sơ công chứng.
- Hệ thống cho phép nhập thông tin chung của hồ sơ.
- Hệ thống cho phép thêm mới các bên tham gia giao dịch (cá nhân/tổ chức).
- Hệ thống cho phép nhập thông tin chi tiết về tài sản theo từng loại.
- Hệ thống cho phép đính kèm các tài liệu liên quan.
- Hệ thống kiểm tra tính hợp lệ của dữ liệu trước khi lưu.
- Hệ thống tự động tạo mã hồ sơ công chứng.
- Hệ thống hỗ trợ nhập hồ sơ từ file Excel.

## Tác nhân chính
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Thêm mới hồ sơ công chứng".
- Người dùng thuộc một tổ chức công chứng đang hoạt động.

## Luồng chính
1. Người dùng chọn chức năng **Thêm mới hồ sơ công chứng** từ danh sách hồ sơ (**UC_HSCC_List**).
2. Hệ thống hiển thị form tạo mới hồ sơ công chứng với các tab:
   
   **Tab Thông tin chung:**
   - Tên giao dịch công chứng (bắt buộc)
   - Ngày công chứng (bắt buộc, mặc định là ngày hiện tại)
   - Số công chứng (tự động tạo hoặc nhập thủ công)
   - Nội dung giao dịch (bắt buộc)
   - Giá trị hợp đồng
   - Tổ chức công chứng (mặc định là tổ chức của người dùng)
   - Công chứng viên thực hiện (mặc định là người dùng)
   
   **Tab Bên tham gia:**
   - Danh sách bên tham gia cá nhân
   - Danh sách bên tham gia tổ chức
   - Nút "Thêm mới bên tham gia"
   
   **Tab Tài sản:**
   - Loại tài sản
   - Thông tin chi tiết về tài sản (tùy theo loại tài sản)
   - Giá trị tài sản
   
   **Tab Tài liệu đính kèm:**
   - Văn bản công chứng giấy
   - Hồ sơ lưu trữ điện tử
   - Các tài liệu khác liên quan
3. Người dùng nhập thông tin vào các tab tương ứng.
4. Người dùng bấm nút **Lưu**.
5. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Kiểm tra các trường bắt buộc đã được nhập
   - Kiểm tra định dạng dữ liệu
   - Kiểm tra logic nghiệp vụ
6. Nếu dữ liệu hợp lệ:
   - Hệ thống tạo mã hồ sơ công chứng tự động
   - Lưu thông tin hồ sơ vào **ENT_HoSoCongChung**
   - Lưu thông tin các bên tham gia vào **ENT_NguoiThamGiaGiaoDichCaNhan** và **ENT_NguoiThamGiaGiaoDichToChuc**
   - Lưu thông tin tài sản vào **ENT_TaiSan**
   - Lưu thông tin tài liệu đính kèm
   - Hiển thị thông báo "Thêm mới hồ sơ công chứng thành công"
   - Chuyển hướng về danh sách hồ sơ công chứng (**UC_HSCC_List**)
7. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Nếu ngày công chứng > Ngày hôm nay: thông báo lỗi "Ngày công chứng không được lớn hơn ngày hiện tại".
- Nếu chưa điền thông tin bắt buộc, hiển thị thông báo yêu cầu điền thông tin bắt buộc.
- Nếu sai định dạng thông tin, hiển thị thông báo lỗi "Thông tin không hợp lệ".
- Nếu số công chứng bị trùng với hồ sơ khác trong cùng tổ chức, hệ thống thông báo lỗi "Số công chứng đã tồn tại".

## Hậu điều kiện
- Nếu thành công: Hồ sơ công chứng mới được thêm vào hệ thống.
- Nếu thất bại: Không có dữ liệu mới nào được thêm.

## Liên kết
- Activity Diagram: [AD_HSCC_Create.puml]
- Form liên quan: [SCR_HSCC_Create.md]
- Entity liên quan: ENT_HoSoCongChung, ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_TaiSan