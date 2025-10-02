# QUY CHUẨN NGHIỆP VỤ DÙNG CHUNG HỆ THỐNG CƠ SỞ DỮ LIỆU CÔNG CHỨNG

Tài liệu này mô tả **các quy chuẩn nghiệp vụ chung** áp dụng cho toàn bộ các tính năng trong hệ thống.  

## 1. Phân trang dữ liệu

| Nội dung          | Quy chuẩn nghiệp vụ                                                                                                                                                          |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cách hiển thị     | Danh sách dữ liệu được phân trang, mặc định 10 bản ghi/trang                                                                                                                 |
| Điều chỉnh        | Người dùng có thể thay đổi số bản ghi/trang: 10, 20, 50, 100, các thông tin hiển thị và điều hướng thay đổi theo số bản ghi/trang mà người dùng chọn                         |
| Điều hướng        | Có biểu tượng chuyển "Trang trước", "Trang sau". Hiển thị số trang hiện tại/Tổng số trang, cho phép điều chỉnh số trang, gõ enter để chuyển tới trang đã điền                |
| Thông tin bổ sung | Luôn hiển thị tổng số bản ghi và tổng số trang. Hiển thị theo định dạng ""STT bản ghi đầu tiên của trang" - "STT bản ghi cuối cuối cùng trang" trên "tổng số lượng bản ghi"" |


## 2. Hiển thị danh sách

| Nội dung | Quy chuẩn nghiệp vụ |
|----------|----------------------|
| Thứ tự hiển thị | Mặc định thứ tự hiển thị là theo thời gian cập nhật từ mới tới cũ nhất. |
| Thông tin hiển thị | Thông tin nào bị trống hoặc không có dữ liệu, hiện dấu "-". Thông tin nào dài quá 2 dòng, chỉ hiển thị 1 phần thông tin, hiển thị biểu tượng "...", hover vào hiển thị chi tiết |
| Hiển thị ngày | Hiển thị ngày theo định dạng dd/mm/yyyy hh:mm|

## 3. Tìm kiếm và lọc

| Nội dung       | Quy chuẩn nghiệp vụ                                                                                                                                                                                                                                                                                                                                                                                         |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tìm kiếm chung | Có ô tìm kiếm theo từ khóa trên danh sách, những trường thông tin tìm kiếm sẽ quy định rõ trong usecase, tìm kiếm gần đúng thông tin đã điền                                                                                                                                                                                                                                                                |
| Tìm kiếm nhanh | Có ô tìm kiếm trực tiếp trong cột, cột nào dạng input điền thông tin trực tiếp, khi click nút tìm kiếm, hệ thống sẽ tìm kiếm kết quả gần đúng theo giá trị đã điền. Trường hợp là lọc/lựa chọn/Dropdown (mô tả chi tiết tron screen), hệ thống sẽ tìm kiếm chính xác theo kết quả đã chọn, chỉ chọn 1 giá trị, danh sách giá trị được mô tả trong enity hoặc được quản lý và tham chiếu trong mô tả screeen |
| Ghi nhớ bộ lọc | Hệ thống tự động giữ lại bộ lọc sau khi người dùng chuyển trang hoặc tải lại                                                                                                                                                                                                                                                                                                                                |


## 4. Xuất Excel

| Nội dung       | Quy chuẩn nghiệp vụ                                                                                |
|----------------|----------------------------------------------------------------------------------------------------|
| Định dạng file | Xuất ra file Excel (.xlsx)                                                                         |
| Tên file       | Tên theo Entity + ngày giờ xuất. Ví dụ: `DanhSachCongChungVien-20251002-0930.xlsx`                 |
| Dữ liệu xuất   | Dữ liệu xuất đúng theo điều kiện tìm kiếm, bộ lọc. Danh sách xuất ra giống với danh sách hiển thị. |
| Giới hạn       | Xuất tối đa 50.000 bản ghi trong một lần                                                           |
| Định dạng cột  | Ngày hiển thị `dd/MM/yyyy` hoặc `dd/MM/yyyy HH:mm`, số tiền có dấu phân cách hàng nghìn                                    |


## 5. File đính kèm

