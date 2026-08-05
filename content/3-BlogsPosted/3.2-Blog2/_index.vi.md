---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# BÓC TÁCH KIẾN TRÚC MỘT WEBSITE E-COMMERCE TỶ TRAFFIC TRÊN AWS

Cứ mỗi mùa Flash Sale hay Black Friday, câu hỏi quen thuộc lại hiện lên trong đầu những lập trình viên: *"Làm sao mà các trang thương mại điện tử lớn không bị sập khi có hàng triệu người cùng vào săn sale?"*. Nếu chỉ dùng một con server cắm thẳng vào database như cách chúng ta hay làm ở các bài tập lớn, chắc chắn hệ thống sẽ bốc khói ngay giây đầu tiên!

AWS đã đưa ra một bộ giải pháp Cloud-Native cực kỳ chuẩn mực. Bằng cách lắp ghép các dịch vụ Mạng, Điện toán, Cache và Database lại với nhau, chúng ta hoàn toàn có thể xây dựng một hệ thống E-commerce chịu tải "quái vật". Hãy cùng mình bóc tách kiến trúc này nhé!

### Nhìn toàn cảnh kiến trúc

Luồng dữ liệu đi vào hệ thống sẽ qua các lớp lá chắn và phân phối như sau:

**Người dùng → Amazon Route 53 → Amazon CloudFront → AWS WAF → Application Load Balancer → Amazon ECS (AWS Fargate) → Amazon ElastiCache / Amazon Aurora Serverless v2**

Mỗi một "mắt xích" đều có một nhiệm vụ sinh tử:

- **Amazon Route 53 (Người gác cổng)**
  - Phân giải tên miền cực nhanh và định tuyến người dùng đến đúng server gần nhất.

- **Amazon CloudFront (Lá chắn bộ nhớ đệm)**
  - Phân phối hình ảnh sản phẩm, file CSS/JS từ các trạm Edge Location. Người dùng chưa kịp chạm vào server chính thì đã lấy được hình ảnh từ bộ đệm rồi.

- **AWS WAF (Hiệp sĩ bảo mật)**
  - Đứng chặn ngay cửa, block ngay lập tức các đòn tấn công SQL Injection hay XSS muốn phá hoại hệ thống.

- **Application Load Balancer (ALB - Người điều phối)**
  - Nhận traffic hợp lệ và chia đều đặn vào các container backend, đảm bảo không có server nào bị "nghẽn cổ chai".

- **Amazon ECS với AWS Fargate (Lính đánh thuê Serverless)**
  - Chạy backend bằng container. Cần bao nhiêu tải thì tự phình ra bấy nhiêu, không cần phải ngồi cấu hình server vật lý mất thời gian.

- **Amazon ElastiCache (Trí nhớ ngắn hạn siêu tốc)**
  - Nhớ ngay các món hàng hot đang sale. Thay vì query thẳng vào database tốn tài nguyên, nó lấy dữ liệu từ RAM trả về cho user chỉ trong vài mili-giây.

- **Amazon Aurora Serverless v2 (Kho lưu trữ đàn hồi)**
  - Nơi chứa thông tin đơn hàng và user quan trọng nhất. Tự động scale lên scale xuống tài nguyên theo đúng nhịp độ mua sắm.

### Tai mắt của hệ thống: Giám sát và cảnh báo

Để một hệ thống lớn sống khỏe, không thể thiếu tai mắt.
**Amazon CloudWatch** đóng vai trò như camera giám sát liên tục nhịp tim (CPU, RAM, Error rate) của ECS và Aurora. Ngay khi thấy có biến (ví dụ CPU vọt lên 90%), nó sẽ kích hoạt **CloudWatch Alarm**, báo cho **Amazon SNS** bắn thẳng tin nhắn SMS hoặc Email dựng đầu team vận hành dậy giữa đêm để xử lý sự cố.

### Bài học thực chiến mình rút ra được

Khi nhìn vào sơ đồ kiến trúc E-commerce khổng lồ này và đối chiếu lại với dự án Snaptics mình vừa làm trong kỳ thực tập, mình thực sự thấy được một bức tranh rất khác biệt!

Bài học lớn nhất mình ngộ ra là: **"Xây dựng ứng dụng Scale lớn không phải là viết một cục code khổng lồ, mà là nghệ thuật sắp xếp các Managed Services hợp lý!"**. Thay vì bắt con Backend Server làm mọi việc từ check bảo mật, serve ảnh, đến query database, kiến trúc AWS đã chia để trị: 
- Cần Cache? Để CloudFront và ElastiCache lo.
- Cần chặn Hack? Giao cho WAF.
- Cần chia tải? Bỏ ALB ra trước mặt.
- Cần xử lý logic? Lúc đó mới đến lượt ECS Fargate lên tiếng.

Kiến trúc này giúp mình thoát khỏi tư duy monolithic (nguyên khối) cũ kỹ, và dạy mình cách tư duy theo kiểu "Cloud-Native" thực thụ: Tách rời các thành phần (Decoupling) để mỗi dịch vụ làm tốt nhất đúng chuyên môn của nó.

### Hình minh họa

<div style="text-align: center;">
    <img src="/fcj-workshop-template/images/3-BlogsPosted/3.2-Blog2/blog2.jpg"
         alt="Kiến trúc website thương mại điện tử"
         style="width: 900px; height: auto; border-radius: 8px;">
    <p>Kiến trúc website thương mại điện tử có khả năng mở rộng trên AWS.</p>
</div>

### Tài liệu tham khảo

Để hiểu sâu hơn, các bạn có thể đọc tài liệu gốc siêu chi tiết từ AWS:

- **Guidance for Web Store on AWS**
  https://docs.aws.amazon.com/solutions/web-store-on-aws/

- **Guidance for Building a Containerized and Scalable Web Application on AWS**
  https://docs.aws.amazon.com/solutions/building-a-containerized-and-scalable-web-application-on-aws/