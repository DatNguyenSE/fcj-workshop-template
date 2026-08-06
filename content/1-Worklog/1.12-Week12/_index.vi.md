---
title: "Worklog Tuần 12"
date: 2026-07-27
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Mục tiêu tuần 12

* Bắt đầu giai đoạn "Code Freeze" (Đóng băng code), tập trung dọn dẹp hệ thống và không thêm tính năng mới.
* Đồng bộ hoàn toàn tài liệu API (Swagger) giữa Backend và Frontend, xóa bỏ các Mock Data giả lập.
* Thực hiện làm mịn trải nghiệm người dùng (UX Polishing) như Skeleton Loaders, Empty States, Toast Notifications.
* Khắc phục triệt để các lỗi Responsive (Vỡ giao diện) trên thiết bị di động (Mobile/Tablet).
* Hoàn thiện tính năng Gửi Email xác thực bằng dịch vụ Amazon SES.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Bắt đầu giai đoạn dọn dẹp hệ thống. Rà soát tài liệu Swagger API, đảm bảo đồng bộ hoàn toàn Endpoints, Request Body giữa Backend và Frontend.<br>- **Chiều:** Xóa toàn bộ dữ liệu giả lập (Mock Data Service) trên Frontend. Sửa lại tất cả Component để bind dữ liệu trực tiếp từ Http Service API thật. | 27/07/2026 | 27/07/2026 | [Swagger API Documentation](https://swagger.io/) |
| 3 | - **Sáng:** Test luồng E2E các tính năng. Bị lỗi crash trắng trang Angular do API trả về mảng dữ liệu null (khi user chưa có giao dịch nào) mà Frontend không chịu kiểm tra.<br>- **Chiều:** Thêm toán tử Optional Chaining `?.` vào HTML template và thiết kế các màn hình Empty State (Ví dụ: "Bạn chưa có giao dịch nào, hãy bấm nút Thêm") để dẫn dắt user. | 28/07/2026 | 28/07/2026 | [Angular Optional Chaining](https://angular.io/guide/template-syntax) |
| 4 | - **Sáng:** Làm mịn trải nghiệm người dùng (UX Polishing). Thêm Skeleton Loading Component nhấp nháy trên giao diện thay vì hiện màn hình trắng tinh khi chờ tải API chậm.<br>- **Chiều:** Chuẩn hóa hệ thống thông báo lỗi (Toast notifications). Bắt các trường hợp lỗi kết nối mạng (Network Error) hoặc Server sập lỗi 500 để báo lỗi thân thiện thay vì im lặng. | 29/07/2026 | 29/07/2026 | [UI Skeleton Screens](https://uxdesign.cc/what-you-should-know-about-skeleton-screens-a820c45a571a) |
| 5 | - **Sáng:** Fix một loạt lỗi giao diện Responsive trên Mobile: Thanh Navigation bar bị lấp, menu dropdown bị che khuất một nửa.<br>- **Chiều:** Fix lỗi cuộn trang (Scrolling) trên thiết bị iOS/Safari bị khựng (thêm thuộc tính CSS `-webkit-overflow-scrolling: touch;`). Xử lý lỗi modal popup bị tràn nội dung. | 30/07/2026 | 30/07/2026 | [CSS Responsive Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design) |
| 6 | - **Sáng:** Hoàn thiện tính năng Cài đặt mật khẩu / Quên mật khẩu. Cấu hình Amazon SES (Simple Email Service) để gửi Email chứa mã OTP tự động.<br>- **Chiều:** Đóng băng code (Code Freeze). Chạy lại các luồng test cơ bản. Lập kế hoạch các bước triển khai Production cho tuần cuối cùng. | 31/07/2026 | 31/07/2026 | [Amazon SES Guide](https://docs.aws.amazon.com/ses/latest/dg/Welcome.html) |

### Kết quả đạt được tuần 12

* Hoàn tất đấu nối 100% API thực tế, loại bỏ hoàn toàn các đoạn code tạm bợ (Mock Data).
* Xử lý mượt mà và an toàn các trường hợp biên (Edge cases) như Empty State, Network Error, Data Null.
* Trải nghiệm ứng dụng (UX) được nâng lên tầm cao mới, thân thiện với Loading Skeleton và Toast.
* Đảm bảo giao diện hiển thị xuất sắc, không lỗi hiển thị (Responsive) trên mọi kích cỡ màn hình di động.
* Sẵn sàng bộ Source Code hoàn chỉnh, "chín muồi" để đem đi triển khai (Deploy) trong tuần cuối.
