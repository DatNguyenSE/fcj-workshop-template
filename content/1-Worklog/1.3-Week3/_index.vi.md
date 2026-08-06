---
title: "Worklog Tuần 3"
date: 2026-05-25
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3

* Tìm hiểu chuyên sâu về dịch vụ tính toán Amazon EC2 (Instance Types, AMI, EBS Volume types).
* Thực hành kết nối máy chủ EC2 qua giao thức SSH và chạy thử ứng dụng web mẫu (Nginx).
* Nghiên cứu dịch vụ cơ sở dữ liệu quản trị Amazon RDS (PostgreSQL/SQL Server, Multi-AZ Deployment, Read Replicas).
* Triển khai Amazon RDS Instance nằm hoàn toàn trong Private Subnet của VPC.
* Thử nghiệm kết nối an toàn từ máy chủ EC2 đến cơ sở dữ liệu Amazon RDS qua Security Group.
* Thực hành bài lab **Workshop 5.3**: Tạo Gateway VPC Endpoint kết nối máy chủ EC2 với Amazon S3 trong môi trường nội bộ VPC không đi qua Internet.
* Thực hành quy trình Sao lưu (DB Snapshot) và Khôi phục (Restore) cơ sở dữ liệu trên Amazon RDS.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Tìm hiểu chuyên sâu về Amazon EC2: phân loại Instance Types (t3, c5, r5), cách chọn Amazon Machine Image (AMI) và EBS Volumes.<br>- **Chiều:** Khởi tạo EC2 Ubuntu, tải Key Pair (`.pem`). Bị lỗi `SSH Permission Denied` do file `.pem` quá mở (quyền public), đã tìm hiểu và chạy lệnh `chmod 400 key.pem` để fix. Cài Nginx lên EC2 và test trang default thành công. | 25/05/2026 | 25/05/2026 | [Amazon EC2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) |
| 3 | - **Sáng:** Đọc tài liệu Amazon RDS, phân biệt việc tự quản trị DB trên EC2 và dùng dịch vụ Managed RDS. Tìm hiểu cơ chế Multi-AZ (High Availability).<br>- **Chiều:** Khởi tạo DB Subnet Group và triển khai một Amazon RDS SQL Server Instance đặt hoàn toàn trong Private Subnet. | 26/05/2026 | 26/05/2026 | [Amazon RDS User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) |
| 4 | - **Sáng:** Kết nối từ máy EC2 (Public) vào RDS (Private) để test. Bị lỗi `Connection Timeout`. Debug và phát hiện do RDS Security Group đóng kín, đã add thêm rule Inbound từ EC2 Security Group và kết nối SQL Server qua port 1433 thành công.<br>- **Chiều:** Thực hành sao lưu RDS: tạo DB Snapshot thủ công, xóa thử RDS hiện tại và thực hiện Restore lại từ Snapshot vừa tạo. | 27/05/2026 | 27/05/2026 | [RDS Backups & Restore](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html) |
| 5 | - **Sáng:** Thực hành Workshop 5.3: Khởi tạo Gateway VPC Endpoint cho dịch vụ Amazon S3. Cập nhật Route Table của Private Subnet, định tuyến traffic `com.amazonaws.<region>.s3` về Endpoint.<br>- **Chiều:** Dùng AWS CLI trên EC2 Private gõ lệnh `aws s3 ls`. Xác nhận gọi API của S3 thành công hoàn toàn qua mạng nội bộ AWS, không cần đi qua Public Internet (nhờ VPC Endpoint). | 28/05/2026 | 28/05/2026 | [VPC Gateway Endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-s3.html) |
| 6 | - **Sáng:** Review lại toàn bộ kiến trúc VPC, EC2, RDS đã học và thực hành trong 3 tuần đầu tiên.<br>- **Chiều:** Dọn dẹp tài nguyên lab (Terminate EC2, Xóa RDS Snapshot & Database) để tối ưu chi phí. Vẽ hoàn chỉnh sơ đồ kiến trúc hệ thống mạng hiện tại lên Draw.io và update file tài liệu nhóm. | 29/05/2026 | 29/05/2026 | [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) |

### Kết quả đạt được tuần 3

* Nắm rõ cách chọn lọc tài nguyên điện toán (Instance Type, EBS) phù hợp cho EC2. Vượt qua các lỗi bảo mật SSH cơ bản.
* Khởi tạo thành công Amazon RDS SQL Server đặt an toàn trong Private Subnet.
* Hiểu rõ cơ chế kết nối chéo giữa các Security Group (Security Group chaining), cấu hình thành công việc cấp quyền EC2 gọi vào RDS.
* Thực hành thành công Snapshot & Restore trên hệ thống DB.
* Hiểu và thực hành mượt mà VPC Endpoint để tăng cường bảo mật khi các server nội bộ cần giao tiếp với S3.
