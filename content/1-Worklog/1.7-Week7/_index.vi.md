---
title: "Worklog Tuần 7"
date: 2026-06-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7

* Chuyển đổi môi trường Cơ sở dữ liệu: Migrate toàn bộ dữ liệu từ Local SQL Server lên Amazon RDS.
* Áp dụng nguyên tắc bảo mật, đặt Amazon RDS hoàn toàn vào mạng Private Subnet.
* Thiết lập hệ thống lưu trữ tĩnh: Chuyển việc lưu trữ hình ảnh hóa đơn từ ổ cứng Local sang Amazon S3.
* Viết code Backend C# (.NET SDK for AWS) giao tiếp với S3 để upload ảnh và sinh `Pre-signed URL`.
* Kiểm thử luồng tích hợp: Frontend upload ảnh thẳng lên S3 an toàn mà không làm nghẽn băng thông của Backend.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Đánh giá lại kiến trúc VPC và khởi tạo DB Subnet Group.<br>- **Chiều:** Khởi tạo Amazon RDS SQL Server trong Private Subnet. Cấu hình Security Group chỉ cho phép IP từ Backend truy cập port 1433. | 22/06/2026 | 22/06/2026 | [Amazon RDS in a VPC](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html) |
| 3 | - **Sáng:** Export dữ liệu từ Local SQL Server, sinh script `.sql`.<br>- **Chiều:** Chạy script migrate schema và data lên RDS. Cập nhật Connection String trong `appsettings.json` của Backend trỏ về Endpoint của RDS. | 23/06/2026 | 23/06/2026 | [Migrating Data to Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.html) |
| 4 | - **Sáng:** Test API kết nối RDS. Bị lỗi `"SSL Provider... connection was successfully established... error occurred during login process"`. Debug và thêm `TrustServerCertificate=True` vào chuỗi kết nối để fix.<br>- **Chiều:** Tạo Amazon S3 Bucket `snaptics-invoices-dev`. Chặn hoàn toàn truy cập công cộng (Block All Public Access). | 24/06/2026 | 24/06/2026 | [SQL Server SSL error](https://learn.microsoft.com/en-us/troubleshoot/sql/database-engine/connect/tls-ssl-issues) |
| 5 | - **Sáng:** Cài đặt `AWSSDK.S3` cho Backend. Viết Service upload ảnh và sinh `Pre-signed URL` (giới hạn sống trong 15 phút) để trả về Frontend.<br>- **Chiều:** Frontend dùng Pre-signed URL để load ảnh. Trình duyệt báo lỗi CORS Policy chặn request ảnh. Truy cập AWS Console sửa lại file JSON CORS Policy trên S3 Bucket (allow Origin `http://localhost:4200`) và fix thành công. | 25/06/2026 | 25/06/2026 | [S3 Pre-signed URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/ShareObjectPreSignedURL.html) |
| 6 | - **Sáng:** Test E2E luồng User upload ảnh: Frontend gọi Backend lấy URL upload -> Upload thẳng file ảnh từ browser lên S3 (tiết kiệm băng thông server Backend).<br>- **Chiều:** Chuyển các thông tin nhạy cảm (AWS Access Key, Secret Key) vào biến môi trường cục bộ (Environment Variables), tuyệt đối không hard-code lên Github. Họp nhóm tổng kết tuần. | 26/06/2026 | 26/06/2026 | [Environment variables in .NET](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/environments) |

### Kết quả đạt được tuần 7

* Migration thành công database từ Local máy cá nhân lên môi trường Cloud (Amazon RDS) an toàn trong Private Subnet.
* Sửa thành công lỗi SSL Provider phổ biến khi .NET kết nối SQL Server RDS.
* Hoàn thiện luồng lưu trữ ảnh cực kỳ tối ưu và bảo mật bằng Amazon S3 kết hợp **Pre-signed URL**.
* Giải quyết triệt để sự cố CORS Policy của S3 chặn các domain bên ngoài.
* Áp dụng thực tiễn nguyên tắc bảo mật thông tin xác thực, lưu key an toàn vào biến môi trường cục bộ thay vì đẩy lên Git.
