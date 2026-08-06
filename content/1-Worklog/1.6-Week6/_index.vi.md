---
title: "Worklog Tuần 6"
date: 2026-06-15
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6

* Xây dựng Backend API CRUD cho nghiệp vụ cốt lõi: Giao dịch (Transactions).
* Thiết kế và code giao diện Overview Dashboard hiển thị tổng số dư và biểu đồ sơ bộ.
* Tích hợp Frontend gọi API và hiển thị danh sách giao dịch có phân trang (Pagination).
* Thiết lập bảo vệ Route trên Frontend (Angular AuthGuard), chỉ cho người dùng đã đăng nhập truy cập.
* Viết HttpInterceptor tự động đính kèm Token và xử lý lỗi 401 Unauthorized.
* Bắt lỗi validation dữ liệu kỹ càng từ Frontend xuống tới Backend.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Xây dựng Backend API (Create, Read, Update, Delete) cho bảng Giao dịch.<br>- **Chiều:** Viết câu truy vấn LINQ tối ưu để lấy danh sách Giao dịch có phân trang (Pagination) và lọc theo Ví, đảm bảo API trả về nhanh chóng với lượng data lớn. | 15/06/2026 | 15/06/2026 | [EF Core LINQ](https://learn.microsoft.com/en-us/ef/core/querying/) |
| 3 | - **Sáng:** Thiết kế giao diện Overview Dashboard (hiển thị thẻ Số dư tổng, chi tiêu tháng) trên Angular.<br>- **Chiều:** Tích hợp gọi API danh sách Giao dịch. Bị lỗi hiển thị sai định dạng ngày tháng và tiền tệ, đã fix triệt để bằng cách dùng Angular Pipes (`DatePipe`, `CurrencyPipe`). | 16/06/2026 | 16/06/2026 | [Angular Pipes](https://angular.io/guide/pipes) |
| 4 | - **Sáng:** Cài đặt tính năng bảo vệ Route (`AuthGuard`) trên Angular, chặn user chưa đăng nhập vào xem Dashboard.<br>- **Chiều:** Viết `HttpInterceptor` để tự động kẹp `Bearer Token` vào Header HTTP. Xử lý logic tự động đá văng về trang Login (Logout) khi API trả về mã lỗi `401 Unauthorized` (Token hết hạn). | 17/06/2026 | 17/06/2026 | [Angular Interceptors](https://angular.io/api/common/http/HttpInterceptor) |
| 5 | - **Sáng:** Code giao diện Form Thêm/Sửa/Xóa giao dịch. Bắt validation các trường bắt buộc (Số tiền phải lớn hơn 0, Danh mục không được bỏ trống).<br>- **Chiều:** Test luồng tạo Giao dịch từ Frontend xuyên suốt tới DB. Phát hiện user có thể bypass truyền số tiền âm qua API, lập tức bổ sung thêm check validation chặt chẽ ở phía Backend. | 18/06/2026 | 18/06/2026 | [Angular Reactive Forms](https://angular.io/guide/reactive-forms) |
| 6 | - **Sáng:** Làm giao diện quản lý Danh mục chi tiêu (chọn Icon, chọn Mã màu hiển thị).<br>- **Chiều:** Chạy thiết bị ảo test UI, fix các bug giao diện vỡ lề trên màn hình điện thoại (Responsive Mobile). Gom commit gọn gàng và push lên nhánh `develop`. Đóng Sprint 2. | 19/06/2026 | 19/06/2026 | [Tailwind Responsive](https://tailwindcss.com/docs/responsive-design) |

### Kết quả đạt được tuần 6

* Xây dựng và hoàn thiện API cốt lõi nhất của dự án là Quản lý Giao dịch.
* Khắc phục các lỗi hiển thị dữ liệu (Date, Currency) phía Frontend.
* Thiết lập thành công tường lửa bảo vệ bên trong ứng dụng Angular bằng `AuthGuard` và `HttpInterceptor`.
* Đồng bộ logic bắt lỗi Validation ở cả hai chiều (Frontend Form và Backend API), chặn đứng dữ liệu rác.
* Đảm bảo giao diện Dashboard và Form Giao dịch tương thích hoàn toàn (Responsive) trên màn hình thiết bị di động.
