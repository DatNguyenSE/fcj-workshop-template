---
title: "Worklog Tuần 10"
date: 2026-07-13
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10

* Xây dựng Fullstack tính năng Trung tâm thông báo (Notification Center) với chuông báo Realtime.
* Ứng dụng WebSockets (SignalR) duy trì kết nối liên tục, ổn định giữa Server và Client.
* Xây dựng hệ thống Hỗ trợ khách hàng (Support Ticket) cho phép User gửi yêu cầu trợ giúp đến Admin.
* Thực hành bài lab **Workshop 5.5**: Cấu hình chi tiết IAM Policy cho VPC Endpoint để thắt chặt bảo mật kết nối tới S3.
* Xây dựng giao diện User Account Settings (Đổi ảnh đại diện, Cập nhật hồ sơ cá nhân).

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Phân tích nghiệp vụ hệ thống Thông báo. Thiết kế bảng `Notifications` trong DB hỗ trợ nhiều phân loại (Cảnh báo ngân sách, AI, Hệ thống, Quét hóa đơn).<br>- **Chiều:** Xây dựng CRUD API cho Thông báo. Cấu hình mở rộng SignalR Hub để mỗi khi có event tạo Thông báo mới dưới DB, Server sẽ push JSON data thẳng tới các User đang online. | 13/07/2026 | 13/07/2026 | [Real-time apps with SignalR](https://learn.microsoft.com/en-us/aspnet/core/signalr/introduction) |
| 3 | - **Sáng:** Code giao diện Chuông thông báo (Dropdown Menu) trên Angular Header. Làm hiệu ứng đếm số thông báo chưa đọc (Unread badge).<br>- **Chiều:** Test luồng Realtime Notification. Bị lỗi WebSocket connection drops (văng kết nối) liên tục khi để máy rảnh quá 1 phút, debug và thêm cấu hình `keepAliveIntervalInMilliseconds` cho client SignalR để fix. | 14/07/2026 | 14/07/2026 | [SignalR Configuration](https://learn.microsoft.com/en-us/aspnet/core/signalr/configuration) |
| 4 | - **Sáng:** Thiết kế luồng nghiệp vụ Support Ticket (Gửi yêu cầu hỗ trợ). Khởi tạo bảng `Tickets` và `TicketMessages` (Lưu lịch sử chat hỗ trợ). Viết API tạo Ticket.<br>- **Chiều:** Code giao diện Form tạo Ticket trên Frontend và làm màn hình chat qua lại giữa User và Admin. Test gửi file đính kèm lỗi lên S3 thông qua luồng Pre-signed URL đã làm ở Tuần 7. | 15/07/2026 | 15/07/2026 | [Customer Support UX Patterns](https://uxdesign.cc/customer-support-ux-best-practices-28c0b561b369) |
| 5 | - **Sáng:** Thực hành lab Workshop 5.5: Siết chặt an ninh cho Gateway VPC Endpoint của S3. Mặc định nó mở Full Access, giờ cần đổi thành Custom Policy.<br>- **Chiều:** Cấu hình Policy chỉ cho phép thao tác Get/Put đúng vào 1 Bucket `snaptics-invoices-dev`. Chạy thử API thì bị văng lỗi "Access Denied 403". Check log AWS CloudTrail phát hiện khai báo sai cú pháp ARN, đã fix lại `arn:aws:s3:::snaptics-invoices-dev/*` và chạy thông. | 16/07/2026 | 16/07/2026 | [VPC Endpoint Policies](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) |
| 6 | - **Sáng:** Xây dựng trang Account Settings UI (Giao diện cài đặt tài khoản, đổi thông tin cá nhân).<br>- **Chiều:** Tích hợp API cập nhật hồ sơ cá nhân. Cuối tuần họp team, Merge các nhánh feature của mọi người vào nhánh `develop`. Gặp conflict ở file `app.module.ts` (do ai cũng khai báo Component mới), cả team ngồi gỡ conflict và build lại thành công. | 17/07/2026 | 17/07/2026 | [Resolving Git Conflicts](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line) |

### Kết quả đạt được tuần 10

* Hoàn thiện tính năng Notification Realtime đỉnh cao, xử lý triệt để lỗi rớt mạng WebSocket bằng cơ chế Ping/Pong (Keep-alive).
* Xây dựng xong bộ khung cốt lõi cho tính năng Support Ticket, sẵn sàng cho Admin Panel ở tuần tới.
* Nâng cao kỹ năng bảo mật AWS (SecOps) thông qua việc cấu hình chính xác VPC Endpoint IAM Policies, chặn nguy cơ lộ lọt dữ liệu ra các Bucket ngoài dự án.
* Rèn luyện kỹ năng làm việc nhóm thực chiến thông qua việc xử lý Conflict Git "khó nhằn" khi merge code chung.
