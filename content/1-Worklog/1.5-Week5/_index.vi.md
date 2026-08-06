---
title: "Worklog Tuần 5"
date: 2026-06-08
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5

* Phối hợp cùng team xây dựng các thành phần cốt lõi cho hệ thống Snaptics.
* Thiết kế Database Schema, xác định các bảng, mối quan hệ và luồng dữ liệu.
* Xây dựng Backend API Authentication và cấu trúc Request/Response chuẩn.
* Khởi tạo Frontend SPA bằng Angular và thiết lập Design System Tokens.
* Tích hợp và kiểm thử API Đăng nhập/Đăng ký giữa Frontend và Backend.
* Phối hợp xử lý các lỗi phát sinh (CORS, Token, Validation) trong quá trình kết nối.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Thiết kế Database Schema chi tiết (Tables: Users, Wallets, Transactions, Categories).<br>- **Chiều:** Setup DBContext bằng Entity Framework Core. Bị lỗi Migration conflict khi team cùng tạo bảng, phải reset DB local, gom code và chạy lại file Migration gốc. | 08/06/2026 | 08/06/2026 | [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/) |
| 3 | - **Sáng:** Xây dựng cấu trúc API Response chuẩn (`ApiResponse<T>`) cho toàn hệ thống Backend.<br>- **Chiều:** Khởi tạo project Angular SPA. Cài đặt Tailwind CSS. Phân chia cấu trúc thư mục (core, shared, features) và tạo các Components cơ bản (Header, Sidebar). | 09/06/2026 | 09/06/2026 | [Angular Folder Structure](https://angular.io/guide/styleguide) |
| 4 | - **Sáng:** Code Backend API cho luồng Authentication (Đăng nhập, Đăng ký) và sinh mã JWT Token.<br>- **Chiều:** Dùng Postman test API Auth thành công. Tích hợp form Đăng nhập trên Angular gọi API. Trình duyệt báo lỗi CORS đỏ chót, đã fix bằng cách cấu hình lại `builder.Services.AddCors()` ở Backend. | 10/06/2026 | 10/06/2026 | [CORS in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/security/cors) |
| 5 | - **Sáng:** Thiết kế trang Main Layout của ứng dụng và Auth UI (Form Login/Register đẹp mắt).<br>- **Chiều:** Xử lý lưu JWT vào LocalStorage bên phía Frontend. Bị lỗi lấy sai payload từ Token, đã debug và viết lại hàm giải mã base64 JWT trên Angular. | 11/06/2026 | 11/06/2026 | [JWT Authentication](https://jwt.io/) |
| 6 | - **Sáng:** Xây dựng các API cơ bản để CRUD Danh mục (Categories) và Ví cá nhân (Wallets).<br>- **Chiều:** Bàn giao task tuần. Xử lý nốt API Quên mật khẩu. Cập nhật tài liệu API Auth lên Swagger để cả nhóm có thể test chéo. | 12/06/2026 | 12/06/2026 | [Swagger/OpenAPI](https://swagger.io/) |

### Kết quả đạt được tuần 5

* Hoàn thành thiết kế Database và triển khai thành công Entity Framework Core.
* Khởi tạo thành công project Angular, thiết lập kiến trúc thư mục chuẩn và tích hợp Tailwind CSS.
* Xây dựng xong luồng xác thực JWT Authentication cho Backend.
* Vượt qua các lỗi kinh điển khi tích hợp hệ thống: lỗi CORS Policy, lỗi parse JWT, và migration conflict.
* Hoàn thiện giao diện Auth UI và Main Layout, đảm bảo API kết nối thông suốt từ Client xuống Server.