| Nội dung           | Quy chuẩn nghiệp vụ                                                                                            |
|--------------------|----------------------------------------------------------------------------------------------------------------|
| Định dạng cho phép | Tùy từng trường hợp cụ thể sẽ mô tả trong chi tiết                                                             |
| Dung lượng         | Tối đa 10MB/file                                                                                               |
| Xem file           | Đối với file PDF, khi click vào tên file sẽ mở tab mới của trình duyệt để hiển thị file. Đối với file ảnh, hiển thị màn hình preview ảnh |


## 6. Nhật ký cập nhật (Audit log)

| Nội dung           | Quy chuẩn nghiệp vụ                                                           |
|--------------------|-------------------------------------------------------------------------------|
| Lưu lại            | Tất cả thao tác thêm, sửa, xóa dữ liệu                                        |
| Thông tin bắt buộc | Người thực hiện, ngày giờ, trường thông tin thay đổi, giá trị cũ, giá trị mới |
| Truy xuất          | Người quản trị có thể xem lại lịch sử thay đổi theo từng bản ghi              |

## 7. Phần đầu trang 
| Nội dung            | Quy chuẩn nghiệp vụ                                                                                                                                        |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Thông tin tài khoản | Luôn hiển thị Họ và tên của người dùng + chức vụ. Hiển thị ảnh nếu có, nếu không sẽ hiển thị ảnh mặc định, click vào sẽ mở trang quản lý tài khoản cá nhân |
| Biểu tượng menu     | Mặc định hiển thị menu chi tiết, bấm vào biểu tượng này sẽ đóng menu, thực hiện lại sẽ mở menu                                                             |


## 8. Menu/Danh mục chức năng hệ thống
| Nội dung                     | Quy chuẩn nghiệp vụ                                                               |
|------------------------------|-----------------------------------------------------------------------------------|
| Bảng điều khiển              | Hiển thị khi người dùng có quyền, click vào mở trang dashboard                    |
| Quản lý công chứng viên      | Hiển thị khi người dùng có quyền, click vào mở trang danh sách công chứng viên    |
| Quản lý tổ chức công chứng   | Hiển thị khi người dùng có quyền, click vào mở trang danh sách tổ chức công chứng |
| Quản lý chữ ký số            | Hiển thị khi người dùng có quyền, click vào mở trang danh sách chữ ký số          |
| Quản lý hồ sơ công chứng     | Hiển thị khi người dùng có quyền, click vào mở trang danh sách hồ sơ công chứng   |
| Tra cứu                      | Hiển thị khi người dùng có quyền, click vào đổ xuống danh mục tra cứu             |
| Tra cứu - Công chứng viên    | Hiển thị khi người dùng có quyền, click vào mở trang tra cứu công chứng viên      |
| Tra cứu - Tổ chức công chứng | Hiển thị khi người dùng có quyền, click vào mở trang tra cứu tổ chức công chứng   |

## 9. Nhập thông tin
| Nội dung                | Quy chuẩn nghiệp vụ                                                                                                                                                                          |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kiểm tra dữ liệu        | Nếu trường thông tin bắt buộc không được nhập, hoặc sai định dạng dữ liệu, hệ thống hiển thị cảnh báo ngay dưới ô nhập                                                                       |
| Ngày sinh, ngày cấp     | Chọn từ lịch, thông báo lỗi thông tin không hợp lệ ngay dưới ô nhập nếu lớn hơn hoặc bằng ngày hiện tại                                                                                      |
| Số điện thoại           | Định dạng số Việt Nam                                                                                                                                                                        |
| Input lựa chọn/dropdown | Click vào, hệ thống hiển thị mặc định 5 giá trị, có thể scroll xuống để hiển thị thêm. Hiển thị ô điền thông tin tìm kiếm, khi người dùng điền, hệ thống lọc giá trị để chọn theo từ đã điền |
| Quy tắc click nút tab   | Gõ tab, hệ thống tự động chuyển từ field này sang field kế tiếp, từ trái sang phải, từ trên xuống . Nếu tab ở input lựa chọn, chọn ngay giá trị đầu tiên                                     |

## 10. Popup nhập/xác nhận/hiển thị thông tin
| Nội dung       | Quy chuẩn nghiệp vụ                                                |
|----------------|--------------------------------------------------------------------|
| Nút "Đóng"     | Luôn hiển thị trong popup, click vào sẽ hủy thao tác và đóng popup |
| Biểu tượng "x" | Luôn hiển thị trong popup, click vào sẽ hủy thao tác và đóng popup |

