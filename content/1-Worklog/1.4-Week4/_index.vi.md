---
title: "Worklog Tuần 4"
date: 2026-06-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4

* Họp nhóm thống nhất chọn đề tài dự án **Snaptics** - Nền tảng quản lý chi tiêu cá nhân/gia đình và quét hóa đơn thông minh.
* Phân tích bài toán quản lý tài chính thực tế và xác định phạm vi tính năng MVP cho 2 nhóm người dùng: User và Admin.
* Nhận vai trò **Fullstack Developer**, chịu trách nhiệm thiết kế hệ thống, Backend API và giao diện UI/UX.
* Tìm kiếm các mẫu giao diện tham khảo, xây dựng Sitemap hệ thống và phác thảo User Flow chính.
* Thiết kế bộ Wireframe ban đầu cho các màn hình cốt lõi và thống nhất phong cách thiết kế UI (Design System tokens).
* Tìm hiểu các dịch vụ AWS hỗ trợ vận hành dự án: Elastic Load Balancer (ALB), Auto Scaling, CloudWatch.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Họp nhóm chốt đề tài dự án **Snaptics** (Quản lý chi tiêu & Quét hóa đơn bằng AI). Nhận vai trò Fullstack Developer.<br>- **Chiều:** Phân tích phạm vi bài toán (User/Admin). Khởi tạo Github repository, thống nhất luồng Git Flow (main, develop, feature branches) và phân quyền Collaborators. | 01/06/2026 | 01/06/2026 | [Proposal Snaptics](2-Proposal/) |
| 3 | - **Sáng:** Xây dựng Sitemap chi tiết các màn hình (Dashboard, Transactions, AI Chat, Wallet, Admin Panel).<br>- **Chiều:** Vẽ User Flow cho tính năng cốt lõi: Luồng User upload ảnh hóa đơn -> Hệ thống gửi AI OCR bóc tách dữ liệu -> Trả kết quả auto-fill form tạo Giao dịch mới. | 02/06/2026 | 02/06/2026 | [UI/UX Design Patterns](https://refactoringui.com/) |
| 4 | - **Sáng:** Phác thảo Wireframe trên Figma cho các trang chính. Thống nhất bộ Design System Tokens (Bảng màu Primary Dark Blue, Typography Inter Font, kiểu dáng Component).<br>- **Chiều:** Họp team chốt Tech-stack (Frontend: Angular 17, Backend: .NET 8 Web API). Cài đặt môi trường code ở máy cá nhân, tạo project template và đẩy commit khởi tạo lên Github. | 03/06/2026 | 03/06/2026 | [Modern Web Layouts](https://uxdesign.cc/) |
| 5 | - **Sáng:** Nghiên cứu kiến trúc triển khai dự án trên AWS: Application Load Balancer (ALB) làm màng lọc traffic và Auto Scaling Group (ASG) để co giãn Server.<br>- **Chiều:** Vẽ nháp sơ đồ kiến trúc Cloud-native cho dự án (Frontend đặt trên AWS Amplify/S3, Backend chạy container phía sau ALB, Database dùng RDS). | 04/06/2026 | 04/06/2026 | [AWS ALB Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html) |
| 6 | - **Sáng:** Thiết lập Trello/Jira Board, lên danh sách backlog các tính năng cần hoàn thành trong Sprint đầu tiên.<br>- **Chiều:** Phân chia task cho tuần sau (Tập trung thiết kế Database Schema và xây dựng API Core). Review lại toàn bộ kế hoạch dự án cùng cả nhóm để chốt tiến độ. | 05/06/2026 | 05/06/2026 | [Agile Project Management](https://www.atlassian.com/agile) |

### Kết quả đạt được tuần 4

* Chính thức chốt đề tài Snaptics, xác định rõ chân dung người dùng (User & Admin) và các tính năng MVP.
* Khởi tạo thành công không gian làm việc nhóm (Github Repo, Jira/Trello Board) và chuẩn hóa quy trình Git Flow.
* Hoàn thành bộ tài liệu thiết kế hệ thống UI/UX cơ bản (Sitemap, User Flow, Wireframe, Design System).
* Định hình được tech-stack sẽ sử dụng (Angular, .NET) và phát thảo xong kiến trúc Cloud-native dự kiến triển khai trên AWS.
