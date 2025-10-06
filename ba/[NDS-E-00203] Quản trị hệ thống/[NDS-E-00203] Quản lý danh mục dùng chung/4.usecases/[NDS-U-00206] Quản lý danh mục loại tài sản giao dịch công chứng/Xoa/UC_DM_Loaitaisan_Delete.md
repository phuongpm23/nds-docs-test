# Use Case: DM_Loaitaisan_Delete (Xóa danh mục Loại tài sản)

## User Story
- là Quản trị viên, tôi muốn xóa danh mục Loại tài sản để có thể Tên bỏ những bản ghi đã bị tạo nhầm.

## Acceptance criteria
- Khi người dùng chọn Xóa danh mục Loại tài sản, hệ thống phải hiển thị hộp thoại xác nhận với nội dung: “Bạn có chắc chắn muốn xóa danh mục Loại tài sản này không?”.
- Hệ thống phải cung cấp hai lựa chọn: Xác nhận và Hủy.
- Nếu người dùng chọn Hủy, hệ thống đóng hộp thoại và danh mục Loại tài sản không bị xóa.
- Nếu người dùng chọn Xác nhận, hệ thống phải kiểm tra điều kiện trước khi xóa.
- Nếu không còn ràng buộc dữ liệu, hệ thống xóa thành công và hiển thị thông báo "Xóa thành công danh mục Loại tài sản".
- Hệ thống phải ghi nhận thông tin xóa danh mục Loại tài sản vào nhật ký hệ thống. 
- Hệ thống phải cập nhật danh sách danh mục Loại tài sản hiển thị trên **DM_Loaitaisan_List** sau khi xóa thành công
- Chỉ có tài khoản Quản trị viên mới được xóa danh mục Loại tài sản.

## Tác nhân chính
- Quản trị viên

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xóa danh mục Loại tài sản.

## Luồng chính
1. Người dùng truy cập màn hình danh sách danh mục Loại tài sản **DM_Loaitaisan_List**.  
2. Nếu người dùng có quyền xóa danh mục Loại tài sản, hệ thống hiển thị nút xóa danh mục Loại tài sản trên mỗi bản ghi
3. Người dùng nhấn nút "Xóa" trên bản ghi danh mục Loại tài sản.  
3. Hệ thống hiển thị popup xác nhận xóa.  
4. Người dùng nhấn nút "Xác nhận".  
5. Hệ thống kiểm tra:  
   - Nếu Thông tin danh mục Loại tài sản đang được sử dụng → Hệ thống đóng popup → Hiển thị cảnh báo lỗi "Không thể xóa danh mục Loại tài sản.Danh mục đang được sử dụng" và không thực hiện xóa.  
   - Nếu không có ràng buộc → Xóa dữ liệu danh mục Loại tài sản trong **DM_Loaitaisan**.  
6. Hệ thống đóng popup, hiển thị thông báo kết quả "Danh mục Loại tài sản thành công" .  
7. Use case kết thúc. 

## Luồng phụ / ngoại lệ
- Người dùng nhấn **Hủy** hoặc biểu tượng đóng popup xác nhận xóa → Hệ thống đóng popup, use case kết thúc, không có thay đổi.  
- Nếu có lỗi hệ thống → Hiển thị thông báo lỗi chung, không xóa dữ liệu.  

## Hậu điều kiện
- Nếu thành công: Thông tin danh mục Loại tài sản bị xóa và không còn trong danh sách.  
- Nếu thất bại hoặc hủy: Không có thay đổi nào trong hệ thống.

## Liên kết
- Activity Diagram: [DM_Loaitaisan_delete.puml]
- Form/Screen: [SCR_DM_Loaitaisan_delete.md]
- Entity liên quan: DM_Loaitaisan
