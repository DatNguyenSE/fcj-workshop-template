---
title: "Worklog Tuần 9"
date: 2026-07-06
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9

* Tích hợp AI tạo sinh (Generative AI) bằng Google Gemini API để phân tích dữ liệu tài chính của người dùng.
* Xây dựng luồng Backend trích xuất dữ liệu giao dịch trong tháng, đóng gói thành Prompt Context gửi cho AI.
* Xây dựng tính năng Báo cáo & Phân tích chi tiêu (Spending Analysis) sử dụng thư viện `ngx-charts` trên Angular.
* Tối ưu hóa các truy vấn SQL (Query optimization) trên hệ thống Amazon RDS để đảm bảo load dữ liệu báo cáo nhanh.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - **Sáng:** Đăng ký Google Gemini API Key. Đưa key vào AWS Parameter Store để bảo mật giống như cách làm với Azure.<br>- **Chiều:** Cài đặt SDK `Google.GenerativeAI` cho Backend. Viết Prompt Engineering cơ bản để AI đọc hiểu được mảng dữ liệu (Array) giao dịch của người dùng. | 06/07/2026 | 06/07/2026 | [Google Gemini API Docs](https://ai.google.dev/docs) |
| 3 | - **Sáng:** Bị lỗi AI hay trả lời dài dòng và format markdown bị lộn xộn. Tinh chỉnh lại Prompt, sử dụng kỹ thuật ép kiểu (force format) bắt AI trả về đúng JSON hoặc bullet points ngắn gọn.<br>- **Chiều:** Hoàn thiện API `/api/ai/insights` trả về lời khuyên tài chính (ví dụ: cảnh báo tiêu quá tay vào Ăn uống). Tích hợp giao diện Chatbot UI đơn giản trên Angular. | 07/07/2026 | 07/07/2026 | [Prompt Engineering Guide](https://www.promptingguide.ai/) |
| 4 | - **Sáng:** Viết câu lệnh SQL Query (tích hợp qua EF Core) dùng `GroupBy` để tính tổng tiền chi tiêu theo từng Danh mục (Categories) trong tháng.<br>- **Chiều:** Test API Report thấy thời gian phản hồi khá chậm khi seed thử 10,000 dòng data. Nghiên cứu và tạo thêm Index trên RDS cho các cột `TransactionDate` và `CategoryId`, tốc độ cải thiện rõ rệt. | 08/07/2026 | 08/07/2026 | [SQL Server Indexing](https://learn.microsoft.com/en-us/sql/relational-databases/indexes/sql-server-index-design-guide) |
| 5 | - **Sáng:** Cài đặt thư viện `ngx-charts` cho Frontend. Code giao diện Biểu đồ tròn (Pie Chart) hiển thị cơ cấu chi tiêu trong tháng.<br>- **Chiều:** Code Biểu đồ cột (Bar Chart) so sánh chi tiêu 6 tháng. Bị lỗi biểu đồ không tự co giãn (Responsive) và bị tràn ra ngoài màn hình trên điện thoại, debug và bọc thêm CSS Flexbox/Grid container để fix lỗi. | 09/07/2026 | 09/07/2026 | [Ngx-charts Documentation](https://swimlane.gitbook.io/ngx-charts/) |
| 6 | - **Sáng:** Lắp ráp hoàn chỉnh trang Phân tích chi tiêu (Spending Analysis UI), kết hợp cả Biểu đồ trực quan bên trên và Insight tư vấn của AI bên dưới.<br>- **Chiều:** Test luồng kết hợp E2E: User đổi tháng xem biểu đồ -> Hệ thống load lại data -> Bấm nút "Xin lời khuyên AI" -> Backend gửi data mới đi hỏi AI. Luồng chạy trơn tru, gom code push lên Repo. | 10/07/2026 | 10/07/2026 | [Angular Component Interaction](https://angular.io/guide/component-interaction) |

### Kết quả đạt được tuần 9

* Tích hợp thành công Generative AI (Gemini Flash) mang lại tính năng độc đáo, thông minh cho hệ thống (AI Insight).
* Làm chủ kỹ năng Prompt Engineering cơ bản, ép định dạng đầu ra của AI để dễ dàng parse trên Backend.
* Tối ưu hóa thành công hiệu năng Database (RDS) thông qua kỹ thuật tạo Index, phục vụ tốt cho tính năng Báo cáo nặng data.
* Sử dụng thành thạo thư viện biểu đồ ngx-charts và khắc phục được triệt để vấn đề Responsive trên thiết bị di động.
