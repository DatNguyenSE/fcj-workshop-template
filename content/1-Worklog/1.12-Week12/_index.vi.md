---
title: "Worklog Tuần 12"
date: 2026-07-27
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12

* Rà soát tài liệu Swagger API, đảm bảo đồng bộ hoàn toàn danh sách Endpoints, Request Body và Response Format giữa Backend và Frontend.
* Xây dựng và cập nhật lớp Frontend API Service bằng **Angular HttpClient** và **Angular HttpInterceptor** để tự động đính kèm Bearer Access Token (JWT) và xử lý tập trung lỗi token hết hạn.
* Bỏ hoàn toàn dữ liệu giả lập (Mock Data Service) và đảm bảo mọi tính năng đều gọi dữ liệu thật từ Backend API.
* Kiểm thử tích hợp toàn diện các API: Đăng nhập/Đăng ký, Giao dịch, Ví, Ngân sách, Quét hóa đơn, Thông báo, AI Insight, Support Ticket và Admin APIs.
* Xử lý mượt mà các trạng thái giao diện: Skeleton Loading Component, thông báo Toast báo lỗi/thành công, lỗi kết nối mạng (Network Error) và dữ liệu rỗng (Empty State).
* Tinh chỉnh Angular Reactive Form Validation và khắc phục lỗi cuộn trang bị nảy/lệch thanh Navigation bar trên thiết bị di động.
* Sửa lỗi responsive trên trang Settings và sửa lỗi menu tài khoản dropdown bị che mờ hoặc đơ đứng.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Rà soát chi tiết tài liệu Swagger UI của Backend .NET.<br>- Kiểm tra chéo toàn bộ danh sách Endpoints, phương thức HTTP (GET, POST, PUT, DELETE), cấu trúc dữ liệu JSON và mã lỗi (Error Codes).<br>- Xây dựng Angular `AuthInterceptor` (`HTTP_INTERCEPTORS`) đính kèm JWT Bearer Token vào Request Header và xử lý tập trung lỗi 401 Unauthorized, 403 Forbidden và 500 Server Error qua RxJS `catchError`. | 27/07/2026 | 27/07/2026 | [Angular HttpClient Guide](https://angular.io/guide/http)<br>[Angular Interceptors](https://angular.io/guide/http-intercept-requests-and-responses) |
| 3 | - Loại bỏ hoàn toàn mock data và kết nối API thật qua Angular Services cho nhóm chức năng Xác thực (Auth), Dashboard tổng quan, Danh sách giao dịch và Quản lý danh mục chi tiêu.<br>- Cập nhật CORS policy trên Backend để cho phép Frontend gọi API.<br>- Xây dựng hiệu ứng Skeleton Loading hiển thị khung xương trang web mượt mà trong thời gian chờ API phản hồi dữ liệu qua RxJS Observables. | 28/07/2026 | 28/07/2026 | [RxJS Observables Guide](https://rxjs.dev/guide/observable) |
| 4 | - Tích hợp và kiểm thử luồng API cho các tính năng phức tạp: Quét hóa đơn (gửi file qua S3 Gateway Endpoint và nhận OCR), Quản lý Ví cá nhân/gia đình, Ngân sách chi tiêu, Chatbot AI Insight và Support Ticket.<br>- Tích hợp dịch vụ thông báo Toast (`Ngx-Toastr`) hiển thị thông báo tức thì khi người dùng thực hiện thao tác thành công hoặc thất bại. | 29/07/2026 | 29/07/2026 | [Ngx-Toastr Guide](https://ngx-toastr.vercel.app/) |
| 5 | - Tích hợp các API cho khu vực Admin Panel (Quản lý người dùng, Quản lý Ticket, Quản lý Thông báo hệ thống và Hangfire Jobs).<br>- Sửa lỗi responsive vỡ khung trên màn hình Cài đặt tài khoản (Settings Page) khi co nhỏ kích thước cửa sổ trình duyệt.<br>- Khắc phục lỗi Menu Dropdown tài khoản bị che khuyết hoặc không đóng khi click ra ngoài. | 30/07/2026 | 30/07/2026 | [UI Bug Fixing Techniques](https://developer.mozilla.org/) |
| 6 | - Khắc phục sự cố thanh Navigation mobile bị xô lệch/giật nảy nội dung khi vuốt cuộn trang (khóa thanh navigation bằng `position: sticky/fixed` và xử lý overflow CSS).<br>- Thực hiện kiểm thử lại Form Validation trên cả Frontend và Backend, đảm bảo hiển thị lỗi minh bạch khi nhập sai định dạng dữ liệu.<br>- Rà soát tính nhất quán UI/UX và kiểm tra độ ổn định kết nối API toàn hệ thống. | 31/07/2026 | 31/07/2026 | [Mobile Navigation CSS Fixes](https://css-tricks.com/) |

### Kết quả đạt được tuần 12

* Hoàn thành rà soát Swagger API và đảm bảo đồng bộ 100% các endpoint tích hợp giữa Backend và Frontend.
* Phát triển thành công Angular API Service & HttpInterceptor quản lý kết nối HTTP, tự động xử lý Access Token JWT và lỗi mạng tập trung qua RxJS.
* Loại bỏ hoàn toàn dữ liệu Mock Data và thay thế thành công bằng dữ liệu thật từ Backend API cho toàn bộ ứng dụng Snaptics.
* Giao diện phản hồi trực quan với các trạng thái Skeleton Loading, Toast Notification minh bạch và xử lý dữ liệu rỗng chu đáo.
* Khắc phục dứt điểm lỗi thanh Navigation mobile bị xô lệch/nảy khung hình khi kéo cuộn trang.
* Sửa hoàn tất các lỗi hiển thị responsive trên trang Cài đặt và Menu Dropdown tài khoản.
* Đảm bảo hệ thống kiểm tra lỗi Form Validation hoạt động chính xác và an toàn trên cả 2 lớp Frontend/Backend.
* Toàn bộ hệ thống Snaptics đạt độ hoàn thiện cao, vận hành thông suốt và sẵn sàng cho giai đoạn đóng gói Production.
