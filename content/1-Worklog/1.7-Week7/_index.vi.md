---
title: "Worklog Tuần 7"
date: 2026-06-22
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7

* Chuyển database của hệ thống từ môi trường local sang Amazon RDS.
* Tạo DB Subnet Group và triển khai RDS trong các Private Subnet thuộc nhiều Availability Zone.
* Cấu hình Security Group cho RDS, chỉ cho phép Backend truy cập database và tắt Public Access.
* Thực hiện migration schema, dữ liệu và cập nhật connection string của Backend.
* Chuyển việc lưu trữ ảnh từ local sang Amazon S3 và cấu hình quyền truy cập phù hợp.
* Kết nối Backend với RDS và S3, kiểm thử các chức năng đọc/ghi dữ liệu và upload ảnh.
* Ghi chép kiến trúc, cấu hình và kết quả kiểm thử để làm cơ sở triển khai các phần AWS tiếp theo.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Rà soát kiến trúc VPC và xác định các Private Subnet dành cho database.<br>- Tạo DB Subnet Group trên nhiều Availability Zone.<br>- Chuẩn bị Security Group và quy tắc kết nối giữa Backend với RDS. | 22/06/2026 | 22/06/2026 | [Amazon RDS in a VPC](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html) |
| 3 | - Tạo Amazon RDS Microsoft SQL Server với Public Access được tắt.<br>- Cấu hình Security Group chỉ cho phép Backend Security Group truy cập cổng SQL Server (1433).<br>- Kiểm tra kết nối từ Backend đến RDS trong Private Subnet. | 23/06/2026 | 23/06/2026 | [RDS Security](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.html) |
| 4 | - Thực hiện migration schema và dữ liệu từ database local sang RDS.<br>- Cập nhật biến môi trường và connection string của Backend.<br>- Kiểm thử các thao tác tạo, đọc, cập nhật và xóa dữ liệu trên RDS. | 24/06/2026 | 24/06/2026 | [Migrating Data to Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.html) |
| 5 | - Tạo S3 Bucket để lưu trữ ảnh thay cho local storage.<br>- Cấu hình IAM permission cần thiết cho Backend upload và truy xuất ảnh.<br>- Cập nhật Backend và kiểm thử luồng upload, lưu đường dẫn và lấy ảnh từ S3. | 25/06/2026 | 25/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) |
| 6 | - Kiểm thử toàn bộ luồng Backend kết nối RDS và S3.<br>- Rà soát quyền truy cập, dữ liệu và các lỗi migration.<br>- Ghi chép kiến trúc, cấu hình đã thực hiện và tổng kết tuần 7. | 26/06/2026 | 26/06/2026 | [Amazon RDS Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)<br>[Amazon S3 Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) |

### Kết quả đạt được tuần 7

* Triển khai Amazon RDS Microsoft SQL Server trong Private Subnets với Public Access được tắt.
* Tạo DB Subnet Group và cấu hình Security Group chỉ cho phép Backend truy cập RDS.
* Migration thành công schema và dữ liệu từ database local sang RDS.
* Cập nhật Backend sử dụng RDS và kiểm thử các thao tác dữ liệu trên database mới.
* Chuyển lưu trữ ảnh từ local sang S3 và cấu hình quyền cho Backend upload, truy xuất ảnh.
* Kiểm thử thành công kết nối giữa Backend, RDS và S3.
* Hoàn thiện tài liệu cấu hình AWS nền tảng để tiếp tục triển khai các thành phần khác ở những tuần sau.
