---
title: "Worklog Tuần 9"
date: 2026-07-06
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9

* Truy xuất Gemini API Key từ AWS Parameter Store và cấu hình tích hợp Google Gemini 2.5 Flash SDK vào Backend .NET.
* Xây dựng luồng Backend API Trợ lý AI Insight phục vụ tư vấn tài chính thông minh dựa trên dữ liệu chi tiêu của người dùng.
* Xây dựng Fullstack tính năng Phân tích & Báo cáo chi tiêu (Spending Analysis & Reports).
* Phát triển API thống kê chi tiêu phía Backend và tích hợp biểu đồ trực quan với **Ngx-charts / Chart.js** trên Frontend (Angular).
* Thiết kế bộ lọc thời gian linh hoạt (ngày, tuần, tháng, quý, năm) và xử lý logic truy vấn dữ liệu từ CSDL SQL Server.
* Thiết kế giao diện trò chuyện Chatbot hiện đại trên Angular (Sidebar lịch sử hội thoại, khung chat chính, ô nhập câu hỏi).
* Xử lý luồng tin nhắn realtime, hiệu ứng AI đang phản hồi (Typing indicator animation) và câu hỏi gợi ý mẫu.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Lấy `GeminiApiKey` một cách bảo mật từ AWS Systems Manager thông qua `IConfiguration` trong Backend .NET.<br>- Tích hợp SDK Gemini 2.5 Flash để xây dựng API Chatbot AI tư vấn tài chính.<br>- Xây dựng API lưu trữ lịch sử hội thoại của người dùng vào cơ sở dữ liệu. | 06/07/2026 | 06/07/2026 | [Google Gemini API Docs](https://ai.google.dev/docs) |
| 3 | - Thiết kế Database schema và viết API Backend lấy dữ liệu thống kê phân tích chi tiêu tổng quan.<br>- Thiết kế bố cục trang Phân tích & Báo cáo chi tiêu trên Angular.<br>- Tích hợp thư viện biểu đồ **Ngx-charts / Chart.js** để vẽ Pie Chart phân bổ ngân sách và Bar Chart tổng quan. | 07/07/2026 | 07/07/2026 | [Ngx-charts Guide](https://swimlane.github.io/ngx-charts/) |
| 4 | - Xây dựng API thống kê biến động chi tiêu theo thời gian.<br>- Phát triển Line Chart trên Frontend và thanh công cụ bộ lọc thời gian (Tuần, Tháng, Quý, Năm).<br>- Tối ưu hóa câu truy vấn SQL để tính toán nhanh % tăng/giảm so với kỳ trước. | 08/07/2026 | 08/07/2026 | [Financial Chart Patterns](https://dribbble.com/) |
| 5 | - Thiết kế cấu trúc giao diện trang Trò chuyện với AI (AI Assistant Chat Component) trên Angular.<br>- Cấu hình Frontend gọi API AI Insight và hiển thị khung tin nhắn (Message Bubbles) phân biệt User và AI.<br>- Xây dựng hiệu ứng visual AI đang suy nghĩ / trả lời (Typing Indicator Animation). | 09/07/2026 | 09/07/2026 | [Chat Interface UI Patterns](https://uicoach.io/) |
| 6 | - Thiết kế danh sách các Prompt gợi ý mẫu trên màn hình bắt đầu của Chatbot.<br>- Cấu hình luồng Dead Letter Queue (DLQ) cho SQS để dự phòng xử lý khi gọi AI API bị lỗi Timeout.<br>- Kiểm tra khả năng hiển thị responsive của các biểu đồ báo cáo và giao diện Chat AI trên thiết bị di động. | 10/07/2026 | 10/07/2026 | [AI Chatbot UX Best Practices](https://uxplanet.org/) |

### Kết quả đạt được tuần 9

* Tích hợp thành công Gemini 2.5 Flash vào hệ thống Backend một cách bảo mật bằng API Key lấy từ AWS.
* Hoàn thành luồng tích hợp Trợ lý AI và giao diện trang Trò chuyện với AI theo chuẩn ứng dụng chat hiện đại.
* Xây dựng hiệu ứng Typing animation phản hồi chân thực mang lại cảm giác tương tác tự nhiên với AI.
* Hoàn thành tính năng Phân tích chi tiêu từ Backend API đến Frontend với hệ thống biểu đồ Ngx-charts vô cùng sống động.
* Phát triển bộ lọc thời gian báo cáo đa dạng và truy vấn dữ liệu hiệu quả từ cơ sở dữ liệu.
* Hiển thị trực quan chỉ số so sánh xu hướng chi tiêu tăng/giảm theo từng chu kỳ tài chính.
* Tích hợp bộ danh sách Prompt Chips gợi ý câu hỏi giúp người dùng dễ dàng bắt đầu hội thoại với AI.
* Đảm bảo các biểu đồ tài chính và giao diện chat AI tương thích chuẩn 100% trên màn hình điện thoại di động.
