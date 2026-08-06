---
title: "Worklog Tuần 11"
date: 2026-07-20
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11

* Thiết kế và xây dựng phân hệ Quản trị viên (Admin Panel) với giao diện độc lập hoàn toàn với User.
* Xây dựng luồng phân quyền Role-Based Access Control (RBAC) chặt chẽ ở cả Frontend (Route Guards) và Backend (Attributes).
* Phát triển các tính năng quản trị: Quản lý người dùng (Block/Unblock), Quản lý Support Ticket.
* Tích hợp công cụ Hangfire để quản lý trực quan các Background Jobs (Task chạy ngầm) trên Dashboard.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Thiết kế UI bộ khung Layout Admin chuyên biệt (Sidebar tối màu, Header riêng). Cài đặt `Angular CanActivate AdminGuard` để chặn User thường truy cập vào `/admin`.<br>- **Chiều:** Xây dựng tính năng Quản lý Người dùng (User Management). API phân trang danh sách Users. UI có tính năng Search và bộ lọc Trạng thái (Active/Locked). | 20/07/2026 | 20/07/2026 | [Angular Route Guards](https://angular.io/guide/router-tutorial-toh#milestone-5-route-guards) |
| 3 | - **Sáng:** Code tính năng Khóa/Mở khóa tài khoản người dùng từ Admin. Thử test bằng cách khóa tài khoản chính mình, kết quả Session bị vô hiệu hóa và đá văng ra màn hình đăng nhập ngay lập tức.<br>- **Chiều:** Code tính năng Quản lý Support Ticket bên phía Admin. Hỗ trợ chức năng xem lịch sử Ticket và chat phản hồi lại User trực tiếp trên bảng điều khiển. | 21/07/2026 | 21/07/2026 | [ASP.NET Core Authorization](https://learn.microsoft.com/en-us/aspnet/core/security/authorization/roles) |
| 4 | - **Sáng:** Phân quyền API phía Backend bằng cách đánh dấu Attribute `[Authorize(Roles = "Admin")]` lên các Controllers nhạy cảm.<br>- **Chiều:** Test gọi thử API Admin bằng JWT Token của User thông thường. Bị trả về lỗi `403 Forbidden` thay vì `401 Unauthorized`, qua đó hiểu rõ thực tế sự khác biệt giữa khái niệm Authentication (Xác thực) và Authorization (Phân quyền). | 22/07/2026 | 22/07/2026 | [401 vs 403 Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/403) |
| 5 | - **Sáng:** Cài đặt thư viện Hangfire lên Backend để quản lý các Background Jobs (ví dụ: Job quét hóa đơn SQS, Job dọn rác DB cũ).<br>- **Chiều:** Bị lỗi lộ lọt giao diện Hangfire Dashboard ra public. Tìm hiểu và gắn bảo mật (Hangfire Authorization Filter) chỉ cho phép tài khoản Admin truy cập. Nếu không cấu hình, ai cũng có thể vào `/hangfire` và tự ý kích hoạt chạy Job. | 23/07/2026 | 23/07/2026 | [Hangfire Dashboard Security](https://docs.hangfire.io/en/latest/configuration/using-dashboard.html) |
| 6 | - **Sáng:** Thiết kế trang 404 Not Found và trang Bảo trì Hệ thống (System Maintenance Page) phòng hờ khi Server có sự cố.<br>- **Chiều:** Rà soát lại toàn bộ Role/Permission trên hệ thống. Sửa các lỗi ẩn/hiện nút bấm tùy theo Role trên UI. Gom code sạch sẽ và chuẩn bị cho giai đoạn ghép nối tích hợp cuối cùng. | 24/07/2026 | 24/07/2026 | [UX Error Pages](https://uxdesign.cc/how-to-design-404-page-12345) |

### Kết quả đạt được tuần 11

* Xây dựng thành công hệ thống Admin Panel độc lập, quản lý triệt để được Users và Tickets.
* Triển khai hoàn hảo cơ chế phân quyền RBAC đa lớp: Chặn giao diện bằng Angular Guard và chặn truy cập Data bằng .NET Authorization.
* Tích hợp thành công Hangfire làm trình giám sát Job chạy ngầm, và đảm bảo Dashboard cấu hình bảo mật đúng cách.
* Hiểu sâu sắc và xử lý chuẩn xác 2 mã lỗi kinh điển trong bảo mật: 401 (Chưa đăng nhập) và 403 (Không đủ quyền).
