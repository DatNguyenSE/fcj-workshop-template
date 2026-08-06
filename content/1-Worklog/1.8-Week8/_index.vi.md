---
title: "Worklog Tuần 8"
date: 2026-06-29
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8

* Thiết lập hệ thống hàng đợi tin nhắn bất đồng bộ bằng Amazon SQS.
* Cấu hình Background Worker xử lý ngầm.
* Tích hợp thành công công nghệ AI (Azure Document Intelligence) để đọc hóa đơn.
* Đẩy thông báo thời gian thực về phía người dùng qua WebSockets.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|------|-----------|-------------|----------------|---------------|
| 2 | **Amazon SQS:** <br> - Tìm hiểu Amazon Simple Queue Service <br> - Khởi tạo Standard Queue <br> - Hiểu và cấu hình cơ chế Visibility Timeout | 29/06/2026 | 29/06/2026 | |
| 3 | **Background Processing:** <br> - Viết IHostedService trên .NET <br> - Cấu hình Worker kéo tin nhắn từ SQS <br> - Quản lý vòng đời tin nhắn trong Queue | 30/06/2026 | 30/06/2026 | |
| 4 | **Azure Document Intelligence:** <br> - Đăng ký dịch vụ Azure OCR <br> - Lưu trữ an toàn API Key bằng AWS Parameter Store <br> - Tích hợp mã gọi API phân tích hóa đơn vào Worker | 01/07/2026 | 01/07/2026 | |
| 5 | **Xử lý dữ liệu AI:** <br> - Parse chuỗi JSON kết quả từ Azure <br> - Mapping thông tin vào các trường Database <br> - Bổ sung logic xử lý các trường hợp dữ liệu thiếu/lỗi | 02/07/2026 | 02/07/2026 | |
| 6 | **Real-time SignalR:** <br> - Tìm hiểu công nghệ WebSockets và SignalR <br> - Cấu hình SignalR Hub trên Backend <br> - Tích hợp đẩy thông báo hoàn tất quét hóa đơn về Frontend | 03/07/2026 | 03/07/2026 | |

### Kết quả đạt được tuần 8

* Tích hợp kiến trúc bất đồng bộ bằng SQS, nâng cao hiệu suất xử lý tác vụ nặng.
* Khai thác thành công API trí tuệ nhân tạo để tự động hóa trích xuất dữ liệu.
* Làm quen với bảo mật cấu hình ứng dụng thông qua AWS Parameter Store.
* Nâng tầm trải nghiệm người dùng (UX) bằng thông báo Real-time mượt mà.
