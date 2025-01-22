# Dự án WebAPI với MongoDB

Dự án này xây dựng một Web API sử dụng ASP.NET Core để quản lý sách, với MongoDB làm cơ sở dữ liệu. Dự án cho phép thực hiện các thao tác CRUD (Create, Read, Update, Delete) trên dữ liệu sách.

## Công nghệ Sử dụng

- **Framework**: ASP.NET Core
- **Cơ sở dữ liệu**: MongoDB
- **Công cụ quản lý DB**: MongoDB Compass
- **API Documentation**: Swagger

## Cấu trúc Dự án

```
WebAPI/
├── Controllers/
│   └── BooksController.cs
├── Models/
│   ├── Book.cs
│   └── BookStoreDatabaseSettings.cs
├── Services/
│   └── BookService.cs
└── Program.cs
```

## Các Bước Đã Thực Hiện

### 1. Thiết lập Cơ sở dữ liệu
- Cài đặt MongoDB từ trang chủ
- Cài đặt MongoDB Compass để quản lý dữ liệu
- Tạo database và collection mới
- Thêm dữ liệu mẫu cho 2 cuốn sách:
  - "Design Patterns" của Ralph Johnson
  - "Clean Code" của Robert C. Martin

### 2. Thiết lập Dự án
- Tạo mới dự án ASP.NET Core Web API
- Cài đặt MongoDB.Driver thông qua NuGet Package Manager
- Cấu hình kết nối MongoDB trong appsettings.json

### 3. Phát triển API
- Tạo các model cần thiết:
  - `Book.cs`: Mô hình dữ liệu sách
  - `BookStoreDatabaseSettings.cs`: Cấu hình kết nối database
- Phát triển BookService với các chức năng:
  - Lấy danh sách sách
  - Lấy sách theo ID
  - Thêm sách mới
  - Cập nhật sách
  - Xóa sách
- Tạo BookController với các endpoint:
  - GET /api/books: Lấy tất cả sách
  - GET /api/books/{id}: Lấy sách theo ID
  - POST /api/books: Thêm sách mới
  - PUT /api/books/{id}: Cập nhật sách
  - DELETE /api/books/{id}: Xóa sách

## Kết quả Đạt Được

1. **API hoạt động**: Tất cả các endpoint đều hoạt động như mong đợi
2. **Tích hợp Swagger**: API documentation đầy đủ và có thể test trực tiếp
3. **Kết nối MongoDB**: Thành công thiết lập và thao tác với MongoDB
4. **SSL được cấu hình**: HTTPS hoạt động cho môi trường development

## Cách Chạy Dự án

1. Đảm bảo MongoDB đang chạy trên máy local
2. Mở solution trong Visual Studio
3. Build và chạy dự án
4. Truy cập Swagger UI tại `https://localhost:7295/swagger/index.html`

## Lưu ý Quan trọng

- Cần chấp nhận SSL certificate khi chạy lần đầu
- Đảm bảo MongoDB đang chạy trước khi khởi động ứng dụng
- ID của sách phải có độ dài 24 ký tự theo chuẩn MongoDB
