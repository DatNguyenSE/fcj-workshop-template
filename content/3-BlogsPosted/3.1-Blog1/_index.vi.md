---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# AWS Đã Nâng Cấp Amazon Cognito Với Mức Gián Đoạn Gần Như Bằng 0 Nhờ Đâu?

Authentication (xác thực) luôn là "trái tim" của mọi ứng dụng. Thử tưởng tượng hệ thống xác thực sập chỉ vài phút thôi, hàng loạt user sẽ bị văng ra ngoài, không thể đăng nhập, không thể đặt lại mật khẩu... thảm họa! Thế nên khi đọc case-study về việc AWS nâng cấp toàn bộ hạ tầng cốt lõi của Amazon Cognito cho hàng triệu người dùng mà gần như không có downtime, mình đã thực sự bị ấn tượng mạnh.

Bài viết này mổ xẻ cách AWS chuyển dịch hệ thống sang kiến trúc thế hệ mới, mang đến hàng loạt tính năng khủng nhưng vẫn giữ được "backward compatibility" (tương thích ngược) một cách hoàn hảo.

### Những tính năng mới "Đáng Tiền"

Hạ tầng mới của Amazon Cognito mang đến những con số và tính năng thực sự ấn tượng:

- **Hiệu năng cực khủng (High-throughput Performance)**
  - Hỗ trợ hàng chục triệu người dùng trong một User Pool.
  - Xử lý hàng nghìn giao dịch mỗi giây (TPS) nhẹ như không.
  - Tối ưu hóa cực tốt, giảm hẳn độ trễ khi user đăng nhập.

- **Customer-managed Encryption Keys (CMK)**
  - Bắt tay với AWS KMS.
  - Các doanh nghiệp giờ đây có thể tự nắm giữ "chìa khóa" mã hóa dữ liệu của mình.
  - Giải quyết bài toán tuân thủ bảo mật khắt khe cấp doanh nghiệp.

- **Multi-Region Replication**
  - Tự động đồng bộ User Profile, Password, và cấu hình xuyên suốt nhiều Region của AWS.
  - Hệ thống bao "sống dai" và phục hồi cực nhanh sau thảm họa (Disaster Recovery).

### Những nguyên tắc kiến trúc cốt lõi

Thay vì đắp thêm code, AWS đã thiết kế lại từ móng dựa trên các nguyên tắc rất hay ho:

- **Identity-first Design**
  - Không ôm đồm! Cognito giờ đây tập trung 100% sức mạnh cho bài toán danh tính, thay vì cố làm một hệ thống lưu trữ đa năng.
  - Giúp việc mở rộng (scale) mượt mà hơn rất nhiều.

- **Backward Compatibility (Tương thích ngược)**
  - Nâng cấp server thì việc của server, khách hàng không cần phải sửa dù chỉ một dòng code!
  - Mọi luồng API xác thực cũ vẫn hoạt động trơn tru.

- **Avoid One-way Doors**
  - Nguyên tắc "không đi vào ngõ cụt": Kiến trúc mới cho phép dễ dàng nâng cấp tiếp trong tương lai mà không bị kẹt lại bởi những quyết định hard-code quá sâu.

### Chiến lược Migration: Đỉnh Cao Của Vận Hành

Đọc đến phần cách AWS migrate hàng trăm triệu hồ sơ user mà không ai hay biết, mình mới thấy kiến trúc ở quy mô toàn cầu nó "khét" như thế nào:

- **Shadow Mode Validation**
  - Test trong bóng tối! Request của user được chạy song song ở cả hệ thống cũ và mới.
  - AWS liên tục soi kỹ Response và Status Code xem hai bên có khớp nhau không rồi mới dám chuyển lưu lượng thật.

- **Dual-write Architecture**
  - Ghi dữ liệu vào cả hai nơi cùng lúc.
  - Lỡ hệ thống mới có "hắt hơi sổ mũi", hệ thống cũ ngay lập tức gánh team.

- **Anti-entropy Validation**
  - Liên tục quét và đối chiếu dữ liệu giữa hai bên.
  - Nếu có sai lệch, hệ thống cũ (Source of Truth) sẽ lập tức ghi đè chuẩn hóa lại hệ thống mới.

- **Incremental Rollout & Rollback**
  - Triển khai cuốn chiếu từng cụm nhỏ.
  - Lỗi phát là Rollback lùi xe ngay lập tức chứ không có chuyện "all-in".

### Bài học xương máu rút ra cho riêng mình

Đọc xong case-study này rồi nhìn lại dự án Snaptics của nhóm mình, mới thấy tư duy "làm cho chạy được" (make it work) và "làm cho không bao giờ sập" (make it resilient) khác nhau một trời một vực! 

Trước đây, khi sửa database hay update API, mình hay có kiểu "deploy and pray" (deploy xong rồi cầu nguyện đừng lỗi). Nhưng qua bài viết này, mình học được bài học cực lớn về **Shadow Mode** và **Dual-write**. Khi bạn thiết kế một hệ thống lớn, bạn không được phép để khách hàng trở thành "chuột bạch". Việc nâng cấp phải vô hình trong mắt người dùng.

Tư duy **Backward Compatibility** cũng làm mình thay đổi cách viết API. Mình nhận ra rằng mỗi khi đổi cấu trúc dữ liệu, mình phải luôn tự hỏi: *"Liệu app Frontend hiện tại gọi vào API mới này có bị crash không?"*. Quả thực, bài viết không chỉ dạy về công nghệ, mà nó dạy mình tư duy của một kỹ sư Cloud thực thụ!

### Hình minh họa

<div style="text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.1-Blog1/blog1.jpg"
         alt="Amazon Cognito Next-generation Infrastructure"
         style="width: 800px; height: auto; border-radius: 8px;">
    <p>Kiến trúc hạ tầng thế hệ mới của Amazon Cognito</p>
</div>

### Bài viết tham khảo

Bài viết này được mình nghiền ngẫm và đúc kết từ Blog bảo mật của AWS:

- **Amazon Cognito unlocks advanced capabilities with next-generation infrastructure**
- https://aws.amazon.com/blogs/security/amazon-cognito-unlocks-advanced-capabilities-with-next-generation-infrastructure/