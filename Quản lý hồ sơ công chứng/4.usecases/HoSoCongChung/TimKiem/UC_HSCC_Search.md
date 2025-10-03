# Use Case: UC_HSCC_Search (Tìm kiếm hồ sơ công chứng)

## User Story
- Với vai trò là **Chuyên viên tại Sở Tư pháp/Lãnh đạo Sở Tư pháp/Lãnh đạo Bộ Tư pháp/Công chứng viên/Nhân viên TCHNCC**, tôi muốn có thể tìm kiếm hồ sơ công chứng theo nhiều tiêu chí khác nhau để nhanh chóng tìm được thông tin cần thiết.

## Acceptance Criteria
- Hệ thống hỗ trợ tìm kiếm nhanh theo từ khóa.
- Hệ thống hỗ trợ tìm kiếm nâng cao theo nhiều tiêu chí.
- Hệ thống hiển thị kết quả tìm kiếm theo phạm vi quyền hạn của người dùng.
- Hệ thống hỗ trợ lưu lại bộ lọc tìm kiếm.
- Hệ thống hỗ trợ xuất kết quả tìm kiếm.

## Tác nhân chính
- Chuyên viên tại Sở Tư pháp
- Lãnh đạo Sở Tư pháp/Lãnh đạo Phòng HCBTTP tại Sở TP
- Lãnh đạo Bộ Tư pháp/Lãnh đạo Cục Bổ trợ tư pháp/Chuyên viên Cục Bổ trợ tư pháp
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Tìm kiếm hồ sơ công chứng".

## Luồng chính
1. Người dùng chọn chức năng **Tìm kiếm hồ sơ công chứng** từ danh sách hồ sơ (**UC_HSCC_List**) hoặc menu chính.
2. Hệ thống hiển thị form tìm kiếm với các tùy chọn:
   
   **Tìm kiếm nhanh:**
   - Ô nhập từ khóa tìm kiếm chung
   
   **Tìm kiếm nâng cao:**
   - Mã hồ sơ công chứng
   - Tên giao dịch công chứng
   - Ngày công chứng (từ - đến)
   - Số công chứng
   - Giá trị hợp đồng (từ - đến)
   - Tên tổ chức công chứng
   - Tên công chứng viên thực hiện
   - Tên bên tham gia (cá nhân/tổ chức)
   - Loại tài sản
   - Địa chỉ tài sản
3. Người dùng nhập các tiêu chí tìm kiếm.
4. Người dùng bấm nút **Tìm kiếm**.
5. Hệ thống xác định phạm vi tìm kiếm theo quyền của người dùng:
   - Chuyên viên/Lãnh đạo Sở Tư pháp: Tìm kiếm hồ sơ trên địa bàn tỉnh/thành phố
   - Lãnh đạo Bộ Tư pháp/Cục BTP: Tìm kiếm hồ sơ toàn quốc hoặc theo địa phương được chỉ định
   - Công chứng viên/Nhân viên TCHNCC: Tìm kiếm hồ sơ tại tổ chức của mình
6. Hệ thống hiển thị danh sách kết quả tìm kiếm:
   - Hiển thị thông tin cơ bản của hồ sơ
   - Phân trang kết quả
   - Sắp xếp theo các cột
7. Người dùng có thể:
   - Xem chi tiết một hồ sơ trong kết quả
   - Chỉnh sửa bộ lọc tìm kiếm
   - Xuất kết quả tìm kiếm
8. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Không tìm thấy kết quả: Hiển thị thông báo "Không tìm thấy hồ sơ công chứng phù hợp với tiêu chí tìm kiếm".
- Lỗi hệ thống: Hiển thị thông báo lỗi, không thực hiện tìm kiếm.
- Người dùng không có quyền: Hiển thị thông báo "Bạn không có quyền tìm kiếm hồ sơ công chứng".

## Hậu điều kiện
- Nếu thành công: Hiển thị danh sách kết quả tìm kiếm hồ sơ công chứng.
- Nếu thất bại: Hiển thị thông báo lỗi tương ứng.

## Liên kết
- Activity Diagram: [AD_HSCC_Search.puml]
- Form liên quan: [SCR_HSCC_Search.md]
- Entity liên quan: ENT_HoSoCongChung, ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_TaiSan