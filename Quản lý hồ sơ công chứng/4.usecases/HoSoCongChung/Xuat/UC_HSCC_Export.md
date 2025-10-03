# Use Case: UC_HSCC_Export (Xuất danh sách hồ sơ công chứng)

## User Story
- Với vai trò là **Chuyên viên tại Sở Tư pháp/Lãnh đạo Sở Tư pháp/Lãnh đạo Bộ Tư pháp/Công chứng viên/Nhân viên TCHNCC**, tôi muốn có thể xuất danh sách hồ sơ công chứng ra file Excel để phục vụ công việc báo cáo và thống kê.

## Acceptance Criteria
- Hệ thống hỗ trợ xuất danh sách hồ sơ công chứng ra file Excel (.xlsx).
- Hệ thống cho phép người dùng chọn các cột thông tin cần xuất.
- Hệ thống xuất dữ liệu theo phạm vi quyền hạn của người dùng.
- Hệ thống hỗ trợ xuất dữ liệu theo bộ lọc đang áp dụng.
- Hệ thống giới hạn số lượng bản ghi xuất trong một lần (tối đa 50.000 bản ghi).
- File xuất có tên theo định dạng: "DanhSachHoSoCongChung-ngày giờ xuất.xlsx".

## Tác nhân chính
- Chuyên viên tại Sở Tư pháp
- Lãnh đạo Sở Tư pháp/Lãnh đạo Phòng HCBTTP tại Sở TP
- Lãnh đạo Bộ Tư pháp/Lãnh đạo Cục Bổ trợ tư pháp/Chuyên viên Cục Bổ trợ tư pháp
- Công chứng viên tại các TCHNCC
- Nhân viên tại các TCHNCC

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Xuất danh sách hồ sơ công chứng".

## Luồng chính
1. Người dùng chọn chức năng **Xuất danh sách** từ danh sách hồ sơ công chứng (**UC_HSCC_List**) hoặc từ kết quả tìm kiếm (**UC_HSCC_Search**).
2. Hệ thống hiển thị form xuất danh sách với các tùy chọn:
   
   **Lựa chọn phạm vi dữ liệu:**
   - Xuất tất cả (theo phạm vi quyền hạn)
   - Xuất theo bộ lọc đang áp dụng
   - Xuất các hồ sơ được chọn
   
   **Lựa chọn cột thông tin:**
   - Mã hồ sơ công chứng
   - Tên giao dịch công chứng
   - Ngày công chứng
   - Số công chứng
   - Nội dung giao dịch
   - Giá trị hợp đồng
   - Tên tổ chức công chứng
   - Tên công chứng viên thực hiện
   - Tên bên tham gia (cá nhân/tổ chức)
   - Loại tài sản
   - Địa chỉ tài sản
   - Trạng thái hồ sơ
   
   **Lựa chọn định dạng:**
   - Excel (.xlsx) - Mặc định
3. Người dùng chọn các tùy chọn xuất dữ liệu.
4. Người dùng bấm nút **Xuất**.
5. Hệ thống xác định phạm vi dữ liệu theo quyền của người dùng:
   - Chuyên viên/Lãnh đạo Sở Tư pháp: Xuất hồ sơ trên địa bàn tỉnh/thành phố
   - Lãnh đạo Bộ Tư pháp/Cục BTP: Xuất hồ sơ toàn quốc hoặc theo địa phương được chỉ định
   - Công chứng viên/Nhân viên TCHNCC: Xuất hồ sơ tại tổ chức của mình
6. Hệ thống kiểm tra số lượng bản ghi cần xuất:
   - Nếu vượt quá 50.000 bản ghi: Hiển thị thông báo và yêu cầu giới hạn phạm vi
7. Hệ thống tạo file Excel với các cột được chọn.
8. Hệ thống tự động tải file về máy người dùng.
9. Hệ thống hiển thị thông báo "Xuất danh sách hồ sơ công chứng thành công".
10. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Không có dữ liệu để xuất: Hiển thị thông báo "Không có dữ liệu để xuất".
- Số lượng bản ghi vượt quá giới hạn: Hiển thị thông báo "Số lượng hồ sơ vượt quá giới hạn cho phép (50.000 bản ghi). Vui lòng giới hạn phạm vi xuất".
- Lỗi hệ thống: Hiển thị thông báo lỗi, không thực hiện xuất.
- Người dùng không có quyền: Hiển thị thông báo "Bạn không có quyền xuất danh sách hồ sơ công chứng".

## Hậu điều kiện
- Nếu thành công: File Excel chứa danh sách hồ sơ công chứng được tải về máy người dùng.
- Nếu thất bại: Hiển thị thông báo lỗi tương ứng.

## Liên kết
- Activity Diagram: [AD_HSCC_Export.puml]
- Form liên quan: [SCR_HSCC_Export.md]
- Entity liên quan: ENT_HoSoCongChung, ENT_NguoiThamGiaGiaoDichCaNhan, ENT_NguoiThamGiaGiaoDichToChuc, ENT_TaiSan