---
title: "Worklog Tuần 8"
date: 2026-06-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8

* Khởi tạo và cấu hình các dịch vụ AWS cốt lõi cho Backend: Amazon S3 (lưu trữ ảnh hóa đơn), Amazon SQS (hàng đợi xử lý bất đồng bộ).
* Cấu hình AWS Systems Manager Parameter Store để lưu trữ bảo mật các API Keys (Azure, Gemini) và chuỗi kết nối Database.
* Tích hợp dịch vụ Azure Document Intelligence vào Backend .NET để tự động trích xuất thông tin (Merchant, Total) từ ảnh hóa đơn.
* Xây dựng API `scan-bill` (Quét hóa đơn) phía Backend, xử lý luồng upload ảnh pre-signed URL S3, đẩy tin nhắn vào SQS và gọi Azure OCR.
* Tích hợp tính năng Quét hóa đơn lên Frontend Angular, cho phép người dùng tải ảnh lên và nhận kết quả bóc tách dữ liệu theo thời gian thực.
* Thiết lập Database RDS SQL Server và điều chỉnh kiến trúc Backend để kết nối an toàn trong VPC.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Khởi tạo Amazon S3 Bucket với chính sách bảo mật (Block Public Access) phục vụ lưu trữ hóa đơn riêng tư.<br>- Khởi tạo Amazon SQS Queue (kèm Dead Letter Queue) để xử lý hàng đợi phân tích hóa đơn bất đồng bộ.<br>- Cấu hình AWS Systems Manager Parameter Store lưu trữ AzureKey, GeminiKey và ConnectionStrings. | 29/06/2026 | 29/06/2026 | [Snaptics Proposal](2-Proposal/)<br>[AWS S3 & SQS Guide](https://aws.amazon.com/s3/) |
| 3 | - Thiết lập Amazon RDS for SQL Server trong Private Subnet và cấu hình Security Group.<br>- Viết code Backend .NET đọc cấu hình bảo mật từ Parameter Store thay vì `appsettings.json`.<br>- Cài đặt SDK AWS để Backend có thể giao tiếp với S3 (tạo Pre-signed URL) và SQS (gửi/nhận messages). | 30/06/2026 | 30/06/2026 | [AWS Systems Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) |
| 4 | - Đăng ký Azure Document Intelligence, lấy Endpoint và Key lưu vào AWS Parameter Store.<br>- Tích hợp SDK Azure Document Analysis Client vào Backend .NET.<br>- Xây dựng API `scan-bill`: Nhận yêu cầu quét, đẩy ảnh vào S3, truyền URI sang Azure OCR để trích xuất Merchant Name và Total Amount. | 01/07/2026 | 01/07/2026 | [Azure Document Intelligence](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/) |
| 5 | - Tích hợp Frontend Angular gọi API `scan-bill`.<br>- Thiết kế giao diện upload hóa đơn (Drag & Drop box), hiển thị trạng thái loading chờ xử lý.<br>- Xử lý dữ liệu trả về từ API và tự động điền (auto-fill) vào form nhập liệu Giao dịch mới trên giao diện. | 02/07/2026 | 02/07/2026 | [Angular File Upload](https://angular.io/guide/file-uploads) |
| 6 | - Kiểm thử toàn trình luồng Quét hóa đơn: Upload ảnh từ Angular -> S3 -> SQS -> Worker xử lý gọi Azure OCR -> Trả kết quả về Frontend.<br>- Xử lý các trường hợp ảnh mờ, sai định dạng hoặc OCR không nhận diện được.<br>- Ghi chép tài liệu API, sửa lỗi cấu hình AWS và tổng kết tuần 8. | 03/07/2026 | 03/07/2026 | [Postman API Testing](https://www.postman.com/) |

### Kết quả đạt được tuần 8

* Triển khai thành công các dịch vụ hạ tầng AWS cốt lõi (S3, SQS, RDS, Parameter Store) phục vụ hệ thống Snaptics.
* Bảo mật toàn bộ thông tin nhạy cảm (API Keys, Database Passwords) trên AWS Systems Manager Parameter Store.
* Tích hợp thành công Azure Document Intelligence vào Backend .NET, bóc tách chính xác dữ liệu từ hóa đơn.
* Hoàn thành API `scan-bill` xử lý luồng nghiệp vụ phức tạp kết hợp S3, SQS và AI OCR.
* Hoàn thiện giao diện Frontend cho phép người dùng upload ảnh hóa đơn và trải nghiệm tính năng bóc tách tự động mượt mà.
* Kiểm thử thành công luồng dữ liệu thông suốt từ Client đến Cloud Services (AWS & Azure).
