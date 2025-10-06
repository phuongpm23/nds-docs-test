# Use Case: DM_Giayto_Delete (Xóa danh mục giấy tờ )

## User Story
- là Quản trị viên, tôi muốn xóa danh mục giấy tờ  để có thể bỏ những bản ghi đã bị tạo nhầm.

## Acceptance criteria
- Khi người dùng chọn Xóa danh mục giấy tờ , hệ thống phải hiển thị hộp thoại xác nhận với nội dung: “Bạn có chắc chắn muốn xóa danh mục giấy tờ  này không?”.
- Hệ thống phải cung cấp hai lựa chọn: Xác nhận và Hủy.
- Nếu người dùng chọn Hủy, hệ thống đóng hộp thoại và danh mục giấy tờ  không bị xóa.
- Nếu người dùng chọn Xác nhận, hệ thống phải kiểm tra điều kiện trước khi xóa.
- Nếu không còn ràng buộc dữ liệu, hệ thống xóa thành công và hiển thị thông báo "Xóa thành công danh mục giấy tờ ".
- Hệ thống phải ghi nhận thông tin xóa danh mục giấy tờ  vào nhật ký hệ thống. 
- Hệ thống phải cập nhật danh sách danh mục giấy tờ  hiển thị trên **DM_Giayto_List** sau khi xóa thành công
- Chỉ có tài khoản Quản trị viên mới được xóa danh mục giấy tờ .

## Tác nhân chính
- Quản trị viên

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xóa danh mục giấy tờ .

## Luồng chính
1. Người dùng truy cập màn hình danh sách danh mục giấy tờ  **DM_Giayto_List**.  
2. Nếu người dùng có quyền xóa danh mục giấy tờ , hệ thống hiển thị nút xóa danh mục giấy tờ  trên mỗi bản ghi
3. Người dùng nhấn nút "Xóa" trên bản ghi danh mục giấy tờ .  
3. Hệ thống hiển thị popup xác nhận xóa.  
4. Người dùng nhấn nút "Xác nhận".  
5. Hệ thống kiểm tra:  
   - Nếu Thông tin danh mục giấy tờ  đang được sử dụng → Hệ thống đóng popup → Hiển thị cảnh báo lỗi "Không thể xóa danh mục giấy tờ .Danh mục đang được sử dụng" và không thực hiện xóa.  
   - Nếu không có ràng buộc → Xóa dữ liệu danh mục giấy tờ  trong **DM_Giayto**.  
6. Hệ thống đóng popup, hiển thị thông báo kết quả "Danh mục giấy tờ  thành công" .  
7. Use case kết thúc. 

## Luồng phụ / ngoại lệ
- Người dùng nhấn **Hủy** hoặc biểu tượng đóng popup xác nhận xóa → Hệ thống đóng popup, use case kết thúc, không có thay đổi.  
- Nếu có lỗi hệ thống → Hiển thị thông báo lỗi chung, không xóa dữ liệu.  

## Hậu điều kiện
- Nếu thành công: Thông tin danh mục giấy tờ  bị xóa và không còn trong danh sách.  
- Nếu thất bại hoặc hủy: Không có thay đổi nào trong hệ thống.

## Liên kết
- Activity Diagram: [DM_Giayto_delete.puml]
- Form/Screen: [SCR_DM_Giayto_Delete.md]
- Entity liên quan: DM_Giayto
