# Use Cases cho Quản lý hồ sơ công chứng

## Tổng quan
Tài liệu này mô tả các use case chi tiết và activity diagram cho chức năng quản lý hồ sơ công chứng trong hệ thống.

## Cấu trúc thư mục
```
4.usecases/
└── HoSoCongChung/
    ├── XemDanhSach/
    │   ├── UC_HSCC_List.md
    │   └── AD_HSCC_List.puml
    ├── XemChiTiet/
    │   ├── UC_HSCC_Detail.md
    │   └── AD_HSCC_Detail.puml
    ├── TimKiem/
    │   ├── UC_HSCC_Search.md
    │   └── AD_HSCC_Search.puml
    ├── Xuat/
    │   ├── UC_HSCC_Export.md
    │   └── AD_HSCC_Export.puml
    ├── ThemMoi/
    │   ├── UC_HSCC_Create.md
    │   └── AD_HSCC_Create.puml
    ├── ChinhSua/
    │   ├── UC_HSCC_Update.md
    │   └── AD_HSCC_Update.puml
    └── Xoa/
        ├── UC_HSCC_Delete.md
        └── AD_HSCC_Delete.puml
```

## Danh sách Use Cases

### 1. Xem danh sách hồ sơ công chứng (UC_HSCC_List)
- **Mô tả:** Hiển thị danh sách hồ sơ công chứng theo phạm vi quyền hạn của người dùng
- **Tác nhân:** Chuyên viên STP, Lãnh đạo STP, Lãnh đạo BTP, Công chứng viên, Nhân viên TCHNCC
- **File liên quan:**
  - Use Case: [UC_HSCC_List.md](HoSoCongChung/XemDanhSach/UC_HSCC_List.md)
  - Activity Diagram: [AD_HSCC_List.puml](HoSoCongChung/XemDanhSach/AD_HSCC_List.puml)

### 2. Xem chi tiết hồ sơ công chứng (UC_HSCC_Detail)
- **Mô tả:** Hiển thị đầy đủ thông tin chi tiết của một hồ sơ công chứng
- **Tác nhân:** Chuyên viên STP, Lãnh đạo STP, Lãnh đạo BTP, Công chứng viên, Nhân viên TCHNCC
- **File liên quan:**
  - Use Case: [UC_HSCC_Detail.md](HoSoCongChung/XemChiTiet/UC_HSCC_Detail.md)
  - Activity Diagram: [AD_HSCC_Detail.puml](HoSoCongChung/XemChiTiet/AD_HSCC_Detail.puml)

### 3. Tìm kiếm hồ sơ công chứng (UC_HSCC_Search)
- **Mô tả:** Tìm kiếm hồ sơ công chứng theo nhiều tiêu chí khác nhau
- **Tác nhân:** Chuyên viên STP, Lãnh đạo STP, Lãnh đạo BTP, Công chứng viên, Nhân viên TCHNCC
- **File liên quan:**
  - Use Case: [UC_HSCC_Search.md](HoSoCongChung/TimKiem/UC_HSCC_Search.md)
  - Activity Diagram: [AD_HSCC_Search.puml](HoSoCongChung/TimKiem/AD_HSCC_Search.puml)

### 4. Xuất danh sách hồ sơ công chứng (UC_HSCC_Export)
- **Mô tả:** Xuất danh sách hồ sơ công chứng ra file Excel
- **Tác nhân:** Chuyên viên STP, Lãnh đạo STP, Lãnh đạo BTP, Công chứng viên, Nhân viên TCHNCC
- **File liên quan:**
  - Use Case: [UC_HSCC_Export.md](HoSoCongChung/Xuat/UC_HSCC_Export.md)
  - Activity Diagram: [AD_HSCC_Export.puml](HoSoCongChung/Xuat/AD_HSCC_Export.puml)

### 5. Thêm mới hồ sơ công chứng (UC_HSCC_Create)
- **Mô tả:** Tạo mới hồ sơ công chứng
- **Tác nhân:** Công chứng viên, Nhân viên TCHNCC
- **File liên quan:**
  - Use Case: [UC_HSCC_Create.md](HoSoCongChung/ThemMoi/UC_HSCC_Create.md)
  - Activity Diagram: [AD_HSCC_Create.puml](HoSoCongChung/ThemMoi/AD_HSCC_Create.puml)

### 6. Chỉnh sửa hồ sơ công chứng (UC_HSCC_Update)
- **Mô tả:** Chỉnh sửa thông tin hồ sơ công chứng
- **Tác nhân:** Công chứng viên, Nhân viên TCHNCC
- **File liên quan:**
  - Use Case: [UC_HSCC_Update.md](HoSoCongChung/ChinhSua/UC_HSCC_Update.md)
  - Activity Diagram: [AD_HSCC_Update.puml](HoSoCongChung/ChinhSua/AD_HSCC_Update.puml)

### 7. Xóa hồ sơ công chứng (UC_HSCC_Delete)
- **Mô tả:** Xóa hồ sơ công chứng
- **Tác nhân:** Công chứng viên, Nhân viên TCHNCC
- **File liên quan:**
  - Use Case: [UC_HSCC_Delete.md](HoSoCongChung/Xoa/UC_HSCC_Delete.md)
  - Activity Diagram: [AD_HSCC_Delete.puml](HoSoCongChung/Xoa/AD_HSCC_Delete.puml)

## Entity liên quan
- ENT_HoSoCongChung
- ENT_NguoiThamGiaGiaoDichCaNhan
- ENT_NguoiThamGiaGiaoDichToChuc
- ENT_TaiSan
- ENT_LichSuCapNhatHoSo

## Lưu ý
- Các use case được thiết kế tuân thủ theo quy chuẩn nghiệp vụ chung của hệ thống
- Mỗi use case đều có activity diagram tương ứng để mô tả luồng xử lý chi tiết
- Phân quyền được áp dụng dựa trên vai trò của người dùng và phạm vi quản lý