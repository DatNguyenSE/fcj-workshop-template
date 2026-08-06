---
title: "Worklog Tuần 13"
date: 2026-08-03
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Mục tiêu tuần 13

* Biên dịch bản ứng dụng (Build Production) cho cả Frontend và Backend.
* Triển khai (Deploy) Frontend SPA tĩnh lên nền tảng AWS Amplify.
* Đóng gói Backend thành Docker Container và triển khai lên kiến trúc Serverless Amazon ECS (Fargate) đằng sau Load Balancer.
* Xử lý chứng chỉ bảo mật SSL/HTTPS bằng AWS Certificate Manager (ACM) để fix lỗi Mixed Content.
* Cấu hình lại các thiết lập mạng, WebSocket để ứng dụng chạy ổn định trên Domain thực tế.
* Thực hành bài lab **Workshop 5.6**: Dọn dẹp tài nguyên rác và Tổng kết dự án.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Biên dịch bản Frontend Production bằng lệnh `ng build --configuration production`. Bị dính các lỗi Strict Type Checking lúc build (môi trường dev thì bỏ qua nhưng build prod thì báo lỗi đỏ), đã ngồi fix lại toàn bộ kiểu dữ liệu.<br>- **Chiều:** Khởi tạo `Dockerfile` cho Backend .NET. Đóng gói thành Docker Image và push thành công lên kho chứa Amazon ECR. | 03/08/2026 | 03/08/2026 | [Angular Deployment](https://angular.io/guide/deployment) |
| 3 | - **Sáng:** Triển khai Frontend lên dịch vụ AWS Amplify. Mất khá lâu để cấu hình các luồng Rewrite/Redirect rules trên Amplify cho các route của Angular (để khi f5 trang không bị trả về lỗi 404).<br>- **Chiều:** Khởi tạo Cluster và Task Definition. Triển khai Backend chạy bằng Amazon ECS (AWS Fargate) để khỏi phải quản lý server. | 04/08/2026 | 04/08/2026 | [Deploying Angular on AWS Amplify](https://aws.amazon.com/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/module-1/) |
| 4 | - **Sáng:** Tạo Application Load Balancer (ALB) làm phễu hứng request cho Backend. Test gọi API từ Frontend (trên Amplify) tới Backend (ALB).<br>- **Chiều:** Trình duyệt web báo lỗi chặn HTTPS Mixed Content (Do Frontend HTTPS cố gọi Backend HTTP). Đăng ký chứng chỉ SSL miễn phí từ AWS Certificate Manager (ACM) và gắn vào ALB. Thiết lập cấu hình trỏ Domain từ Route53 về ALB. | 05/08/2026 | 05/08/2026 | [ALB and HTTPS](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html) |
| 5 | - **Sáng:** Gặp sự cố tính năng Notification không nhảy. Debug phát hiện ALB đang không định tuyến đúng chuẩn WebSocket. Cấu hình lại Header trên ALB, cho phép giao thức `ws://` và `wss://` hoạt động thông qua Custom Domain.<br>- **Chiều:** Thực hành lab Workshop 5.6: Rà soát và dọn dẹp sạch sẽ tài nguyên rác (VPC Endpoints, Test EC2, Test Buckets) trên AWS Console để tránh bị AWS "cắn" tiền sau khi kết thúc chương trình. | 06/08/2026 | 06/08/2026 | [WebSockets on ALB](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html) |
| 6 | - **Sáng:** Dự án đã chạy Live trên Domain thực tế. Chụp ảnh màn hình giao diện hệ thống. Hoàn thiện bộ hồ sơ tài liệu báo cáo thực tập kiến trúc Snaptics.<br>- **Chiều:** Demo sản phẩm lần cuối với cả nhóm để xem xét các luồng. Nộp chính thức dự án và kết thúc tốt đẹp chương trình FCJ Workforce 13 tuần. | 07/08/2026 | 07/08/2026 | [Project Submission Guidelines](#) |

### Kết quả đạt được tuần 13

* Vượt qua các quy định kiểm tra khắt khe khi Build Production, đóng gói chuẩn chỉnh cả Frontend lẫn Backend.
* Hoàn thành triển khai hệ thống Cloud-native thực thụ: Frontend Serverless (Amplify) và Backend Containerized (ECS Fargate).
* Xử lý dứt điểm các lỗi đặc thù khi lên môi trường thật: Lỗi 404 F5 trên SPA, lỗi HTTPS Mixed Content, lỗi chặn WebSocket.
* Áp dụng nguyên tắc dọn dẹp (Cleanup resources) theo bài lab cuối để làm chủ việc quản lý chi phí đám mây.
* Nghiệm thu và bàn giao xuất sắc đồ án Snaptics - kết tinh kiến thức Fullstack & AWS Cloud sau 13 tuần nỗ lực.
