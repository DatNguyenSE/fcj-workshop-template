---
title: "Worklog Tuần 13"
date: 2026-08-03
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Mục tiêu tuần 13

* Đóng gói và biên dịch toàn bộ hệ thống (Build Production).
* Triển khai hệ thống lên hạ tầng Cloud-native (Amplify & ECS).
* Cấu hình tên miền (Domain) và bảo mật SSL/HTTPS.
* Bàn giao đồ án và dọn dẹp tài nguyên.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|------|-----------|-------------|----------------|---------------|
| 2 | **Build Production:** <br> - Dịch bản Frontend Angular cho môi trường Production <br> - Đóng gói Backend thành Docker Image <br> - Push Image lên kho chứa Amazon ECR | 03/08/2026 | 03/08/2026 | |
| 3 | **Triển khai Frontend:** <br> - Đưa bản build Frontend lên AWS Amplify <br> - Cấu hình Rewrite/Redirect Rules cho Single Page App <br> - Kiểm tra truy cập qua tên miền mặc định | 04/08/2026 | 04/08/2026 | |
| 4 | **Triển khai Backend (ECS):** <br> - Khởi tạo Cluster và Task Definition <br> - Triển khai ECS Fargate chạy container <br> - Thiết lập Application Load Balancer (ALB) | 05/08/2026 | 05/08/2026 | |
| 5 | **Bảo mật SSL/HTTPS:** <br> - Tạo chứng chỉ qua dịch vụ AWS Certificate Manager (ACM) <br> - Gắn SSL vào ALB để chạy giao thức HTTPS <br> - Cấu hình Route53 trỏ Custom Domain về ALB | 06/08/2026 | 06/08/2026 | |
| 6 | **Tối ưu và Bàn giao:** <br> - Cấu hình Header cho phép WebSocket chạy qua ALB <br> - Thực hành lab dọn dẹp sạch sẽ tài nguyên rác (VPC Endpoints, Test EC2) <br> - Demo và chính thức nghiệm thu dự án Snaptics | 07/08/2026 | 07/08/2026 | |

### Kết quả đạt được tuần 13

* Hoàn thành triển khai dự án lên môi trường AWS chuẩn doanh nghiệp.
* Vận hành trơn tru kiến trúc Cloud-native thực thụ (Serverless & Containers).
* Giải quyết triệt để các vấn đề liên quan đến mạng, chứng chỉ bảo mật và Domain.
* Kết thúc thành công tốt đẹp chặng đường 13 tuần FCJ Workforce với sản phẩm hoàn chỉnh.
