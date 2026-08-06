---
title: "Worklog Tuần 1"
date: 2026-05-11
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1

* Làm quen với chương trình First Cloud Journey (FCJ Workforce).
* Tìm hiểu quy định, lộ trình và yêu cầu đánh giá của chương trình thực tập.
* Tìm hiểu tổng quan về Điện toán đám mây (Cloud Computing) và hạ tầng toàn cầu AWS (Regions, Availability Zones, Edge Locations).
* Tạo tài khoản AWS Free Tier và thiết lập bảo mật với Multi-Factor Authentication (MFA).
* Nghiên cứu dịch vụ AWS IAM (Users, Groups, Policies, Roles) và áp dụng nguyên tắc đặc quyền tối thiểu (Least Privilege).
* Cài đặt, cấu hình AWS CLI trên máy tính cá nhân và kiểm tra các câu lệnh quản trị cơ bản.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Tham gia buổi định hướng chương trình FCJ Workforce, làm quen nhóm thực tập. Đọc nội quy, lộ trình 13 tuần.<br>- **Chiều:** Setup môi trường làm việc cá nhân (Cài đặt Visual Studio, VS Code, Git, Docker). Họp nhóm bàn về quy ước làm việc (Daily Standup 9h sáng). | 11/05/2026 | 11/05/2026 | [Nội quy FCJ](https://hcm-rules.awsfcaj.com/1-regulations/) |
| 3 | - **Sáng:** Đọc tài liệu AWS Cloud Overview, mô hình IaaS/PaaS/SaaS và Global Infrastructure (Regions, AZs).<br>- **Chiều:** Tìm hiểu mô hình AWS Shared Responsibility. Thảo luận nhóm về các Use-case thực tế ứng dụng AWS tại Việt Nam. | 12/05/2026 | 12/05/2026 | [AWS Cloud Overview](https://aws.amazon.com/what-is-aws/) |
| 4 | - **Sáng:** Khởi tạo tài khoản AWS Free Tier. Gắn thẻ thanh toán và kích hoạt Multi-Factor Authentication (MFA) cho tài khoản Root.<br>- **Chiều:** Thiết lập AWS Budgets cảnh báo chi phí ban đầu. Xử lý lỗi thẻ thanh toán bị từ chối do thẻ chưa mở tính năng thanh toán quốc tế. | 13/05/2026 | 13/05/2026 | [AWS Free Tier](https://aws.amazon.com/free/) |
| 5 | - **Sáng:** Đọc tài liệu AWS IAM (Users, Groups, Policies, Roles) và nguyên tắc Least Privilege.<br>- **Chiều:** Thực hành tạo IAM User dành riêng cho công việc hàng ngày. Bị lỗi IAM Policy không đủ quyền khi thử tạo S3 bucket, tự debug bằng JSON Policy và gán thêm quyền truy cập phù hợp. | 14/05/2026 | 14/05/2026 | [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) |
| 6 | - **Sáng:** Tải, cài đặt và cấu hình AWS CLI v2 trên máy tính cá nhân. Thiết lập default profile.<br>- **Chiều:** Test các lệnh CLI cơ bản (`aws sts get-caller-identity`). Bị lỗi "Access Denied", phát hiện do copy thiếu ký tự ở Secret Key, đã sửa lỗi và cấu hình thành công. Viết báo cáo tuần lên Notion. | 15/05/2026 | 15/05/2026 | [Configuring AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) |

### Kết quả đạt được tuần 1

* Setup hoàn chỉnh môi trường làm việc nhóm, công cụ lập trình và làm quen với lộ trình 13 tuần thực tập.
* Khởi tạo thành công tài khoản AWS Free Tier và kích hoạt bảo mật MFA cho Root Account.
* Nắm vững kiến thức cốt lõi về AWS IAM và tạo IAM User quản trị hàng ngày tuân thủ quy tắc Least Privilege, biết cách đọc và fix lỗi JSON Policy.
* Cài đặt và cấu hình thành công AWS CLI v2 trên máy cá nhân, troubleshoot thành công lỗi xác thực Credentials.