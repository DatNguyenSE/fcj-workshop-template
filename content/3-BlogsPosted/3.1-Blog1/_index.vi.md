---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS Đã Nâng Cấp Amazon Cognito Với Mức Gián Đoạn Bằng 0 Bằng Cách Nào?

Xác thực (Authentication) luôn là thành phần cốt lõi của mọi ứng dụng. Một sự cố gián đoạn nhỏ của hệ thống xác thực cũng có thể gây ảnh hưởng lớn đến trải nghiệm của hàng nghìn, thậm chí hàng triệu người dùng. Gần đây, khi đọc case-study về việc AWS nâng cấp toàn bộ hạ tầng cốt lõi của Amazon Cognito cho quy mô toàn cầu mà gần như không có downtime, mình đã học được rất nhiều điều về tư duy thiết kế hệ thống.

Bài viết này mổ xẻ cách AWS chuyển dịch hệ thống sang kiến trúc thế hệ mới, mang đến hàng loạt tính năng mạnh mẽ nhưng vẫn giữ được tính "tương thích ngược" (backward compatibility) một cách hoàn hảo.

### Những tính năng mới nổi bật

Hạ tầng mới của Amazon Cognito mang đến những năng lực vận hành ấn tượng:

- **Hiệu năng xử lý cao (High-throughput Performance)**
  - Hỗ trợ hàng chục triệu người dùng trong một User Pool.
  - Xử lý hàng nghìn giao dịch mỗi giây (TPS) ổn định.
  - Tối ưu hóa hiệu suất, giảm đáng kể độ trễ khi người dùng đăng nhập.

- **Customer-managed Encryption Keys (CMK)**
  - Tích hợp sâu với AWS KMS.
  - Các doanh nghiệp giờ đây có thể tự nắm giữ chìa khóa mã hóa dữ liệu của mình.
  - Giải quyết bài toán tuân thủ các tiêu chuẩn bảo mật khắt khe.

- **Multi-Region Replication**
  - Tự động đồng bộ User Profile, Password, và cấu hình xuyên suốt nhiều Region của AWS.
  - Tăng cường tính sẵn sàng (High Availability) và khả năng phục hồi sau thảm họa (Disaster Recovery).

### Những nguyên tắc kiến trúc cốt lõi

Thay vì chỉ tối ưu mã nguồn, AWS đã thiết kế lại kiến trúc dựa trên các nguyên tắc cơ bản:

- **Identity-first Design**
  - Hệ thống tập trung hoàn toàn vào việc tối ưu hóa bài toán danh tính, thay vì cố gắng trở thành một kho lưu trữ đa năng. Điều này giúp việc mở rộng quy mô (scaling) diễn ra trơn tru hơn.

- **Backward Compatibility (Tương thích ngược)**
  - Quá trình nâng cấp hoàn toàn vô hình với khách hàng, không yêu cầu thay đổi bất kỳ dòng code nào.
  - Toàn bộ luồng API xác thực cũ vẫn hoạt động bình thường trên hạ tầng mới.

- **Avoid One-way Doors**
  - Nguyên tắc "không đi vào ngõ cụt": Kiến trúc được thiết kế mở, cho phép dễ dàng tích hợp và nâng cấp tiếp trong tương lai mà không bị ràng buộc bởi những quyết định hard-code.

### Chiến lược Migration: Nghệ thuật vận hành

Việc chuyển đổi hàng trăm triệu hồ sơ người dùng một cách an toàn đòi hỏi những chiến lược rất tỉ mỉ:

- **Shadow Mode Validation**
  - Kiểm thử vô hình: Request của người dùng được chạy song song ở cả hệ thống cũ và mới.
  - AWS liên tục đối chiếu Response và Status Code để đảm bảo hệ thống mới hoạt động chính xác trước khi chuyển đổi luồng dữ liệu thật.

- **Dual-write Architecture**
  - Ghi dữ liệu vào cả hai hệ thống cùng lúc.
  - Đảm bảo cơ sở dữ liệu luôn đồng bộ và sẵn sàng fallback (chuyển về hệ thống cũ) nếu có sự cố.

- **Anti-entropy Validation**
  - Cơ chế liên tục quét và đối chiếu dữ liệu giữa hai bên. Hệ thống cũ đóng vai trò là "Source of Truth" để chuẩn hóa lại hệ thống mới nếu phát hiện sai lệch.

- **Incremental Rollout & Rollback**
  - Triển khai theo từng cụm nhỏ. Sẵn sàng rollback ngay lập tức nếu phát hiện bất thường, giảm thiểu rủi ro tối đa.

### Bài học thực tiễn rút ra cho dự án Snaptics

Đọc xong case-study này và nhìn lại quá trình triển khai dự án Snaptics, mình nhận ra sự khác biệt lớn giữa tư duy "phát triển tính năng" (make it work) và "đảm bảo tính sẵn sàng cao" (make it resilient).

Trước đây, khi thay đổi cấu trúc database hoặc cập nhật API, mình thường thiên về việc triển khai trực tiếp. Tuy nhiên, qua bài học về **Shadow Mode** và **Dual-write**, mình hiểu rằng khi vận hành hệ thống thực tế, việc đảm bảo trải nghiệm liền mạch cho người dùng là ưu tiên hàng đầu. Việc cập nhật cần phải được thực hiện một cách an toàn và có kiểm soát.

Tư duy **Backward Compatibility** cũng giúp mình cẩn trọng hơn khi thiết kế API. Mình học được thói quen đặt câu hỏi: *"Sự thay đổi này có làm ảnh hưởng đến các Client hiện tại đang gọi API hay không?"*. Đây là những kinh nghiệm vô cùng giá trị để hướng tới hình ảnh một Kỹ sư Cloud chuyên nghiệp.

### Hình minh họa

<div style="text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.1-Blog1/blog1.jpg"
         alt="Amazon Cognito Next-generation Infrastructure"
         style="width: 800px; height: auto; border-radius: 8px;">
    <p>Kiến trúc hạ tầng thế hệ mới của Amazon Cognito</p>
</div>

### Bài viết tham khảo

Bài viết này được đúc kết từ phân tích trên AWS Security Blog:

- **Amazon Cognito unlocks advanced capabilities with next-generation infrastructure**
- https://aws.amazon.com/blogs/security/amazon-cognito-unlocks-advanced-capabilities-with-next-generation-infrastructure/