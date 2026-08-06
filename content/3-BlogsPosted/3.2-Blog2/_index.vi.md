---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# PHÂN TÍCH KIẾN TRÚC WEBSITE E-COMMERCE KHẢ NĂNG MỞ RỘNG CAO TRÊN AWS

Mỗi dịp Flash Sale hay các sự kiện mua sắm lớn, các nền tảng thương mại điện tử thường phải đối mặt với áp lực truy cập khổng lồ. Nếu kiến trúc hệ thống chỉ đơn giản là một ứng dụng kết nối trực tiếp với cơ sở dữ liệu nguyên khối, hệ thống sẽ rất dễ gặp tình trạng quá tải và gián đoạn dịch vụ.

Để giải quyết bài toán này, AWS cung cấp một bộ giải pháp Cloud-Native tiêu chuẩn. Bằng cách kết hợp linh hoạt các dịch vụ Mạng, Điện toán, Caching và Cơ sở dữ liệu, chúng ta có thể xây dựng một hệ thống E-commerce có khả năng chịu tải và mở rộng vượt trội. Hãy cùng phân tích các thành phần trong kiến trúc này.

### Nhìn toàn cảnh kiến trúc

Luồng dữ liệu đi vào hệ thống sẽ được phân phối và bảo vệ qua các lớp dịch vụ sau:

**Người dùng → Amazon Route 53 → Amazon CloudFront → AWS WAF → Application Load Balancer → Amazon ECS (AWS Fargate) → Amazon ElastiCache / Amazon Aurora Serverless v2**

Mỗi dịch vụ đảm nhận một vai trò chuyên biệt:

- **Amazon Route 53 (Định tuyến mạng)**
  - Cung cấp dịch vụ phân giải tên miền (DNS) tốc độ cao và định tuyến người dùng đến các điểm truy cập tối ưu nhất.

- **Amazon CloudFront (Tối ưu hóa phân phối)**
  - Phân phối các nội dung tĩnh (hình ảnh sản phẩm, file CSS/JS) từ mạng lưới Edge Locations toàn cầu, giúp giảm tải cho server chính và tăng tốc độ tải trang.

- **AWS WAF (Bảo mật ứng dụng)**
  - Tường lửa ứng dụng web giúp ngăn chặn kịp thời các cuộc tấn công phổ biến (như SQL Injection, XSS), bảo vệ hệ thống khỏi các lưu lượng độc hại.

- **Application Load Balancer (Cân bằng tải)**
  - Phân phối đều đặn lưu lượng truy cập hợp lệ vào các container xử lý backend, ngăn chặn tình trạng nghẽn cổ chai cục bộ.

- **Amazon ECS với AWS Fargate (Điện toán linh hoạt)**
  - Môi trường chạy backend bằng container (Serverless). Hệ thống tự động co giãn tài nguyên điện toán dựa trên nhu cầu thực tế mà không cần quản lý hạ tầng máy chủ vật lý.

- **Amazon ElastiCache (Caching tốc độ cao)**
  - Lưu trữ tạm thời các dữ liệu thường xuyên được truy xuất (ví dụ: sản phẩm hot, giỏ hàng). Việc đọc dữ liệu từ RAM giúp phản hồi cực nhanh và giảm bớt áp lực truy vấn cho cơ sở dữ liệu chính.

- **Amazon Aurora Serverless v2 (Cơ sở dữ liệu đàn hồi)**
  - Quản lý các dữ liệu cốt lõi (người dùng, đơn hàng). Khả năng tự động mở rộng tài nguyên tính toán trong tích tắc giúp cơ sở dữ liệu đáp ứng tốt những thời điểm lượng giao dịch tăng đột biến.

### Hệ thống Giám sát và Cảnh báo

Để duy trì tính ổn định, hệ thống được tích hợp các công cụ giám sát:
**Amazon CloudWatch** liên tục thu thập các số liệu về hiệu suất (CPU, RAM, tỷ lệ lỗi) của ECS và Aurora. Khi các ngưỡng an toàn bị vượt qua, **CloudWatch Alarm** sẽ được kích hoạt, thông báo qua **Amazon SNS** tới đội ngũ vận hành để kịp thời xử lý.

### Kinh nghiệm thực tiễn đúc kết được

Khi đối chiếu sơ đồ kiến trúc quy mô lớn này với dự án Snaptics trong kỳ thực tập, mình đã rút ra được nhiều bài học về tư duy thiết kế hệ thống.

Kinh nghiệm lớn nhất là: **Sức mạnh của một hệ thống có khả năng mở rộng (scalable) nằm ở sự kết hợp khéo léo các Managed Services, thay vì cố gắng xây dựng một ứng dụng nguyên khối (monolithic) làm mọi việc.** 
Việc tách rời các thành phần (Decoupling) đóng vai trò then chốt:
- Caching được giao cho CloudFront và ElastiCache.
- Bảo mật và chặn lọc lưu lượng được giao cho WAF.
- Cân bằng tải được xử lý bởi ALB.
- Logic nghiệp vụ hoàn toàn tập trung xử lý tại ECS Fargate.

Tư duy này giúp hệ thống trở nên linh hoạt, dễ dàng bảo trì và mỗi thành phần đều có thể tự mở rộng một cách độc lập tùy theo nhu cầu vận hành thực tế.

### Hình minh họa

<div style="text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.2-Blog2/blog2.jpg"
         alt="Kiến trúc website thương mại điện tử"
         style="width: 900px; height: auto; border-radius: 8px;">
    <p>Kiến trúc website thương mại điện tử có khả năng mở rộng trên AWS.</p>
</div>

### Tài liệu tham khảo

Để hiểu sâu hơn về kiến trúc này, các bạn có thể tham khảo tài liệu từ AWS:

- **Guidance for Web Store on AWS**
  https://docs.aws.amazon.com/solutions/web-store-on-aws/

- **Guidance for Building a Containerized and Scalable Web Application on AWS**
  https://docs.aws.amazon.com/solutions/building-a-containerized-and-scalable-web-application-on-aws/