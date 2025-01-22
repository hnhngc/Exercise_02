# Todo API

Dự án này triển khai một API tối giản để quản lý các công việc cần làm (todo items) sử dụng ASP.NET Core. API cung cấp các thao tác CRUD cơ bản và sử dụng cơ sở dữ liệu trong bộ nhớ.

## Tổng quan

- **Framework**: ASP.NET Core (.NET 9.0)
- **Cơ sở dữ liệu**: Entity Framework Core với InMemory provider
- **Loại dự án**: Minimal API
- **Kiến trúc**: REST API

## Tính năng

API hỗ trợ các endpoint sau:

| Endpoint | Phương thức | Mô tả | Kết quả trả về |
|----------|-------------|--------|----------------|
| `/todoitems` | GET | Lấy tất cả công việc | Mảng các công việc |
| `/todoitems/complete` | GET | Lấy các công việc đã hoàn thành | Mảng các công việc đã hoàn thành |
| `/todoitems/{id}` | GET | Lấy một công việc cụ thể | Một công việc |
| `/todoitems` | POST | Tạo công việc mới | Công việc vừa tạo |
| `/todoitems/{id}` | PUT | Cập nhật công việc | Không có nội dung |
| `/todoitems/{id}` | DELETE | Xóa công việc | Không có nội dung |

## Các bước đã thực hiện

1. Tạo dự án mới ASP.NET Core Empty với tên "TodoApi"
2. Cài đặt các gói NuGet cần thiết:
   - Microsoft.EntityFrameworkCore.InMemory
   - Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore

3. Tạo các lớp mô hình:
   - `Todo.cs` cho mô hình công việc
   - `TodoDb.cs` cho ngữ cảnh cơ sở dữ liệu Entity Framework

4. Triển khai tất cả các endpoint API trong `Program.cs`

## Kết quả Kiểm thử

Đã kiểm tra thành công tất cả các endpoint sử dụng Endpoints Explorer trong Visual Studio:

1. **Kiểm tra POST**:
   - Đã tạo công việc mới với tên "walk dog"
   - Nhận được phản hồi thành công với chi tiết công việc đã tạo

2. **Kiểm tra GET**:
   - Lấy thành công tất cả các công việc
   - Lấy các công việc đã hoàn thành
   - Lấy từng công việc theo ID

3. **Cấu hình SSL**:
   - Đã cấu hình chứng chỉ SSL cho môi trường phát triển
   - Xử lý thành công các yêu cầu HTTPS

## Cách Chạy Dự án

1. Mở solution trong Visual Studio 2022
2. Đảm bảo đã cài đặt .NET 9.0 SDK
3. Build và chạy dự án
4. Truy cập API tại `https://localhost:....` 

## Cấu trúc Dự án

```
TodoApi/
├── Program.cs         # Các endpoint API và cấu hình
├── Todo.cs            # Mô hình công việc      
└── TodoDb.cs          # Ngữ cảnh cơ sở dữ liệu
```

## Ghi chú Phát triển

- Sử dụng cơ sở dữ liệu trong bộ nhớ cho phát triển
- Đã cấu hình chứng chỉ SSL cho môi trường local
- API tuân thủ nguyên tắc REST
- Cách tiếp cận Minimal API giúp giảm thiểu mã boilerplate
- Entity Framework Core xử lý việc lưu trữ dữ liệu
