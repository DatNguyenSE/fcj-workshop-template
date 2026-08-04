---
title: "Tự đánh giá"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### TỰ ĐÁNH GIÁ

Trong thời gian thực tập từ **11/05/2026 đến 07/08/2026**, tôi chủ yếu làm ở vị trí Backend Developer cho một dự án quản lý chi tiêu. Tôi mới bắt đầu tìm hiểu AWS nên mục tiêu chính là nắm kiến thức nền tảng, học theo các best practice cơ bản và từng bước kết nối việc phát triển Backend với hạ tầng Cloud.

Tôi làm việc với .NET 10 Web API, SQL Server và Entity Framework Core. Song song với việc phát triển chức năng, tôi thực hành các dịch vụ AWS qua bài lab và các phần việc của dự án. Qua đó, tôi hiểu rằng một tính năng Backend không chỉ cần chạy đúng mà còn cần cấu hình an toàn, lưu trữ phù hợp, có khả năng theo dõi và được triển khai trong môi trường hợp lý.

### Các đóng góp và nội dung kỹ thuật chính

#### 1. Phát triển Backend API và cơ sở dữ liệu

* Xây dựng và cập nhật các API .NET 10 cho người dùng, danh mục, nguồn thu, ngân sách và khoản chi.
* Dùng Entity Framework Core để tạo model SQL Server, thiết lập quan hệ và quản lý migration.
* Thêm validation, authorization và xử lý lỗi cơ bản để mỗi người dùng chỉ thao tác trên dữ liệu phù hợp.
* Kiểm thử cả trường hợp hợp lệ và dữ liệu sai, thay vì chỉ kiểm tra luồng thành công.

#### 2. Xác thực và tích hợp dịch vụ Cloud

* Xây dựng luồng đăng ký, đăng nhập bằng JWT và bảo vệ các API riêng tư.
* Tích hợp Amazon S3 để lưu ảnh hóa đơn, chứng từ thay vì chỉ lưu trên máy local.
* Tìm hiểu Azure Document Intelligence và Google Gemini để đọc hóa đơn, trích xuất khoản chi rồi map về entity của Backend.
* Dùng AWS SQS và background worker để tách phần xử lý AI lâu khỏi request upload, đồng thời dùng SignalR cập nhật trạng thái.

#### 3. Best practice AWS và nền tảng Cloud

* Thực hành phân quyền IAM ở mức cần thiết, giữ cấu hình an toàn và không để API key trong source code.
* Tìm hiểu AWS Systems Manager Parameter Store để đưa cấu hình ứng dụng ra khỏi mã nguồn.
* Nắm được vai trò cơ bản của S3, SQS, VPC, subnet, NAT Gateway, ECS Fargate và Application Load Balancer trong kiến trúc Cloud.
* Tạo Docker image cho Backend và làm quen với quy trình đưa container lên AWS.

### Tự đánh giá

Tôi tự đánh giá mình là người mới ở lĩnh vực Cloud, đã có tiến bộ tốt nhưng vẫn cần thêm nhiều thời gian thực hành với hệ thống production.

| STT | Tiêu chí | Đánh giá | Nhận xét |
| :-: | :--- | :-: | :--- |
| 1 | **Kiến thức chuyên môn** | Đang phát triển | Có nền tảng tốt hơn về Backend .NET và kiến thức AWS cơ bản, nhưng chưa tự tin với kiến trúc Cloud phức tạp. |
| 2 | **Khả năng học hỏi** | Tốt | Có thể đọc tài liệu, đặt câu hỏi đúng trọng tâm và áp dụng góp ý vào task mới. |
| 3 | **Tính chủ động** | Đang phát triển | Có cố gắng tìm nguyên nhân trước khi hỏi; cần chủ động hơn trong việc đề xuất giải pháp hoàn chỉnh. |
| 4 | **Kỷ luật** | Tốt | Tuân thủ lịch học, nội quy và duy trì worklog hàng tuần. |
| 5 | **Giao tiếp** | Tốt | Biết báo cáo tiến độ và vấn đề với mentor, nhưng cần trình bày các chi tiết kỹ thuật ngắn gọn hơn. |
| 6 | **Làm việc nhóm** | Tốt | Phối hợp với các thành viên về API contract, kiểm thử và các task triển khai, đồng thời tiếp nhận góp ý khi review. |
| 7 | **Giải quyết vấn đề** | Đang phát triển | Có thể xử lý các lỗi thường gặp về API, database và cấu hình; cần thêm kinh nghiệm troubleshooting trên môi trường thực tế. |
| 8 | **Đóng góp cho dự án** | Tốt | Đóng góp các API Backend, phần tích hợp Cloud và chuẩn bị triển khai cho luồng chính của hệ thống quản lý chi tiêu. |

### CẦN CẢI THIỆN

* **Củng cố nền tảng AWS:** Tiếp tục thực hành IAM, VPC, networking, storage, monitoring và quản lý chi phí. Tôi cần hiểu lý do chọn dịch vụ thay vì chỉ nhớ các bước trong bài lab.

* **Nâng cao kỹ năng triển khai:** Thực hành Docker, ECS, load balancer, DNS, HTTPS, CI/CD, đọc log và rollback trong các môi trường nhỏ nhưng đầy đủ.

* **Áp dụng bảo mật và độ tin cậy:** Tìm hiểu thêm về quản lý secret, least privilege, backup, encryption, validation, retry và xử lý lỗi cho Backend service.

* **Phát triển vai trò Backend Developer:** Cải thiện thiết kế API, automated testing, hiệu năng database và clean code, đồng thời tiếp tục rèn cách trao đổi rõ ràng với mentor và các thành viên trong nhóm.
