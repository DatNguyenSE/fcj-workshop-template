---
title: "Worklog Tuần 8"
date: 2026-06-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8

* Thiết kế kiến trúc xử lý bất đồng bộ (Asynchronous processing) dùng hàng đợi tin nhắn Amazon SQS.
* Tích hợp AI Azure Document Intelligence (Azure OCR) để tự động bóc tách thông tin hóa đơn (Merchant, Total, Date).
* Sử dụng AWS Systems Manager Parameter Store để lưu trữ các API Key của bên thứ 3 một cách an toàn.
* Xây dựng Background Worker (Hosted Service) trên .NET Backend để liên tục kéo (pull) tin nhắn từ SQS và xử lý hình ảnh.
* Tích hợp SignalR WebSocket để đẩy thông báo kết quả thời gian thực (Real-time) về cho người dùng trên Frontend.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Khởi tạo hàng đợi Amazon SQS (Standard Queue) trên AWS Console.<br>- **Chiều:** Đăng ký tài khoản Microsoft Azure, khởi tạo dịch vụ Document Intelligence (OCR) và lấy API Key, Endpoint. Đưa 2 Key này vào lưu trữ bảo mật tại AWS Systems Manager Parameter Store thay vì để trong file config. | 29/06/2026 | 29/06/2026 | [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) |
| 3 | - **Sáng:** Code tính năng gửi (Publish) message chứa S3 Image URI vào SQS mỗi khi người dùng upload hóa đơn xong.<br>- **Chiều:** Code Background Worker (`IHostedService`) trên .NET để pull message từ SQS. Bị lỗi worker kéo chung 1 message nhiều lần, tìm hiểu và nâng cấu hình `Visibility Timeout` của SQS lên 30s vì quá trình AI phân tích ảnh tốn nhiều thời gian. | 30/06/2026 | 30/06/2026 | [Amazon SQS Visibility Timeout](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html) |
| 4 | - **Sáng:** Viết Service gọi API Azure OCR trong Background Worker. Truyền URI ảnh S3 sang Azure phân tích.<br>- **Chiều:** Parse dữ liệu JSON từ Azure trả về, mapping các trường Merchant Name, Total Amount, Transaction Date sang Object C# và lưu bản nháp vào RDS. | 01/07/2026 | 01/07/2026 | [Azure Document Intelligence REST API](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/) |
| 5 | - **Sáng:** Bị lỗi Exception sập worker do JSON từ Azure trả về bị Null một số trường (do test bằng hình hóa đơn mờ/rách). Debug, viết thêm các câu lệnh check Null an toàn (Null-conditional operators).<br>- **Chiều:** Cấu hình thư viện SignalR trên Backend .NET. Đẩy thông báo báo hiệu trạng thái quét "Thành công/Thất bại" realtime về Frontend Angular. | 02/07/2026 | 02/07/2026 | [SignalR in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/signalr/introduction) |
| 6 | - **Sáng:** Code giao diện Frontend (Review Invoice Form) cho phép User xem lại và xác nhận (hoặc chỉnh sửa) các thông tin mà AI vừa bóc tách ra.<br>- **Chiều:** Test chịu tải nhẹ hệ thống: Nhấn nút upload cùng lúc 10 ảnh hóa đơn. Kiểm tra AWS SQS Queue và quan sát Worker rút từng message ra xử lý tuần tự, không bị rớt cái nào. Vẽ sơ đồ luồng dữ liệu SQS -> Azure lên Draw.io. | 03/07/2026 | 03/07/2026 | [Design Patterns: Queue-Based Load Leveling](https://learn.microsoft.com/en-us/azure/architecture/patterns/queue-based-load-leveling) |

### Kết quả đạt được tuần 8

* Triển khai thành công kiến trúc xử lý bất đồng bộ bằng Amazon SQS, giúp Frontend không bị treo khi chờ xử lý ảnh lâu.
* Tích hợp thành công giải pháp AI Azure OCR, bóc tách chính xác thông tin hóa đơn tiếng Việt/tiếng Anh.
* Hiểu sâu về cơ chế Visibility Timeout của hàng đợi tin nhắn và xử lý lỗi duplicate processing.
* Quản lý API keys an toàn tuyệt đối với AWS Parameter Store.
* Tích hợp SignalR WebSocket hoàn hảo, mang lại trải nghiệm Real-time mượt mà cho người dùng (Upload xong đi làm việc khác, máy tự báo khi xong).
