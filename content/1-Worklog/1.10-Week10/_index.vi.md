---
title: "Worklog Tuần 10"
date: 2026-07-13
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10

* Xây dựng Fullstack tính năng Danh sách Thông báo (Notification Center) và Header Dropdown Menu.
* Tích hợp SignalR để đẩy thông báo realtime từ Backend .NET lên Frontend Angular.
* Thiết lập API và phân loại thông báo: Quét hóa đơn, Cảnh báo ngân sách, Gợi ý AI, Lời mời ví gia đình.
* Xây dựng Fullstack tính năng Yêu cầu Hỗ trợ (Support Ticket) bao gồm API quản lý Ticket và giao diện Form tạo Ticket, luồng thảo luận.
* Thực hành bài lab **Workshop 5.5**: Cấu hình VPC Endpoint IAM Policies để siết chặt an ninh và giới hạn quyền truy cập tài nguyên Amazon S3.
* Xây dựng trang Cài đặt Tài khoản Người dùng (User Account Settings UI) và tích hợp API cập nhật hồ sơ.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Thiết kế Database schema cho Notification và Support Ticket.<br>- Viết API lấy danh sách thông báo và đánh dấu đã đọc.<br>- Thiết kế giao diện Notification Dropdown Menu trên Top Header và biểu tượng Chuông thông báo đếm số chưa đọc. | 13/07/2026 | 13/07/2026 | [Notification System UX](https://uxdesign.cc/) |
| 3 | - Tích hợp SignalR WebSockets vào Backend .NET và Frontend Angular để đẩy thông báo realtime.<br>- Phân loại thiết kế UI cho các mẫu thông báo: Quét hóa đơn, Cảnh báo ngân sách, Gợi ý tài chính, Lời mời tham gia Ví.<br>- Kiểm thử luồng nhận thông báo khi có giao dịch mới. | 14/07/2026 | 14/07/2026 | [SignalR with Angular](https://learn.microsoft.com/en-us/aspnet/core/signalr/javascript-client) |
| 4 | - Xây dựng các API CRUD cho Support Ticket và luồng thảo luận tin nhắn (Discussion Thread).<br>- Thiết kế bố cục trang Yêu cầu Hỗ trợ (Support Ticket Page) trên Angular.<br>- Xây dựng Bảng danh sách Ticket đã gửi và Form Tạo Ticket hỗ trợ mới với validation. | 15/07/2026 | 15/07/2026 | [Helpdesk UI Patterns](https://dribbble.com/) |
| 5 | - **Thực hành Workshop 5 (Phần 5 - VPC Endpoint Policies):**<br>&emsp; + Tìm hiểu mô hình bảo mật phân lớp bằng VPC Endpoint IAM Policy ([Workshop VPC Endpoint Policies](5-Workshop/5.5-Policy/)).<br>&emsp; + Soạn thảo bản chính sách JSON Endpoint Policy gắn vào VPC Endpoint để chỉ cho phép truy cập duy nhất S3 Bucket của dự án Snaptics.<br>&emsp; + Chạy lệnh kiểm thử từ chối truy cập (Access Denied) khi truy vấn tới các S3 Buckets ngoài danh sách cho phép. | 16/07/2026 | 16/07/2026 | [Workshop VPC Endpoint Policies](5-Workshop/5.5-Policy/)<br>[VPC Endpoint Policy Reference](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-access.html) |
| 6 | - Tích hợp API và thiết kế màn hình Xem chi tiết Ticket (Ticket Detail & Discussion Thread UI).<br>- Xây dựng trang Cài đặt Tài khoản Người dùng và tích hợp API cập nhật thông tin cá nhân, đổi mật khẩu.<br>- Kiểm tra lỗi form validation và tối ưu responsive tuần 10. | 17/07/2026 | 17/07/2026 | [Account Settings Layout](https://refactoringui.com/) |

### Kết quả đạt được tuần 10

* Hoàn thành trung tâm Thông báo (Notification Center) Fullstack, tích hợp thành công SignalR đẩy thông báo realtime mượt mà.
* Phân loại và thiết kế trực quan cho 4+ nhóm thông báo chính, đảm bảo dữ liệu đồng bộ với Backend.
* Hoàn thành tính năng Quản lý Yêu cầu Hỗ trợ (Support Ticket) chuyên nghiệp từ API đến giao diện người dùng.
* Thực hành thành công bài lab Workshop 5.5: Soạn thảo và gắn thành công VPC Endpoint Policy, ngăn chặn truy cập trái phép tới các S3 Buckets không thuộc dự án.
* Tích hợp thành công luồng trao đổi thảo luận chi tiết trong Ticket giữa User và Đội ngũ Hỗ trợ.
* Hoàn thành trang Cài đặt Tài khoản Người dùng gọn gàng, bảo mật và gọi API thay đổi mật khẩu thành công.
* Đảm bảo tính nhất quán thẩm mỹ và khả năng phản hồi mượt mà trên mọi kích thước màn hình.
