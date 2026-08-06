---
title: "Worklog Tuần 5"
date: 2026-06-08
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5

* Thiết kế cấu trúc cơ sở dữ liệu (Database Schema) cho dự án Snaptics.
* Thiết lập Entity Framework Core và thực hiện quá trình Migration.
* Xây dựng kiến trúc cơ bản cho Backend API.
* Phát triển các API cốt lõi: Authentication, Quản lý Danh mục, Quản lý Ví.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|------|-----------|-------------|----------------|---------------|
| 2 | **Thiết kế Cơ sở dữ liệu:** <br> - Phân tích yêu cầu dự án Snaptics <br> - Thiết kế các bảng: Users, Wallets, Transactions, Categories <br> - Vẽ sơ đồ quan hệ thực thể (ERD) | 08/06/2026 | 08/06/2026 | |
| 3 | **Cấu hình Entity Framework Core:** <br> - Khởi tạo DbContext <br> - Tạo các Entity Models tương ứng với bảng <br> - Thực hiện Migration và tạo Database | 09/06/2026 | 09/06/2026 | |
| 4 | **Kiến trúc Backend API:** <br> - Xây dựng cấu trúc thư mục dự án <br> - Định nghĩa chuẩn API Response chung <br> - Cấu hình Dependency Injection | 10/06/2026 | 10/06/2026 | |
| 5 | **Phát triển API Authentication:** <br> - Xây dựng luồng Đăng ký tài khoản <br> - Xây dựng luồng Đăng nhập <br> - Tích hợp tạo và mã hóa JWT Token | 11/06/2026 | 11/06/2026 | |
| 6 | **Xây dựng API Cốt lõi:** <br> - Phát triển API quản lý Danh mục (Categories) <br> - Phát triển API quản lý Ví cá nhân (Wallets) <br> - Kiểm thử API thông qua Swagger/Postman | 12/06/2026 | 12/06/2026 | |

### Kết quả đạt được tuần 5

* Hoàn thành thiết kế cấu trúc dữ liệu cơ sở cho dự án.
* Thiết lập thành công kết nối Database thông qua Entity Framework Core.
* Hoàn thiện phân hệ Authentication (Đăng nhập/Đăng ký) tạo tiền đề cho các chức năng bảo mật.
* Triển khai thành công các API quản lý danh mục và ví, hỗ trợ quản lý chi tiêu cá nhân.
