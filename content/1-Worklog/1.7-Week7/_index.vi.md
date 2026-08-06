---
title: "Worklog Tuần 7"
date: 2026-06-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7

* Triển khai hệ thống cơ sở dữ liệu lên môi trường Cloud.
* Thực hiện di chuyển dữ liệu (Migration) từ môi trường Local.
* Thiết lập hệ thống lưu trữ tĩnh trên AWS S3.
* Tích hợp thành công luồng tải ảnh an toàn bằng Pre-signed URL.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|------|-----------|-------------|----------------|---------------|
| 2 | **Triển khai Database lên AWS:** <br> - Xem xét kiến trúc mạng VPC <br> - Tạo DB Subnet Group <br> - Khởi tạo RDS SQL Server trong Private Subnet | 22/06/2026 | 22/06/2026 | |
| 3 | **Migration Database:** <br> - Xuất dữ liệu từ Local SQL Server <br> - Chạy script migrate schema và data lên RDS <br> - Cập nhật Connection String của Backend | 23/06/2026 | 23/06/2026 | |
| 4 | **Amazon S3:** <br> - Tìm hiểu dịch vụ lưu trữ Amazon S3 <br> - Tạo S3 Bucket lưu trữ ảnh hóa đơn <br> - Cấu hình bảo mật chặn Public Access | 24/06/2026 | 24/06/2026 | |
| 5 | **Tích hợp S3 SDK:** <br> - Cài đặt thư viện AWS SDK for .NET <br> - Viết service sinh Pre-signed URL <br> - Xử lý logic tải ảnh thông qua Backend | 25/06/2026 | 25/06/2026 | |
| 6 | **Kiểm thử luồng Upload:** <br> - Tích hợp gọi API upload từ Frontend Angular <br> - Xử lý cấu hình CORS trên S3 Bucket <br> - Kiểm tra toàn bộ luồng lưu trữ hình ảnh E2E | 26/06/2026 | 26/06/2026 | |

### Kết quả đạt được tuần 7

* Đưa thành công cơ sở dữ liệu lên nền tảng Amazon RDS với độ bảo mật cao.
* Nắm vững quy trình Migration dữ liệu an toàn.
* Thiết lập hoàn chỉnh kho lưu trữ Amazon S3.
* Triển khai luồng Upload ảnh an toàn, bảo mật thông qua Pre-signed URL.
