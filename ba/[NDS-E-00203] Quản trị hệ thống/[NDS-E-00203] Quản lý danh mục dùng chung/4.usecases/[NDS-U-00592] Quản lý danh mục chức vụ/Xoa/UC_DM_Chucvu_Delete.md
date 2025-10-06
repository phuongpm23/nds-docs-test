# Use Case: DM_Chucvu_Delete (Xóa danh mục chức vụ)

## User Story
- là Quản trị viên, tôi muốn xóa danh mục chức vụ để có thể bỏ những bản ghi đã bị tạo nhầm.

## Acceptance criteria
- Khi người dùng chọn Xóa danh mục chức vụ, hệ thống phải hiển thị hộp thoại xác nhận với nội dung: “Bạn có chắc chắn muốn xóa danh mục chức vụ này không?”.
- Hệ thống phải cung cấp hai lựa chọn: Xác nhận và Hủy.
- Nếu người dùng chọn Hủy, hệ thống đóng hộp thoại và danh mục chức vụ không bị xóa.
- Nếu người dùng chọn Xác nhận, hệ thống phải kiểm tra điều kiện trước khi xóa.
- Nếu không còn ràng buộc dữ liệu, hệ thống xóa thành công và hiển thị thông báo "Xóa thành công danh mục chức vụ".
- Hệ thống phải ghi nhận thông tin xóa danh mục chức vụ vào nhật ký hệ thống. 
- Hệ thống phải cập nhật danh sách danh mục chức vụ hiển thị trên **DM_Chucvu_List** sau khi xóa thành công
- Chỉ có tài khoản Quản trị viên mới được xóa danh mục chức vụ.

## Tác nhân chính
- Quản trị viên

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xóa danh mục chức vụ.

## Luồng chính
1. Người dùng truy cập màn hình danh sách danh mục chức vụ **DM_Chucvu_List**.  
2. Nếu người dùng có quyền xóa danh mục chức vụ, hệ thống hiển thị nút xóa danh mục chức vụ trên mỗi bản ghi
3. Người dùng nhấn nút "Xóa" trên bản ghi danh mục chức vụ.  
3. Hệ thống hiển thị popup xác nhận xóa.  
4. Người dùng nhấn nút "Xác nhận".  
5. Hệ thống kiểm tra:  
   - Nếu Thông tin danh mục chức vụ đang được sử dụng → Hệ thống đóng popup → Hiển thị cảnh báo lỗi "Không thể xóa danh mục chức vụ.Danh mục đang được sử dụng" và không thực hiện xóa.  
   - Nếu không có ràng buộc → Xóa dữ liệu danh mục chức vụ trong **DM_Chucvu**.  
6. Hệ thống đóng popup, hiển thị thông báo kết quả "Danh mục chức vụ thành công" .  
7. Use case kết thúc. 

## Luồng phụ / ngoại lệ
- Người dùng nhấn **Hủy** hoặc biểu tượng đóng popup xác nhận xóa → Hệ thống đóng popup, use case kết thúc, không có thay đổi.  
- Nếu có lỗi hệ thống → Hiển thị thông báo lỗi chung, không xóa dữ liệu.  

## Hậu điều kiện
- Nếu thành công: Thông tin danh mục chức vụ bị xóa và không còn trong danh sách.  
- Nếu thất bại hoặc hủy: Không có thay đổi nào trong hệ thống.

## Liên kết
- Activity Diagram: [DM_Chucvu_delete.puml]
- Form/Screen: [SCR_DM_Chucvu_Delete.md]
- Entity liên quan: DM_Chucvu
