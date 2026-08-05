---
title: "Worklog Tuần 13"
date: 2026-08-03
weight: 13
chapter: false
pre: " <b> 1.13. </b> "
---

### Mục tiêu tuần 13

* Tiến hành kiểm thử toàn bộ luồng người dùng (End-to-End User Flow testing) xuyên suốt từ Frontend qua Backend đến Database.
* Khắc phục tất cả các lỗi vặt giao diện (UI/UX polishing) và tối ưu hóa hiệu năng toàn bộ hệ thống (Angular & .NET API).
* Cấu hình triển khai hạ tầng AWS (Amplify cho Frontend, CloudFront & ALB cho Backend API) kết hợp chứng chỉ SSL/HTTPS bảo mật.
* Thực hiện biên dịch bản Frontend Production tĩnh thành công bằng Angular CLI và cấu hình CI/CD tự động từ GitHub.
* Đảm bảo kiến trúc CloudFront gọi tới ALB hoạt động trơn tru qua Custom Domain, xử lý chuẩn xác các Header và WebSocket (SignalR).
* Thực hành bài lab **Workshop 5.6**: Tiến hành dọn dẹp sạch sẽ tài nguyên thử nghiệm (VPC Endpoints, EC2 test instances, IAM policies, S3 test buckets) tránh phát sinh chi phí thừa trên AWS.
* Chụp ảnh màn hình giao diện thực tế, hoàn thiện hồ sơ tài liệu báo cáo thực tập, chuẩn bị kịch bản demo sản phẩm và nộp chính thức dự án Snaptics vào ngày **07/08/2026**.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tiến hành End-to-End Testing toàn hệ thống Fullstack:<br>&emsp; + Luồng Đăng nhập, Đăng ký, JWT Auth.<br>&emsp; + Luồng Dashboard, Giao dịch, Ví, Ngân sách lưu vào SQL Server.<br>&emsp; + Luồng Quét hóa đơn (S3 + SQS + Azure OCR), Thông báo SignalR, Chatbot AI Gemini, Support Ticket.<br>&emsp; + Luồng Quản trị Admin và Hangfire Background Jobs.<br>- Rà soát và tinh chỉnh các lỗi UI/UX, tối ưu API response time. | 03/08/2026 | 03/08/2026 | [Software Testing Best Practices](https://developer.mozilla.org/) |
| 3 | - Kiểm tra chính xác các biến môi trường Production (`src/environments/environment.prod.ts` trỏ về API CloudFront URL).<br>- Chạy lệnh `ng build --configuration production` biên dịch bản tĩnh Production và xác nhận quá trình build hoàn tất thành công 100%.<br>- Tối ưu hóa cấu hình Parameter Store trên AWS Systems Manager cho Backend. | 04/08/2026 | 04/08/2026 | [Angular Deployment Guide](https://angular.io/guide/deployment) |
| 4 | - Triển khai hệ thống lên Production AWS:<br>&emsp; + Host Frontend trên **AWS Amplify** kết hợp CI/CD từ GitHub.<br>&emsp; + Cấu hình **CloudFront** đứng trước ALB của Backend API, thiết lập Cache Policy `CachingDisabled` và Origin Request Policy `AllViewer`.<br>&emsp; + Trỏ tên miền Custom Domain qua Route 53 và cấu hình chứng chỉ bảo mật ACM SSL. | 05/08/2026 | 05/08/2026 | [AWS Amplify Hosting](https://docs.aws.amazon.com/amplify/latest/userguide/welcome.html)<br>[CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 5 | - **Thực hành Workshop 5 (Phần 6 - Dọn dẹp tài nguyên):**<br>&emsp; + Tiến hành dọn dẹp toàn bộ tài nguyên lab Workshop theo hướng dẫn ([Workshop Clean-up](5-Workshop/5.6-Cleanup/)).<br>&emsp; + Xóa Gateway VPC Endpoint, Interface VPC Endpoint, các EC2 test instances, S3 test buckets và giải phóng Elastic IP.<br>&emsp; + Rà soát trên AWS Cost Explorer đảm bảo không còn tài nguyên rác chạy ngầm gây phát sinh chi phí. | 06/08/2026 | 06/08/2026 | [Workshop Clean-up](5-Workshop/5.6-Cleanup/)<br>[AWS Cost Management](https://aws.amazon.com/aws-cost-management/) |
| 6 | - **Hoàn thiện & Nộp Báo cáo Thực tập:**<br>- Thu thập ảnh chụp màn hình ứng dụng và chuẩn bị kịch bản Demo sản phẩm phục vụ buổi tổng kết.<br>- Tổng kết lại toàn bộ kiến thức Fullstack (.NET, Angular) và các dịch vụ đám mây AWS đã vận dụng kiến trúc vào Snaptics trong 13 tuần.<br>- Hoàn thiện hồ sơ báo cáo thực tập và **chính thức nộp Project Snaptics** khép lại chương trình thực tập FCJ Workforce vào ngày **07/08/2026**. | 07/08/2026 | 07/08/2026 | [FCJ Workforce Regulations](https://hcm-rules.awsfcaj.com/1-regulations/) |

### Kết quả đạt được tuần 13

* Thực hiện kiểm thử End-to-End thành công, đảm bảo toàn bộ hệ thống Fullstack từ Frontend đến Database vận hành trơn tru.
* Tối ưu hóa dung lượng ứng dụng Angular và hiệu suất API Backend, nâng cao tốc độ phản hồi hệ thống.
* Thực hiện biên dịch bản Build Angular Production thành công 100% không gặp bất kỳ lỗi syntax nào.
* Triển khai hạ tầng Production AWS thành công: Frontend chạy siêu tốc trên Amplify, Backend API được bảo vệ an toàn sau CloudFront & ALB.
* Cấu hình tên miền hoàn chỉnh qua Route 53 kèm chứng chỉ bảo mật HTTPS cho cả Frontend và API Backend.
* Thực hành dọn dẹp thành công 100% tài nguyên bài lab Workshop 5 (Clean-up), đảm bảo tối ưu chi phí AWS.
* Chuẩn bị đầy đủ kịch bản Demo sản phẩm và nội dung bảo vệ tổng kết chất lượng cao.
* Đúc kết được nhiều kinh nghiệm thực chiến giá trị về Fullstack Web Development, kiến trúc Serverless/Container và dịch vụ AWS.
* Hoàn thành và nộp chính thức Báo cáo thực tập & Project Snaptics đúng thời hạn vào ngày **07/08/2026**.
