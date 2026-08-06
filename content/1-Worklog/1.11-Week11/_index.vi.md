---
title: "Worklog Tuần 11"
date: 2026-07-20
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11

* Phát triển phân hệ Quản trị (Admin Panel) với giao diện độc lập.
* Thiết lập hệ thống phân quyền (Role-Based Access Control) chặt chẽ.
* Tích hợp công cụ giám sát Background Jobs (Hangfire).
* Tối ưu hóa các màn hình lỗi của hệ thống.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|------|-----------|-------------|----------------|---------------|
| 2 | **Giao diện Admin:** <br> - Xây dựng Layout riêng cho Admin <br> - Cấu hình Angular CanActivate <br> - Xây dựng trang Quản lý User (Tìm kiếm, Lọc trạng thái) | 20/07/2026 | 20/07/2026 | |
| 3 | **Role-Based Access Control:** <br> - Cấu hình Authorization `[Authorize(Roles)]` trên .NET <br> - Phân biệt Authentication và Authorization <br> - Kiểm tra và chặn truy cập trái phép | 21/07/2026 | 21/07/2026 | |
| 4 | **Quản lý Ticket (Admin):** <br> - Xây dựng UI danh sách Ticket phía Admin <br> - Tích hợp API phản hồi người dùng <br> - Xử lý luồng khóa/mở khóa tài khoản User | 22/07/2026 | 22/07/2026 | |
| 5 | **Hangfire Background Jobs:** <br> - Cài đặt thư viện Hangfire <br> - Cấu hình Dashboard giám sát các Job chạy ngầm <br> - Chuyển đổi Worker SQS sang mô hình Hangfire | 23/07/2026 | 23/07/2026 | |
| 6 | **Bảo mật Hangfire:** <br> - Viết Authorization Filter cho Dashboard <br> - Giới hạn quyền truy cập chỉ cho Admin <br> - Thiết kế các trang thông báo lỗi (404, 403) | 24/07/2026 | 24/07/2026 | |

### Kết quả đạt được tuần 11

* Triển khai thành công phân hệ Quản trị với đầy đủ tính năng thiết yếu.
* Hệ thống phân quyền RBAC đa lớp hoạt động hiệu quả.
* Quản lý Background Jobs trực quan, an toàn thông qua Hangfire.
* Hoàn thiện trải nghiệm xử lý lỗi (Error Handling) cho người dùng.
